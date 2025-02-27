# Git Leaks POC

| *Author*            | *Created on* | *Version* | *Last updated by*       | *Last edited on* | *Reviewer* |     
|-----------------------|----------------|-------------|----------------------------|-------------------|-----------------------|
| Aman Raj      | 26-02-2025       | Version 1 | Aman Raj         | 26-02-2025       | Siddharth Pawar    |  
| Aman Raj      | 26-02-2025       | Version 2 | Aman Raj         | 26-02-2025       | Siddharth Pawar    |  

# Table of Content
1.⁠ ⁠[Introduction](#introduction)  
2.⁠ ⁠[Why Use GitLeaks?](#why-use-gitleaks)  
3.⁠ ⁠[Installation](#installation)  
4.⁠ ⁠[Git Leak Commands](#commands)  
   - [Regular Git Scanning](#1-regular-git-scanning)  
   - [Pre-commit Scanning (Not Tracking Staged Changes)](#2-pre-commit-scanning-not-tracking-staged-changes)  
   - [Pre-commit Scanning (Tracking Staged Changes)](#3-pre-commit-scanning-tracking-staged-changes)  
   - [Scanning Directory/File](#4-scanning-directoryfile)  
   - [Scanning Piped Data](#5-scanning-piped-data)  
5.⁠ ⁠[Example Scans](#example-scans)  
   - [Running Git Leaks on Attendance API](#running-git-leaks-on-attendance-api)  
   - [Running Git Leaks on Salary API](#running-git-leaks-on-salary-api)  
   - [Running Git Leaks on Employee API](#running-git-leaks-on-employee-api)  
   - [Running Git Leaks on Frontend Server](#running-git-leaks-on-frontend-server)  
   - [Testing with Pre-commit Flag](#for-testing-made-some-changes-in-attendance-api-code-and-checked-using-pre-commit-flag)  
   - [Generated Report](#generated-report)  
6.⁠ ⁠[Conclusion](#conclusion)  
7.⁠ ⁠[Contact Information](#contact-information)  
8.⁠ ⁠[References](#references)  


# Introduction
GitLeaks is an open-source tool designed to detect hardcoded secrets like API keys, passwords, and tokens in Git repositories. This document provides a proof of concept (POC) demonstrating how GitLeaks can be used to scan repositories and prevent credential leaks.

# Why Use GitLeaks?
•⁠  ⁠*Prevents Security Breaches:* Detects exposed credentials before they can be exploited.
•⁠  ⁠*Automated Scanning:*Can be integrated with CI/CD pipelines.
•⁠  ⁠*Compliance:* Helps meet security standards like GDPR, SOC 2, and PCI-DSS.
•⁠  ⁠*Lightweight & Efficient:* Simple CLI tool with regex-based scanning.

# Installation
•⁠  ⁠To install gitleaks follow the following command:-
⁠ bash
wget https://github.com/gitleaks/gitleaks/releases/latest/download/gitleaks-linux-amd64
chmod +x gitleaks-linux-amd64
sudo mv gitleaks-linux-amd64 /usr/local/bin/gitleaks
 ⁠
•⁠  ⁠wget → A command-line utility used to download files from the internet.
•⁠  ⁠Moves the file to the system’s binary directory (/usr/local/bin/), so it can be run from anywhere using gitleaks instead of ./gitleaks-linux-amd64.

![Install](./assets/gitleaks_install.png)

# Commands

## 1. Regular git scanning

 gitleaks detect --source={repo} # OLD CMD
 gitleaks git {repo} # NEW CMD

## 2. Pre-commit scanning (not tracking staged changes)

gitleaks protect --source={repo} # OLD CMD
gitleaks git --pre-commit {repo} # NEW CMD

## 3. Pre-commit scanning (tracking staged changes)

gitleaks protect --staged --source={repo} # OLD CMD
gitleaks git --pre-commit --staged {repo} # NEW CMD

## 4. Scanning directory/file

gitleaks detect --no-git --source={repo} # OLD CMD
gitleaks directory {directory/file} # NEW CMD

## 5. Scanning piped data

gitleaks detect --no-git --pipe # OLD CMD
gitleaks stdin # NEW CMD



# Example Scans

### Running Git Leaks on Attendance API:
![attendance api](./assets/gitleaks_attendance.png)

### Running Git Leaks on Salary API:
![attendance api](./assets/gitleaks_salary.png)

### Running Git Leaks on Employee API:
![attendance api](./assets/git_leaks_employee.png)

### Running Git Leaks on Frontend Server:
![attendance api](./assets/gitleaks_frontend.png)

### For testing made some changes in Attendance API code and checked using pre commit flag:
![pre-commit](./assets/gitleaks_precommit.png)

### Generated report
![report](./assets/gitleaks-json.png)


# Conclusion
GitLeaks is a powerful and lightweight tool that helps prevent credential leaks by scanning Git repositories for secrets. By integrating it into your development workflow and CI/CD pipelines, you can enhance security and prevent unauthorized access to sensitive data.

##  Contact Information
For any queries or further information, feel free to contact:
| *Name*  | *Email*                       |
|-----------------|-----------------------------------|
| Aman | aman.raj@mygurukulam.co |

---
##  References
| *Resource* | *Link* |
|-------------|---------|
| Git Leaks | [Link](https://github.com/gitleaks/gitleaks) |
| GitLeaks Updated Commands | [Link](https://gist.github.com/zricethezav/b325bb93ebf41b9c0b0507acf12810d2) |
