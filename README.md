# Install Gitleaks Package POC

| **Author** | **Created on** | **Version** | **Last updated by**|**Last Edited On**|**Internal Reviewer** |**Reviewer L0** |**Reviewer L1** |**Reviewer L2** |
|------------|---------------------------|-------------|----------------|-----|-------------|-------------|-------------|-------------|
| Aayush Verma|   13-02-2025             | v1          | Aayush Verma   | 18-02-2025   |  Komal Jaiswal | Akshit kapil | Taranddeep | Abhishek  Dubey|


---

## **Table of Contents**

  - [1. Introduction](#introduction)
  - [2. Update Package List](#1-update-package-list)
  - [3. Install Poetry](#2-install-poetry)
  - [4. Add Poetry to the Path](#3-add-poetry-to-the-path)
  - [5. Reload Bash Configuration](#4-reload-bash-configuration)
  - [6. Verification](#5-verify-the-installation)
 
 ---

## **Introduction**
Poetry is designed to streamline Python project management. With its modern approach, you can manage dependencies, handle virtual environments, and simplify project configuration all in one tool. This guide will walk you through installing Poetry on Linux and setting up a simple Proof of Concept (POC) project to demonstrate its features.

---

## Step-by-step installation of Poetry


### **1. Update Package List**

```bash
sudo apt update
```
Updates the list of available packages. Ensures you have the latest information about available software packages before installing anything.



### **2. Install Gitleaks**
Run the following command to install Gitleaks:

```bash
wget https://github.com/gitleaks/gitleaks/releases/download/v8.24.0/gitleaks_8.24.0_linux_x64.tar.gz
```



### **3. Extract Gitleaks Archive**

```bash
tar -xzvf gitleaks_8.24.0_linux_x64.tar.gz 
```



### **4.  Move Gitleaks Binary to System Path**

Move the Gitleaks binary to `/usr/local/bin/` to make it accessible system-wide:

```bash
mv gitleaks /usr/local/bin/
```



### **5. Verify the Installation**

```bash
gitleaks version
```

---

## Commands

### **1. Regular git scanning**
```
 gitleaks detect --source={repo} # OLD CMD
 gitleaks git {repo} # NEW CMD
```
### **2. Pre-commit scanning (not tracking staged changes)**
```
gitleaks protect --source={repo} # OLD CMD
gitleaks git --pre-commit {repo} # NEW CMD
```
### **3. Pre-commit scanning (tracking staged changes)**
```
gitleaks protect --staged --source={repo} # OLD CMD
gitleaks git --pre-commit --staged {repo} # NEW CMD
```
### **4. Scanning directory/file**
```
gitleaks detect --no-git --source={repo} # OLD CMD
gitleaks directory {directory/file} # NEW CMD
```
### **5. Scanning piped data**
```
gitleaks detect --no-git --pipe # OLD CMD
gitleaks stdin # NEW CMD
```

### **6. Run Gitleaks Scan and Generate Report**
```
gitleaks detect -source={repo} --report-format=json --report-path={path} # OLD CMD
gitleaks git {repo} -f {report format} -r {report path} # NEW CMD
```


# Contact Information

| **Name**       | **Email Address**            |
|-----------------|------------------------------|
| Aayush Verma    | <aayush.verma@mygurukulam.co>     |

# References

| **Link**                                                                                                                     | **Description**                   |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| [How to install Gitleaks]() | Gitleaks installation  |
