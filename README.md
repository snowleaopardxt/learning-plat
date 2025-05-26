# Learning Platform Project

A full-stack learning platform application built with Node.js (Express) backend and Next.js (React) frontend.

## Features

This project includes core features for a learning platform:

*   User Authentication (Register, Login, Logout)
*   Role-based Authorization (Learner and Admin roles)
*   Admin Dashboard for managing users and courses
*   Learner Dashboard for viewing enrolled and available courses
*   Dynamic Course Pages with nested content (Modules & Lessons)
*   Course Progress Tracking for learners
*   RESTful API built with Express and Mongoose
*   Modern frontend built with Next.js, React, and Tailwind CSS
*   Authentication handled via HTTP-only cookies

## Setup and Installation

Follow these steps to get the project running on your local machine:

### Prerequisites

Make sure you have the following installed:

*   Node.js (LTS version recommended)
*   npm or yarn
*   MongoDB (running locally or accessible via a connection string)

### 1. Clone the Repository

```bash
git clone https://github.com/snowleaopardxt/learning-plat.git
cd learning-plat
```

### 2. Backend Setup

Navigate into the `backend` directory and install dependencies:

```bash
cd backend
npm install
```

Create a `.env` file in the `backend` directory with the following variables:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
```

Replace `your_mongodb_connection_string` with your MongoDB connection string and `your_jwt_secret_key` with a strong, random string.

### 3. Frontend Setup

Navigate into the `frontend` directory and install dependencies:

```bash
cd ../frontend
npm install
```

Create a `.env.local` file in the `frontend` directory with the following variable:

```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api
```

### 4. Running the Project

First, start the backend server from the `backend` directory:

```bash
cd ../backend
npm start
```

Then, start the frontend development server from the `frontend` directory:

```bash
cd ../frontend
npm run dev
```

The frontend application should now be running at `http://localhost:3000`.

## API Documentation

The backend provides a RESTful API. Key endpoints include:

*   `/api/auth/register` (POST): Register a new user.
*   `/api/auth/login` (POST): Login an existing user. Sets an HTTP-only cookie.
*   `/api/auth/logout` (POST): Logout the current user. Clears the HTTP-only cookie.
*   `/api/users/profile` (GET): Get the profile of the currently logged-in user.
*   `/api/users` (GET): Get all users (Admin only).
*   `/api/users/:id/role` (PUT): Update a user's role (Admin only).
*   `/api/courses` (GET): Get all courses.
*   `/api/courses` (POST): Create a new course (Admin only).
*   `/api/courses/:id` (GET): Get a specific course by ID.
*   `/api/courses/:id` (PUT): Update a specific course by ID (Admin only).
*   `/api/courses/:id` (DELETE): Delete a specific course by ID (Admin only).
*   `/api/courses/enrolled` (GET): Get courses the logged-in learner is enrolled in (Learner only).
*   `/api/courses/:id/enroll` (POST): Enroll the logged-in learner in a course.
*   `/api/progress/:courseId` (GET): Get the logged-in user's progress for a specific course.
*   `/api/progress/:courseId` (PUT): Update the logged-in user's progress for a specific course (Learner only).

Authentication is handled via HTTP-only cookies set after login/registration.

## Testing Credentials

You can register new users via the `/register` route.

*(Note: If you need specific admin credentials for testing, you might need to manually update a user's role in the database or add a dedicated admin registration route in the backend.)*

## Postman Collection (Optional)

A Postman collection can be useful for testing the backend API endpoints directly. (Not included in this initial commit, but can be added.)

## Future Improvements

*   Implement password hashing in the backend if not already handled by Mongoose model.
*   Add more robust error handling and validation.
*   Enhance UI/UX.
*   Implement features like quizzes, discussions, etc. 