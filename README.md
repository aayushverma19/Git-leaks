# Install Gitleaks Package POC

| **Author** | **Created on** | **Version** | **Last updated by**|**Last Edited On**|**Level** |**Reviewer** |
|------------|---------------------------|-------------|----------------|-----|-------------|-------------|
| Aayush Verma|   26-02-2025             | v1          | Aayush Verma   |26-02-2025    |  Internal Reviewer | Komal Jaiswal |


---

## **Table of Contents**

  - [1. Introduction](#introduction)
  - [2. Update Package List](#1-update-package-list)
  - [3. Install Gitleaks](#2-install-gitleaks)
  - [4. Extract Gitleaks Archive](#3-extract-gitleaks-archive)
  - [5. Move gitleakes to system path](#4-move-gitleaks-binary-to-system-path)
  - [6. Verification](#5-verify-the-installation)
  - [7. Git Leak Commands](#commands)
    - [Regular Git Scanning](#1-regular-git-scanning)  
    - [Pre-commit Scanning (Not Tracking Staged Changes)](#2-pre-commit-scanning-not-tracking-staged-changes)  
    - [Pre-commit Scanning (Tracking Staged Changes)](#3-pre-commit-scanning-tracking-staged-changes)  
    - [Scanning Directory/File](#4-scanning-directoryfile)  
    - [Scanning Piped Data](#5-scanning-piped-data) 
    - [Run Gitleaks Scan and Generate Report](#6-run-gitleaks-scan-and-generate-report) 
   
 
 ---

## **Introduction**
GitLeaks is an open-source tool designed to detect hardcoded secrets like API keys, passwords, and tokens in Git repositories. This document provides a proof of concept (POC) demonstrating how GitLeaks can be used to scan repositories and prevent credential leaks.

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



### **4. Move Gitleaks Binary to System Path**

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
| [How to install Gitleaks](https://github.com/gitleaks/gitleaks) | Gitleaks installation  |
| [Link](https://gist.github.com/zricethezav/b325bb93ebf41b9c0b0507acf12810d2) | GitLeaks Updated Commands |
