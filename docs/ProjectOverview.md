# TutorMe - Zoom/Blackboard Hybrid Application

## Project Title 
TutorMe

## Project Description
TutorMe is a "hybrid" video conferencing platform designed to provide seamless real-time communication, content sharing, and collaboration features. It integrates the functionalities of Zoom/blakcboard-like video meetings with content management, making it ideal for small online tutoring sessions, small online classes, and collaborative environments.

The application aims to support high-quality video conferencing, live chat, screen sharing, and collaborative tools such as whiteboards, file sharing, and annotation tools, providing an engaging and interactive experience for users.

## Project Objectives
- Enable Real-time Communication: Provide high-quality video and audio conferencing with support for multiple participants.
- Content Sharing: Facilitate sharing of documents, presentations, and other materials during sessions.
- Interactive Learning: Include features like whiteboards, collaborative editing, and annotation tools to enhance participation.
- User Management: Allow user profiles, session scheduling, and participant management.
- Seamless Integration: Integrate with existing tools such as cloud storage, file sharing, and calendar services.
- Scalability and Security: Build a scalable and secure system to support large numbers of users while ensuring data privacy and integrity.

## Key Features
- Video Conferencing: Real-time video and audio with screen sharing capabilities.
- Chat Functionality: Live chat with text-based communication, file sharing, and reactions.
- User Profiles and Authenication: Customizable user profiles, including profile picures and authentication for secure access.
- Whiteboard: Virtual whiteboard for drawing and collaboration during sessions
- Closed Captioning and Transcripts: Real-time closed captioning and automatic transcript generation for accessibilty.
- Integration with Cloud Storage: File sharing integration with serices like Google Drive or Dropbox.
- Calendar Integration: Schedule session with Google Calendar and other platforms.

## Project Scope
- Core Components:
    - Backend: A Node.js and Express server for handling API requests, WebSocket connections(via Socket.IO), and WebRTC integration for real-time communication.
    - Frontend: A React frontend to create a responsive intuitive user interface.
    - Database: Use a combination of MySQL for relational data (e.g., user management) and MongoDB for non-relational data (e.g., session streams, chat histories).
    - Real-time Communication: Implement WebRTC fro video and audio functionality, and Socket.IO for real-time chat and session updates.

- Additional Features:
    - Security features: authenication, authorization, and encryption of communication channels.
    - Performance optimization fro smooth user experiences, including video quality aadjustments based on network conditions.
    - Scalability features: load balancing and containerization with docker fro efficient deployment.

## Technology Stack
- Frontend: React or Next.js for building interactive, responsive user interfaces.
- Backend: Node.js with Express for handling API requests and real-time communication using WebSockets (Socket.IO) and WebRTC.
- Databases:
    - MySQL for relational data (user profiles, authentication, scheduling).
    - MongoDB for non-relational data (session metadata, chat logs, file storage).
- WebSockets: Socket.IO for real-time communication (chat, live updates).
- WebRTC: For video and audio conferencing features with SFU.
- Docker/Kubernetes: Containerization and orchestration for deployment and scaling.
- Security: JWT (JSON Web Tokens) for authentication, SSL encryption for communication.

## Milestones and Timeline
- Planning & Design: (TBD weeks)
    - System design, UML diagrams, and technical specifications.
- Backend Development: (TBD weeks)
    - Set up Node.js server, authentication, API routes, database connections, and WebSocket setup.
- Frontend Development: (TBD weeks)
    - Build UI components, integrate API routes, chat functionality, and real-time features.
- Testing & QA: (TBD weeks)
    - Unit tests, integration tests, and end-to-end testing of video, chat, and content-sharing functionalities.
- Deployment: (TBD weeks)
    - Dockerize the application, set up CI/CD pipelines, and deploy to a cloud service provider.
- Launch & Maintenance: Ongoing support and feature updates.

## PotentialRisks and Mitigations
- Scalability Challenges:
    - Risk: Potential performance bottlenecks with large numbers of users.
    - Mitigation: Implement/Integrate SFU(selective forwarding unit)load balancing and horizontal scaling using cloud services like AWS or Google Cloud.
- Security Concerns:
    - Risk: Data breaches or unauthorized access.
    - Mitigation: Ensure SSL encryption, use OAuth or JWT for secure user authentication, and regularly audit security measures. Also use salting and hashing.
- Video Quality Issues:
    - Risk: Low video quality under poor network conditions.
    - Mitigation: Implement adaptive video streaming using WebRTC.

## Contributors and Stakeholders
- Project Lead/Developer: Milton Long
- Stakeholders: Potential users (students, tutors, educators)~~, community contributors, collaborators.~~

## Future Enhancements
- Implement AI-based features like automated note-taking or real-time language translation.
- Add advanced analytics for educators, including insights on student engagement and participation.
- Expand to mobile platforms with React Native or other mobile frameworks.
