# Assignment 4 — Gotto Job: Backlog Refinement & Sprint 1 in Jira

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this 90-minute, time-boxed exercise, you will act as a Scrum team — or run in Solo Mode, playing every role yourself — to turn the Gotto Job template into a value-ordered backlog, estimate the work in story points, plan Sprint 1, open the burndown chart, and ship one small UI-only increment (text, color, spacing, a label, or a CTA — no backend changes).

---

# Task 1 — Roles & Mode Setup (Team vs Solo)

## Goal

Choose Team Mode or Solo Mode, and document how each Scrum role (Product Owner, Scrum Master, Dev Lead, DevOps Lead) was handled.

### Evidence

#### Screenshot 1 — Jira "Create project" screen, or the project sidebar after creation

![screenshot_1](screenshots/assignment4-ss1.jpg)

---

### Notes

Write one line for each role: PO (what you prioritized), SM (how you ensured process), Dev Lead (what you built), DevOps Lead (how you shipped).

PO: Prioritized the highest-value UI improvements that make the Gotto Job experience clearer and more user-friendly.
SM: Ensured the Scrum process was followed by refining the backlog, estimating stories, planning Sprint 1, and tracking progress through the burndown.
Dev Lead: Built and verified a small UI-only improvement involving text, color, spacing, a label, or CTA.
DevOps Lead: Shipped the UI change through the deployment pipeline, verified the live increment, and documented the deployment outcome.

---

# Task 2 — Create the Jira Project (Team-managed → Scrum)

## Goal

Create a Team-managed Scrum project named `Gotto Job – Team <#>` (Team Mode) or `Gotto Job – <YourName>` (Solo Mode).

### Evidence

#### Screenshot 2 — Project created page showing the project name and key

![screenshot_2](screenshots/assignment4-ss1.jpg)

---

# Task 3 — Create the Epic

## Goal

Create the Epic `Improve Gotto Job UI discoverability & trust` to group the UI improvement initiative.

### Evidence

#### Screenshot 3 — Backlog showing the Epic panel with the Epic visible

![screenshot_3](screenshots/assignment4-ss3.jpg)

---

# Task 4 — Seed the Product Backlog (6–8 Stories + Fibonacci Points + Ranking)

## Goal

Create at least six Stories under the Epic, estimate each with 1, 2, or 3 story points, and rank them by value.

### Evidence

#### Screenshot 4 — Backlog showing the Epic and at least six Stories under it

![screenshot_4](screenshots/assignment4-ss4.jpg)

---

#### Screenshot 5 — One Story opened showing its Story Points and acceptance criteria filled in

![screenshot_5](screenshots/assignment4-ss4.1.jpg)

---

# Task 5 — Planning Poker (Estimate + Debate Notes)

## Goal

Confirm the Story Points (1, 2, or 3) for each Story and record brief reasoning for each estimate.

### Evidence

#### Screenshot 6 — Backlog showing Story Points visible, or two or three Stories opened showing their points

![screenshot_6](screenshots/assignment4-ss5.jpg)

---

### Notes

For each story, explain in one or two lines why it is a 1, 2, or 3 (mention any debate, even in Solo Mode).


Hero tagline clarity - (1pt) Very small change: replace/add one headline with minimal implementation and testing. In Solo Mode, there was little debate because the scope is straightforward.

Primary CTA color - (1pt) A simple styling change affecting an existing button, with only hover and contrast verification required. The main debate was whether site-wide styling might increase the effort.

Job card typography - (2pts) Requires identifying the correct job-card styles and adjusting typography while checking the Job Listing page across screen sizes. In Solo Mode, this was considered more than a one-line change because of visual verification.

Remote badge (UI-only) - (2pts) Requires conditional UI logic to display the badge only on cards marked REMOTE, plus styling and testing. The debate was whether the existing card data already supported the REMOTE flag.

Posted on <date> text - (1pt) Small UI addition, especially since static dates are acceptable, requiring minimal implementation and verification. In Solo Mode, there was little debate.

Advanced search labels - (2pts)  Involves updating multiple form labels/placeholders and checking alignment and usability. The debate was whether the changes were purely text updates or required additional form-layout adjustments.

Job detail Apply Now CTA - (1pt)  A small UI addition with a simple mailto: or # destination, followed by keyboard and click testing. The main debate was choosing the safest/simple link behavior.

