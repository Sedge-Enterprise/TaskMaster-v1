# Project Tracking Platform

[![Power Platform](https://img.shields.io/badge/Microsoft-Power%20Platform-blue)](https://powerplatform.microsoft.com/)
[![SharePoint](https://img.shields.io/badge/Microsoft-SharePoint-green)](https://www.microsoft.com/en-us/microsoft-365/sharepoint/collaboration)
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](LICENSE)

---

## Overview
  TaskMaster is a low-code project tracking platform built on the **Microsoft Power Platform**.  
It enables teams to manage tasks, monitor progress, and automate notifications using **Power Apps**, **Power Automate**, and **SharePoint**.

---

## Quick Start
Launch the app directly in your browser:

[**Open Sedge Power App**](https://apps.powerapps.com/play/e/default-ea5219a2-9f77-49d9-a241-c7547b01585c/a/813fb2c2-9391-4f11-b20e-d2ed80d68f51?tenantId=ea5219a2-9f77-49d9-a241-c7547b01585c&hint=0b38990b-c7dd-444a-a891-ec8f31fa2461&sourcetime=1760702750545)

---

## Features

### Power App
- Create, edit, and track tasks
- Improved UI/UX for easier navigation
- Load specific tasks automatically via query parameters (`Param("ID")`)
- Direct links in notification emails to open tasks in the app
- [Download Power App `.msapp`](./PowerApps/SedgeApp.msapp) *(optional)*

### Power Automate Flows
1. **Task Completed Notification**
   - Trigger: When a task is modified
   - Sends an email to the assigned user when a task is marked as **Completed**
   - [View Flow JSON](./PowerAutomate/TaskCompletedNotification.json)

2. **Task Created or Updated Notification**
   - Trigger: When a task is created or modified
   - Conditional logic:
     - If newly created → send "New Task Assigned" email
     - If updated → send "Task Updated" email
   - Corrected expressions:
     - AssignedTo Email: `triggerOutputs()?['body/AssignedTo']?['Email']`
     - AssignedTo DisplayName: `triggerOutputs()?['body/AssignedTo']?['DisplayName']`
   - Optional: Sends notifications only if key fields (Status, Progress, AssignedTo) change
   - [View Flow JSON](./PowerAutomate/TaskCreatedOrUpdatedNotification.json)

---

## Getting Started

### Prerequisites
- Microsoft Power Apps access
- Power Automate access
- SharePoint list with **Tasks** schema

### Setup
1. Import the **Power Automate flow JSON files** from `/PowerAutomate`.
2. Import the **Power Apps `.msapp` file** from `/PowerApps` (optional if using Quick Start link).
3. Publish the app to make it available for users.
4. Update flow links if needed.

---

## Usage
- Users create or edit tasks in Power Apps.
- Assigned users receive automated emails for:
  - New tasks
  - Task updates
  - Task completion
- Email notifications contain a **direct link** to the task in the app.

---

---

## Version Control
- Power Apps and Flows maintain **version history** for rollback
- Always **save and publish** the latest app version before sharing with users

---

## Future Features
Planned updates and enhancements for Sedge:

### 1️⃣ Advanced Task Management
- Subtasks & dependencies
- Recurring tasks support

### 2️⃣ Enhanced Notifications
- Customizable email templates
- Push notifications via Teams or mobile

### 3️⃣ Analytics & Reporting
- Dashboard views with visual charts
- Export reports (PDF/Excel) for stakeholders

### 4️⃣ Collaboration Features
- In-app comments & notes
- File attachments per task

### 5️⃣ Integration Enhancements
- Connect with Outlook, Teams, or other project management apps
- Power BI dashboard integration for real-time analytics

### 6️⃣ App Usability Improvements
- Mobile optimization for better on-the-go use
- Dark mode & theme customization

---

## Collaborators
- **Khutjo Mosatjana Maria Satekge** – Project Owner / Power Platform Developer
- [Add other collaborators here as needed]

---

## Contact


---

*End of README*

## Repository Structure
