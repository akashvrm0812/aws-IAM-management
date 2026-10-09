![AWS IAM Terraform Banner](https://capsule-render.vercel.app/api?type=waving&color=0:232F3E,50:2563EB,100:00C7B7&height=220&section=header&text=AWS%20IAM%20Management&fontSize=38&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Identity%20%7C%20Access%20Control%20%7C%20Terraform&descAlignY=58&descSize=16)

<div align="center">

# AWS IAM Management using Terraform

### Automating AWS Identity and Access Management with Infrastructure as Code

[![Terraform](https://img.shields.io/badge/Terraform-IaC-7B42BC?logo=terraform&logoColor=white)](https://www.terraform.io/)
[![AWS](https://img.shields.io/badge/AWS-IAM-FF9900?logo=amazonaws&logoColor=white)](https://aws.amazon.com/iam/)
[![YAML](https://img.shields.io/badge/Config-YAML-CB171E?logo=yaml&logoColor=white)](https://yaml.org/)
[![GitHub](https://img.shields.io/badge/Version_Control-GitHub-181717?logo=github&logoColor=white)](https://github.com/akashvrm0812)

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&pause=1000&color=00C7B7&center=true&vCenter=true&width=700&lines=Automating+AWS+IAM+with+Terraform;Managing+Users+and+Permissions;Infrastructure+as+Code+%7C+AWS+%7C+Terraform)](https://git.io/typing-svg)

</div>

---

## Overview

This project demonstrates how to automate AWS Identity and Access Management (IAM) using **Terraform Infrastructure as Code (IaC)**.

It uses Terraform to define and manage IAM users, login profiles, and policy attachments, with user configuration maintained in a YAML file.

The goal is to demonstrate practical AWS IAM administration, infrastructure automation, and repeatable infrastructure management.

## Architecture

```text
users.yaml
    |
    v
Terraform Configuration
    |
    v
AWS IAM Resources
    |
    +-- IAM Users
    |
    +-- Login Profiles
    |
    +-- IAM Policy Attachments
    |
    v
AWS IAM
```

## Technologies Used

- **AWS IAM** — Identity and access management
- **Terraform** — Infrastructure as Code
- **AWS Provider for Terraform** — AWS resource management
- **YAML** — User configuration and input data
- **Git and GitHub** — Version control and project documentation

## Project Structure

```text
aws-IAM-management/
├── screenshots/
├── .gitignore
├── .terraform.lock.hcl
├── main.tf
├── users.yaml
└── README.md
```

## Features

- **Automated IAM user creation** using Terraform.
- **YAML-based configuration** for organizing user and permission assignment data.
- **IAM login profile management** through Terraform.
- **Automated policy attachments** for associating users with configured AWS managed policies.
- **Repeatable infrastructure management** using declarative configuration.
- **Configuration validation** with `terraform validate`.
- **Infrastructure version control** using Git and GitHub.

## Prerequisites

Before running this project, ensure you have:

- An AWS account.
- Terraform installed.
- AWS CLI installed and configured, or another supported AWS credentials method.
- Appropriate AWS permissions to manage IAM users, login profiles, and policy attachments.
- Git installed.

> **Security:** Use a dedicated development account or sandbox where possible. Avoid using root account credentials.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/akashvrm0812/aws-IAM-management.git
cd aws-IAM-management
```

### 2. Configure AWS Credentials

Configure a local AWS CLI profile:

```bash
aws configure
```

Enter your AWS access key, secret access key, default region, and output format when prompted.

For improved security, prefer temporary credentials through AWS IAM Identity Center or an appropriate role-based workflow when available. Never commit credentials to GitHub.

### 3. Review the Configuration

Review `main.tf` to understand the provider configuration, local values, IAM resources, and policy attachments.

Review `users.yaml` to understand how user information and permission assignments are defined. Ensure it contains no passwords, access keys, or other secrets.

### 4. Initialize Terraform

```bash
terraform init
```

This initializes the Terraform working directory and installs the required provider.

### 5. Validate the Configuration

```bash
terraform validate
```

Terraform should report that the configuration is valid if there are no configuration errors.

### 6. Preview Infrastructure Changes

```bash
terraform plan
```

Review the proposed changes before applying them. IAM changes can grant significant access to AWS resources.

### 7. Apply the Configuration

```bash
terraform apply
```

Review the execution plan and type `yes` only when you intend to create or modify the listed resources.

## Security Best Practices

- Never hardcode AWS access keys, secret keys, or passwords in Terraform files.
- Do not commit `.env` files, Terraform state files, or generated credentials.
- Exclude `.terraform/` and `*.tfstate*` using `.gitignore`.
- Store Terraform state securely because it can contain sensitive information.
- Follow the principle of least privilege when attaching IAM policies.
- Avoid broad permissions unless the use case genuinely requires them.
- Enable MFA for console users where appropriate.
- Prefer temporary credentials and role-based access whenever possible.
- Protect generated IAM login passwords and access keys as secrets.
- Blur account identifiers and access-key details in any publicly shared images.

## Cleanup

When you have finished testing, you can remove resources managed by this Terraform configuration:

```bash
terraform destroy
```

Review the proposed deletions and confirm only if you intend to delete those resources. Do not run this against shared or production infrastructure without authorization.

## Learning Outcomes

Through this project, I practiced:

- Managing AWS IAM resources using Terraform.
- Organizing configuration data with YAML.
- Defining IAM users and attaching permissions through code.
- Initializing and validating Terraform configurations.
- Reviewing infrastructure changes using Terraform plans.
- Maintaining infrastructure code with Git and GitHub.
- Applying security practices to infrastructure repositories.

## Future Improvements

- Introduce reusable Terraform modules.
- Add input validation and stronger configuration checks.
- Configure encrypted remote state storage and state locking.
- Add automated formatting and validation using GitHub Actions.
- Improve policy management with custom least-privilege policies.
- Introduce automated testing and deployment workflows.

## Author

**Akash Verma**


---

*This project is intended for learning and demonstration purposes. Review all IAM permissions and resource changes before applying them to an AWS account.*
