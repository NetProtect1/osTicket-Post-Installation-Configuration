<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">Post-Install Configuration</h1>

Here I outline the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems</h2>

- Windows 10</b> (22H2)

<h2>Post-Installation Objectives</h2>

- Configure Roles and Departments
- Configure Teams and allow anyone to create tickets
- Now we will configure agents/workers and user/customers
- Configure SLA
- Configure Help Topics

<h2>Prerequisites</h2>

- _This walkthrough assumes that you went through the <a href="https://github.com/Emq17/osTicket-Prerequisites-and-Installation/tree/main">"Prerequisites and Installation"</a> demonstration to successfully install osTicket_

<h1>Configuration Steps</h1>

# Admin Panel

> **Note***
>**Admin vs Agent:** *The Admin panel is used by the Administrator of the osTicketing System carrying out tasks like setting up the tickets, defining roles & SLA's, and general administrative duties (ex. Sys Admins) whereas Agent is used by the Workers (Helpdesk Professionals) who actually uses the platform instead of setting things up and solving user problems.*

<h3>Creating Roles</h3>

>**Note***
>*"Roles are the permissions granted to Agents per Department that they have access to. Each Role has a set of permissions that can be checked/unchecked for agents given that Role in association with a Department they have access to. An unlimited number of roles can be created and assigned to Agents with access to various departments."* - [osTicket Documentation ](https://docs.osticket.com/en/latest/Admin/Agents/Roles.html)

- So right now we are on the `Agent` panel because we can see it give us the option to switch to `Admin` on the top right of your screen

![Screen Shot 2023-12-27 at 2 51 38 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/b1a40ba4-72dd-4a62-ac8e-0fe3b03d2daa)

- Click `Admin` 
- Double Click `Agents` 

![Screen Shot 2023-12-27 at 3 16 33 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/925df49a-14a3-47ee-9f75-a8d425ef50bd)

- And then `Roles`

![Screen Shot 2023-12-27 at 3 19 22 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/054aa932-2f82-47ce-8af4-5878b8a7be0f)

- Find `Add New Role`
- Name it "Supreme Admin"
- Click on `Permissions` and check every single box ("Assign", "Close", "Create", etc). Use `tab` and `spacebar`

![Screen Shot 2023-12-27 at 3 23 16 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/32e4d098-b3ff-45b6-bb4c-2cbd003a2a7e)

- Click on `Tasks` and `Knowledgebase` and do the same
- Click on `Add Role` 

![Screen Shot 2023-12-27 at 3 23 59 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/4305978c-886d-4b99-8d78-8587be9221e7)

![Screen Shot 2023-12-27 at 3 24 18 PM](https://github.com/Emq17/osTicket-Post-Installation-Configuration/assets/147126755/9b162427-beaf-4c46-a913-b12ef9502bca)

> **Note***
>This role should now have all permissions over the Ticketing System

---

<h3>Creating Departments</h3>

>**Note***
>*Departments are just the collection of Agents in a department.* 

- Click the `Admin Panel` on the top-right of the page.
- Click `Agents`
- Click `Departments`
- Click `Add a New Department`

![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/c9eeb70b-cca8-4d36-951e-21af1757b3d8)

- Create a Department called **System Administrators**
- Click `Create Dept`

![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/72e15e09-5e5e-49e8-a5f3-18f3e8471dab)

<h3>Creating Teams</h3>

>**Note***
>*Having Agents from different Departments assigned to a Team will supersede the parameters of the Agents’ Department rules. For example, you can create a Help Topic associated with a particular product you produce, and assign it to a Team of specialist Agents from different Departments.*
- Inside the `Admin Panel`
- Click on `Agents`
- Click on `Teams`
- Click on `Add New Teams`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/8583d4ac-7a05-4260-be53-2791d7edcced)

- Create a Team called **Level II Support**
- Click on `Create Team`

![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/e4c83283-2211-410f-a9c3-00c1ed48a4ad)

<h3>Creating Agents</h3>

>**Note***
>*Agents are given access to the help desk with the intent to respond and resolve the tickets.*

- Inside the `Admin Panel`
- Click on `Agents`
- CLick on `Agent`
- Click on `Add a New Agent`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/162f5a72-c17f-4ee7-8952-4694647c06c0)

