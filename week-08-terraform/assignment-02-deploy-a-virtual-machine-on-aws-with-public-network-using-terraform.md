<<<<<<< HEAD
# Assignment 2 — Deploy a Virtual Machine on AWS with Public Network Using Terraform

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will use Terraform to create a custom AWS network (VPC, public and private subnets, Internet Gateway, route table) and launch an EC2 instance into the public subnet with a public IP, a Security Group allowing SSH and HTTP, and Nginx installed for validation.

---

# Task 1 — Create a New Terraform Project

## Goal

Create a `terraform-aws-vm` project directory for the AWS Terraform configuration.

### Evidence

#### Screenshot 1 — File Explorer, VS Code, or terminal showing the `terraform-aws-vm` project directory

![screenshot_1](screenshots/assignment02-ss1.png)

---

# Task 2 — Create main.tf with the Required AWS Resources

## Goal

Define the AWS provider, a VPC (10.0.0.0/16) with a public subnet (10.0.1.0/24) and private subnet (10.0.2.0/24), an Internet Gateway with public routing, a Security Group (SSH 22, HTTP 80), an EC2 instance in the public subnet with a public IP, and a public IP output.

### Evidence

#### Screenshot 2 (optional) — `main.tf` showing the VPC and EC2 resource blocks

![screenshot_2](screenshots/assignment02-ss2.png)

---

# Task 3 — Initialize Terraform

## Goal

Run `terraform init` and confirm the working directory initializes successfully.

### Evidence

#### Screenshot 3 — Terminal showing successful `terraform init` output

![screenshot_3](screenshots/assignment02-ss3.png)

---

# Task 4 — Plan and Apply the Configuration

## Goal

Review `terraform plan`, run `terraform apply`, and record the EC2 instance's public IP from the Terraform output.

### Evidence

#### Screenshot 4 — Terraform apply output showing successful completion

![screenshot_4](screenshots/assignment02-ss4.png)

---

#### Screenshot 5 — Terraform output showing the EC2 public IP

![screenshot_5](screenshots/assignment02-ss5.png)

---

# Task 5 — Verify the Deployment

## Goal

Confirm the EC2 instance is running in the public subnet with a public IP, install Nginx, and confirm it is accessible by browser or SSH.

### Evidence

#### Screenshot 6 — EC2 instance running in the AWS Console, with the subnet and public IP visible

![screenshot_6](screenshots/assignment02-ss6.png)

---

#### Screenshot 7 — Browser showing the Nginx page through the EC2 public IP, or terminal showing a successful SSH connection

![screenshot_7](screenshots/assignment02-ss7.png)

---

# Task 6 — Destroy Resources

## Goal

Run `terraform destroy` to remove the Terraform-managed AWS resources after testing.

### Evidence

#### Screenshot 8 — Terminal showing successful `terraform destroy` completion

![screenshot_8](screenshots/assignment02-ss8.png)

---

### Notes

Write a short paragraph about any challenges you faced and how you solved them.

During this Terraform deployment, I encountered several real-world infrastructure challenges that strengthened my troubleshooting skills. First, Azure Policy blocked deployments in the `East US` region with a 403 Forbidden error, so I identified the policy restriction and changed the deployment region to South Africa North. Next, Terraform lost track of resources after a failed deployment, causing a 404 ResourceNotFound error for the virtual network. I resolved this by importing the existing Azure resources into the Terraform state and refreshing the state before continuing the deployment. Finally, the virtual machine failed due to an unavailable or invalid VM SKU, so I reviewed the valid VM sizes for the region and updated the configuration to use a supported size. These challenges reinforced the importance of understanding Azure policies, Terraform state management, and cloud resource availability when deploying infrastructure as code.


---

# Submission Instructions

- Add all required screenshots in your submission
- Include the EC2 public IP
- Do not expose AWS credentials, private keys, or account IDs

---

# Completion Checklist

- [✅] Task 1: `terraform-aws-vm` project created (Screenshot 1)
- [✅] Task 2: `main.tf` defines VPC, subnets, IGW, Security Group, and EC2 (Screenshot 2, optional)
- [✅] Task 3: `terraform init` completed successfully (Screenshot 3)
- [✅] Task 4: Plan reviewed and `terraform apply` completed, public IP recorded (Screenshots 4–5)
- [✅] Task 5: EC2 instance verified running and accessible (Screenshots 6–7)
- [✅] Task 6: `terraform destroy` completed successfully (Screenshot 8)
- [✅] Challenges/solutions paragraph written (Notes)
- [✅] No sensitive information exposed

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*
=======
# Assignment 2 — Create an AWS EC2 Virtual Machine Using Terraform

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will use Terraform to provision a complete AWS environment consisting of a custom VPC, public and private subnets, an Internet Gateway, a public route table, a security group, and an EC2 instance deployed inside the public subnet.

You will configure SSH and HTTP access, install Nginx, capture the EC2 instance’s public IP address, verify the deployment using AWS CLI and a web browser, and destroy all Terraform-managed resources after testing.

---

# Task 0 — Set Up and Verify the Terraform and AWS CLI Environment

## Goal

Prepare your local environment for Terraform deployment by installing Terraform, AWS CLI, and the HashiCorp Terraform extension in VS Code, configuring AWS CLI with your AWS account, and confirming that all required tools are working correctly.

### Evidence

#### Screenshot 1 — Terminal showing successful `aws --version` output

Ensure that your full name is visible and that no AWS credentials, account IDs, or other sensitive information are exposed.

