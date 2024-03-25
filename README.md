

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










 
