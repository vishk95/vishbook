---
title: "Admin topics"
---

# Admin topics

For a **Salesforce Senior Developer / Tech Lead**, you don’t need deep admin operational knowledge, but you **must understand the architecture and configuration layer thoroughly** because most real-world implementations combine **code + configuration**.

Below is a **concise but complete list of Admin topics a senior Salesforce developer should know**.

**1. Data Model & Object Architecture**

A senior developer must understand how to design scalable Salesforce data models.

Topics:

- **Standard vs Custom Objects**
- **Fields and Field Types**
- **External Objects**
- **Custom Metadata Types**
- **Custom Settings (Hierarchy & List)**
- **Master-Detail vs Lookup Relationships**
- **Junction Objects**
- **Roll-Up Summary Fields**
- **Schema Builder**
- **Big Objects (conceptual)**
- **Polymorphic relationships (****WhoId****,** **WhatId****)**

Key Skills:

- Designing scalable data models
- Avoiding data skew
- Understanding record ownership patterns

**2. Security Model**

This is **critical for developers** because all Apex/LWC must respect security.

Topics:

- **Organization-Wide Defaults (OWD)**
- **Role Hierarchy**
- **Sharing Rules**
- **Manual Sharing**
- **Apex Managed Sharing**
- **Territory Management (conceptual)**

Access Control:

- **Profiles**
- **Permission Sets**
- **Permission Set Groups**
- **Muting Permission Sets**

Field/Object Security:

- **Field Level Security**
- **Object Permissions**
- **CRUD/FLS enforcement**

Security APIs:

- with sharing
- without sharing
- stripInaccessible
- Security.stripInaccessible()

**3. Automation Tools**

Developers must know **when NOT to write code**.

Topics:

- **Record Triggered Flows**
- **Scheduled Flows**
- **Autolaunched** **Flows**
- **Screen Flows**
- **Flow Orchestration (basic)**

Legacy Tools (for maintenance):

- Workflow Rules
- Process Builder
- Approval Processes

Key Developer Skill:
Choosing between:

- **Flow vs Apex**
- **Flow + Apex hybrid architectures**

**4. User Interface Configuration**

Even developers often need to modify the UI layer.

Topics:

- **Lightning App Builder**
- **Dynamic Forms**
- **Dynamic Actions**
- **Page Layouts**
- **Compact Layouts**
- **Lightning Pages**

Navigation:

- Apps
- Tabs
- Utility Bars

**5. Validation & Data Integrity**

Important for enforcing business logic without code.

Topics:

- **Validation Rules**
- **Duplicate Rules**
- **Matching Rules**
- **Required Fields**
- **Field Dependencies**
- **Default Values**
- **Formula Fields**

Developer Use Case:
Ensure Apex respects **validation logic and business constraints**.

**6. Reports & Analytics**

Senior developers should know how data is consumed.

Topics:

- **Report Types**
- **Custom Report Types**
- **Report Filters**
- **Joined Reports**
- **Summary Reports**
- **Dashboards**
- **Dashboard Filters**
- **Bucket Fields**

Why developers need this:

- Design objects for **reportability**
- Avoid anti-patterns that break reporting

**7. Data Management**

Important for integrations, migrations, and maintenance.

Topics:

- **Data Import Wizard**
- **Data Loader**
- **Mass Update Tools**
- **Duplicate Management**
- **Data Export**
- **External IDs**
- **Upsert** **Operations**

Architectural concerns:

- Data skew
- Lookup skew
- Large Data Volumes (LDV)

**8. Email & Notifications**

Common requirement in many systems.

Topics:

- **Email Templates**
- **Lightning Email Templates**
- **Workflow Email Alerts**
- **Send Email in Flow**
- **Custom Notifications**

**9. Sandboxes & Environments**

Important for development lifecycle.

Topics:

- **Developer Sandbox**
- **Developer Pro**
- **Partial Copy**
- **Full Sandbox**

Key Knowledge:

- Sandbox refresh strategies
- Data masking
- Seeding sandboxes

**10. Deployment Basics**

Even though DevOps tools exist, developers must understand metadata deployment.

Topics:

- **Change Sets**
- **Deployment Status**
- **Deployment Errors**
- **Metadata Types**
- **Outbound Change Sets**

Also understand:

- Metadata dependencies
- Deployment order

**11. AppExchange & Packages**

Developers should understand how packaged apps behave.

Topics:

- **Managed Packages**
- **Unlocked Packages**
- **Namespace**
- **Package Versioning**
- **Upgrade impacts**

**12. Activity & Collaboration Features**

Many enterprise implementations use these.

Topics:

- **Tasks & Events**
- **Activity Timeline**
- **Chatter**
- **Feeds**
- **Files vs Attachments**

**13. Search & Productivity Features**

Important for user experience.

Topics:

- **Global Search**
- **Search Layouts**
- **Search** **Filters**
- **List Views**
- **Kanban Views**

**14. Platform Limits & Governance**

A senior developer must understand platform constraints.

Topics:

- Storage Limits
- API Limits
- Data Storage
- File Storage
- Concurrent Apex limits

**15. Monitoring & Debugging Tools**

Important for production support.

Topics:

- **Debug Logs**
- **Event Monitoring (basic)**
- **Login History**
- **System Overview**
- **Health Check**

**Bonus: What distinguishes a Senior Developer vs Regular Developer**

Senior developers should additionally understand:

- **Flow + Apex architecture**
- **Declarative vs programmatic tradeoffs**
- **Data model scalability**
- **Security architecture**
- **Admin–developer collaboration**
- **Production troubleshooting**
