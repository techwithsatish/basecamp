Project Camp Backend

1. Product Overview
   Product Name: Project Camp Backend
   Version: 1.0.0
   Product Type: Backend API for Project Management System

Project Camp Backend is a RESTful API service designed to support collaborative project management.
The system enables teams to organize projects, manage tasks with subtasks, maintain project notes, and handle user authentication with role-based access control.

2. Target Users

- Project Administrators: Create and manage projects, assign roles, oversee all project activities
- Project Admins: Manage tasks and project content within assigned projects
- Team Members: View projects, update task completion status, access project information

3. Core Features
   3.1 User Authentication & Authorization

- User Registration: Account creation with email verification
- User Login: Secure authentication with JWT tokens
- Password Management: Change password, forgot/reset password functionality
- Email Verification: Account verification via email tokens
- Token Management: Access token refresh mechanism
- Role-Based Access Control: Three-tier permission system (Admin, Project Admin, Member)

  3.2 Project Management

- Project Creation: Create new projects with name and description
- Project Listing: View all projects user has access to with member count
- Project Details: Access individual project information
- Project Updates: Modify project information (Admin only)
- Project Deletion: Remove projects (Admin only)
  3.3 Team Member Management
- Member Addition: Invite users to projects via email
- Member Listing: View all project team members
- Role Management: Update member roles within projects (Admin only)
- Member Removal: Remove team members from projects (Admin only)
- 3.4 Task Management
  Task Creation: Create tasks with title, description, and assignee
  Task Listing: View all tasks within a project
  Task Details: Access individual task information
  Task Updates: Modify task information and status
  Task Deletion: Remove tasks from projects
  File Attachments: Support for multiple file attachments on tasks
  Task Assignment: Assign tasks to specific team members
  Status Tracking: Three-state status system (Todo, In Progress, Done)

  3.5 Subtask Management

Subtask Creation: Add subtasks to existing tasks
Subtask Updates: Modify subtask details and completion status
Subtask Deletion: Remove subtasks (Admin/Project Admin only)
Member Completion: Allow members to mark subtasks as complete

3.6 Project Notes
Note Creation: Add notes to projects (Admin only)
Note Listing: View all project notes
Note Details: Access individual note content
Note Updates: Modify existing notes (Admin only)
Note Deletion: Remove notes (Admin only)

3.7 System Health
Health Check: API endpoint for system status monitoring

4. Technical Specifications

4.1 API Endpoints Structure

Authentication Routes (/api/v1/auth/)

POST/register User registration
POST/login User authentication
POST /logout - User logout (secured)
GET /current-user - Get current user info (secured)
POST /change-password Change user password (secured)
POST/refresh-token Refresh access token
GET /verify-email/:verificationToken - Email verification
POST/forgot-password Request password reset
POST /reset-password/:resetToken Reset forgotten password
POST /resend-email-verification Resend verification email (secured)

Project Routes (/api/v1/projects/)

GET / List user projects (secured)
POST / Create project (secured)
GET /:projectId Get project details (secured, role-based)
PUT /:projectId Update project (secured, Admin only)
DELETE /:projectId Delete project (secured, Admin only)
GET /:projectId/members List project members (secured)
POST /:projectId/members - Add project member (secured, Admin only)
PUT /:projectId/members/:userId Update member role (secured, Admin only)
DELETE /:projectId/members/: userId - Remove member (secured, Admin only)

Task Routes (/api/v1/tasks/)

GET /:projectId List project tasks (secured, role-based)
POST /:projectId Create task (secured, Admin/Project Admin)
GET /:projectId/t/: taskId - Get task details (secured, role-based)
PUT /:projectId/t/: taskId - Update task (secured, Admin/Project Admin)
DELETE /:projectId/t/:taskId Delete task (secured, Admin/Project Admin)
POST /:projectId/t/: taskId/subtasks Create subtask (secured, Admin/Project Admin)
PUT /:projectId/st/:subTaskId - Update subtask (secured, role-based)
DELETE /:projectId/st/:subTaskId Delete subtask (secured, Admin/Project Admin)

Note Routes (/api/v1/notes/)

GET /:projectId List project notes (secured, role-based)
POST /:projectId Create note (secured, Admin only)
GET /:projectId/n/: noteId Get note details (secured, role-based)
PUT /:projectId/n/: noteId - Update note (secured, Admin only)
DELETE /:projectId/n/: noteId Delete note (secured, Admin only)

Health Check (/api/v1/healthcheck/)

GET / System health status

<img width="640" height="468" alt="image" src="https://github.com/user-attachments/assets/19b58e2c-7337-4059-8af7-7bf72a709e03" />

<img width="561" height="327" alt="image" src="https://github.com/user-attachments/assets/30765cef-62e3-4429-8604-ae58a25dfab9" />

<img width="475" height="428" alt="image" src="https://github.com/user-attachments/assets/9b9f6c05-3a21-4878-9fe6-b4422dcf48a1" />

<img width="702" height="256" alt="image" src="https://github.com/user-attachments/assets/a1917fc8-24af-49c0-95cd-a81d588660af" />
