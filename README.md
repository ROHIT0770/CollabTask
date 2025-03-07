# Collaborative Task Management System

Welcome to the **Collaborative Task Management System**! This project is designed to help teams manage tasks, collaborate in real-time, and track progress across multiple projects. Whether you're an Admin, Manager, or Member, this system provides a seamless experience for task management, collaboration, and reporting.

---

## 🚀 **Features**

### **User Management**
- **User Roles**: Admin, Manager, or Member.
- **User Actions**: Create, update, and delete tasks within assigned projects.
- **User Details**: Each user has an email, name, and role.

### **Project & Task Management**
- **Projects**: Create projects and add team members.
- **Tasks**: Each task includes:
  - Title, description, and due date.
  - Status (To-Do, In Progress, Completed).
  - Priority (Low, Medium, High).
  - Assignee (user working on the task).
  - Reporter (user who created the task).

### **Task Assignment & Collaboration**
- **Comments**: Discuss progress by commenting on tasks.
- **File Attachments**: Attach files to tasks for additional context.
- **Notifications**: Receive real-time notifications for task assignments and updates.
- **Task Transfer**: Transfer tasks between users if needed.

### **Reporting & Tracking**
- **Task Views**: Users can view all tasks assigned to them.
- **Filters**: Managers/Admins can filter tasks by priority, assignee, and status.
- **Project Summary Report**: Generate and download a detailed report of all tasks, assignees, and statuses.

---

## 🛠️ **Tech Stack**

### **Backend**
- **Node.js**: For building the backend service.
- **Express.js**: For creating RESTful APIs.
- **MongoDB**: For database management.
- **Socket.IO**: For real-time notifications and collaboration.

### **Frontend**
- **React.js**: For building the user interface.
- **React Router**: For navigation between pages.
- **Redux**: For state management.
- **Material-UI**: For a visually appealing and responsive design.

---

## 📂 **Project Structure**

```
collaborative-task-management-system/


├── backend/
│   ├── package-lock.json        # Locks versions of backend dependencies.
│   ├── package.json             # Lists backend project metadata and dependencies.
│   ├── readme.md                # Documentation for backend setup and usage.
│   └── src/                     # Source code for the backend.
│       ├── controllers/         # Manages business logic.
│       │   ├── projectController.js # Handles project operations.
│       │   ├── taskController.js    # Manages task-related actions.
│       │   └── userController.js    # Manages user authentication and profiles.
│       ├── middleware/          # Contains middleware functions.
│       │   └── auth.js          # Handles authentication processes.
│       ├── models/              # Defines data schemas.
│       │   ├── Project.js       # Schema for project data.
│       │   ├── Task.js          # Schema for task data.
│       │   └── User.js          # Schema for user data.
│       ├── routes/              # Defines API endpoints.
│       │   ├── projectRoutes.js  # Routes for project APIs.
│       │   ├── taskRoutes.js     # Routes for task APIs.
│       │   └── userRoutes.js     # Routes for user APIs.
│       └── server.js            # Initializes the server and database connection.
│
└── frontend/
    ├── eslint.config.js         # Configuration for ESLint.
    ├── index.html               # Main HTML file for the web app.
    ├── package-lock.json        # Locks versions of frontend dependencies.
    ├── package.json             # Lists frontend project metadata and dependencies.
    ├── public/                  # Contains static assets.
    │   └── vite.svg             # Logo for Vite.
    ├── readme                   # Documentation for frontend setup and usage.
    └── src/                     # Source code for the frontend.
        ├── App.css              # Styles for the main application.
        ├── App.jsx              # Main application component.
        ├── index.css            # Global styles.
        ├── main.jsx             # Entry point for the React application.
        ├── assets/               # Contains images and icons.
        │   └── react.svg        # React logo.
        ├── components/           # Reusable UI components.
        │   ├── Layout.jsx        # Overall layout structure.
        │   ├── PrivateRoute.jsx  # Protects routes for authenticated users.
        │   └── ProjectMembers.jsx # Displays project member information.
        ├── context/              # Contains context APIs for state management.
        │   └── AuthContext.jsx   # Manages authentication state.
        ├── pages/                # Individual pages of the application.
        │   ├── Dashboard.jsx     # Overview of projects and tasks.
        │   ├── Login.jsx         # User login page.
        │   ├── Profile.jsx       # Displays user profile.
        │   ├── ProjectDetail.jsx # Details of a specific project.
        │   ├── ProjectList.jsx   # Lists all user projects.
        │   ├── Register.jsx      # User registration page.
        │   ├── TaskBoard.jsx     # Visual task management board.
        │   ├── TaskDetail.jsx    # Details of a specific task.
        │   └── TaskForm.jsx      # Form for creating/editing tasks.
    └── vite.config.js           # Configuration for Vite build tool.



---

## 🚀 **Getting Started**

### **Prerequisites**
- Node.js (v16 or higher)
- MongoDB (v5 or higher)
- npm (v8 or higher)

### **Installation**

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/collaborative-task-management-system.git
   cd collaborative-task-management-system
   ```

