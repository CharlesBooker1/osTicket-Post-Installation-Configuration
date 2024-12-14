<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Post-Install Configuration</h1>
This guide walks you through the post-install configuration of the open-source help desk system, osTicket. This assumes you have already completed the installation process, set up login credentials, and performed any necessary clean-up following the osTicket Prerequisites and Installation guide.

---

## Environments and Technologies Used
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket

## Operating Systems Used
- Windows 10

---

## Post-Install Configuration Objectives
1. Get familiar with the osTicket user interface (UI).
2. Configure roles, departments, and teams.
3. Learn how to create tickets.
4. Add agents and users.
5. Set up Service Level Agreements (SLA Plans).
6. Configure help topics.

---

## Configuration Steps

### 1. Configuring Roles, Departments, and Teams

#### Roles
Roles determine permissions for agents within assigned departments.

- Navigate to the **Admin Panel** > **Agents** > **Roles**.
- Click **Add New Role**.
- Provide a name, such as `Supreme Admin`, and configure permissions under **Tickets**, **Tasks**, and **Knowledgebase** by selecting all options.
- Save the role by clicking **Add Role**.

#### Departments
Departments route and prioritize tickets based on their nature.

- In the **Admin Panel**, go to **Agents** > **Departments**.
- Click **Add New Department**.
- Name the department, e.g., `System Administrators`, and leave other settings as default.
- Click **Create Dept** to save.

#### Teams
Teams allow collaboration across departments for handling specific tasks.

- Navigate to **Admin Panel** > **Agents** > **Teams**.
- Click **Add New Team**.
- Name the team, e.g., `Level II Support`, and save by clicking **Create Team**.

---

### 2. Allowing Anyone to Create Tickets

To allow ticket creation without registration:

- Go to **Admin Panel** > **Settings** > **Users**.
- Ensure the option **Registration Required** is unchecked.

---

### 3. Adding Agents and Users

#### Adding Agents
Agents handle ticket responses and updates.

- Navigate to **Admin Panel** > **Agents** > **Add New Agent**.
- Fill in agent details (e.g., name: Jane Doe, username: `jane.doe`, email: `jane.doe@osticket.com`).
- Set a password and disable password reset options for simplicity.
- Assign a primary department under the **Access** tab. Optionally, assign the agent to teams.

#### Adding Users
Users create and track tickets.

- Navigate to **Agent Panel** > **Users** > **Add User**.
- Fill in user details (e.g., name: Ken, email: `ken@osticket.com`).

---

### 4. Adding SLA Plans

Service Level Agreements (SLAs) define ticket resolution timelines.

- Go to **Admin Panel** > **Manage** > **SLA** > **Add New SLA Plan**.
- Create SLA plans based on priority:
  - **SEV-A**: 1-hour grace period, 24/7 schedule.
  - **SEV-B**: 4-hour grace period, 24/7 schedule.
  - **SEV-C**: 8-hour grace period, business hours schedule.
- Save each plan using **Add Plan**.

---

### 5. Configuring Help Topics

Help topics streamline ticket submission and routing.

- Navigate to **Admin Panel** > **Manage** > **Help Topics** > **Add New Help Topic**.
- Create topics such as:
  - Business Critical Outage
  - Personal Computer Issues
  - Equipment Request
  - Password Reset
- Save each topic using **Add Topic**.

---

### Further Reading
For more detailed documentation on osTicket, visit the [official documentation](https://docs.osticket.com/en/latest/index.html).

---
