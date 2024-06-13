## Project Requirements: LSOE Backed Project

### Preferred Technology Stack
- **Backend**: Node.js, Express.js
- **Database**: MongoDB, Mongoose

### User Roles
1. **Super Admin**
2. **Partners/Agents**
3. **Students**

### Functional Requirements

#### General Features
- **Agent Application**: All users can submit an application to become an LSOE partner.
- **Application Form**: Users can submit applications using a comprehensive form.
- **Chatbot Integration**: Integrate a simple chatbot for each application to assist users.
- **Status System**: Implement a status system for applications with predefined statuses:
  - Draft Applications
  - Submitted Applications
  - On Assessment
  - Enrolled
  - Rejected
- **Notifications**: Send email notifications to users when the status of their application changes.

#### Student Features
- **Profile Management**: Students can create and update their profiles.
- **Application Submission**: Students can submit applications.

#### Agent Features
- **Profile Management**: Agents can create and update their profiles.
- **Application Submission**: Agents can submit applications for multiple students.
- **Search Functionality**: Agents can search applications by name or email.

#### Super Admin Features
- **Manage Applications**: Super Admins can manage all applications.
- **Manage Agents**: Super Admins can manage all agents.
- **Manage Users**: Super Admins can manage all users.
- **Search Functionality**: Super Admins can search applications and agents by name or email.

### Detailed Requirements

#### User Authentication and Authorization
- **Authentication**: Implement user authentication using JWT (JSON Web Token).
- **Authorization**: Implement role-based access control to differentiate functionalities for Super Admins, Agents, and Students.

#### Application Form
- Develop a comprehensive form for users to submit applications.
- Ensure the form captures all necessary details required for the application.

#### Chatbot Integration
- Integrate a simple chatbot to assist users during the application process.
- The chatbot should provide guidance and answer common questions.

#### Status System
- Implement a status tracking system for applications with the following statuses:
  - **Draft Applications**: Applications saved as drafts.
  - **Submitted Applications**: Applications that have been submitted.
  - **On Assessment**: Applications that are being reviewed.
  - **Enrolled**: Applications that have been accepted.
  - **Rejected**: Applications that have been rejected.
- Ensure that status changes trigger email notifications to the associated user.

#### Profile Management
- **Students**: Allow students to create and update their profiles, and submit applications.
- **Agents**: Allow agents to create and update their profiles, submit applications for multiple students, and search for applications by name or email.
- **Super Admin**: Allow super admins to manage all applications, agents, and users, and perform searches by name or email.

### Non-Functional Requirements
- **Security**: Ensure the system is secure, protecting user data and preventing unauthorized access.
- **Scalability**: Design the system to handle a growing number of users and applications efficiently.
- **Maintainability**: Write clean, modular code to ensure the system is easy to maintain and extend.
- **Usability**: Ensure the user interface is intuitive and user-friendly.

### Project Structure

#### Directories and Files
```
lsoe-backed-project/
|-- models/
|   |-- User.js
|   |-- Application.js
|-- routes/
|   |-- auth.js
|   |-- users.js
|   |-- applications.js
|-- middleware/
|   |-- auth.js
|-- config/
|   |-- db.js
|-- controllers/
|   |-- authController.js
|   |-- userController.js
|   |-- applicationController.js
|-- utils/
|   |-- email.js
|-- app.js
|-- server.js
```

#### Implementation Details

1. **Database Configuration (`config/db.js`)**
    - Set up MongoDB connection using Mongoose.

2. **User Models (`models/User.js`)**
    - Define schemas for Students, Agents, and Super Admins.

3. **Application Models (`models/Application.js`)**
    - Define schemas for the application forms, including the status field.

4. **Authentication Middleware (`middleware/auth.js`)**
    - Implement JWT-based authentication.

5. **Controllers**
    - `authController.js`: Handle user authentication and registration.
    - `userController.js`: Handle profile management for Students and Agents.
    - `applicationController.js`: Manage application submissions, status updates, and chatbot interactions.

6. **Routes**
    - `auth.js`: Routes for authentication (login, register).
    - `users.js`: Routes for profile management.
    - `applications.js`: Routes for application submission and management.

7. **Email Utility (`utils/email.js`)**
    - Implement email notifications for status updates.

8. **Server Setup (`server.js`)**
    - Initialize Express server and connect to MongoDB.

By following this organized structure, the development team can systematically implement the features and requirements for the LSOE Backed Project.
