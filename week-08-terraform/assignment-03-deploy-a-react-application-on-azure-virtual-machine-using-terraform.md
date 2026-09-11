<<<<<<< HEAD
# Assignment 3 — Deploy a React Application on Azure Virtual Machine Using Terraform

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will use Terraform to provision an Azure resource group, network, and Ubuntu 20.04 VM, then deploy the `my-react-app` React application onto the VM over SSH and serve it through Nginx.

---

# Task 1 — Create a New Terraform Project

## Goal

Create a `terraform-react-azure` project directory for the Azure Terraform configuration.

### Evidence

#### Screenshot 1 — File Explorer, VS Code, or terminal showing the `terraform-react-azure` project directory

![screenshot_1](screenshots/assignment03-ss1.png)

---

# Task 2 — Write main.tf to Provision the Azure Infrastructure

## Goal

Define the resource group, virtual network/subnet, Network Security Group (SSH 22, HTTP 80), public IP, network interface, and Ubuntu 20.04 Standard B1s VM in `main.tf`.

### Evidence

#### Screenshot 2 — VS Code showing `main.tf` with the required Azure resources, with any password or sensitive values hidden

![screenshot_2](screenshots/assignment03-ss2.png)

---

# Task 3 — Initialize Terraform

## Goal

Run `terraform init` and confirm the working directory initializes successfully.

### Evidence

#### Screenshot 3 — Terminal showing successful `terraform init` output

![screenshot_3](screenshots/assignment03-ss3.png)

---

# Task 4 — Plan and Apply the Configuration

## Goal

Review `terraform plan`, run `terraform apply`, and record the VM's public IP.

### Evidence

#### Screenshot 4 — Terraform apply output showing successful completion

![screenshot_4](screenshots/assignment03-ss4.png)

---

#### Screenshot 5 — Azure portal showing the Virtual Machine running and its public IP

![screenshot_5](screenshots/assignment03-ss5.png)

---

# Task 5 — Connect to the Virtual Machine

## Goal

Establish an SSH session with the Ubuntu VM through its public IP.

### Evidence

#### Screenshot 6 — Terminal showing a successful SSH connection to the Azure VM

![screenshot_6](screenshots/assignment03-ss6.png)

---

# Task 6 — Install Node.js, npm, and Git

## Goal

Update Ubuntu and install Node.js, npm, and Git.

### Evidence

#### Screenshot 7 — Terminal showing successful installation and the `node -v` and `npm -v` output

![screenshot_7](screenshots/assignment03-ss7.png)

---

# Task 7 — Clone, Build, and Serve the React App with Nginx

## Goal

Follow the `my-react-app` repository README to clone, install, and build the app, then serve the production build through Nginx.

### Evidence

#### Screenshot 8 — Terminal showing the successful React build

![screenshot_8](screenshots/assignment03-ss8.png)

---

#### Screenshot 9 — Terminal showing that Nginx is active and running

![screenshot_9](screenshots/assignment03-ss9.png)

---

# Task 8 — Test the Deployment

## Goal

Confirm the React application loads through the VM's public IP and navigation works.

### Evidence

#### Screenshot 10 — Browser showing the React application with the Azure VM public IP visible in the address bar

![screenshot_10](screenshots/assignment03-ss10.png)

---

### Notes

Write a short summary of what you built and any issues you encountered and how you resolved them.

Write your answer here.

---

# Submission Instructions

- Add all required screenshots in your submission
- Include the Azure VM public IP
- Do not expose Azure credentials, passwords, or private keys

---

# Completion Checklist

- [✅] Task 1: `terraform-react-azure` project created (Screenshot 1)
- [✅] Task 2: `main.tf` defines all required Azure resources (Screenshot 2)
- [✅] Task 3: `terraform init` completed successfully (Screenshot 3)
- [✅] Task 4: Plan applied and VM running with public IP (Screenshots 4–5)
- [✅] Task 5: SSH connection verified (Screenshot 6)
- [✅] Task 6: Node.js, npm, and Git installed (Screenshot 7)
- [✅] Task 7: React app built and served through Nginx (Screenshots 8–9)
- [✅] Task 8: App verified through the VM public IP (Screenshot 10)
- [✅] Summary paragraph written (Notes)
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
# Assignment 3 — Deploy a React Application on Azure Using Terraform

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will use Terraform to provision the required Azure infrastructure and automatically deploy the `my-react-app` React application on an Azure Linux virtual machine using a `cloud-init.sh` deployment script passed to the VM through `custom_data`.

