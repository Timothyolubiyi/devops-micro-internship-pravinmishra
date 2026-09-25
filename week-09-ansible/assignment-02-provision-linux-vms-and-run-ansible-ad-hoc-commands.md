# Assignment 02 — Provision Linux VMs with Terraform and Run Ansible Ad-Hoc Commands

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will use Terraform to provision three or four Ubuntu Linux Virtual Machines on either Microsoft Azure or Amazon Web Services.

You will configure SSH key-based authentication, organize the servers using a custom Ansible inventory, and run Ansible ad-hoc commands across individual hosts and inventory groups.

---

# Task 1 — Create the Multi-Host Lab Structure

## Goal

Create a separate project directory for the multi-host lab and prepare the Terraform, Ansible, and documentation files.

This project will use the Git repository and Ansible controller prepared in Assignment 01.

### Evidence

#### Screenshot 1 — Terminal showing the complete `ansible-adhoc-lab` project structure

![screenshot_2](screenshots/assignment2-ss1.png)

---

#### Screenshot 2 — Terminal showing `git status --short` with the new project files and updated `.gitignore`

![screenshot_2](screenshots/assignment2-ss2.png)

---

### Notes



---

# Task 2 — Create the Terraform Configuration

## Goal

Create the Terraform configuration required to provision three or four Ubuntu Linux VMs on your selected cloud platform.

Complete only one option:

- Option A — Microsoft Azure
- Option B — Amazon Web Services

Do not configure both providers for this assignment.

### Evidence

#### Screenshot 3 — Terraform configuration showing the three or four server roles and the `for_each` or `count` implementation

![screenshot_3](screenshots/assignment2-ss3.png)

---

#### Screenshot 4 — Terraform configuration showing SSH restricted to the controller IP and HTTP allowed only for web hosts

![screenshot_4](screenshots/assignment2-ss4.png)

---

#### Screenshot 5 — Terraform output configuration showing how public IP addresses are associated with the server roles

![screenshot_5](screenshots/assignment2-ss5.png)

---

### Notes



---

# Task 3 — Provision the Infrastructure with Terraform

## Goal

Initialize and validate the Terraform configuration, review the execution plan, provision the selected three or four VMs, and retrieve their public IP addresses.

### Evidence

#### Screenshot 6 — Final `terraform apply` output showing `Apply complete`

![screenshot_6](screenshots/assignment2-ss6.png)

---

#### Screenshot 7 — `terraform output public_ips` showing the role-to-IP mapping for all three or four VMs

![screenshot_7](screenshots/assignment2-ss7.png)

---

#### Screenshot 8 — Azure Portal or AWS Management Console showing all three or four VMs in the `Running` state, with their role-based names visible

![screenshot_8](screenshots/assignment2-ss8.png)

---

### Notes


---

# Task 4 — Verify SSH Key-Based Access

## Goal

Verify that each managed VM can be accessed from the Ansible controller using SSH key-based authentication.

### Evidence

#### Screenshot 9 — Terminal showing successful SSH hostname output from all VMs

![screenshot_9](screenshots/assignment2-ss9.png)

---

### Notes



---

# Task 5 — Create the Custom Ansible Inventory

## Goal

Create an Ansible inventory file that groups the managed VMs by role.

The inventory allows Ansible to run commands against all servers, or only specific groups such as `web`, `app`, or `db`.

### Evidence

#### Screenshot 10 — `inventory.ini` showing the `web`, `app`, and `db` groups

![screenshot_10](screenshots/assignment2-ss10.png)

---

#### Screenshot 11 — Output of `ansible-inventory -i inventory.ini --graph`

![screenshot_11](screenshots/assignment2-ss11.png)

---

### Notes



---

# Task 6 — Run Ansible Ad-Hoc Commands

## Goal

Run Ansible ad-hoc commands from the controller to verify connectivity, check server information, and manage packages and services across inventory groups.

