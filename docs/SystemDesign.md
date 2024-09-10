# TutorMe Hybrid Application: System Design Document

## 1. Introduction
This document provides an overview of the system design for the TutorMe Hybrid Application. The project combines Zoom-like video conferencing capabilities with Blackboard-style content sharing and collaboration tools. The system will be scalable, secure, and accessible, using modern web technologies.

---

## 2. System Overview

### 2.1 Architecture Style
The system follows a **client-server architecture**:
- **Frontend:** Built with React (or Next.js for server-side rendering).
- **Backend:** Node.js/Express for handling API requests and WebSocket connections.
- **Database:** Combination of MongoDB for session data and user activity logging, and MySQL for relational data like user profiles, authentication.
- **Real-time Communication:** WebRTC and Socket.IO for video, audio, chat, and collaborative features.
- **Deployment:** deployed using Docker.

### 2.2 System Components
- **Frontend (React/Next.js)**  
  User Interface (UI): Designed for video conferencing, file sharing, collaboration tools, and user management.  
  Chat, Whiteboard, and Video components interact with the backend via WebSocket connections and HTTP API.
  
- **Backend (Node.js/Express)**  
  RESTful API for managing user profiles, authentication, session management, and resource sharing.  
  WebSocket-based real-time server for chat communication.  
  WebRTC with SFU for real-time video and audio communication.
  Handles API authentication (JWT), data validation, and business logic.
  
- **Database Layer**  
  **MySQL** for relational data like user profiles, session schedules, and role-based access control.  
  **MongoDB** for non-relational data like real-time session data, chat logs, and whiteboard activity.
  
- **File Storage**  
  Integration with cloud services (e.g., AWS S3, Google Drive) for storing session recordings, shared files, and documents.

---

## 3. Technology Stack

| Component              | Technology                         |
|------------------------|-------------------------------------|
| Frontend               | React/Next.js, WebRTC, Socket.IO    |
| Backend                | Node.js, Express.js, Socket.IO      |
| Relational Database    | MySQL                              |
| Non-relational Database| MongoDB                            |
| Real-time Communication| WebRTC, Socket.IO                  |
| Authentication         | JWT, OAuth 2.0                     |
| Storage                | AWS S3 or Google Drive             |
| CI/CD                  | Docker, Kubernetes, GitHub Actions |
| Deployment             | Docker, Kubernetes, Nginx          |

---

## 4. Detailed Component Design

### 4.1 Frontend
- **UI/UX**: The user interface will be built using React or Next.js to create responsive, interactive components.
  - **Video Conferencing Component**: Integrates WebRTC for real-time video and audio streaming.
  - **Chat Component**: Real-time text-based chat built with Socket.IO for instantaneous communication.
  - **Whiteboard**: Allows real-time drawing and collaboration with participants.
  - **File Sharing**: Users can upload, share, and download files during sessions.
  
- **State Management**: React’s Context API or Redux will handle global state, such as user session data, chat messages, and notifications.

### 4.2 Backend
- **REST API**: Built with Node.js and Express.js for serving user data, session information, and managing file uploads.
  - **Authentication**: Implemented using JWT for secure authentication and session management.
  - **WebSocket Management**: Socket.IO used to handle real-time chat, notifications, and video conferencing.
  
- **API Endpoints**:
  - `/api/auth/register` – User registration.
  - `/api/auth/login` – User login and token issuance.
  - `/api/sessions/create` – Schedule and create a new session.
  - `/api/files/upload` – File upload during a session.
  
- **Session Management**: Handles session creation, recording, and storage of session data.
  
- **WebRTC Signaling**: The backend will act as a signaling server for WebRTC, coordinating peer connections for video/audio streaming.

### 4.3 Database Layer
- **MySQL**:  
  **User Management**: Stores relational data, including user profiles, roles, session scheduling, and permissions.  
  **Session Records**: Stores past sessions with metadata like session duration, host, and participants.

- **MongoDB**:  
  **Session Data**: Used for real-time data, such as chat logs, whiteboard interactions, and user activity.  
  **Non-relational Data**: Stores real-time communications data such as chat messages, whiteboard drawings, and session statistics.

---

## 5. System Workflow

### 5.1 User Authentication
1. The user registers or logs in using the OAuth 2.0 service or via traditional email/password (JWT tokens issued for session management).
2. The frontend sends a POST request to `/api/auth/login` or `/api/auth/register`, and the backend validates the credentials.
3. On successful authentication, the JWT token is sent to the frontend and stored in local storage for future authenticated requests.

### 5.2 Real-time Communication (WebRTC & Socket.IO)
1. When a user joins a session, the frontend establishes a WebSocket connection with the backend (via Socket.IO).
2. The backend acts as the signaling server for WebRTC to help users establish peer-to-peer video/audio connections.
3. All chat messages, whiteboard updates, and notifications are sent through WebSocket channels.

### 5.3 File Upload and Storage
1. Users upload files during a session, and the frontend sends the files to the backend via a POST request to `/api/files/upload`.
2. The backend processes and stores the files in AWS S3 or Google Drive.
3. The URLs of the stored files are saved in the database and sent back to users for download.

---

## 6. Non-Functional Requirements

### 6.1 Scalability
- Horizontal scaling with Docker to handle an increasing number of users and sessions.
- Load balancing to distribute requests across servers for performance optimization.

### 6.2 Security
- End-to-end encryption of video, audio, and chat data using TLS.
- Secure authentication and authorization using JWT tokens.
- Role-based access control (RBAC) to ensure only authorized users can perform certain actions.

### 6.3 Availability
- **Uptime**: Targeting 99.9% uptime with automated failover and load balancing.
- **Backups**: Daily backups of the database and session data.

---

## 7. Deployment and DevOps

### 7.1 Containerization
- The system will use Docker to containerize all services (frontend, backend, database).
- Docker Compose will manage local development environments, while Kubernetes (K8s) will be used in production for orchestration.

### 7.2 CI/CD Pipeline
- GitHub Actions or Jenkins for continuous integration and automated testing.
- Deployments automated using Docker, Kubernetes, and Helm for production releases.

---

## 8. Conclusion
This system design provides a scalable, secure, and efficient architecture for the **TutorMe Hybrid Application**, ensuring a seamless user experience for real-time communication and collaboration in virtual learning environments. The design is modular, allowing future enhancements such as AI-based transcription and mobile apps.

---


