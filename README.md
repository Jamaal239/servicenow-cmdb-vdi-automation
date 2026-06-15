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
![Staging](01_Notification_Action_Staging.png)

### Step 2: Target Record Mapping
*Mapping the newly engineered CMDB Computer Record dynamically into the notification targeting engine.*
![Target Mapping](02_Target_Record_Mapped.png)

### Step 3: Recipient Routing via Dot-Walking
*Extracting the user's live profile email address dynamically across relational tables.*
![Recipient Mapping](03_Recipient_Email_Mapped.png)

### Step 4: Subject Line Engineering
*Combining static professional text with dynamic string tokens for a clear user experience.*
![Subject Config](04_Email_Subject_Configured.png)

### Step 5: Fully Automated Engine Activation
*The finalized, activated, and published end-to-end IT automation pipeline.*
![Pipeline Complete](05_Notification_Engine_Complete.png)
