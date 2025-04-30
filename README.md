ECHOS BACKEND

Overview
--------

This is the backend of the Echos real-time chat application. It is built using Node.js, Express.js, and MongoDB to provide a robust and scalable API for the frontend. The backend handles user authentication, real-time messaging, and file uploads via Cloudinary.

Features
--------

- Authentication: Secure user signup, login, and logout using JWT.
- Real-Time Messaging: Powered by WebSocket (Socket.IO) for instant communication.
- User Management: Manage user profiles, including profile picture updates.
- File Uploads: Upload and manage images via Cloudinary.
- Online/Offline Status: Track and broadcast user presence in real-time.
- Secure API: Input validation, JWT-based authentication, and encrypted WebSocket connections.

Tech Stack
----------

- Node.js: JavaScript runtime for building scalable server-side applications.
- Express.js: Web framework for creating RESTful APIs.
- MongoDB: NoSQL database for storing user and message data.
- Socket.IO: Real-time, bidirectional communication.
- Cloudinary: Image hosting and management.
- JWT: Secure authentication using JSON Web Tokens.
- Bcrypt: Password hashing for secure storage.

Getting Started
---------------

Prerequisites:

- Node.js (v16 or higher)
- MongoDB (local or cloud instance)
- Cloudinary account for image uploads

Installation:

1. Navigate to the 'backend' directory:
   cd backend

2. Install dependencies:
   npm install

3. Create a .env file in the backend directory with the following content:
   PORT=5000  
   MONGO_URI=your_mongodb_connection_string  
   JWT_SECRET=your_jwt_secret  
   CLOUDINARY_CLOUD_NAME=your_cloud_name  
   CLOUDINARY_API_KEY=your_api_key  
   CLOUDINARY_API_SECRET=your_api_secret

Running the Application
-----------------------

Start the development server:
   npm run dev

Start the production server:
   npm start

Project Structure
-----------------

src/
├── routes/       - API routes for authentication and messaging  
├── controllers/  - Business logic for handling requests  
├── models/       - MongoDB schemas for users and messages  
├── lib/          - Utility functions, DB connection, and WebSocket setup  
├── middleware/   - Authentication and error-handling middleware  

API Endpoints
-------------

Authentication Routes:
- POST /api/auth/signup: Register a new user
- POST /api/auth/login: Log in an existing user
- POST /api/auth/logout: Log out the current user
- PUT /api/auth/update-profile: Update user profile picture
- GET /api/auth/check: Check if the user is authenticated

Messaging Routes:
- GET /api/messages/users: Get list of users for sidebar
- GET /api/messages/:id: Fetch messages with another user
- POST /api/messages/send/:id: Send a message to another user

Database Schema
---------------

Users:
- email: User's email (unique)
- fullName: User's full name
- password: Hashed password
- profilePic: URL of profile picture
- timestamps: Auto-generated

Messages:
- senderId: Reference to sender's user ID
- receiverId: Reference to receiver's user ID
- text: Message content
- image: URL of attached image (if any)
- timestamps: Auto-generated

Security Considerations
------------------------

- Authentication: Stateless JWT-based auth
- Password Security: Hashed using bcrypt
- WebSocket Security: Encrypted communication
- Input Validation: Proper sanitization and validation
- Environment Variables: Sensitive data stored in .env files

Scalability & Performance
-------------------------

- Caching: Use Redis to cache frequently accessed data
- Database Optimization: Indexing in MongoDB for faster queries
- Horizontal Scaling: Scale WebSocket connections as needed
- Efficient Resource Management: Optimized request and WebSocket handling


Author
------

Name  : Shashi Kumar  
Email : shashikrpatwa.work36@gmail.com