You will verify the automated deployment through SSH, confirm that Nginx is running, access the React application through the VM public IP, and destroy the Terraform-managed resources after testing.

---

# Task 0 — Set Up and Verify the Terraform and Azure CLI Environment

## Goal

Prepare your local environment for Terraform deployment by installing Terraform, Azure CLI, and the HashiCorp Terraform extension in VS Code, signing in to your Azure account, and confirming that all required tools are working correctly.

## Evidence

### Screenshot 1 — Terraform Version

Add a screenshot of the terminal showing successful `terraform version` output.

Add your screenshot here.

---

### Screenshot 2 — Azure CLI Version

Add a screenshot of the terminal showing successful `az version` output.

Add your screenshot here.

---

### Screenshot 3 — HashiCorp Terraform Extension

Add a screenshot of the VS Code Extensions panel showing the HashiCorp Terraform extension installed and enabled.

Add your screenshot here.

---

# Task 1 — Create a New Terraform Project and Define the Infrastructure

## Goal

Create a new Terraform project and define the complete Azure infrastructure required to host the React application using the official Terraform Registry documentation.

The `terraform-react-azure` project must contain:

```text
terraform-react-azure/
├── main.tf
└── cloud-init.sh
```

The Terraform configuration must include:

- Terraform and AzureRM provider configuration
- Resource group
- Virtual network and subnet
- Network Security Group
- SSH rule for TCP port `22`
- HTTP rule for TCP port `80`
- Public IP address
- Network interface
- Linux virtual machine
- `custom_data` configuration referencing `cloud-init.sh`
- Public IP output

The `cloud-init.sh` file must contain the complete automated React application deployment workflow based on the repository instructions.

## Evidence

### Screenshot 4 — Provider, Resource Group, and Network Security Group

Add a screenshot of VS Code showing the AzureRM provider, resource group, and Network Security Group configuration in `main.tf`.

Add your screenshot here.

---

### Screenshot 5 — Linux Virtual Machine and `custom_data`

Add a screenshot of VS Code showing the Linux virtual machine configuration, including the `custom_data` configuration, in `main.tf`.

Ensure that passwords, private keys, account IDs, access tokens, and other sensitive information are hidden.

Add your screenshot here.

---

### Screenshot 6 — Completed `cloud-init.sh`

Add a screenshot of VS Code showing the completed `cloud-init.sh` deployment script.

Ensure that no passwords, Azure credentials, access tokens, SSH private keys, or other sensitive information are visible.

Add your screenshot here.

---

### Screenshot 7 — Public IP Output Block

Add a screenshot of VS Code showing the public IP `output` block in `main.tf`.

Add your screenshot here.

---

# Task 2 — Initialize Terraform

## Goal

Initialize the Terraform working directory and download the required provider components.

## Evidence

### Screenshot 8 — Terraform Initialization

Add a screenshot of the terminal showing successful `terraform init` output.

Add your screenshot here.

---

# Task 3 — Plan and Apply the Configuration

## Goal

Review the Terraform execution plan and provision the Azure infrastructure.

## Evidence

### Screenshot 9 — Terraform Plan

Add a screenshot showing the Terraform plan summary and the proposed resources.

Add your screenshot here.

---

### Screenshot 10 — Terraform Apply

Add a screenshot showing successful `terraform apply` completion.

Add your screenshot here.

---

### Screenshot 11 — VM Public IP Output

Add a screenshot showing the VM public IP address returned by `terraform output`.

Add your screenshot here.

## VM Public IP Address

Record the public IP address displayed by `terraform output`.

**VM Public IP Address:** Add the VM public IP address here

---

# Task 4 — Verify the Automated Deployment

## Goal

Connect to the Azure Linux virtual machine and confirm that the cloud-init/user data deployment script completed successfully.

## Evidence

### Screenshot 12 — SSH Connection and Completed React Deployment

Add a screenshot of the SSH terminal showing a successful connection to the Azure VM and evidence that the React application deployment completed.

Add your screenshot here.

---

