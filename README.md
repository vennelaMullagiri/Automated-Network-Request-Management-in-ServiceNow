# Automated Network Request Management in ServiceNow

This project implements an end-to-end automated workflow in ServiceNow to handle network-related service requests. It leverages ServiceNow’s Service Catalog, Flow Designer, custom tables and approvals to streamline how network requests are captured, routed and tracked.

---

## 📋 Overview

Employees often need to raise network-related service requests (e.g., device setup, connectivity changes, new network resources). Traditionally these requests were handled manually, leading to delays and inconsistencies.  

This project creates a **self-service network request form** and an **automated workflow** that:

- Collects all required information at the time of request.
- Automatically validates and routes requests.
- Handles approvals and notifications without manual effort.
- Provides a single place to track the status of each request.

---

## 🎯 Objectives

- Provide a user-friendly Service Catalog item for network requests.
- Automate record creation, assignment, notification and approval steps.
- Reduce manual effort and improve turnaround time.
- Maintain a clear audit trail of every request.

---

## ✨ Key Features

- **Service Catalog Item**  
  A “Network Request” catalog form with variable sets to collect:
  - Requester Information (Name, Email ID, Department)
  - Network Details (Location, Device Type, Justification, Priority)

- **Dynamic UI Policies**  
  Show/hide and make fields mandatory based on user selections (e.g., additional details field appears only when device type = Others).

- **Custom Table**  
  A dedicated `u_network_database_table` for storing all incoming requests, with fields such as:
  - Customer Address, Request Number, Requested For, Assignment Group, Work Status, Device Details, Updates, Assigned To, Date of Enquiry, Customer Document.

- **Relationships & Related Lists**  
  Linked the custom table with the Approval table to display related approvals on the record form.

- **Flow Designer Automation**  
  - Retrieves catalog variables.
  - Creates a record in the custom table.
  - Sends dynamic email notifications to requester and approver.
  - Triggers an “Ask for Approval” action.
  - Updates record sta
