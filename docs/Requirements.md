# TutorMe Hybrid Application: Requirements Document

## 1. Introduction
**TutorMe** is a Zoom/Blackboard hybrid platform designed for real-time communication, content sharing, and collaboration in virtual learning environments. This document outlines the functional and non-functional requirements for the system.

## 2. Functional Requirements
Functional requirements specify what the system must do, covering both the core and optional features.

### 2.1 User Management
- **User Registration & Authentication**
  - Users must be able to create accounts with email and password.
  - Implement OAuth-based authentication for third-party sign-in (e.g., Google, Facebook).
  - Users must receive email verification for account activation.
- **User Profiles**
  - Users can create and edit their profiles with the following fields:
    - Name, Profile Picture.

### 2.2 Video Conferencing & Audio
- **Real-time Video & Audio Communication**
  - Users must be able to join and participate in video conferencing sessions.
  - System must allow users to mute/unmute their audio and turn their video on/off.
- **Screen Sharing**
  - Users can share their screen during video conferencing.
- **Video Recording**
  - Enable session hosts to record video sessions and save them to a specified location (e.g., cloud storage).

### 2.3 Chat Functionality
- **Real-time Chat**
  - Participants must be able to send and receive real-time chat messages within a session.
- **Private Messaging**
  - Users must be able to send private messages to other participants in the session.
- **File Sharing**
  - Users must be able to upload and share files (e.g., PDFs, Word documents) via the chat interface.

### 2.4 Collaboration Features
- **Whiteboard**
  - A shared virtual whiteboard must be available for collaborative drawing and note-taking.
- **Annotation Tools**
  - Users must be able to annotate content shared on the screen or whiteboard.

### 2.5 Scheduling and Session Management
- **Session Scheduling**
  - Tutors can schedule sessions and invite participants via email, sharable link, or calendar integration (e.g., Google Calendar).
- **Session History**
  - Users must be able to view past sessions, including recordings, transcripts, and shared files.
- **Session Controls (Host/Moderator)**
  - Hosts must be able to mute/unmute participants, remove participants from the session, or lock the session.

~~###2.6 Polling and Surveys~~  
-~~**Live Polls**~~
  - ~~Hosts can create polls during a session, and participants must be able to vote.~~
- ~~**Survey Results**~~
  - ~~Display poll results in real-time or after the session.~~

### 2.7 File and Content Sharing
- **File Upload**
  - Users must be able to upload, share, and download files during a session.
- **Cloud Integration**
  - The system must integrate with cloud storage solutions like Google Drive or Dropbox for saving and retrieving shared files.

### 2.8 Notifications and Alerts
- **Real-time Alerts**
  - Users must receive notifications for important events (e.g., new message, user joins session, ~~poll creation~~).
- **Email Notifications**
  - Users must receive email notifications for session invitations, updates, and cancellations.

## 3. Non-Functional Requirements
These define how the system performs its functions, including performance, security, and usability.

### 3.1 Performance
- **Real-time Responsiveness**
  - The system must support real-time interaction (video, chat, and whiteboard) with minimal latency.
- **Scalability**
  - The system must handle sessions with up to 5 participants, with scalable infrastructure to support larger user bases.
- **Adaptive Video Quality**
  - The system must adjust video quality based on network conditions to ensure smooth communication.

### 3.2 Security
- **Encryption**
  - All data, including chat messages, video streams, and file uploads, must be encrypted (e.g., using SSL/TLS) to ensure security.
- **Authentication**
  - User data must be secured through JWT (JSON Web Tokens) and password hashing (e.g., bcrypt).
- **Access Control**
  - Role-based access control (RBAC) must ensure that only authorized users can access certain features or data.
- **Data Privacy**
  - The system must comply with privacy regulations (e.g., GDPR) to ensure user data is protected.

### 3.3 Reliability and Availability
- **System Uptime**
  - The system must have 99.9% uptime to ensure that sessions are not interrupted due to server downtime.
- **Failover Mechanism**
  - Implement automated failover for critical services like video conferencing and chat.

### 3.4 Usability
- **Intuitive User Interface**
  - The user interface must be clean and easy to use, with a focus on clear navigation.
- **Mobile Responsiveness**
  - The platform must be fully responsive, working seamlessly on desktops, tablets, and smartphones.
- ~~**Accessibility**~~
  - ~~The system must comply with accessibility standards (e.g., WCAG) to ensure that it can be used by people with disabilities.~~

### 3.5 Scalability
- ~~**Load Balancing**~~
  - ~~The system must use load balancing techniques to distribute traffic across multiple servers for scalability.~~
- **Containerization**
  - The system must be containerized using Docker to simplify deployment and scaling across multiple environments (development, testing, production).

### 3.6 Maintainability
- **Modular Codebase**
  - The codebase must follow a modular architecture to ensure that individual components (e.g., video, chat, file sharing) can be easily updated or replaced.
- **Automated Testing**
  - The system must include automated unit and integration tests for continuous validation of core functionalities.

### 3.7 Data Backup and Recovery
- **Daily Backups**
  - All user data, including session recordings and files, must be backed up daily.
- **Disaster Recovery**
  - The system must have a disaster recovery plan to restore services in case of data loss or failure.

## 4. Assumptions and Constraints
- **Assumptions:**
  - Users will have stable internet connections for optimal video conferencing.
  - Users will have basic familiarity with virtual learning tools (e.g., video calls, chat).
- **Constraints:**
  - The system must operate within browser-based environments (e.g., Chrome, Firefox).
  - Limited to a maximum of 5 participants per session during the initial release.

## 5. Future Enhancements
- **AI-based Transcription:** Automatically transcribe live video and audio sessions.
- **Multilingual Support:** Provide real-time language translation for chat and captions.
- **Mobile App:** Build a native mobile app for both iOS and Android platforms.

---

**Conclusion:**
This **Requirements Document** serves as the foundation for the development of the TutorMe Zoom/Blackboard hybrid project. It defines what the system should do (functional requirements) and how it should perform (non-functional requirements). As the project progresses, the requirements can be refined and expanded to accommodate new features or improvements.

