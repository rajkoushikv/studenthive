# Deployment Manual for StudentHive

## Overview
This document provides deployment instructions for the StudentHive project. StudentHive uses a React-based frontend and a backend comprising Node.js, Fastify, and MongoDB.

## Audience Definition
This deployment manual is intended for system administrators, IT personnel, or developers responsible for deploying and maintaining the StudentHive application.

## Platform-Specific Deployment Instructions
The deployment steps vary depending on the operating system. Below are detailed instructions for deploying StudentHive on Windows, macOS, and Linux.

### Prerequisite Installation
Ensure you have the following installed before deploying StudentHive:

- Node.js (LTS version recommended)
- MongoDB (latest stable release)
- Git
- React CLI

#### Windows
1. Download and install Node.js from [nodejs.org](https://nodejs.org/). Ensure Node.js and npm are added to your system's PATH.
2. Install MongoDB Community Edition. Follow the instructions from [mongodb.com](https://www.mongodb.com/try/download/community).
3. Verify the installations by running `node -v`, `npm -v`, and `mongod --version`.

#### macOS
1. Install Node.js using [Homebrew](https://brew.sh/):
   ```bash
   brew install node
   ```
2. Install MongoDB Community Edition with Homebrew:
   ```bash
   brew tap mongodb/brew
   brew install mongodb-community
   ```
3. Verify the installations by running `node -v`, `npm -v`, and `mongod --version`.

#### Linux (Ubuntu)
1. Install Node.js with APT:
   ```bash
   sudo apt-get install -y nodejs npm
   ```
2. Install MongoDB Community Edition with APT:
   ```bash
   sudo apt-get install -y mongodb
   ```
3. Verify the installations by running `node -v`, `npm -v`, and `mongod --version`.

### Configuration Instructions
After installing the prerequisites, follow these configuration steps for deploying StudentHive:

1. Clone the StudentHive repository from GitHub:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the backend directory and install the necessary dependencies:
   ```bash
   cd backend
   npm install
   ```
3. Configure environment variables, such as MongoDB connection strings and port numbers. Create a `.env` file with the following content:
   ```bash
   MONGODB_URI=<your-mongodb-connection-string>
   PORT=<backend-port>
   ```
4. Start the MongoDB server:
   ```bash
   mongod
   ```
5. Start the backend with Fastify:
   ```bash
   npm start
   ```
6. Navigate to the frontend directory and install the required dependencies:
   ```bash
   cd ../frontend
   npm install
   ```
7. Start the frontend development server:
   ```bash
   npm start
   ```

### Deployment Scripts or Code Snippets
The following scripts or code snippets can automate parts of the deployment process.

```bash
# Start backend and frontend in separate terminal windows
# Start MongoDB server
mongod &

# Start Fastify backend
cd backend
npm start &

# Start React frontend
cd ../frontend
npm start
```

### Testing and Troubleshooting
After deploying StudentHive, follow these steps to test the application:

1. Access the application in a web browser using the frontend server's address and port (default is `http://localhost:3000/`).
2. Test the application by performing common user actions (e.g., logging in, creating data, retrieving data).
3. Monitor the backend logs for any errors or warnings.

If you encounter issues, consider the following troubleshooting tips:

- **Frontend errors**: Check the console for error messages. Ensure all dependencies are installed correctly.
- **Backend errors**: Review the server logs for any errors. Verify MongoDB is running and accessible.
- **Connection issues**: Ensure the backend and frontend servers are running and accessible via the specified ports.