- Using the Required Credenitals **(In Bold)**
     - `First Name:` **Jane**
     - `Last Name:` **Doe**
     - `Email Address:` **jane.doe@osTicket.com**
     - `Username:` **jane.doe**
     - Click on `Set Password` 

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/ac82c903-6a0b-4750-8fd7-53b6ca826efe)

 - Uncheck "Send the agent a password reset email"
 - Create a Password
 - Uncheck "Require password change at next login"
 - CLick `Set`

 ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/f156e82e-896d-41db-9382-ee597ce80703)

- CLick the `Access` tab:
   - Assign Jane's `Primary Department` to **System Administrators**
   - Assign Jane's `Role` to **Supreme Admin**
- Underneath `Extended Access`tab:
    - Assign Jane to `Support Department`
    - Assign Jane's `Role` to **Supreme Admin**
    - Click `Save Changes`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/e315cccd-d69b-4027-b00d-8f7540ab0b27)

- Click the `Teams` tab:
  - Assign Jane to **Level II Support**
-  Click on `Create`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/d1acc2f4-a6d8-4b0a-a7d2-c3b155eec0eb)

- Create another Agent following the same steps, using the name **John Doe**

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/0157ad60-414f-4470-8a6c-07ac9408104e)

- Make John's `Department`: **Level I Support**
- Assign John's `Role`: View Only
- Underneath `Extended Access`: Support
- Click on `Create`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/62c95383-8b87-4c48-b3e4-f9537090af11)

<h3>Creating Users</h3>

>**Note***
>*Users are the individuals who submit tickets to your support team.*

- Click on the `Agent Panel`
- Navigate to `Users`
- Click `Add User` 

![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/a3ca0589-1cab-4344-92d2-e00e49631546)

- Make the User's `Email Address`: **karen@osticket.com**
- `Username`: **Karen Karen**
- Click `Add User`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/e32cd67b-b900-4983-9cf2-1d1ebaa927ba)

- Create another user, following the same steps but `Email address`: **ken@osticket.com**
- `Username`: **Ken Ken**
- Click `Add User`

![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/9ef34fbd-e2d2-4f64-97e0-82646cc0b5b2)

<h3>Creating SLA's</h3>

>**Note***
>*The purpose of the SLA Plan is to provide a length of time in which the help desk Administrator expects tickets to be closed.*


- Click on the `Admin Panel`
- Navigate to `Manage` tab
- Click `SLA`
- Click `Add New SLA Plan`

![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/ddb8f02a-aeb9-4c16-8ca1-f75b0e6be474)

- Create the following plans:
  - **SEV-A**
    - Grace Period: **1 hour** *(Amount, in hours, before tickets with tis SLA will become overdue if not closed in allotted time.)*
    - Schedule: **24/7**
  - **SEV-B**
     - Grace Period: **4 hours**
     - Schedule: **24/7**
  - **SEV-C**
      - Grace Period: **8 hours**
      - Schedule: **Monday - Friday: 8 a.m - 5 p.m (with U.S Holidays)**
- Click `Add Plan` for each

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/6d82beb6-fa1d-41e7-ae69-592eebc078c8)

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/e9eca7cf-a46f-4f41-b6d6-ce59c2355876)

<h3>Creating Help Topics</h3>

>**Note***
>*Help Topics will determine what Department the ticket is routed to which will determine which Agents have access to the ticket. The Help Topic also can determine other configurations of the ticket, such as the ticket’s SLA (or Service Level Agreement) and priority of a ticket, i.e. Emergency to Low.*

- Click on the `Admin Panel`
- Navigate to the `Manage` tab
- Click on `Help Topic`
- Click `Add New Help Topic`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/4ee33849-7948-4749-aa3b-128453973455)

- Create Help Topics with the following names:
    - **Business Critical Outage**
    - **Personal Computer Issues**
    - **Equipment Request**
    - **Password Reset**
- `Internal Notes` can be used, but not necessary
- Click `Add Topic`

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/f162a73d-063f-440e-94de-27c026b6a7eb)

  ![image](https://github.com/CarlosAlvarado0718/osTicket-PostConfig/assets/140138198/ec00fd9d-f9dc-4aec-a2ae-a03427a1535b)

---

  <h1>ALL DONE!! CONGRATS!! </h1>

  <h3>NEXT TUTORIAL:  <a href="https://github.com/CarlosAlvarado0718/osTicket_Lifecycle">"Ticket Lifecycle Examples"</a>  </h3>
