# Credential Scanning

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer**      
|-----------------------|----------------|-------------|----------------------------|---------------------|-------------------|


# Table of Content
1. [Introduction](#introduction)
2. [Why Credential Scanning ?](#why-credential-scanning)
2. [Tools For Credential Scanning](#different-tools-for-credential-scanning)
3. [Tools Comparison](#tools-comparison)
4. [Advantages](#advantages)
5. [POC](#poc)
6. [Best Practices](#best-practices-for-credential-scanning)
7. [Conclusion](#conclusion)
8. [Contact Information](#contact-information)
9. [References](#references)

# Introduction
Credential Scanning is a crucial practice to detect and prevent hardcoded secrets, API keys, passwords, and other sensitive information from being exposed in source code repositories. Exposed credentials can lead to data breaches, unauthorized access, and security vulnerabilities.

# Why Credential Scanning?

| **Aspect**                  | **Description** |
|-----------------------------|---------------|
| **Prevents Leaks**         | Identifies and removes hardcoded credentials before they cause security breaches. |
| **Automated Protection**    | Integrates with CI/CD pipelines to prevent exposure in builds or deployments. |
| **Compliance**             | Helps meet regulations like GDPR, PCI-DSS, and SOC 2 by preventing sensitive data leaks. |
| **Security Best Practice**  | Enforces keeping credentials out of source code to minimize unauthorized access risks. |
| **Reduces Human Error**     | Detects credentials accidentally committed by developers. |
| **Improves Incident Response** | Enables quick detection and response to exposed credentials (e.g., rotating keys, revoking access). |


# Different Tools for Credential Scanning
| **Tools Name** | **Description** | **Key Features** | **Open Source** |
|-----------|-----------------|------------------|------------------|
| **GitLeaks**  | A tool that scans Git repositories for hardcoded secrets. | 1. Scans commit history to find exposed secrets <br/> 2. Blocks sensitive commits before pushing <br/> 3. Can be integrated into CI/CD pipelines|  Yes|
| **TruffleHog** | A credential scanning tool that searches for high-entropy strings and known credential patterns. | 1. Uses entropy analysis to detect passwords and API keys <br/> 2. Supports scanning multiple platforms such as GitHub, GitLab, and Bitbucket <br/> 3. Uses machine learning to improve accuracy| Yes  |
| **AWS Secrets Manager** | A service provided by Amazon Web Services to securely store, manage, and retrieve credentials. | 1. Automatic secret rotation <br/> 2. Encrypted storage for API keys and passwords <br/> 3. Fine-grained access control| No |
| **GitGuardian** | A commercial tool specializing in scanning for secrets and credentials. Supports public and private repositories. | 1. Continuous real-time monitoring <br/> 2. CI/CD integration <br/> 3. Alerts for exposed secrets| No |

# Tools Comparison
| Feature |	GitLeaks | TruffleHog | AWS Secrets Manager | GitGuardian |
|---------|----------|------------|--------------------|-------------|
| **Type** | Open-source tool | Open-source tool | Managed cloud service | Commercial tool|
| **Purpose** | Scans Git repositories for exposed secrets | Detects high-entropy secrets in repositories | Securely stores and manages credentials | Scans repositories for leaked credentials in real-time |
| **Scanning Method** | Uses regex patterns and entropy analysis | Uses entropy analysis and regex scanning | No scanning; focuses on secret storage and access management | AI-powered scanning for secrets in repositories |
| **CI/CD Integration** | Supports GitHub Actions, GitLab CI/CD, Jenkins, etc. | Can be integrated but requires scripting | Not applicable |Native integration with major CI/CD platforms |
| **Pre-commit Hook Support** | Yes (Pre-commit integration available)| Yes (Can be used with pre-commit hooks) | No  | Yes |
|**Alerts & Notifications**|No built-in alerting	| No built-in alerting	|Supports AWS CloudWatch alerts| Provides real-time alerts & notifications|
|**Ease of Use**|Simple CLI-based tool|Requires fine-tuning|Fully managed service|User-friendly with a web dashboard|
|**Best For**|Developers looking for an easy-to-use CLI tool	|Security teams needing deep scans of repositories	|Organizations needing secure credential storage	|Enterprises needing real-time monitoring & alerts|
|**Cost**|Open Source & Free|Open Source & Free|Paid (AWS pricing varies)|Paid (Subscription-based)|

# Advantages
 **Early Detection of Secrets** :
Credential scanning ensures that secrets are identified before they are exposed, reducing security risks.

**Automated Enforcement of Security Policies**
By integrating credential scanning tools in CI/CD pipelines, organizations can automatically enforce security policies and prevent sensitive data from being committed.

 **Compliance with Security Standards**
Many security frameworks require organizations to implement controls for protecting credentials. Automated scanning helps in maintaining compliance with industry regulations.

 **Improved Developer Productivity**
Credential scanning automates security checks, allowing developers to focus on writing secure code without worrying about accidental leaks.

# POC
Please Refer Here for [POC](https://github.com/Snaatak-Skyops/Documentation/blob/d5cdf2205c53899de56c76166838b80355bc8936/Application%20CI%20Design/Generic%20CI%20operation/Cred%20Scanning/POC/README.md)

# Best Practices for Credential Scanning
| **Best Practice** |	**Description** |
|---------------|---------------|
| **Use Pre-Commit Hooks** |	Prevent secrets from being committed using tools like Talisman or Detect-Secrets. |
|**Integrate Scanning in CI/CD** |	Automate secret detection with GitLeaks or TruffleHog in pipelines. |
| **Store Secrets Securely**|	Use AWS Secrets Manager or HashiCorp Vault instead of hardcoding credentials.|
|**Monitor and Alert for Leaks**|	Set up real-time alerts with GitGuardian or GitHub Secret Scanning. |
|**Revoke and Rotate Compromised Secrets**|	Immediately revoke exposed credentials and rotate keys regularly.|


# Conclusion
Credential scanning is essential for preventing security breaches caused by exposed secrets. By integrating automated scanning tools, secure secret management, and proactive monitoring, organizations can minimize risks and protect sensitive data. Regular scanning, proper secret storage, and immediate remediation of leaks ensure a strong security posture in DevOps workflows.



##  Contact Information
For any queries or further information, feel free to contact:
| **Name**  | **Email**                       |
|-----------------|-----------------------------------|


---
## References

| **Resource** |  |
|-------------|---------|
| Git Secret Scanning Tool | [Link](https://spectralops.io/blog/top-9-git-secret-scanning-tools/) |
| Git Leaks | [Link](https://github.com/gitleaks/gitleaks) |
| POC | [Link](https://github.com/Snaatak-Skyops/Documentation/blob/d5cdf2205c53899de56c76166838b80355bc8936/Application%20CI%20Design/Generic%20CI%20operation/Cred%20Scanning/POC/README.md) |
