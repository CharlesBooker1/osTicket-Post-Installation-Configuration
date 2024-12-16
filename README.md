<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Post-Installation Setup</h1>
This guide walks you through the post-installation setup of the open-source ticketing system, osTicket. It assumes that you have already completed the installation, set up login credentials, and performed the necessary cleanup steps as described in the prior tutorial: <a href ="https://github.com/ColtonTrauCC/osticket-prereqs">"osTicket - Prerequisites and Installation"</a>.<br />

</br>

<h2>Technologies and Environments Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Internet Information Services (IIS)</li>
  <li>osTicket</li>
</ul>

</br>

<h2>Operating System Used</h2>
<ul>
  <li>Windows 10</li>
</ul>

</br>

<h2>Post-Installation Setup Goals</h2>
<ol>
  <li>Understanding the osTicket User Interface</li>
  <li>Creating and Managing Roles</li>
  <li>Creating Tickets</li>
  <li>Setting up Agents and Users</li>
  <li>Configuring Service Level Agreements (SLA)</li>
  <li>Customizing Help Topics</li>
</ol>

</br>

<h2>Configuration Steps</h2>

<h3>Setting up Roles, Departments, & Teams</h3>

<p>
  
<ul>
  <li><b>Note</b>: osTicket has two panels: the <b>Agent Panel</b> and the <b>Admin Panel</b>. You can identify which one you're on by checking for the name of the opposite panel in the top-right corner of the interface, next to your login name.</li>
  <ul>
    <li>For this example, the user "josh" is logged into the Agent Panel.</li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/6abb22de-3ec5-47a9-8efd-46caf9d1622f" height="80%" width="80%" alt="osTicket Panel Example"/></li>
  </ul>
  <li><b>Roles</b> determine what permissions Agents have in the Department they belong to.</li>
  <ul>
    <li>In the <b>Admin Panel</b>, navigate to the <b>Agents</b> tab, click on <b>Roles</b>, and select <b>Add New Role</b>.</li>
    <ul>
      <li><b>Note</b>: osTicket creates four default Roles (All Access, Expanded Access, Limited Access, and View Only).</li>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/6347ce31-f5f1-4078-b738-dc70dd037df6" alt="Add Role Example"/></li>
    </ul>
    <li>Name the role <b>Supreme Admin</b> and go to the <b>Permissions</b> tab to assign specific permissions. For our role, select every box under the <b>Tickets</b>, <b>Tasks</b>, and <b>Knowledgebase</b> sections. Click <b>Add Role</b> to finalize.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/306c368f-76fb-4b25-869b-d1a1f430ed76" height="80%" width="80%" alt="Set Role Permissions"/></li>
    </ul>
  </ul>

  <li><b>Departments</b> are essential for directing and resolving tickets based on their importance or assigned instructions.</li>
  <ul>
    <li>In the Agents tab, click on <b>Departments</b> and select <b>Add New Department</b>.</li>
    <ul>
      <li><b>Note</b>: Two default Departments are created by osTicket (Maintenance and Support).</li>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/2a449d47-9632-47ee-9606-65512e292a2e" height="80%" width="80%" alt="Add Department Example"/></li>
    </ul>
    <li>Name the Department <b>System Administrators</b> and click <b>Create Dept</b> to finish.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/700f78be-2640-4f34-85d6-0ab8ff6ae994" height="80%" width="80%" alt="Create Department Example"/></li>
    </ul>
  </ul>

  <li><b>Teams</b> allow you to group Agents from different Departments to handle specific issues, overriding individual Department rules.</li>
  <ul>
    <li>In the Agents tab, click on <b>Teams</b> and choose <b>Add New Team</b>.</li>
    <ul>
      <li><b>Note</b>: osTicket automatically creates a default Team (Level I Support).</li>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/5ede2f9c-91d5-4f9b-8199-99e8f0696e5c" height="80%" width="80%" alt="Add Team Example"/></li>
    </ul>
    <li>Name the Team <b>Level II Support</b> and click <b>Create Team</b> to complete the process.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/b9aa5ab2-2c41-4666-a4f2-6a0f3ff88bc1" height="80%" width="80%" alt="Set Up Team Example"/></li>
    </ul>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Allowing Ticket Creation by Anyone</h3>

<p>
  
<ul>
  <li>To permit anonymous ticket creation, go to the <b>Admin Panel</b>, select the <b>Settings</b> tab, and click on <b>Users</b>. Ensure that <b>Registration Required</b> is unchecked. This allows ticket creation without user registration.</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/97c51388-324a-42e0-a808-067de164c4b6" height="80%" width="80%" alt="Disable Registration Example"/></li>
  </ul>
