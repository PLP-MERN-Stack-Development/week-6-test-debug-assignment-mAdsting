# 🐛 MERN Bug Tracker

A comprehensive bug tracking system built with the MERN stack (MongoDB, Express.js, React, Node.js) designed for testing and debugging practice.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Running the Application](#running-the-application)
- [Testing](#testing)
- [Debugging](#debugging)
- [Intentional Bugs](#intentional-bugs)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)

## 🎯 Overview

The MERN Bug Tracker is a full-stack application that demonstrates robust testing and debugging practices. It serves as a practical example for implementing comprehensive testing strategies on both backend and frontend, with intentional bugs included for debugging practice.

### Key Learning Objectives

- **Backend Testing**: Integration tests with Jest and Supertest
- **Frontend Testing**: Component testing with React Testing Library
- **Error Handling**: Comprehensive error boundaries and middleware
- **Debugging**: Practice debugging with intentional bugs
- **API Design**: RESTful API with proper validation and responses

## ✨ Features

### Backend Features
- **RESTful API**: Full CRUD operations for bugs
- **MongoDB Integration**: Mongoose schema with validation
- **Error Handling**: Centralized error handling middleware
- **Logging**: Comprehensive request/response logging
- **Validation**: Input validation and sanitization
- **Testing**: Integration tests for all API endpoints
- **Ownership & Source**: `assignedTo`, `source` (internal or customer), and customer metadata
- **Collaboration**: Threaded `comments` on bugs
- **Auditability**: `statusHistory` recording who/why/when status changed
- **Customer Feedback**: Public-friendly endpoint to capture feedback as bugs
- **Notifications**: Optional Slack webhook on new bug/feedback

### Frontend Features
- **Modern UI**: Responsive design with modern styling
- **Real-time Updates**: Status updates and filtering
- **Error Boundaries**: Graceful error handling
- **Form Validation**: Client-side validation with feedback
- **Testing**: Unit and integration tests
- **Debugging Tools**: Console logging and error tracking
- **Extended Form**: Fields for `assignedTo`, `source`, and customer details when source is customer
- **List Enhancements**: Columns and filters for `Assignee` and `Source`

## 🛠️ Technology Stack

### Backend
- **Node.js**: Runtime environment
- **Express.js**: Web framework
- **MongoDB**: NoSQL database
- **Mongoose**: MongoDB object modeling
- **Jest**: Testing framework
- **Supertest**: HTTP testing library
- **Helmet**: Security middleware
- **CORS**: Cross-origin resource sharing

### Frontend
- **React 18**: UI library
- **Vite**: Build tool and dev server
- **React Testing Library**: Component testing
- **Jest**: Testing framework
- **Axios**: HTTP client
- **CSS-in-JS**: Styled components

## 📁 Project Structure

```
mern-bug-tracker/
├── server/                     # Backend application
│   ├── config/                 # Configuration files
│   │   └── database.js         # MongoDB connection
│   ├── models/                 # Mongoose models
│   │   └── Bug.js             # Bug schema
│   ├── routes/                 # API routes
│   │   └── bugsRouter.js      # Bug CRUD operations
│   ├── middleware/             # Express middleware
│   │   └── errorHandler.js    # Error handling
│   ├── tests/                  # Backend tests
│   │   ├── setup.js           # Test configuration
│   │   └── integration/       # Integration tests
│   │       └── bugs.test.js   # API tests
│   ├── package.json           # Backend dependencies
│   └── server.js              # Express server
├── client/                     # Frontend application
│   ├── src/                   # Source code
│   │   ├── components/        # React components
│   │   │   ├── BugList.jsx    # Bug list component
│   │   │   ├── BugForm.jsx    # Bug form component
│   │   │   ├── Layout.jsx     # Layout component
│   │   │   └── ErrorBoundary.jsx # Error boundary
│   │   ├── services/          # API services
│   │   │   └── api.js         # HTTP client
│   │   ├── tests/             # Frontend tests
│   │   │   ├── setup.js       # Test configuration
│   │   │   ├── unit/          # Unit tests
│   │   │   └── integration/   # Integration tests
│   │   ├── App.jsx            # Main app component
│   │   └── main.jsx           # Entry point
│   ├── package.json           # Frontend dependencies
│   ├── vite.config.js         # Vite configuration
│   └── index.html             # HTML template
└── README.md                  # Project documentation
```

## 🚀 Setup Instructions

### Prerequisites

- **Node.js** (v16 or higher)
- **MongoDB** (local installation or MongoDB Atlas)
- **npm** or **yarn** package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd mern-bug-tracker
   ```

2. **Install backend dependencies**
   ```bash
   cd server
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd ../client
   npm install
   ```

4. **Set up environment variables**
   
   Create a `.env` file in the `server` directory:
   ```env
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/mern-bug-tracker
   NODE_ENV=development
    # Optional: Send Slack notifications on new bugs/feedback
    SLACK_WEBHOOK_URL=https://hooks.slack.com/services/XXX/YYY/ZZZ
   ```

    Note: The project originally included intentional bugs (e.g., DB env var mismatch, wrong API method in form) for debugging practice. These have been fixed as part of the assignment.

## 🏃‍♂️ Running the Application

### Development Mode

1. **Start the backend server**
   ```bash
   cd server
   npm run dev
   ```
   The server will start on `http://localhost:5000`

2. **Start the frontend development server**
   ```bash
   cd client
   npm run dev
   ```
   The client will start on `http://localhost:3000`

3. **Access the application**
   Open your browser and navigate to `http://localhost:3000`

### Production Mode

1. **Build the frontend**
   ```bash
   cd client
   npm run build
   ```

2. **Start the production server**
   ```bash
   cd server
   npm start
   ```

## 🧪 Testing

### Backend Testing

Run backend tests from the `server` directory:

```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage
```

**Test Coverage**:
- Integration tests for all API endpoints (POST, GET, PUT, DELETE)
- Database connection testing
- Error handling validation
- Input validation testing

### Frontend Testing

Run frontend tests from the `client` directory:

```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage
```

**Test Coverage**:
- Unit tests for BugForm component
- Integration tests for BugList component
- API service testing
- Error boundary testing

### Test Structure

#### Backend Tests (`server/tests/integration/bugs.test.js`)
- **POST /api/bugs**: Create bug tests
- **GET /api/bugs**: Fetch bugs tests
- **GET /api/bugs/:id**: Get single bug tests
- **PUT /api/bugs/:id**: Update bug tests
- **DELETE /api/bugs/:id**: Delete bug tests
- **PATCH /api/bugs/:id/status**: Status update tests

#### Frontend Tests
- **BugForm.test.jsx**: Form validation, submission, error handling
- **BugList.test.jsx**: Data fetching, filtering, sorting, CRUD operations

## 🐛 Debugging

### Intentional Bugs

The application includes **two intentional bugs** for debugging practice:

#### 1. Backend Bug (Database Configuration)
**Location**: `server/config/database.js`
**Bug**: Uses `MONGODB_URL` instead of `MONGODB_URI`
```javascript
// INTENTIONAL BUG: Using wrong environment variable name
// Should be MONGODB_URI but using MONGODB_URL
const mongoURI = process.env.MONGODB_URL || 'mongodb://localhost:27017/mern-bug-tracker';
```

**Symptoms**: Database connection fails
**Debugging Steps**:
1. Check console logs for connection errors
2. Verify environment variable names
3. Compare with `.env` file

#### 2. Frontend Bug (API Method Name)
**Location**: `client/src/components/BugForm.jsx`
**Bug**: Uses `createNewBug` instead of `createBug`
```javascript
// INTENTIONAL BUG: Using wrong API method name
// Should be createBug but using createNewBug
const response = await bugAPI.createNewBug(formData);
```

**Symptoms**: Form submission fails
**Debugging Steps**:
1. Check browser console for errors
2. Verify API method names in service file
3. Check network tab for failed requests

### Debugging Tools

#### Backend Debugging
- **Console Logging**: Extensive logging throughout the application
- **Node.js Inspector**: Use `npm run debug` for debugging
- **Error Middleware**: Centralized error handling with detailed logs

#### Frontend Debugging
- **React DevTools**: Component inspection and state debugging
- **Browser DevTools**: Network, console, and performance debugging
- **Error Boundaries**: Graceful error handling with detailed information

### Debugging Workflow

1. **Identify the Issue**
   - Check console logs
   - Review error messages
   - Verify API responses

2. **Locate the Bug**
   - Use stack traces
   - Check component state
   - Verify data flow

3. **Fix the Bug**
   - Apply the correction
   - Test the fix
   - Verify functionality

4. **Document the Fix**
   - Update comments
   - Add tests if needed
   - Document the solution

## 📚 API Documentation

### Base URL
```
http://localhost:5000/api
```

### Endpoints

#### Create Bug
```http
POST /bugs
Content-Type: application/json

{
  "title": "Bug Title",
  "description": "Bug Description",
  "priority": "Medium",
  "reportedBy": "User Name",
  "assignedTo": "Assignee Name",           // optional
  "source": "internal" | "customer",       // default: internal
  "customer": {                              // required if source=customer
    "name": "Customer Name",
    "email": "customer@example.com",
    "id": "cust_123"
  }
}
```

#### Get All Bugs
```http
GET /bugs
GET /bugs?status=Open&priority=High&sortBy=createdAt&order=desc
```

#### Get Single Bug
```http
GET /bugs/:id
```

#### Update Bug
```http
PUT /bugs/:id
Content-Type: application/json

{
  "title": "Updated Title",
  "description": "Updated Description",
  "priority": "High",
  "status": "In Progress"
}
```

#### Delete Bug
```http
DELETE /bugs/:id
```

#### Update Bug Status
```http
PATCH /bugs/:id/status
Content-Type: application/json

{
  "status": "Resolved",
  "reason": "QA verified fix",
  "by": "alice"
}
```

#### Add Comment
```http
POST /bugs/:id/comments
Content-Type: application/json

{
  "author": "alice",
  "message": "Investigating logs"
}
```

#### Create Bug from Customer Feedback
```http
POST /bugs/feedback
Content-Type: application/json

{
  "title": "Payment fails on mobile",
  "description": "Getting 500 on checkout",
  "customerName": "Jane Doe",
  "customerEmail": "jane@example.com",
  "customerId": "cust_123",
  "priority": "High"
}
```

### Response Format
```json
{
  "success": true,
  "data": { ... },
  "message": "Operation successful"
}
```

### Error Response
```json
{
  "success": false,
  "error": "Error message",
  "message": "Detailed error information"
}
```

## 🤝 Contributing

### Development Workflow

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes**
4. **Add tests for new functionality**
5. **Run the test suite**
   ```bash
   # Backend tests
   cd server && npm test
   
   # Frontend tests
   cd client && npm test
   ```
6. **Commit your changes**
   ```bash
   git commit -m "Add feature: description"
   ```
7. **Push to your branch**
   ```bash
   git push origin feature/your-feature-name
   ```
8. **Create a pull request**

### Code Standards

- **JavaScript**: Use ES6+ features
- **React**: Functional components with hooks
- **Testing**: Minimum 80% test coverage
- **Documentation**: Comprehensive comments and README updates
- **Error Handling**: Graceful error handling throughout

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- **MERN Stack**: MongoDB, Express.js, React, Node.js
- **Testing Libraries**: Jest, React Testing Library, Supertest
- **Development Tools**: Vite, ESLint, Prettier

---

**Happy Debugging! 🐛✨**