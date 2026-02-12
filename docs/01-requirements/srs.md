# Software Requirements Specification (SRS)
## AI-Powered Social Media Moderation System
## 1. Introduction

### 1.1 Purpose
This document describes the requirements for the AI-Powered Social Media Moderation System.
The system is designed to detect abusive or toxic content using AI and apply automated moderation policies.


### 1.2 Scope
The system will:
- Allow users to register and log in
- Allow users to comments
- Analyze comments using an AI model
- Apply moderation rules automatically
- Provide an admin dashboard for monitoring users and moderation actions

The system will not:
- Support real-time chat (initial version)
- Integrate with external social media platforms (initial version)


### 1.3 Definitions, Acronyms, and Abbreviations

| Term | Meaning |
|------|---------|
| AI | Artificial Intelligence |
| ML | Machine Learning |
| API | Application Programming Interface |
| Admin | System administrator |
| NLP | Natural Language Processing |


## 2. Overall Description

### 2.1 Product Perspective
The system is a web-based platform where user-generated content is monitored by an AI service before being accepted.
It consists of:

- Frontend interface
- Java backend service
- SQL database
- Python AI microservice


### 2.2 Product Functions
Main system functions:

- User registration and authentication
- Comment submission
- AI-based toxicity detection
- Moderation rule enforcement
- Admin dashboard for monitoring


### 2.3 User Classes and Characteristics

| User Type | Description |
|-----------|-------------|
| Normal User | Can register, log in, and comment |
| Admin | Can monitor users, view reports, and apply moderation actions |


### 2.4 Operating Environment

| Component | Technology |
|-----------|------------|
| Backend | Java Spring Boot |
| Database | MySQL |
| AI Service | Python + FastAPI |
| Frontend | Web-based UI |
| Deployment | Cloud server using Docker |


### 2.5 Design and Implementation Constraints

- Backend must be implemented using Java and Spring Boot
- Database must be relational (MySQL)
- AI service must run as a separate microservice
- System must be deployable on a cloud environment


## 3. System Features (Functional Requirements)

### 3.1 User Registration
**Description:**  
Users can create accounts.

**Inputs:**
- Username
- Email
- Password

**Outputs:**
- Confirmation message
- User stored in database


### 3.2 User Login
**Description:**  
Users can log into the system.

**Inputs:**
- Email
- Password

**Outputs:**
- Authentication success or failure



### 3.3 Comment Submission
**Description:**
Users can submit comments on posts.

**Process:**
1. User submits comment
2. Backend sends comment to AI service
3. AI returns toxicity result
4. System applies moderation rules
5. Comment stored with moderation status


### 3.4 Moderation Rules

| Offense Count | Action |
|--------------|--------|
| 1 | Warning |
| 3 | Temporary mute |
| 5 | Permanent ban |


### 3.5 Admin Dashboard
Admin can:
- View toxic comments
- View user offense history
- Ban or unban users
- Monitor moderation actions

## 4. External Interface Requirements

### 4.1 User Interface
- Web-based interface
- Comment input field
- Admin dashboard with tables and charts


### 4.2 Backend API Interfaces

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/users` | POST | Register user |
| `/login` | POST | User login |
| `/comments` | POST | Add comment |
| `/admin/users` | GET | List users |

### 4.3 AI Service API

**Endpoint:**
