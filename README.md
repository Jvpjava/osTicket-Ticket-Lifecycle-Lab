# osTicket Ticket Lifecycle Lab

<p align="center">
  <img src="images/Osticket Project Cover.png" width="900">
</p>

## Overview
This project documents a hands-on **osTicket help desk lab** built in a Windows domain environment.  
The goal was to simulate how support teams handle tickets from creation to closure while working with **Active Directory, domain-joined endpoints, user permissions, SLAs, departments, and ticket escalation**.

This lab shows how a help desk workflow operates in a structured IT environment and how different roles interact with the same ticket from end user to resolution.

---

## Project Goals
In this lab, I practiced how to:

<p align="center">
  <img src="images/AD and VB.png" width="900">
</p>

- Deploy and configure a new **Windows 10 virtual machine**
- Use **osTicket** as both an end user and a help desk agent
- Review and update ticket properties such as:
  - Priority
  - Department
  - SLA
  - Assigned technician
- Escalate tickets when access or department scope changes
- Resolve and close tickets while tracking the full ticket history

---

## Lab Environment
### Systems Used
- **Windows Server 2019 Domain Controller**
- **Windows 10 Enterprise virtual machines**
- **osTicket**
- **Active Directory Users and Computers**
- **VirtualBox**

<p align="center">
  <img src="images/1. Network Topology.png" width="900">
</p>

### URLs Used
- **Admin / Analyst Login:** `http://DC-2019/osTicket/scp/login.php`
- **End User Portal:** `http://DC-2019/osTicket`

---

## What I Built

### 1. Prepared the Help Desk Environment
I started by powering on the domain controller and signing into the help desk workstation. 

<p align="center"><img src="images/1. DC-2019 ON.png" width="700"></p>

Turned on Desktop1 windows machine with helpdesk1 credentials.
<p align="center"><img src="images/1. Login to helpdesk1 Domain.png" width="700"></p>
<p align="center"><img src="images/1. helpdesk1 System Settings.png" width="700"></p>

From there, I accessed the osTicket Login: `http://DC-2019/osTicket/scp/login.php`
<p align="center"><img src="images/2. osTicket Login.png" width="700"></p>

adjusted the department structure by making **SysAdmins** a top-level department and deleting the **Maintenance** department.
<p align="center"><img src="images/3. Delete Maintenance Department.png" width="700"></p>

### 2. Logged in as the End User
Sign into **Desktop2** using Karen’s domain account.  
From there, I accessed the osTicket end-user portal to submit tickets as if I were a real employee needing support.

<p align="center"><img src="images/9. Signin To Domain.png" width="700"></p>
<p align="center"><img src="images/9. Gethired-KarenV.png" width="700"></p>
<p align="center"><img src="images/9. KarenV in Windows Machine.png" width="700"></p>
---

## Ticket Scenarios Completed

### Ticket 1: Entire mobile/online banking system is down
As Karen, I created a ticket reporting a banking outage.

As a help desk agent, I reviewed the ticket and checked:

- Priority
- Department
- SLA
- Assigned technician

At first, the agent account did not have permission to fully manage the ticket.  
I logged in as an administrator and updated the agent’s access so the ticket could be worked correctly.

I then updated the ticket with:

- **SLA:** Sev-A (1 hour, 24/7)
- **Department:** Online Banking

The issue was escalated to system administration and assigned to Jane for completion.  
Jane reviewed the full ticket history, responded, resolved the issue, and closed the ticket.

### Ticket 2: Accounting department needs Adobe upgrade, broken
As Karen, I created another ticket for a software-related support issue.

As the help desk agent, I reviewed the same key ticket properties and then updated the ticket with:

- **SLA:** Sev-B (4 hours, 24/7)
- **Department:** Support

The ticket was then worked through to completion from the agent side.

### Ticket 3: CFO’s laptop will no longer turn on
This scenario simulated a hardware failure involving a high-value user device.

Again, I reviewed the ticket properties and assigned:

- **SLA:** Sev-B (4 hours, 24/7)
- **Department:** Support

I then worked the issue through the help desk workflow until it was resolved.

---

## Permission and Escalation Testing
One of the biggest things I practiced in this lab was how **permissions affect ticket visibility and control**.

I tested ticket access by:
- Assigning tickets to **SysAdmins**
- Observing how they became inaccessible from certain views
- Switching to the admin panel to grant the proper **view access**
- Returning to the agent panel to confirm what could and could not be modified

This helped show how role-based access affects ticket handling inside a real support platform.

---

## What This Project Demonstrates
This project highlights skills that are useful in help desk, desktop support, and junior system administration roles:

- Active Directory user creation
- Domain join process
- Workstation setup in a lab environment
- Ticket triage
- SLA assignment
- Department-based routing
- Permission troubleshooting
- Escalation workflow
- End-user communication
- Ticket resolution and closure

---

## Real-World Help Desk Takeaway
A key lesson from this lab is that tickets can come from many places in a real environment, including:

- Web portals
- Email
- Phone calls
- Chat tools
- In-person requests

Even if an issue is handled quickly, it should still be documented in the ticketing system.  
That creates accountability, improves reporting, and helps track support metrics over time.

Also, most ticketing platforms include email notifications, which means users are updated whenever a ticket changes and can continue the conversation through the system.

---

## Why I Built This
I created this project to strengthen my understanding of:

- IT support workflows
- User and device management
- Ticket lifecycle management
- Escalation and access control
- How enterprise support environments operate

This lab helped me connect technical administration tasks with the day-to-day work of a help desk team.

---

## Documentation Source
This README was built from my lab documentation, which included:
- osTicket login URLs
- Active Directory user creation
- VirtualBox workstation setup
- Domain join steps
- Ticket creation scenarios
- Agent access updates
- SLA and department assignment
- Ticket escalation and closure