2. **Install Backend Dependencies**
   ```bash
   cd backend
   npm install
   ```

3. **Install Frontend Dependencies**
   ```bash
   cd ../frontend
   npm install
   ```

4. **Set Up Environment Variables**
   - Create a `.env` file in the `backend` directory:
     ```env
     MONGO_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     PORT=5000
     ```

5. **Run the Backend Server**
   ```bash
   cd ../backend
   npm start
   ```

6. **Run the Frontend Server**
   ```bash
   cd ../frontend
   npm start
   ```

7. **Access the Application**
   - Open your browser and navigate to `http://localhost:3000`.

---

Here’s the updated **API Documentation** section in proper code format for easy readability. You can directly paste this into your README file:

---

## 📄 **API Documentation**

### **User Endpoints**

#### **Authentication**
```plaintext
POST /api/users/register
- Validates user registration details and creates a new user.

POST /api/users/login
- Authenticates the user and returns a token for accessing protected routes.
```

#### **Profile Management**
```plaintext
GET /api/users/profile
- Retrieves the authenticated user's profile details.

PATCH /api/users/profile
- Updates the authenticated user's profile details.
```

#### **Project Member Management**
```plaintext
GET /api/users/available
- Retrieves a list of users available to be added to a project.
```

#### **Admin-Only Routes**
```plaintext
GET /api/users/users
- Retrieves a list of all users (accessible only to Admins).

PATCH /api/users/:userId/role
- Updates the role of a specific user (accessible only to Admins).

DELETE /api/users/:userId
- Deletes a specific user (accessible only to Admins).
```

---

### **Task Endpoints**

#### **Task Management**
```plaintext
POST /api/tasks
- Creates a new task with validated details.

GET /api/tasks/project/:projectId
- Retrieves all tasks associated with a specific project.

GET /api/tasks/user
- Retrieves all tasks assigned to the authenticated user.

GET /api/tasks/:taskId
- Retrieves details of a specific task.

PATCH /api/tasks/:taskId
- Updates the details of a specific task.

PATCH /api/tasks/:taskId/status
- Updates the status of a specific task.

DELETE /api/tasks/:taskId
- Deletes a specific task.
```

#### **Task Comments**
```plaintext
POST /api/tasks/:taskId/comments
- Adds a comment to a specific task.
```

#### **Task Attachments**
```plaintext
POST /api/tasks/:taskId/attachments
- Uploads and attaches a file to a specific task.
```

#### **Task Statistics**
```plaintext
GET /api/tasks/project/:projectId/stats
- Retrieves statistics for tasks within a specific project.
```

---

## 🎨 **Frontend Screenshots**

### **Login Page**
![Login Page](https://via.placeholder.com/600x400?text=Login+Page)

### **User Dashboard**
![User Dashboard](https://via.placeholder.com/600x400?text=User+Dashboard)

### **Task Board**
![Task Board](https://via.placeholder.com/600x400?text=Task+Board)

### **Task Details Page**
![Task Details](https://via.placeholder.com/600x400?text=Task+Details)

---

## 📝 **Data Validation & Constraints**
- **Email Validation**: Ensures valid email format during user creation.
- **Due Date Validation**: Ensures due dates are in the future when creating tasks.
- **Duplicate Task Prevention**: Prevents duplicate tasks within the same project.

---

## 🤝 **Contributing**
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeatureName`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeatureName`).
5. Open a pull request.

---
