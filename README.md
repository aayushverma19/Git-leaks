# Install Poetry Package POC

| **Author** | **Created on** | **Version** | **Last updated by**|**Last Edited On**|**Internal Reviewer** |**Reviewer L0** |**Reviewer L1** |**Reviewer L2** |
|------------|---------------------------|-------------|----------------|-----|-------------|-------------|-------------|-------------|
| Aayush Verma|   13-02-2025             | v1          | Aayush Verma   | 18-02-2025   |  Komal Jaiswal | Akshit kapil | Taranddeep | Abhishek  Dubey|


---

## **Table of Contents**

  - [1. Introduction](#introduction)
  - [2. Pre Installation](#pre-installation-checklist)
  - [3. Update Package List](#1-update-package-list)
  - [4. Install Poetry](#2-install-poetry)
  - [5. Add Poetry to the Path](#3-add-poetry-to-the-path)
  - [6. Reload Bash Configuration](#4-reload-bash-configuration)
  - [7. Verification](#5-verify-the-installation)
 
 ---

## **Introduction**
Poetry is designed to streamline Python project management. With its modern approach, you can manage dependencies, handle virtual environments, and simplify project configuration all in one tool. This guide will walk you through installing Poetry on Linux and setting up a simple Proof of Concept (POC) project to demonstrate its features.

---

## **How to Install Poetry on Linux**

### **Pre-Installation Checklist**

1. **Ensure Python is Installed:** Poetry requires **Python 3.7 or later**. Check your Python version:
   ```bash
   python3 --version
   ```
   If Python is not installed, refer to [Python's installation guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Aayush-SCRUM-2/Common/Software/python/Installation/README.md).

2. **Install `curl`:** Poetry's installation script uses `curl`. Verify its availability:
   ```bash
   curl --version
   ```
   If `curl` is not installed, you can add it with:
   ```bash
   sudo apt install curl
   ```

3. **Check System Requirements:** Ensure your Linux distribution meets the prerequisites for Poetry's installation script.

---

## Step-by-step installation of Poetry


### **1. Update Package List**
```bash
sudo apt update
```
Updates the list of available packages. Ensures you have the latest information about available software packages before installing anything.

---

### **2. Install Poetry**
Run the following command to install Poetry:
```bash
curl -sSL https://install.python-poetry.org | python3 -
```

This script will install Poetry in `$HOME/.local/bin` by default.

---

### **3. Add Poetry to the PATH**
Make the `poetry` command globally accessible by adding it to your system's PATH:
```bash
export PATH="$HOME/.local/bin:$PATH"
```

To make this change persistent, append the command to your shell configuration file (`.bashrc` or `.zshrc`):
```bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
```

---

### **4. Reload Bash Configuration**
Apply the changes by reloading your shell configuration file:
```bash
source ~/.bashrc
```

---

### **5. Verify the Installation**
Check if Poetry is installed correctly:
```bash
poetry --version
```
You should see the installed version number, confirming the setup.

---


# Contact Information

| **Name**       | **Email Address**            |
|-----------------|------------------------------|
| Aayush Verma    | <aayush.verma@mygurukulam.co>     |

# References

| **Link**                                                                                                                     | **Description**                   |
|---------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| [How to install Poetry](https://medium.com/@akshatgadodia/mastering-poetry-commands-unlocking-the-full-power-of-python-poetry-8363f347beb5) | Python installation  |
