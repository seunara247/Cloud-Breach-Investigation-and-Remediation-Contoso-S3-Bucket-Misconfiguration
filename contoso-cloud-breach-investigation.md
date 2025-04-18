
# **Cloud Breach Investigation and Remediation: Contoso S3 Bucket Misconfiguration**

## **Overview**

This project was a cloud security investigation simulation involving a real-world breach scenario. I acted as a **Cloud Security Engineer** tasked with analyzing the root cause of the compromise, identifying the attacker’s activity, and recommending security improvements to prevent future incidents.

---

## **Scenario Summary**

Contoso recently migrated all its services and applications to AWS. However, the environment was compromised due to a **misconfigured S3 bucket** which exposed sensitive AWS credentials. As part of the investigation, I was granted temporary access to the compromised AWS account, along with access logs, to conduct a full analysis and report my findings.

---

## **Key Objectives**

- Identify the exposed credentials and their associated permissions.
- Analyze the attacker’s actions and determine the extent of the data exfiltration.
- Recommend security improvements based on findings.

---

## **Investigation Findings**

| **Question** | **Answer** |
|--------------|-----------|
| Access Key ID | `AKIA VPEYV7H4ALHONAA V` |
| Owner of Access Key | Cole |
| Permissions Associated | Administrative access |
| Access Key Status | Inactive |
| Were Permissions Necessary? | No — excessive privileges for the employee’s role |

---

## **Log Analysis (Attack Forensics)**

- **Sensitive Data Bucket:** `contoso-private-data`
- **Country of Origin:** India
- **Attacker's IP Address:** `223.113.128.138`
- **Exfiltration Timestamp:** October 16, 2024 at 09:54:10 and 09:54:10.925569Z
- **Stolen Files:**
  - `Employee-PII-records.xlsx`
  - `Customer-PII.xlsx`
  - `Employee-records.xlsx`

---

## **Security Recommendations**

To prevent similar breaches in the future, I recommended a comprehensive security overhaul with the following action points:

### 1. **Logging and Monitoring**
- Enable AWS **CloudTrail** and **S3 access logs** to track user activity.
- Store logs securely and monitor them continuously using SIEM tools.

### 2. **Enable Threat Detection**
- Use **AWS GuardDuty** to detect threats based on behavior analytics and intelligence feeds.

### 3. **Set Up Real-Time Alerts**
- Configure **Amazon CloudWatch** alarms for sensitive actions (e.g., `GetObject` on private buckets).
- Set up auto-remediation workflows for high-severity alerts.

### 4. **Enforce Principle of Least Privilege**
- Ensure IAM policies grant only the minimum necessary permissions.
- Revoke administrative rights from non-admin users like finance staff.

### 5. **Use Encryption for Data Protection**
- Encrypt all S3 data **at rest (SSE-KMS)** and **in transit (SSL/TLS)**.
- Require encryption through bucket policies.

### 6. **Regular Security Audits**
- Use **AWS Config**, **IAM Access Analyzer**, and **Trusted Advisor** to conduct periodic reviews.
- Monitor for unused access keys and outdated permissions.

### 7. **Employee Security Training**
- Conduct mandatory **security awareness training** focused on:
  - Proper credential handling
  - Phishing resistance
  - Cloud hygiene and secure configuration
- Establish a **"security-first" culture** across teams.

---

## **Tools and Skills Used**

- AWS Console (IAM, S3, CloudTrail, CloudWatch)
- Base64 decoding (to retrieve credential contents)
- Threat analysis and log parsing
- AWS GuardDuty and security configuration best practices
- Cybersecurity incident response planning

---

## **Outcome**

This project sharpened my ability to:
- Identify and respond to real-world cloud breaches,
- Analyze IAM roles and logs in AWS,
- Make actionable recommendations aligned with best practices for cloud security.

It also highlighted how a **single misconfiguration** can lead to **massive security incidents**, and how **proactive monitoring, access control, and training** are critical to a strong cloud security posture.
