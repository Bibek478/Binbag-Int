# User Profile API

## Overview

This codebase implements a RESTful API for managing user profiles. It includes endpoints for user registration, login, profile retrieval, and profile update. The API uses JWT authentication to protect routes and stores data in MongoDB.

## Setup Instructions

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  **Install dependencies:**

    ```bash
    npm install
    ```

3.  **Configure environment variables:**

    *   Create a `.env` file in the root directory.
    *   Add the following environment variables:

        ```
        PORT=5000
        MONGODB_URI=mongodb://localhost:27017/your_database_name
        JWT_SECRET=your_jwt_secret
        ```

        *   Replace `mongodb://localhost:27017/your_database_name` with your MongoDB connection string.
        *   Replace `your_jwt_secret` with a strong, randomly generated secret key.

4.  **Start the server:**

    ```bash
    node server.js
    ```

    The server will start on port 5000 (or the port specified in the `.env` file).

## File Structure

*   **`server.js`:** The main entry point for the application. It starts the Express server.
*   **`app.js`:** Contains the Express application setup, including middleware, route definitions, and error handling.
*   **`config/db.js`:** Contains the database connection logic using Mongoose.
*   **`models/User.js`:** Defines the User model using Mongoose.
*   **`routes/userRoutes.js`:** Defines the API routes for user registration, login, profile retrieval, and profile update.
*   **`middleware/authMiddleware.js`:** Implements the JWT authentication middleware to protect routes.
*   **`.env`:** Contains environment variables such as the port number, MongoDB URI, and JWT secret key.
*   **`README.md`:** This file, providing setup instructions and documentation for the codebase.

## API Endpoints

The API endpoints are documented in the Postman collection.
https://documenter.getpostman.com/view/43608572/2sB2cRC4Qz

## Postman Collection

The Postman collection is organized into two folders:

*   **No Auth:** Contains endpoints that do not require authentication (e.g., user registration, login).
*   **Auth:** Contains endpoints that require a valid JWT token (e.g., get profile, update profile).

To use the "Auth" endpoints, you must include the `Authorization` header with the value `Bearer <your_jwt_token>`, replacing `<your_jwt_token>` with the actual JWT token obtained from the login endpoint.

## Error Handling

The API implements comprehensive error handling. All endpoints return appropriate HTTP status codes and error messages in case of failure.