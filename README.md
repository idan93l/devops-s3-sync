# DevOps Assignment — Terraform + Jenkins + Helm on S3

This project demonstrates infrastructure automation, CI/CD integration, and artifact hosting using AWS, Terraform, Jenkins, and Helm.

---

## ✅ Part 1 — AWS Budget with Terraform

An AWS monthly cost budget is defined using Terraform.

Features:
- Monthly budget limit
- Email notification at 80% threshold
- Managed entirely as Infrastructure-as-Code
- Terraform state stored remotely in S3

Terraform backend:
- S3 remote state bucket
- DynamoDB table for state locking
- Encrypted backend

Resources created:
- AWS Budget
- S3 Terraform state bucket
- DynamoDB locking table

---

## ✅ Part 2 — Terraform Remote Backend

Terraform is configured with:

- S3 bucket as remote backend
- DynamoDB table to prevent concurrent operations
- Versioned and encrypted state storage

This setup simulates a real production Terraform workflow.

---

## ✅ Bonus 1 — Jenkins CI Pipeline

A Jenkins pipeline was implemented that:

- Pulls from GitHub repository
- Automatically triggers on push (SCM polling)
- Uses stored AWS credentials securely
- Syncs repository files to an S3 bucket using AWS CLI

Pipeline actions:

```
GitHub push → Jenkins build → aws s3 sync → S3 deploy bucket
```

This demonstrates CI/CD automation and artifact deployment.

---

## ✅ Bonus 2 — Helm Repository on S3

An S3 bucket was converted into a Helm chart repository.

Steps completed:

- Installed helm-s3 plugin
- Initialized S3 bucket as Helm repo
- Created a sample Helm chart
- Packaged and pushed chart to S3
- Verified chart availability via Helm search

This simulates a private Helm artifact repository hosted on AWS.

---

## Tools Used

- Terraform
- AWS S3
- AWS Budgets
- DynamoDB
- Jenkins
- GitHub
- Helm
- helm-s3 plugin
- AWS CLI
- WSL (Linux environment)

---

## Result

The assignment demonstrates:

- Infrastructure-as-Code best practices
- Secure remote Terraform state management
- CI/CD automation with Jenkins
- Cloud artifact hosting
- Helm repository management on S3

All components are fully functional and reproducible.

---

