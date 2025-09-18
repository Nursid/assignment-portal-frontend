# Assignment Portal Frontend - Quick Setup Guide

## 🚀 Project Setup

### 1. Install Dependencies
```bash
npm install
```

### 2. Create Environment File
Create a `.env` file in the root directory:

```env
# Backend API URL
REACT_APP_API_URL=http://localhost:5000/api
```

### 3. Run the Application
```bash
# Development server
npm start
# Runs on http://localhost:3000

# Production build
npm run build

# Run tests
npm test
```

## 📋 Required Environment Variables

### Frontend (.env)
```env
REACT_APP_API_URL=http://localhost:5000/api
```

### Backend (.env) - For Reference
```env
# Database
MONGO_URI=mongodb://localhost:27017/assignment-portal
# or MongoDB Atlas: mongodb+srv://username:password@cluster.mongodb.net/assignment-portal

# Authentication
JWT_SECRET=your-super-secret-jwt-key-here

# Server Configuration
PORT=5000
NODE_ENV=development

# Optional: Email Service (if using email notifications)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-app-password
```

## 📝 Key Features & Assumptions

### 🔒 Authentication
- JWT token-based authentication
- Automatic token refresh and logout on expiry
- Role-based access (Teacher/Student)

### 📚 Assignment Management
- **Teachers**: Create, edit, delete assignments
- **Students**: View and submit assignments
- **Status Workflow**: Draft → Published → Completed
- **Due Date Validation**: Submissions blocked after deadline

### 📊 Submission System
- **One submission per assignment** (students)
- **Text-based submissions only**
- **Grading**: 0-100 scale with written feedback
- **Status Tracking**: Pending → Submitted → Graded

### 🎨 UI/UX Features
- **Responsive Design**: Mobile-first approach
- **Real-time Updates**: Live status changes
- **Pagination**: For large assignment lists
- **Analytics Dashboard**: Teacher statistics
- **Due Date Indicators**: Visual overdue warnings

### 🔧 Technical Assumptions
- **Backend API**: Must be running on localhost:5000
- **Database**: MongoDB (local or Atlas)
- **Browser Support**: Modern browsers (Chrome, Firefox, Safari, Edge)
- **Node Version**: v14 or higher

### 🛡️ Security Features
- **Route Protection**: Role-based access control
- **Input Validation**: Client-side form validation
- **XSS Prevention**: Input sanitization
- **Token Management**: Secure localStorage handling

## 🚨 Important Notes

1. **Backend Dependency**: Frontend requires backend API to be running first
2. **CORS Configuration**: Backend must allow frontend domain
3. **Due Date Enforcement**: Submissions automatically blocked after deadline
4. **Single Submission**: Students can only submit once per assignment
5. **Status Restrictions**: Only Draft assignments can be edited/deleted
6. **Authentication Required**: All routes except login are protected

## 🔍 Default Test Users (Backend Setup Required)

```javascript
// Teachers
Email: teacher@example.com
Password: password123

// Students  
Email: student@example.com
Password: password123
```

## 📱 Quick Start Commands

```bash
# Clone and setup
git clone <repository>
cd assignment-portal-frontend
npm install

# Create .env file
echo "REACT_APP_API_URL=http://localhost:5000/api" > .env

# Start development
npm start
```

---
**Note**: Make sure your backend server is running on `http://localhost:5000` before starting the frontend application.
