# Student Appointment System

A fully functional RESTful API designed to handle scheduling and management of appointments between professors and students in a college environment.

## Features

- Secure authentication for both professors and students
- Manage and update professor availability
- Schedule, view, and modify appointments
- Role-specific access control for users

## Prerequisites

- Node.js: Ensure Node.js is installed on your system.
- MongoDB: A running instance of MongoDB is required.

## Installation

1. Clone the repository to your local machine
2. Install dependencies:
   ```bash
   npm install
   ```
   
3. Create a .env file and add the following:
   ```
   JWT_SECRET=your_jwt_secret
   MONGODB_URI=your_mongodb_uri
   PORT=3000
   ```

## Running the Application

Development mode:
```bash
npm run dev
```

Production mode:
```bash
npm start
```

## Running Tests
Ececute the test suite with:
```bash
npm test
```

## API Documentation

Swagger documentation is available at /api-docs when the server is active.

## API Endpoints

### Authentication
- POST /api/auth/login
- POST /api/auth/register

### Professor Availability
- POST /api/availability
- GET /api/availability/{professorId}
- DELETE /api/availability/{slotId}

### Appointments
- POST /api/appointments
- GET /api/appointments
- DELETE /api/appointments/{appointmentId}

## Database Schema

### Users
- id: ObjectId
- email: String
- password: String (hashed)
- role: String (student/professor)
- name: String

### Availability
- id: ObjectId
- professorId: ObjectId
- startTime: Date
- endTime: Date
- status: String (available/booked)

### Appointments
- id: ObjectId
- studentId: ObjectId
- professorId: ObjectId
- slotId: ObjectId
- status: String (scheduled/cancelled)