Footer trust links - (1pt) Requires adding two links and confirming their visibility, keyboard accessibility, and routing. In Solo Mode, the effort was judged low because the change is limited to the footer UI.

---

# Task 6 — Sprint Planning: Create Sprint 1 + Sprint Goal + Scope

## Goal

Create Sprint 1, move three or four Stories into it (approximately 3–6 points), set the Sprint Goal, and break each selected Story into Build, Verify, Deploy, and Screenshot Sub-tasks.

### Evidence

#### Screenshot 7 — Sprint 1 with the selected Stories inside it

![screenshot_7](screenshots/assignment4-ss6.jpg)

---

#### Screenshot 8 — One Story showing the Sub-tasks created

![screenshot_7](screenshots/assignment4-ss7.jpg)

---

# Task 7 — Reports: Open Burndown Chart

## Goal

Open the Burndown Chart and confirm it exists for Sprint 1. It is acceptable if the chart is not yet populated.

### Evidence

#### Screenshot 9 — Burndown Chart page opened, even if empty

![screenshot_8](screenshots/assignment4-ss8.jpg)

---

# Task 8 — Ship One Small Increment (Build + Deploy + Proof)

## Goal

Implement one small UI-only Story from Sprint 1, commit it, deploy it live, and move the Story and its Sub-tasks to Done in Jira.

### Evidence

#### Screenshot 10 — Jira board showing the Story moved to Done

![screenshot_8](screenshots/assignment4-ss9.jpg)

---

#### Screenshot 11 — Git commit output

![screenshot_8](screenshots/assignment4-ss10.jpg)
---

#### Screenshot 12 — Live URL in the browser showing the UI change, with the URL visible

![screenshot_8](screenshots/assignment4-ss11.jpg)

---

# Task 9 — Retro Notes (Scrum Pillar + Value)

## Goal

Add a retro comment covering what went well, what to improve, one Scrum pillar observed (Transparency, Inspection, or Adaptation), and one Scrum value (Openness, Focus, Commitment, Courage, or Respect).

### Evidence

#### Screenshot 13 — Jira retro comment visible

![screenshot_13](screenshots/assignment4-ss12.jpg)

---

# Task 10 — LinkedIn Post (Mandatory)

## Goal

Publish a LinkedIn post about what you delivered, including your live URL, three to five lines on what you did and learned, and one screenshot (Burndown Chart, Sprint board, or the live UI change).

## Evidence

#### LinkedIn Post URL

Paste your LinkedIn post URL here:

https://www.linkedin.com/posts/timothy-olubiyi-05b9ba123_agile-scrum-jira-share-7492576124263223296-vhaw/?utm_source=share&utm_medium=member_desktop&rcm=ACoAAB6VGscB2AplIT7PcrwZvA0ECup4mNaUoIw

---

#### Screenshot 14 — Published LinkedIn post

![screenshot_14](screenshots/assignment4-ss14.jpg)

---

# Submission Instructions

- Add all 14 required screenshots
- Full name must be visible in required screenshots
- Do not expose sensitive information (keys, passwords, account IDs)

---

# Completion Checklist

- [✅] Task 1: Team Mode or Solo Mode selected and all four roles documented (Screenshot 1 & Notes)
- [✅] Task 2: Team-managed Scrum project created with the required name (Screenshot 2)
- [✅] Task 3: UI improvement Epic created (Screenshot 3)
- [✅] Task 4: 6–8 Stories added under the Epic and ranked by value (Screenshots 4 & 5)
- [✅] Task 5: Story Points set (1, 2, or 3) with reasoning recorded (Screenshot 6 & Notes)
- [✅] Task 6: Sprint 1 created with Sprint Goal, 3–4 Stories, and Sub-tasks (Screenshots 7 & 8)
- [✅] Task 7: Burndown Chart opened (Screenshot 9)
- [✅] Task 8: One UI-only increment implemented, committed, deployed, and verified (Screenshots 10–12)
- [✅] Task 9: Retro comment with one Scrum pillar and one Scrum value (Screenshot 13)
- [✅] Task 10: Mandatory LinkedIn post published with the live URL, backlog refinement, Sprint planning, one shipped increment, proof, and Screenshot 14
- [✅] Full Name visible in required screenshots
- [✅] No sensitive data exposed

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