</ul>
  
</p>

</br>

<h3>Creating Agents and Users</h3>

<p>
  
<ul>
  <li><b>Agents</b> have the permissions to access the help desk, respond to, and manage tickets.</li>
  
  <ul>
    <li>In the <b>Admin Panel</b>, go to the <b>Agents</b> tab and click <b>Add New Agent</b>.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/d66757f0-54d1-458f-8a2d-4f1890b2da1d" height="80%" width="80%" alt="Add Agent Example"/></li>
    </ul>
    <li>Create two Agents: <b>Jane</b> and <b>John</b>, using <b>[name].doe</b> as their usernames and <b>Password1</b> for the password (the same password as used in the installation tutorial).</li>
    <ul>
      <li>Enter the Agent's details, then set their email as <b>[name].doe@osticket.com</b> and click on <b>Set Password</b>.</li>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/06fbd1ca-9d97-4f4f-b866-9b304dbdeb57" height="80%" width="80%" alt="Set Agent Info Example"/></li>
    </ul>
    <li>Set their password to <b>Password1</b> and uncheck the boxes to avoid forcing the Agent to change their password after login.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/51953148-bddc-476c-9368-4b62f4bf3d42" height="80%" width="80%" alt="Set Agent Password Example"/></li>
    </ul>
    <li>Under the <b>Access</b> tab, set their <b>Primary Department</b> (this is required to create the Agent).</li>
    <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/c57bca22-2622-4f01-88eb-bd699d1f12de" height="80%" width="80%" alt="Set Agent Access Example"/></li>
    </ul>
  </ul>
  
  <li><b>Users</b> (or customers) are ticket creators who can track the status of their submissions.</li>
  
  <ul>
    <li>In the <b>Agent Panel</b>, go to the <b>Users</b> tab and select <b>Add User</b>.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/f08ec067-3a66-420e-bfaf-6a3003512bcb" height="80%" width="80%" alt="Add User Example"/></li>
    </ul>
    <li>Create two Users: <b>Ken</b> and <b>Karen</b>, following similar steps to creating Agents.</li>
    <ul>
      <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/8eadff14-b483-4781-9679-80b252a092c4" height="80%" width="80%" alt="Set User Example"/></li>
    </ul>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Adding SLA Plans</h3>

<p>
  
<ul>
  <li><b>Service Level Agreements</b> (SLAs) define the expected resolution time for tickets based on their priority.</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and click on <b>SLA</b>, then select <b>Add New SLA Plan</b>.</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/1ebc6fe9-aa95-4e52-9fd9-1ecd7724d3b9" height="80%" width="80%" alt="Add SLA Example"/></li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/cf8da66d-209b-40e6-a4f1-c99bbd102b3a" height="80%" width="80%" alt="SLA Plan Example"/></li>
  </ul>
  <li>We will create three SLA plans based on priority: SEV-A (1 hour grace), SEV-B (4 hours), and SEV-C (8 hours during business hours).</li>
  <li>Example: To create SEV-A, click <b>Add Plan</b>.</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/ee7d6fbb-f67a-4055-aa9b-b9fd77d48de1" height="80%" width="80%" alt="SLA Creation Example"/></li>
  </ul>
</ul>
  
</p>

</br>

<h3>Configuring Help Topics</h3>

<p>
  
<ul>
  <li><b>Help Topics</b> simplify the ticket creation process, helping users select appropriate options for their issues and direct tickets to the right Department.</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and click on <b>Add New Help Topic</b>.</li>
  <ul>
    <li><b>Note</b>: osTicket provides four default Help Topics: Feedback, General Inquiry, Report a Problem, and Report an Access Issue.</li>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/27299450-a705-462c-a7d0-6fcdac6f5a59" height="80%" width="80%" alt="Add Help Topic Example"/></li>
  </ul>
  <li>We will create four new Help Topics based on ticket severity:</li>
  <ul>
    <li><img src="https://github.com/ColtonTrauCC/post-install-config/assets/147654000/c1ed7b51-b126-4e59-83e1-10b86ff7f03f" height="80%" width="80%" alt="Create Help Topic Example"/></li>
  </ul>
</ul>
  
</p>

<h2>Conclusion</h2>

<p>
By the end of this tutorial, you should have set up roles, agents, users, SLAs, and help topics within osTicket. You are now ready to start managing tickets effectively and customizing the system as per your needs!
</p>
