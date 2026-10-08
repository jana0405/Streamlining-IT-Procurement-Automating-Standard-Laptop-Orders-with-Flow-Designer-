# Streamlining IT Procurement: Automating Standard Laptop Orders with Flow Designer

A ServiceNow project that automates the handling of standard laptop orders. When a Standard Laptop request is raised from the Service Catalog, a Flow Designer flow creates a Catalog Task and assigns it to the **Hardware** group for configuration.

## Problem Statement

The IT procurement process lacks automation. Configuring standard laptops is manual and prone to oversight or delay, which frustrates users and wastes IT resources.

## Objectives

1. Give users a seamless experience with timely laptop configuration.
2. Reduce manual intervention and errors in procurement.
3. Improve resource use in the IT department by optimising task allocation.
4. Improve overall efficiency of IT procurement operations.

## Solution Overview

| Component | Detail |
|---|---|
| Platform | ServiceNow |
| Automation | Flow Designer, flow named **Standard laptop task** |
| Application scope / Run as | Global / System User |
| Trigger | Service Catalog |
| Action | Create Catalog Task (from the Requested Item record) |
| Task values | Short description and description: `Laptop need to Configured`; Approval: `Approved`; Assignment group: `Hardware` |
| Catalog item | Standard Laptop (Service Catalog > Hardware) |

## Implementation Steps

### Milestone 1: Flow
1. In ServiceNow, open **All > Flow Designer** (under Process Automation).
2. Click **New > Flow**. Name it `Standard laptop task`, set Application to Global and Run as to System User, then **Submit**.
3. **Add a trigger**, search for `Service Catalog`, select it and click **Done**.
4. Under Actions, **Add an action** and select **Create Catalog Task**.
5. Drag the **Requested Item** record into the Request Item field. The table is filled in as Catalog Task.
6. Set the short description, description, Assignment group (`Hardware`) and Approval (`Approved`), then click **Done**.
7. **Save**, then **Activate** and confirm.

### Milestone 2: Flow Assignment
1. Open **All > Maintain Items** and select the **Standard Laptop** record.
2. Go to **Process Engine**, remove any other automations and add the `Standard laptop task` flow.
3. Save the record.

### Milestone 3: Service Catalog (Order and Approval)
1. Open **Service Catalog > Hardware > Standard Laptop** and click **Order Now**.
2. Open the Request Number from the order status page.
3. In the **Approvers** section, right-click the record and choose **Approve**.
4. Open the **Requested Item**, then the record under **Catalog Tasks**.
5. Confirm the short description and Assignment group on the Catalog Task.

## Result

A Catalog Task (for example `SCTASK0010001`) is created automatically for the Requested Item, with the correct short description and assigned to the Hardware group, so laptops can be configured promptly on arrival.

## Project Documentation (Phase-wise)

| Phase | Contents |
|---|---|
| 1. Ideation | Problem statements, empathy map, brainstorming |
| 2. Requirement Analysis | Customer journey map, solution requirements, data flow diagram and user stories, technology stack |
| 3. Project Design | Problem-solution fit, proposed solution, solution architecture |
| 4. Project Planning | Product backlog, sprint schedule, velocity |
| 5. Project Development | Performance testing, UAT report |
| 6. Project Documentation | Final report |
| 7. Project Demonstration | Demo video and links |

## Links

- **Demo video:** https://drive.google.com/drive/folders/1C-KCuvhXJs8FTvE3_3Bh-Xcveqd9iXHz?usp=sharing
- **Repository:** https://github.com/jana0405/Streamlining-IT-Procurement-Automating-Standard-Laptop-Orders-with-Flow-Designer-

## Future Scope

- Notify the requester when configuration starts and finishes.
- Assign tasks to individual technicians by workload.
- Extend the flow to other catalog items (monitors, mobile devices).
- Add a dashboard and SLA tracking for configuration tasks.

## Team Details

**Team ID:** SWTID-2026-5416 | **Team Size:** 5

| Role | Name |
|---|---|
| Team Leader | Dineshkumar K |
| Team Member | Elavarasan S |
| Team Member | Gokul N |
| Team Member | Hariprasath M |
| Team Member | Janardhan S |