Add your screenshot here.

---

# Task 1 — Create a New Terraform Project and Define the Infrastructure

## Goal

Create a new Terraform project and define the complete AWS EC2 environment in `main.tf` by using the official Terraform Registry documentation.

The configuration must include:

* Terraform and AWS provider configuration
* Custom VPC using the CIDR block `10.0.0.0/16`
* Public subnet using the CIDR block `10.0.1.0/24`
* Private subnet using the CIDR block `10.0.2.0/24`
* Internet Gateway
* Public route table with a route to `0.0.0.0/0`
* Public subnet route table association
* Security group allowing SSH on port `22`
* Security group allowing HTTP on port `80`
* EC2 instance deployed inside the public subnet
* SSH authentication configuration
* Public IP address association
* Public IP output block

### Evidence

#### Screenshot 2 — VS Code showing the AWS provider configuration and VPC configuration in `main.tf`

Add your screenshot here.

---

#### Screenshot 3 — VS Code showing the EC2 instance configuration and public IP `output` block in `main.tf`

Ensure that no AWS credentials, private keys, account IDs, or other sensitive information are visible.

Add your screenshot here.

---

# Task 2 — Initialize Terraform

## Goal

Initialize the Terraform working directory and download the required provider components.

### Evidence

#### Screenshot 4 — Terminal showing the successful `terraform init` output

Add your screenshot here.

---

# Task 3 — Plan and Apply the Configuration

## Goal

Review the Terraform execution plan, provision the AWS resources, and record the EC2 instance’s public IP address from the Terraform output.

### Evidence

#### Screenshot 5 — Terraform plan summary showing the proposed resources

Add your screenshot here.

---

#### Screenshot 6 — Terraform apply output showing successful completion

Add your screenshot here.

---

#### Screenshot 7 — Terraform output showing the public IP address of the EC2 instance

Add your screenshot here.

---

### EC2 Public IP Address

Record the public IP address displayed by `terraform output`.

**EC2 Public IP Address:** `Add the public IP address here`

---

# Task 4 — Verify the Deployment

## Goal

Confirm through AWS CLI that the EC2 instance was created successfully and is running, and verify HTTP access through the instance public IP.

Confirm that:

* The EC2 instance appears in the AWS CLI output.
* The EC2 instance state shows `running`.
* The public IP shown by AWS matches the public IP recorded from Terraform.
* Nginx is installed and running.
* The Nginx page is accessible through the EC2 instance’s public IP.

### Evidence

#### Screenshot 8 — AWS CLI output showing the EC2 instance ID, `running` state, and public IP address

Add your screenshot here.

---

#### Screenshot 9 — Browser showing the Nginx page successfully loaded using the EC2 instance public IP

Add your screenshot here.

---

# Task 5 — Destroy the Resources

## Goal

Remove all AWS resources created by Terraform after completing the deployment and verification.

### Evidence

#### Screenshot 10 — Terminal showing successful `terraform destroy` completion

Add your screenshot here.

---

# Submission Instructions

* Complete all tasks in sequence.
* Include all required screenshots specified in Tasks 0–5.
* Ensure that your full name is visible in the required screenshots.
* Record the EC2 public IP address in Task 3.
* Follow the screenshot requirements exactly as specified.
* Ensure that the submitted evidence clearly matches the required task outputs.
* Do not expose AWS access keys, secret keys, private keys, passwords, account IDs, or other sensitive information.
* Do not upload your private key file (`.pem`) to your GitHub repository.
* Review your submission carefully before submitting it through GitHub.

---

# Completion Checklist

* [ ] Installed Terraform and verified it using `terraform version`
* [ ] Installed AWS CLI and verified it using `aws --version`
* [ ] Configured AWS CLI and verified account access
* [ ] Confirmed the correct AWS Region
* [ ] Installed and enabled the HashiCorp Terraform extension in VS Code
* [ ] Created the `terraform-aws-vm` project directory and `main.tf`
* [ ] Added the Terraform and AWS provider configuration
* [ ] Defined the custom VPC, public subnet, and private subnet
* [ ] Configured the Internet Gateway and public route table
* [ ] Associated the public route table with the public subnet
* [ ] Defined the security group for SSH and HTTP access
* [ ] Restricted SSH access to my public IP whenever possible
* [ ] Defined the EC2 instance inside the public subnet
* [ ] Configured SSH authentication without exposing the private key
* [ ] Added the Terraform output for the EC2 public IP address
* [ ] Completed `terraform init` successfully
* [ ] Reviewed the Terraform execution plan using `terraform plan`
* [ ] Completed `terraform apply` successfully
* [ ] Captured and recorded the EC2 public IP using `terraform output`
* [ ] Verified that the EC2 instance is running using AWS CLI
* [ ] Verified that the AWS public IP matches the Terraform output
* [ ] Verified Nginx access through the EC2 public IP
* [ ] Completed `terraform destroy` successfully
* [ ] Captured all 10 required screenshots
* [ ] Confirmed that my full name is visible in the required screenshots
* [ ] Checked that no AWS credentials, private keys, passwords, account IDs, or other sensitive information are visible
* [ ] Confirmed that no `.pem` private key file has been uploaded to the GitHub repository

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory), focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations through hands-on experience.

---

## 📌 Resources

* 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme
* 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme
* 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme
* 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme
* ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho
* 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/
* 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of the DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*
>>>>>>> upstream/main
