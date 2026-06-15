# CMDB VDI Asset Lifecycle Tracking & Automation Pipeline

## Project Overview
An automated lifecycle tracking pipeline built within ServiceNow Workflow Studio to streamline Virtual Desktop Infrastructure (VDI) provisioning. The flow triggers automatically upon the successful completion of an IT Service Catalog task, programmatically creates a configuration item (CI) record inside the CMDB, and dynamically dispatches a rich-text deployment notification to the end-user.

## Key Features & Automated Workflow
1. **Event-Driven Trigger:** Listens for `Catalog Task [sc_task]` updates where the state shifts to `Closed Complete` and the short description matches provisioning criteria.
2. **Programmatic Asset Creation:** Auto-generates a computer record inside the `Computer [cmdb_ci_computer]` table, establishing a data-driven naming convention (`VDI-{{username}}`).
3. **Dynamic Dot-Walking Notification:** Extracts the requester's target email directly via data stream dot-walking (`Catalog Task -> Requested For -> Email`) and triggers a stylized rich-text onboarding email detailing their new digital workspace credentials.

## Technical Skills Demonstrated
* **ITSM & ITOM Alignment:** Automated bridge between Service Catalog fulfilment and CMDB asset configuration.
* **ServiceNow Workflow Studio / Flow Designer:** Advanced data pill mapping, conditional flow triggers, and core action formatting.
* **Data Architecture:** Dot-walking across related tables (`sc_task`, `sys_user`, `cmdb_ci_computer`).

## Implementation Walkthrough
### Step 1: Notification Action Staging
*Staging the ServiceNow Core email action directly into the lifecycle draft canvas.*
<img width="1920" height="939" alt="01_Notification_Action_Staging" src="https://github.com/user-attachments/assets/34b79a60-0adb-44ec-bd8a-12dd6776074e" />


### Step 2: Target Record Mapping
*Mapping the newly engineered CMDB Computer Record dynamically into the notification targeting engine.*
<img width="1920" height="944" alt="02_Target_Record_Mapped" src="https://github.com/user-attachments/assets/daa50951-1bfe-4ddc-bce2-0b297b32ab0b" />


### Step 3: Recipient Routing via Dot-Walking
*Extracting the user's live profile email address dynamically across relational tables.*
<img width="1920" height="947" alt="03_Recipient_Email_Mapped" src="https://github.com/user-attachments/assets/033c0b45-9f7a-4549-807b-830984b532ff" />


### Step 4: Subject Line Engineering
*Combining static professional text with dynamic string tokens for a clear user experience.*
<img width="1920" height="943" alt="04_Email_Subject_Configured" src="https://github.com/user-attachments/assets/fdfa7d26-333f-4a6e-ba65-5d21a2770b54" />


### Step 5: Fully Automated Engine Activation
*The finalized, activated, and published end-to-end IT automation pipeline.*
<img width="1920" height="944" alt="05_Notification_Engine_Complete" src="https://github.com/user-attachments/assets/72c488b6-dabe-4809-a32f-563c5b440214" />


## What I Learned
* **Table Relationships:** Learned how ServiceNow connects different tables, using "dot-walking" to pull a user's email into an automated process.
* **Platform Workflow:** Understood how to safely copy, edit, and publish draft flows without breaking active system processes.
* **Problem Solving:** Learned how to troubleshoot layout restrictions and find workarounds using different menus in Workflow Studio.

## Corporate Application
In a real company, this stops the Help Desk from wasting time. Instead of an agent manually creating an asset record and typing out a welcome email every time someone gets a virtual desktop, the system does it instantly. This prevents manual typos, keeps the asset inventory accurate, and lets the Help Desk focus on fixing actual technical problems.
