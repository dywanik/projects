# Project: Migration from Azure DevOps on GCP to GitHub Actions on AWS

## Summary

This project involved a complete overhaul of a CI/CD system that previously relied on Azure DevOps running on Google Cloud Platform (GCP). The goal was to migrate to a more modern, scalable, and cost-effective solution using GitHub Actions and Amazon Web Services (AWS). The motivation behind the project was standardization of acquired systems and, therefore, cost optimization.

## Key Responsibilities and Achievements

### Infrastructure Migration to AWS

- Designed and provisioned AWS infrastructure using **Terraform** and **Terragrunt**.
- Deployed **EC2 instances** as self-hosted **GitHub Runners** to replace GCP-hosted build agents.
- Migrated all CI/CD pipelines from **Jenkins** to **GitHub Actions**, aligning with GitHub-native workflows.

### CI/CD Pipeline Transformation

- Recreated Azure DevOps workflows as modular, reusable GitHub Actions.
- Integrated test automation and data population tasks directly into the CI/CD flow.
- Utilized EC2 and S3 to simulate production-like environments for reliable testing.

### Cloud-Native Architecture Components

- **EC2**: Hosted applications and GitHub runners.
- **ECS**: Launched services for test data generation and environment provisioning as well as providing MSSQL databases.
- **Amazon S3**: Separated buckets for test logs and application data.

### Cost Optimization

- Serverless functions scaled down RDS, ECS, and EC2 resources during idle times.
- Applied **S3 lifecycle policies** for automated log/data archival and deletion.

### Standardization and Automation

- Implemented **schema standardization**
- Codified infrastructure and workflows to ensure consistent deployment and reproducibility.
- Promoted **Infrastructure as Code (IaC)** and **GitOps** principles across the engineering teams.

### Team Enablement & Knowledge Transfer

- Conducted internal workshops and documentation sessions to onboard the team to GitHub Actions and AWS.
- Established guidelines for maintaining GitHub workflows and scaling runner instances efficiently.
- Introduced automation pipelines for tests and validations.

## Outcome

The migration project led to:

- **Improved scalability** and **faster pipeline execution**.
- **Reduced cloud costs** through intelligent resource management, i.e., data not "leaving" AWS.
- **Increased team agility** through streamlined workflows and modern tools.
- A foundation for **future expansion** with reusable, cloud-native patterns.

---

This migration positioned the organization for long-term cloud success, with a leaner, more scalable, and DevOps-friendly CI/CD ecosystem.
