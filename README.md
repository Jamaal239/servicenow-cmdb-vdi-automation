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
* **Relational Data Mapping:** Gained a solid understanding of how ServiceNow uses "dot-walking" to pull data from a user's profile across completely different tables.
* **Platform Security & Workflow Drafts:** Learned how ServiceNow manages version control through checking out flows, modifying drafts safely, and publishing them to prevent live errors.
* **Troubleshooting Automation Blocks:** Developed the skill to identify read-only canvas restrictions and resolve setup dead-ends independently by utilizing system duplication tools.

## Corporate Application
In an enterprise environment, this automation solves a major operational bottleneck. Instead of a tier-1 help desk agent spending 10 minutes manually typing out emails and creating CMDB records for every single employee who gets a new VDI workspace, this pipeline handles it instantly. This eliminates manual copy-paste data errors, keeps the asset database completely accurate in real-time, and lets the help desk focus on closing technical support tickets.

