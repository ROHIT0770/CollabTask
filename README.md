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
     MONGO_URI=mongodb://localhost:27017/task_management
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

## 📄 **API Documentation**

### **User Endpoints**
- **Create User**: `POST /api/users`
- **Retrieve User Details**: `GET /api/users/:id`
- **Assign Users to Projects**: `POST /api/projects/:projectId/users`

### **Project Endpoints**
- **Create Project**: `POST /api/projects`
- **Add/Remove Users from Project**: `PUT /api/projects/:projectId/users`
- **Retrieve Project Details**: `GET /api/projects/:id`

### **Task Endpoints**
- **Create Task**: `POST /api/tasks`
- **Retrieve Tasks by User/Project**: `GET /api/tasks?userId=:userId&projectId=:projectId`
- **Update Task Status**: `PUT /api/tasks/:id/status`
- **Comment on Tasks**: `POST /api/tasks/:id/comments`
- **Attach Files to Tasks**: `POST /api/tasks/:id/attachments`
- **Download Project Summary Report**: `GET /api/projects/:id/report`

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
