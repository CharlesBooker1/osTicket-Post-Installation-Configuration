<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket. This tutorial assumes that you have completed the installation of osTicket lab.
</p>
osTicket official online documentation: https://docs.osticket.com/en/latest/index.html
</p>


<h3>Environments and Technologies</h3>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket

<h3>Operating Systems</h3>

- Windows 10</b>

</ul>


<h3>Post-Install Configuration Objectives</h3>
<ol>
  <li>Familiarity with the UI of osTicket</li>
  <li>Creating and Configuring Roles</li>
  <li>Creation of Tickets</li>
  <li>Creating Agents and Users</li>
  <li>Setting up Service Level Agreements (SLA Plans) in ticketing system</li>
  <li>Configuring Help Topics</li>
</ol>


<h3>Configuration Steps</h3>


<h3>Configuring Roles, Departments, & Teams</h3>

<p>

There are two panels when navigating osTicket: Agent Panel and Admin Panel. You will know which panel you're on if the opposite panel is displayed on the top right of the UI next to your user login name. For example the user "Eric" is on the Agent Panel
<p>
<img src="https://i.imgur.com/QNC8AoF.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p>
<b>Configure Roles</b>
</li>
<p>
Roles are the permissions granted to Agents per Department that they have access to. Access the Admin Panel, go to Agents tab and click on Roles, then click on Add New Role
<p>
Note: osTicket creates Four Roles - All Access, Expanded Access, Limited Access, and View Only by default.
<img src="https://i.imgur.com/U8t4YwD.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p>
Name the role Supreme Admin, then click on the permissions tab; in this tab you can assign specific permissions to this role. For the Supreme Admin role, check every box under the Tickets, Tasks, and Knowledgebase tabs. Click on Add Role to finish this process
<p>
<img src="https://i.imgur.com/CMXdTZM.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p/>
<b>Configure Departments</b>
</li>
<p>

Departments are used to route and resolve tickets based on their importance or instructions. On the Agents tab, click on Departments and click on Add New Department.

Note: osTicket creates two departments (Maintenance and Support) by default
<img src="https://i.imgur.com/zQLYDMS.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name the Department System Administrators, leave all other options as default, then Create Dept to create department
<p>
<img src="https://i.imgur.com/zCcwT0A.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
<b>Configure Teams</b>
</li>
<p>

The Teams section is used to organize Agents from different departments in osTicket to handle specific issues and supersede Agents and their Departments' parameter rules. Access Admin Panel, in Agents tab, click on Teams and Add New Team.
<p>
Note: osTicket creates a team - Level I Support by default
<p>
<img src="https://i.imgur.com/oWvLUlA.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p>
Add New Team, name it Level II Support, then click on Create Team
<p>
<img src="https://i.imgur.com/Efmf1ih.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
</p>

</br>

<h3>Allowing anyone to create Tickets</h3>

<p>
  
<p/>
<p>
Access the Admin Panel, go to the Settings tab and click on Users, make sure Registration Required is unchecked. This will allow the user to create tickets anonymously.
<p/>
<p>
<img src="https://i.imgur.com/OEtYw31.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p/>
<p>
</ul>
  
</p>

</br>

<h3>Configure Agents and Users</h3>

<p>
  
<p>

Agents are given the access to the help desk in osTicket to respond, resolve, and update the status of tickets. In the Admin Panel, go to the agents tab and click on Add New Agent.
<p>
For this tutorial, you will create two new agents Jane and John. Its advised to have a notepad to catalog information as you enter the credentials. You will set their user names as [name.doe] and both of their passwords as Password1 for convenience.
<p>
Fill in the Agent's basic info and set the Agent's email address as [name].doe@osticket.com and Set Password
</p>
<img src="https://i.imgur.com/JHdJS7c.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p>
Set the Agent's password to Password1 and uncheck the boxes to prevent the Agent from needing to reset password or change password after login
<p>
Go to the access tab, to set the agents Primary Department. Extended access can be added to the agent in order to access additional departments. It is optional to assign the agent to a team in the Teams tab.
</p>
<p>
<img src="https://i.imgur.com/0g0BhVb.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
</p>
<p>
As an Example, for the agent Jane Doe in the access tab we can assign for her in Primary Department: System Administrators. For role: Supreme Admin. In Extended Access: Support. For Role select Supreme Admin. We can assign her to Level II Support in Teams.
<p/>
Example 2: for the agent John Doe in the access tab we can assign for him in Primary Department: Support. For role: View Only. In Extended Access assign him to Support. Leave everything else as default.
</p>
Users are creators and owners of tickets and by using osTicket they are able to track the status of their tickets. In the Agent Panel, go to the Users tab and click on Add User. In this tutorial you will be creating two new users Ken and Karen and setting up usernames, emails, and passwords similiar to our Agents.
</p>
<p>
<img src="https://i.imgur.com/Y6JgfEx.png" height="55%" width="55%" alt="Disk Sanitization Steps"/>
</p>
<p>
</ul>
  
</p>

</br>

<h3>Configure SLA Plans</h3>

<p>


<p>
Service Level Agreements provide a length of time for the Administrator when the tickets are expected to be closed. They can also be designated to specific Departments or Help Topics. In the Admin Panel, go to the Manage tab and drop down to SLA then click on Add New SLA Plan.
</p>
osTicket by default has the SLA Plan Default SLA. You will create three SLA Plans each with their own length of time for different kinds of importance of the ticket, from highest priority to lowest priority
<p/>
<p>
1.) SEV-A with 1 hour Grace Period, 24/7 schedule, suitable for tickets that are business critical
<p>
2.) SEV-B with 4 hour Grace Period, 24/7 schedule, suitable for tickets affecting employees such as troubleshooting or PC problems
<p>
3.) SEV-C with 8 hour Grace Period, Business Hours schedule, suitable for tickets requesting new equipment
<p>
Example of creating an SLA Plan, click on Add Plan to create the SLA Plan
<p>
<img src="https://i.imgur.com/40oT52p.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p/>
<p>
</ul>
  
</p>

</br>

<h3>Configure Help Topics</h3>

<p>
  

<p>
Help Topics are helpful to streamline the ticket entry experience for the user by helping them specify their ticket info and also determine what department the ticket should go to. In the Admin Panel, go to the Manage tab and click on Add New Topic.
<p>
Note: osTicket creates four Help Topics. Feedback, General Inquiry, Report a Problem, and Report a Problem / Access Issue be default.
<p>
<img src="https://i.imgur.com/tjaOwio.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p>
You will create four different Help Topics based on the potential severity a ticket could have, from lowest to highest priority
<p>
1.) Business Critical Outage
<p>
2.) Personal Computer Issues
<p>
3.) Equipment Reset
<p>
4.) Password Reset
</p>
Example of Adding a New Help Topic
<p></p>
<img src="https://i.imgur.com/S8013HP.png" height="65%" width="65%" alt="Disk Sanitization Steps"/>
<p>
<p/>
This is the conclusion of the lab