### Screenshot 13 — Nginx Service Status

Add a screenshot of the terminal showing that the Nginx service is running successfully.

Add your screenshot here.

---

# Task 5 — Verify the React Application Deployment

## Goal

Confirm that the automatically deployed React application is publicly accessible and functioning correctly.

## Evidence

### Screenshot 14 — React Application in the Browser

Add a screenshot of the browser showing the deployed React application successfully loaded using the Azure VM public IP.

Ensure that the Azure VM public IP is visible in the browser address bar.

Add your screenshot here.

---

# Task 6 — Destroy the Resources

## Goal

Remove all Azure resources created by Terraform after completing the application deployment and verification.

## Evidence

### Screenshot 15 — Terraform Destroy

Add a screenshot of the terminal showing successful `terraform destroy` completion.

Add your screenshot here.

---

# Submission Instructions

- Complete Tasks 0–6 in sequence.
- Include all 15 required screenshots exactly as specified.
- Ensure that your full name is visible in the required screenshots.
- Record the VM public IP address under Task 3.
- Ensure that the submitted evidence clearly matches the required task outputs.
- Include `main.tf` and `cloud-init.sh` in your GitHub submission.
- Do not expose passwords, SSH private keys, account IDs, access tokens, Azure credentials, or other sensitive information.
- Do not store secrets inside `cloud-init.sh`.
- Review all screenshots and project files carefully before submitting through GitHub.

---

# Completion Checklist

- [ ] Installed Terraform and verified it using `terraform version`
- [ ] Installed Azure CLI and verified it using `az version`
- [ ] Signed in to Azure and confirmed the correct subscription
- [ ] Installed and enabled the HashiCorp Terraform extension in VS Code
- [ ] Created the `terraform-react-azure` project
- [ ] Created `main.tf`
- [ ] Defined the Terraform and AzureRM provider configuration
- [ ] Defined the resource group
- [ ] Defined the virtual network and subnet
- [ ] Defined the Network Security Group
- [ ] Configured SSH and HTTP rules
- [ ] Defined the public IP and network interface
- [ ] Created `cloud-init.sh`
- [ ] Reviewed the React application repository instructions
- [ ] Created the complete deployment workflow inside `cloud-init.sh`
- [ ] Defined the Linux virtual machine
- [ ] Connected `cloud-init.sh` to the VM using `custom_data`
- [ ] Used `file()` and `base64encode()` correctly
- [ ] Added the Terraform public IP output
- [ ] Completed `terraform init` successfully
- [ ] Reviewed the Terraform execution plan
- [ ] Completed `terraform apply` successfully
- [ ] Recorded the VM public IP
- [ ] Connected to the VM through SSH
- [ ] Verified that the automated deployment completed successfully
- [ ] Verified that Nginx is running
- [ ] Verified the React application through the browser
- [ ] Completed `terraform destroy` successfully
- [ ] Captured all 15 required screenshots
- [ ] Confirmed that my full name is visible in the required screenshots
- [ ] Checked that no passwords, keys, account IDs, access tokens, or other sensitive information are exposed

---

## About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory), focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations through hands-on experience.

---

## Resources

- React Application Repository: [https://github.com/pravinmishraaws/my-react-app](https://github.com/pravinmishraaws/my-react-app)
- DMI Official Website: [https://dmi.pravinmishra.com](https://dmi.pravinmishra.com)
- University: [https://university.pravinmishra.com](https://university.pravinmishra.com)
- Discord Community: [https://discord.pravinmishra.com](https://discord.pravinmishra.com)
- Blog: [https://dmi.pravinmishra.com/blog](https://dmi.pravinmishra.com/blog)
- YouTube Playlist: [https://www.youtube.com/playlist?list=PLFeSNDtI4Cho](https://www.youtube.com/playlist?list=PLFeSNDtI4Cho)
- Pravin Mishra on LinkedIn: [https://www.linkedin.com/in/pravin-mishra-aws-trainer/](https://www.linkedin.com/in/pravin-mishra-aws-trainer/)
- CloudAdvisory on LinkedIn: [https://www.linkedin.com/company/thecloudadvisory/](https://www.linkedin.com/company/thecloudadvisory/)

---

*This submission is part of the DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*
>>>>>>> upstream/main
