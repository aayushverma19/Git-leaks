# Git Leaks POC

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer** |     
|-----------------------|----------------|-------------|----------------------------|-------------------|-----------------------|
| Aman Raj      | 26-02-2025       | Version 1 | Aman Raj         | 26-02-2025       | Siddharth Pawar    |  
| Aman Raj      | 26-02-2025       | Version 2 | Aman Raj         | 26-02-2025       | Siddharth Pawar    |  

# Table of Content
- [1. Introduction](#introduction)
- [2. Why Use GitLeaks?](#why-use-gitleaks)
- [3. Installation](#installation)
- [4. Example Scans](#example-scans)
- [5. Conclusion](#conclusion)  
7. [Contact Information](#contact-information)  
8. [References](#references)  


# Introduction
GitLeaks is an open-source tool designed to detect hardcoded secrets like API keys, passwords, and tokens in Git repositories. This document provides a proof of concept (POC) demonstrating how GitLeaks can be used to scan repositories and prevent credential leaks.

# Why Use GitLeaks?
- **Prevents Security Breaches:** Detects exposed credentials before they can be exploited.
- **Automated Scanning:**Can be integrated with CI/CD pipelines.
- **Compliance:** Helps meet security standards like GDPR, SOC 2, and PCI-DSS.
- **Lightweight & Efficient:** Simple CLI tool with regex-based scanning.

# Installation

To install Gitleaks on your system, please follow the link below for the Gitleaks Installation Guide. :- [Gitleaks Installation Guide]()

# Example Scans



### Running Git Leaks:


### For testing made some changes in code and checked using pre commit flag:


### Generated report



# Conclusion
GitLeaks is a powerful and lightweight tool that helps prevent credential leaks by scanning Git repositories for secrets. By integrating it into your development workflow and CI/CD pipelines, you can enhance security and prevent unauthorized access to sensitive data.

##  Contact Information
For any queries or further information, feel free to contact:
| **Name**  | **Email**                       |
|-----------------|-----------------------------------|
| Aman | aman.raj@mygurukulam.co |

---
##  References
| **Resource** | **Link** |
|-------------|---------|
| Git Leaks | [Link](https://github.com/gitleaks/gitleaks) |
| GitLeaks Updated Commands | [Link](https://gist.github.com/zricethezav/b325bb93ebf41b9c0b0507acf12810d2) |
