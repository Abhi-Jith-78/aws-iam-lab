# 🛡️ AWS Identity and Access Management (IAM) – Hands-On Lab

This repository documents my hands-on lab practice with **AWS Identity and Access Management (IAM)**.  
The goal of this lab was to explore IAM Users, Groups, Policies, and understand how different permission levels affect access to AWS services such as **EC2** and **S3**.

---

## 🚀 **Lab Overview**

In this lab, I practiced the following:

- Exploring IAM Users and Groups  
- Reviewing Managed and Inline Policies  
- Assigning users to groups based on a business scenario  
- Testing access using IAM user sign-in  
- Verifying permissions for EC2 and S3 operations  

---

## 🧩 **Business Scenario**

A company needs to give new staff access to AWS based on job role:

| User   | Group         | Permissions |
|--------|---------------|-------------|
| user-1 | S3-Support    | Read-only S3 access |
| user-2 | EC2-Support   | Read-only EC2 access |
| user-3 | EC2-Admin     | Describe + Start/Stop EC2 |

I assigned users to the correct IAM groups and tested their permissions.

---

## 📊 **IAM Architecture Diagram (Mermaid)**

GitHub renders this automatically — no image needed.

```mermaid
flowchart TD
    A[IAM Users] --> B{IAM Groups}

    user1[user-1] --> group1[S3-Support]
    user2[user-2] --> group2[EC2-Support]
    user3[user-3] --> group3[EC2-Admin]

    group1 --> policy1["AmazonS3ReadOnlyAccess (Managed Policy)"]
    group2 --> policy2["AmazonEC2ReadOnlyAccess (Managed Policy)"]
    group3 --> policy3["EC2-Admin-Policy (Inline Policy)"]

    policy1 --> access1["S3 Read-Only Access"]
    policy2 --> access2["EC2 Describe Access"]
    policy3 --> access3["EC2 Start/Stop/Describe Access"]