This task proves that the inventory is working and that Ansible can control multiple managed VMs without writing a playbook.

### Evidence

#### Screenshot 12 — Output of `ansible all -i inventory.ini -m ping`

![screenshot_12](screenshots/assignment2-ss12.png)


---

#### Screenshot 13 — Output of `ansible all -i inventory.ini -m command -a "uptime"`

![screenshot_13](screenshots/assignment2-ss13.png)

---

#### Screenshot 14 — Output of `ansible web -i inventory.ini -m apt -a "name=nginx state=present update_cache=yes" --become`

![screenshot_14](screenshots/assignment2-ss14.png)

---

#### Screenshot 15 — Output of `ansible web -i inventory.ini -m service -a "name=nginx state=started enabled=yes" --become`

![screenshot_15](screenshots/assignment2-ss15.png)

---

#### Screenshot 16 — Output of `ansible all -i inventory.ini -m apt -a "name=htop state=present update_cache=yes" --become`

![screenshot_16](screenshots/assignment2-ss16.png)

---

#### Screenshot 17 — Output of `ansible web -i inventory.ini -m command -a "systemctl is-active nginx"`

![screenshot_17](screenshots/assignment2-ss17.png)

---

### Notes



---

# LinkedIn Post Required

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

https://lnkd.in/p/eXrXE-ZR

---

#### Screenshot — Published LinkedIn post

![screenshot_18](screenshots/assignment2-ss18.png)

---

# Assignment Questions

Answer the following in your own words:

**1. What is the purpose of an Ansible inventory file?**

The Ansible inventory file defines and organizes the servers, devices, or hosts that Ansible will manage. It contains information such as the hostnames or IP addresses of managed nodes, host groups, connection details, usernames, and SSH authentication settings. By grouping hosts into categories such as web, application, and database servers, the inventory allows Ansible to target specific systems when executing commands or playbooks, making infrastructure management and automation more organized, efficient, and scalable.

---

**2. What is the difference between the `web`, `app`, and `db` groups in your inventory?**

The web, app, and db groups in the Ansible inventory represent different roles within the infrastructure. 
The web group contains servers responsible for handling web traffic and serving web applications, the app group contains servers that run the application's business logic and backend services, while the db group contains servers responsible for storing and managing application data in databases. Grouping servers this way allows Ansible to apply specific configurations, commands, and playbooks to the appropriate infrastructure tier.

---

**3. What does the Ansible `ping` module verify?**

The Ansible ping module verifies that Ansible can successfully connect to a managed host and execute a basic Python-based command on that host. It helps confirm that the inventory, SSH connection, authentication credentials, and remote Ansible environment are correctly configured. A successful response such as "pong" indicates that the managed node is reachable and ready to be controlled by Ansible.

---

**4. Why do package installation commands require `--become`?**

Package installation commands often require --become because installing or modifying system packages requires root or administrative privileges. Ansible uses --become to temporarily elevate the privileges of the remote user, typically through sudo, allowing it to perform privileged tasks such as installing packages, modifying system files, or managing services. This follows the principle of least privilege, as the normal user does not need permanent administrative access.

---

**5. When would you use an ad-hoc command instead of a playbook?**

You would use an Ansible ad-hoc command for quick, one-time, or simple administrative tasks that do not require a reusable automation workflow. For example, you might use an ad-hoc command to check server connectivity, view disk usage, restart a service, or install a package on a few servers. A playbook is more appropriate for complex, repeatable, and documented automation tasks because it allows you to define multiple steps, configurations, variables, and conditions in a structured and reusable way.

---

**6. What is one challenge you faced while setting up SSH or inventory, and how did you fix it?**

One challenge I faced was an SSH configuration error that prevented Ansible from connecting to the Azure virtual machines. The issue was caused by a typo in my SSH configuration file, where IdentifyFile was used instead of the correct IdentityFile directive. I identified the error from Ansible's SSH connection output, corrected the configuration, verified the SSH settings, and tested the connection using the correct private key. After updating the Ansible inventory with the appropriate SSH key path, I successfully verified connectivity to the managed hosts using the Ansible ping module.

