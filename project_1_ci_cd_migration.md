# Project: Scalable CI/CD and Storage Migration from Jenkins to GitHub Actions on AWS

## Summary

In this project, I led the end-to-end migration of a complex CI/CD system from Jenkins on bare metal servers to a modern, scalable infrastructure using GitHub Actions and AWS services. The project aimed to resolve challenges related to scalability, high maintenance costs, and data-heavy QA environments that generated up to 30 GB per test suite across nearly 30 environments.

## Key Responsibilities and Achievements

We executed a comprehensive migration strategy centered around AWS and GitHub Actions. The first step was provisioning infrastructure on AWS, where dedicated EC2 instances were configured as self-hosted GitHub runners to execute CI/CD workflows. These runners also automated the creation of database schemas and the population of test data, which was retrieved from services deployed in ECS.

Application environments were deployed on separate EC2 instances, running containerized services via Docker. For storage, we utilized Amazon S3—one bucket for test suite logs and another for application data. The application database was managed using Amazon RDS for PostgreSQL within a VPC, ensuring high availability and scalability.

To support automated data operations, ECS services were launched to populate and validate the application database with relevant datasets. The CI/CD pipeline was migrated from Jenkins to GitHub Actions, with new workflows designed to handle testing and data operations seamlessly. The entire infrastructure was codified using Terraform and Terragrunt, ensuring consistent, reproducible environments with built-in backup capability.

Security and observability were integral to the solution. AWS IAM was used to control access across all resources, while CloudWatch provided detailed monitoring, logging, and alerting for both infrastructure and application layers. Encryption key management was handled securely using AWS KMS.

To further optimize costs and scalability, we developed a Lambda-based automation function that dynamically scaled AWS resources—such as RDS instances, ECS services, and Auto Scaling Groups—based on workload demand.

- **Infrastructure Migration to AWS**: Designed and implemented infrastructure using Terraform and Terragrunt. Deployed self-hosted GitHub Runners on EC2 instances and migrated CI/CD pipelines from Jenkins to GitHub Actions.
- **CI/CD Transition**: Migrated pipelines from Jenkins to GitHub Actions using EC2-hosted runners.
- **Cloud-Native Architecture**:
  - EC2 for application hosting and GitHub runners
  - ECS for environment provisioning
  - RDS (PostgreSQL) for application data
  - S3 buckets for log and data storage
- **Cost Optimization**: Developed 30 serverless AWS Lambda functions (one per environment) to scale down resources dynamically, reducing costs and idle resource usage.
- **Security and Monitoring**: Implemented AWS IAM for access control, AWS CloudWatch for monitoring and alerting, and AWS KMS for encryption.

- **Standardization**: Introduced schema standardization across projects and Infrastructure as Code practices.
- **TCO Analysis**: Conducted a thorough total cost of ownership analysis, revealing substantial savings in hardware, energy, and labor, validating the shift to AWS as financially sound.

- **Team Enablement and Lessons Learned**: Facilitated team upskilling on AWS and GitHub Actions, enforced Infrastructure as Code best practices, and applied effective S3 lifecycle policies to manage storage costs.

## Outcome

The migration significantly improved scalability, reduced operational overhead, enhanced data handling, and modernized the CI/CD workflow, positioning the organization for faster development cycles and long-term cloud efficiency.

## Architecture Diagram

![CI/CD and AWS Architecture](A_digital_diagram_illustrates_CI/CD_and_storage_mi.png)
