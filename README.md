## Oracle Visual Builder Web Application integrated with Office 365
The Oracle VBCS is a cloud-based, low-code application development solutions for creating, extending, and customizing business applications. 
### Oracle Visual Builder specifications
- Based on a component architecture, supporting the integration and extension of Oracle PaaS and SaaS Cloud Services as well as third-party REST based services (including Microsoft Graph API).
- Ability to create, copy, edit, delete, version, stage, and publish these applications as part of application lifecycle management.
- Unlimited number of authenticated users may access the development tools and may develop and publish any number of applications, with no any restrictions. 
- Unlimited number of API calls may be made with no restrictions.
- Provides up to 5 gigabytes of capacity for applications and data.

## MS Graph API

This Web Application developed with Oracle Visual Builder platform, is used to show case how to integrate with Office 365, using and leveraging MS GraphAPI. 
Microsoft Graph is the gateway to data and intelligence in Microsoft 365, Windows, and Enterprise Mobility + Security.  
Microsoft Graph exposes REST APIs and client libraries to access data on the following Microsoft cloud services:
-	Microsoft 365 core services: 
Bookings, Calendar, Delve, Excel, Microsoft 365 compliance eDiscovery, Microsoft Search, OneDrive, OneNote, Outlook/Exchange, People (Outlook contacts), Planner, SharePoint, Teams, To Do, Viva Insights 
-	Enterprise Mobility + Security services: 
Advanced Threat Analytics, Advanced Threat Protection, Microsoft Entra ID, Identity Manager, and Intune
-	Windows services: 
activities, devices, notifications, Universal Print
-	Dynamics 365 Business Central services

This Web Application is using Graph API and leverage the available endpoints and APIs to access:  
-	Outlook data: 
o	List of Active Directory users
o	List of emails received for given user.
o	Viewing email elements and access full email content
o	Email Creation and Sent message.
-	Notebooks: 
o	List of Active Directory users
o	List of notebooks created for a given user.
o	Notebook creation
-	Teams:
o	List of Active Directory users
o	List of Teams that the given user is assigned.
o	Access Teams group that the given user is assigned.


<img width="401" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/2b291538-1298-4c03-9ff3-739a0cb1921c">

## Configuration of Microsft Entra 
In order to use MS Graph APi and make requests, you need to register your Application and get authentication tokens for a user (or a service). 
- To register your application you can access and apply the following official documentation: https://learn.microsoft.com/en-us/graph/auth-register-app-v2
- To get access on behalf of a user : https://learn.microsoft.com/en-us/graph/auth-v2-user 
- To get access without a user : https://learn.microsoft.com/en-us/graph/auth-v2-service 

### Oracle Visual Builder Platform integration with MS Graph API
Once Oracle Visual Builder application is registered to Microsoft Entra, and the required secrets have been generated and stored, the following Service connections need to be configured within Visual Builder applicatiion as depicted in the following pictures: 

#### Server definition 
Configure a back server inside Visual Builder, using the https://graph.microsoft.com URL to define the instance, and as the authenitcation protocol use : "OAuth 2.0 Client Credentials", providing the scope, Token URL, Client, and Secret with using the data from Microsoft Entra, as depicted below. 

<img width="1138" alt="Screenshot 2024-03-25 at 16 59 00" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/86e1d97e-17cc-4032-b14c-3132e1a1d0a0">

#### EndPoint definition
For each server defined, you can access the REST end points and test each API that you will use later iunside your application. 

<img width="1100" alt="Screenshot 2024-03-25 at 17 03 35" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/a35d0f1d-7748-4bc5-8a6d-e6939145396d">

#### Types based on endpoints 
Once you have successfully tested and save the response messages for all the REST Endpoint that you will use inside your application, create accordignly Visual Builder data types, based on these Service Endpoints that you will use later inside your application. 

<img width="1079" alt="Screenshot 2024-03-25 at 17 06 07" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/fbd3261d-2aac-440e-a389-33486980d495">



### From github repository to Oracle VisualBuilder application. 
1. Connect to your Oracle Visual Builder Studio Instance
2. Into an existing Project OR Create a new project --> create a new git repository by importing the existing public GitHub repository.
   ![Screenshot 2024-03-25 at 12 33 33](https://github.com/johnkarasoulos/aircraftBlockchain/assets/25766024/235cf9ae-c01f-449a-8764-96fdda1e543b)

3. Create a new Workspace using the button "Clone From Git" where you are selecting the Repository Name, the Branch , the Development Environment and you are providing the name of the Workspace Name.
   ![Screenshot 2024-03-25 at 12 37 06](https://github.com/johnkarasoulos/aircraftBlockchain/assets/25766024/5592e9b4-d1c1-44ba-ab37-364f87f06809)

4. You redirected to the new VisualBuilder instance assigned to this workspace and you can start working.  


### Step by Step instructions to implment your own integration base on the provided source code. 
1.	Create Endpoints
    ![image](https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/f96e2ec0-8a6e-4238-8c0f-1f371e4a6246)
2.  Create a Type based on get users
3.	Create a Type based on get messages
4.	Create a Type based on get message
5.	Create a Variable UserId of type String
6.	Create a Variable MessageId of type String
7.	Create a Variable based on the getActiveDirectoryUsers 
8.	Create a Variable based on the getListOfMessages4UserId
9.	Go to page designer, create dropdown field and get data from getADUSers API
    <img width="452" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/230274c3-7c04-430d-8d78-306a43ad3d26">
10. Change Label to “List of Active Directory Users”
11. On the Data tab chose the variable UserID to populate:
<img width="284" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/b9ae8441-c5bd-4c79-8e4d-46d533ee080e">

12. Add User Id Text field:
<img width="283" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/7fbdb45d-1081-4f9f-9369-f5a39b0906d8">

13. Add a table and addData
<img width="452" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/12e80d38-2b21-4254-891b-dbc8ad6c1325">
<img width="452" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/ecfb9155-bcad-4764-a8e1-40d85b5b6e73">

14. Create new page called main-message :  
With a Form Layout
<img width="283" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/48455a8a-3ce6-44ef-a951-b8a450fa6f6f">

15. Create a Type based on getMessage : 
<img width="371" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/45a4f2ef-601f-484e-87dc-bf1cd2e357f4">

16. Create a variable from get Message type (REQUIRED variable)
And then create the following page
<img width="240" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/84861550-2f49-4411-b6f4-7d77f3c73218">

17. Go to the main page and create a new action on selectRow:
<img width="452" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/b6ef83ee-ecfc-46d4-9b39-ed12c2b6f33a">

18. Into the new Action chain:
<img width="263" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/8b703966-db16-437f-9ce7-a230ecfb5f32">

a.	Assign variables userId and message Id: 
I.	userId with the field SearchUserID 
II.	messageid with rowData.id
b. Create a type of a GetEmail RestAPI
c. CallRest GetEmail
<img width="133" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/8461d65d-4379-40c4-8ac4-e4c94f45ca66">

I. Assign messageId and user Id parameter
<img width="341" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/6248d34c-453f-4224-b831-0404106904a0">

II. Chose the response type previously created
d. On Success: Navigate to the page main-graphapi-email with inputs parameter:

<img width="452" alt="image" src="https://github.com/johnkarasoulos/VisualBuilderIntegration2Office365/assets/25766024/213410d9-aa9b-42cb-947b-443678cd7ac2">

e.	Close with Navigate Back










 