---

# Required Files

Confirm that the following files are included in your assignment workspace:

- [✅] `ansible-adhoc-lab/README.md`
- [✅] `ansible-adhoc-lab/terraform/providers.tf`
- [✅] `ansible-adhoc-lab/terraform/main.tf`
- [✅] `ansible-adhoc-lab/terraform/variables.tf`
- [✅] `ansible-adhoc-lab/terraform/outputs.tf`
- [✅] `ansible-adhoc-lab/ansible/inventory.ini`
- [✅] Updated `.gitignore`

---

# Submission Instructions

- Add all required screenshots from the tasks.
- Full Name must be visible in required screenshots.
- Mention whether you used Azure or AWS.
- Mention whether you used the three-VM option or four-VM option.
- Add the public IP addresses of the VMs, redacted if preferred.
- Add your `inventory.ini` proof.
- Add a short explanation of what you learned.
- Answer all assignment questions clearly in your own words.
- Add your LinkedIn post URL.
- Do not expose SSH private keys, Terraform state files, cloud credentials, passwords, access keys, secret keys, account IDs, or subscription IDs.

---

# Completion Checklist

- [✅] Task 1: `ansible-adhoc-lab` project structure created
- [✅] Task 1: `.gitignore` updated for Terraform files
- [✅] Task 2: Terraform configuration created
- [✅] Task 2: Server roles defined for either three or four VMs
- [✅] Task 2: `count` or `for_each` used
- [✅] Task 2: SSH restricted to the controller public IP
- [✅] Task 2: HTTP allowed only for web hosts
- [✅] Task 2: Terraform output maps roles to public IPs
- [✅] Task 3: Terraform initialized successfully
- [✅] Task 3: Terraform configuration validated
- [✅] Task 3: Terraform apply completed successfully
- [✅] Task 3: All selected VMs are running
- [✅] Task 4: SSH key-based access works for every VM
- [✅] Task 5: `inventory.ini` contains `web`, `app`, and `db` groups
- [✅] Task 5: `ansible-inventory -i inventory.ini --graph` shows the correct groups
- [✅] Task 6: `ansible all -i inventory.ini -m ping` returns `SUCCESS`
- [✅] Task 6: Ad-hoc commands run successfully
- [✅] Task 6: `--become` was used for package and service tasks
- [✅] Task 6: Nginx is active on the `web` group
- [✅] Screenshots 1–17 are included
- [✅] Assignment questions are answered
- [✅] LinkedIn post published
- [✅] LinkedIn post URL added
- [✅] No sensitive information is exposed

---

## About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra and The CloudAdvisory, focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## Resources

- DMI Official Website: [https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme](https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme)
- University: [https://university.pravinmishra.com?utm_source=github&utm_medium=readme](https://university.pravinmishra.com?utm_source=github&utm_medium=readme)
- Discord Community: [https://discord.pravinmishra.com?utm_source=github&utm_medium=readme](https://discord.pravinmishra.com?utm_source=github&utm_medium=readme)
- Blog: [https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme](https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme)
- YouTube Playlist: [https://www.youtube.com/playlist?list=PLFeSNDtI4Cho](https://www.youtube.com/playlist?list=PLFeSNDtI4Cho)
- Pravin Mishra LinkedIn: [https://www.linkedin.com/in/pravin-mishra-aws-trainer/](https://www.linkedin.com/in/pravin-mishra-aws-trainer/)
- CloudAdvisory LinkedIn: [https://www.linkedin.com/company/thecloudadvisory/](https://www.linkedin.com/company/thecloudadvisory/)

---

*This submission is part of DevOps Micro Internship (DMI) — Agentic AI Track.*