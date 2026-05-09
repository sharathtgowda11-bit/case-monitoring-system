📋 README Highlights:
✅ Project Overview - Clear description of the system for Davangere Police Department

✅ Key Features - Detailed breakdown of:

Case Management
Hearing Tracking
Witness Management
Advanced Reporting
Excel Bulk Upload
User & Security Management
Search & Filtering
✅ Complete Tech Stack - All frontend, backend, and database technologies used

✅ Architecture Diagram - Visual representation of the 3-tier architecture

✅ Detailed Project Structure - Full directory layout with descriptions of each component

✅ Installation Instructions - Step-by-step setup guide including prerequisites and database initialization

✅ Configuration Guide - Environment setup for both frontend and backend with security notes

✅ How to Run - Commands for development and production builds

✅ Database Schema - Documentation of all tables, views, and indexes

✅ API Endpoints - Complete list of all REST endpoints organized by functionality

✅ User Roles & Permissions - Three-tier role system (Writer, SHO, SP) with detailed permissions

✅ Component Documentation - Overview of all key React components and utilities

✅ Development Guide - Scripts, best practices, and database migration tips

✅ Deployment Instructions - Production setup guide with Nginx configuration example

The README is professional, well-structured, and ready for developers to understand and work with your project! 🚔
README.md

md
# 🚔 Court Case Monitoring System - Davangere Police Department

> A comprehensive web-based platform for monitoring and managing court cases with real-time tracking, detailed reporting, and multi-role access control. Built for the Davangere Police Department.

![Language](https://img.shields.io/badge/TypeScript-90.5%25-blue)
![Backend](https://img.shields.io/badge/Node.js-Express-green)
![Frontend](https://img.shields.io/badge/React-19.2-cyan)
![Database](https://img.shields.io/badge/PostgreSQL-Database-336791)

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Database Schema](#database-schema)
- [API Endpoints](#api-endpoints)
- [User Roles & Permissions](#user-roles--permissions)
- [Key Components](#key-components)
- [Development](#development)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

The **Court Case Monitoring System** is an on-premise solution designed to help the Davangere Police Department efficiently track and manage court cases from registration through final judgment. The system provides comprehensive case documentation, hearing tracking, witness management, and detailed reporting capabilities.

### Core Objectives
- **Centralized Case Management** - All case information in one secure location
- **Real-time Hearing Tracking** - Never miss a court hearing date
- **Comprehensive Reporting** - Generate detailed reports on case status and outcomes
- **Multi-user Support** - Different roles with specific access levels
- **Data Security** - Secure authentication and role-based access control

## ✨ Key Features

### 📝 Case Management
- **Case Registration** - Register new cases with complete information
- **Case Details Tracking** - Track all aspects of a case including:
  - Basic case information (crime number, sections of law, etc.)
  - Charge sheet details
  - Court information
  - Accused information and custody status
  - Witness details by category
  - Trial progress and stages
  - Judgment and conviction details
  
### 👂 Hearing Management
- Track all hearing dates and stages
- Monitor upcoming hearings (with 7-day and 3-day urgent views)
- Update hearing outcomes and remarks
- View hearing history for each case

### 👥 Witness Management
- Track witnesses by category:
  - Complainant witnesses
  - Mahazar/Seizure witnesses
  - Investigating Officer witnesses
  - Eye witnesses
  - Other witnesses
- Record witness support/hostility status

### 📊 Advanced Reporting
- **Case Status Reports** - Filter by various criteria
- **Hearing Status Reports** - Track upcoming and completed hearings
- **Conviction Reports** - View convicted accused and sentences
- **Higher Court Proceedings** - Track appeals and petitions
- **Export Functionality** - Generate PDF and Excel reports

### 📤 Excel Bulk Upload
- Import multiple cases at once using Excel spreadsheets
- Automatic validation and error handling
- Batch processing capabilities

### 🔐 User & Security Management
- **Role-based Access Control** with three user types:
  - **Writer** - Create and edit case information
  - **SHO** (Station House Officer) - Manage cases and hearings
  - **SP** (Superintendent of Police) - Administrative and user management
- User account management
- Password management and profile updates
- Secure authentication with JWT tokens
- Rate limiting and DDoS protection

### 📈 Search & Filtering
- Advanced case search with multiple filters
- Quick access to case details
- Filter by status, police station, crime number, etc.

## 🛠 Tech Stack

### Frontend
- **React 19.2.3** - UI library with hooks and modern patterns
- **React Router v7.12** - Client-side routing
- **TypeScript 5.9** - Type-safe development
- **Vite 7.2** - Build tool and development server
- **Tailwind CSS 4.1** - Utility-first CSS framework
- **jsPDF** - PDF report generation
- **XLSX** - Excel file handling
- **Lucide React** - Icon library

### Backend
- **Node.js** - JavaScript runtime
- **Express.js 5.1** - Web framework
- **TypeScript 5.9** - Type-safe server code
- **PostgreSQL** - Relational database
- **pg** - PostgreSQL client for Node.js
- **JWT (jsonwebtoken)** - Authentication tokens
- **bcryptjs** - Password hashing
- **Helmet** - Security headers
- **CORS** - Cross-origin resource sharing
- **Rate Limit** - API rate limiting
- **Morgan** - HTTP request logging

### Database
- **PostgreSQL** - Enterprise-grade relational database
- **PL/pgSQL** - Stored procedures and triggers
- Custom views and indexes for optimized queries

## 🏗 Architecture

The application follows a modern three-tier architecture:

┌─────────────────────────────────────────────────────────────┐ │ Frontend (React/Vite) │ │ ┌──────────────────────────────────────────────────────┐ │ │ │ Components │ Context │ Utils │ Types │ Styles │ │ │ └──────────────────────────────────────────────────────┘ │ └─────────────────────────────────────────────────────────────┘ ↕ (HTTP/REST API) ┌─────────────────────────────────────────────────────────────┐ │ Backend (Node.js/Express) │ │ ┌──────────────────────────────────────────────────────┐ │ │ │ Routes │ Controllers │ Middleware │ Config │ │ │ └──────────────────────────────────────────────────────┘ │ └─────────────────────────────────────────────────────────────┘ ↕ (Database Connection) ┌─────────────────────────────────────────────────────────────┐ │ Database (PostgreSQL) │ │ ┌──────────────────────────────────────────────────────┐ │ │ │ Tables │ Views │ Indexes │ Triggers │ Functions │ │ │ └──────────────────────────────────────────────────────┘ │ └─────────────────────────────────────────────────────────────┘

Code

## 📁 Project Structure

case-monitoring-system/ ├── src/ # Frontend application │ ├── components/ # React components │ │ ├── LoginPage.tsx # Authentication page │ │ ├── Dashboard.tsx # Main dashboard view │ │ ├── DashboardLayout.tsx # Layout wrapper │ │ ├── CaseEntryForm.tsx # Multi-step case entry │ │ ├── CaseDetail.tsx # Case details view │ │ ├── SearchCases.tsx # Case search interface │ │ ├── ExcelUpload.tsx # Bulk import │ │ ├── HearingUpdate.tsx # Hearing management │ │ ├── Reports.tsx # Reporting interface │ │ ├── UserManagement.tsx # User admin (SP only) │ │ ├── ChangePassword.tsx # Password management │ │ ├── UpdateProfile.tsx # Profile editing │ │ ├── ProtectedRoute.tsx # Route protection │ │ └── ... # Additional components │ ├── context/ # React Context providers │ │ ├��─ AuthContext.tsx # Authentication state │ │ └── CaseContext.tsx # Case data state │ ├── utils/ # Utility functions │ │ ├── pdfGenerator.ts # PDF report generation │ │ ├── excelGenerator.ts # Excel export │ │ ├── cn.ts # CSS class utilities │ │ └── ... │ ├── types/ # TypeScript types │ ├── App.tsx # Main application component │ ├── main.tsx # Entry point │ └── index.css # Global styles │ ├── server/ # Backend application │ ├── src/ │ │ ├── index.ts # Main server file │ │ ├── config/ # Configuration │ │ │ └── database.ts # Database connection │ │ ├── routes/ # API routes │ │ │ ├── auth.ts # Authentication endpoints │ │ │ ├── users.ts # User management │ │ │ └── cases.ts # Case endpoints │ │ ├── controllers/ # Request handlers │ │ ├── middleware/ # Express middleware │ │ │ └── logger.ts # Request logging │ │ └── types/ # TypeScript types │ ├── scripts/ │ │ └── init-db.ts # Database initialization │ ├── tsconfig.json │ ├── package.json │ └── .env.example │ ├── backend/ │ ├── schema.sql # PostgreSQL database schema │ └── java/ # (Legacy Java components) │ ├── public/ # Static assets ├── index.html # HTML template ├── package.json # Frontend dependencies ├── tsconfig.json # TypeScript config ├── vite.config.ts # Vite configuration ├── .env.example # Environment variables template ├── .gitignore # Git ignore rules └── README.md # This file

Code

## 🚀 Installation

### Prerequisites
- **Node.js** 16.0 or higher
- **PostgreSQL** 12.0 or higher
- **npm** or **yarn** package manager
- **Git** for version control

### Step 1: Clone the Repository

```bash
git clone https://github.com/sharathtgowda11-bit/case-monitoring-system.git
cd case-monitoring-system
Step 2: Install Frontend Dependencies
bash
npm install
Step 3: Install Backend Dependencies
bash
cd server
npm install
cd ..
Step 4: Create PostgreSQL Database
bash
# Connect to PostgreSQL
psql -U postgres

# Create the database
CREATE DATABASE case_monitoring;

# Exit PostgreSQL
\q
Step 5: Initialize Database Schema
bash
cd server
npm run db:init
cd ..
This will create all necessary tables, views, indexes, and triggers in the database.

⚙️ Configuration
Frontend Configuration
Create a .env file in the root directory:

env
# Backend API URL (default for local development)
VITE_API_URL=http://localhost:3001/api

# For production, update to your server address:
# VITE_API_URL=http://your-police-server:3001/api
Backend Configuration
Create a .env file in the server directory:

env
# Server Configuration
PORT=3001
NODE_ENV=development

# Database Configuration
DB_HOST=localhost
DB_PORT=5432
DB_NAME=case_monitoring
DB_USER=postgres
DB_PASSWORD=your_secure_password_here

# JWT Configuration
JWT_SECRET=your_very_long_and_secure_jwt_secret_key_here_minimum_32_characters
JWT_EXPIRES_IN=15m
JWT_REFRESH_EXPIRES_IN=7d

# CORS Configuration
FRONTEND_URL=http://localhost:5173

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
Important Security Notes
⚠️ PRODUCTION DEPLOYMENT:

Use strong, randomly generated JWT secrets (minimum 32 characters)
Set NODE_ENV=production
Update FRONTEND_URL to your actual frontend domain
Use HTTPS in production
Enable proper database backups
Use environment-specific configuration management
Development Mode
Terminal 1 - Start Backend Server:

bash
cd server
npm run dev
Expected output:

Code
============================================================
  🚔 Police Case Monitoring System - Backend Server
============================================================
  ✅ Server running at: http://localhost:3001
  ✅ API base URL: http://localhost:3001/api
  ✅ Health check: http://localhost:3001/api/health
  ✅ Environment: development
  ✅ CORS origin: http://localhost:5173
============================================================
Terminal 2 - Start Frontend Dev Server:

bash
npm run dev
Expected output:

Code
VITE v7.2.4  ready in 200 ms

➜  Local:   http://localhost:5173/
➜  press h + enter to show help
Production Build
Build Frontend:

bash
npm run build
This creates an optimized build in the dist directory.

Build Backend:

bash
cd server
npm run build
npm start
📊 Database Schema
Main Tables
cases Table
Central table containing all case information with 50+ columns including:

Case identification (crime_number, sl_no)
Police station and investigation details
Court information and charge sheets
Accused information and custody status
Trial progress and stages
Judgment and conviction details
Timestamps and user tracking
Indexes:

crime_number - Fast case lookups
next_hearing_date - Hearing scheduling
police_station - Station-wise filtering
judgment_result - Conviction tracking
witness_details Table
Tracks witnesses by category with support/hostility status:

Complainant witnesses
Mahazar/Seizure witnesses
IO (Investigating Officer) witnesses
Eye witnesses
Other witnesses
hearings Table
Dynamic list of all hearing dates and stages for case tracking

accused_convictions Table
Names and sentences of convicted accused

higher_court_details Table
Information about appeals and petitions in higher courts (REV, REW, APP, CP, WP)

Database Views
v_upcoming_hearings - Cases with hearings within 7 days
v_urgent_hearings - Cases with hearings within 3 days
v_case_summary - Complete case information with related data
🔌 API Endpoints
Authentication Routes (/api/auth)
Code
POST   /login           - User login (credentials → JWT token)
POST   /logout          - User logout
GET    /me              - Get current user information
PUT    /password        - Change password
PUT    /profile         - Update user profile
User Management Routes (/api/users) - SP Role Only
Code
GET    /                - List all users
POST   /                - Create new user
PUT    /:id            - Update user
DELETE /:id            - Delete user
Case Management Routes (/api/cases)
Code
GET    /                - List all cases (with filters)
POST   /                - Create new case (Writer, SHO)
GET    /:id             - Get case details
PUT    /:id             - Update case (Writer, SHO)
DELETE /:id             - Delete case (SHO, SP)
GET    /search          - Search cases (advanced filters)
POST   /bulk-upload     - Bulk import from Excel
GET    /reports         - Generate reports
PUT    /:id/hearings    - Update case hearings
System Routes
Code
GET    /api/health      - Health check endpoint
👥 User Roles & Permissions
1. Writer
Permissions:

Create new cases
Edit case information
Upload cases via Excel
View all cases
Search cases
Update personal profile
Change password
Restrictions:

Cannot delete cases
Cannot manage users
Cannot update hearings
Cannot generate reports
2. SHO (Station House Officer)
Permissions:

All Writer permissions
Update hearing information
Delete cases
Generate reports
View case analytics
Restrictions:

Cannot manage users
3. SP (Superintendent of Police)
Permissions:
All SHO permissions
Create and manage users
View user activity logs
System administration
Full report access
User role management
🧩 Key Components
Frontend Components
Authentication

LoginPage.tsx - Secure login interface with JWT handling
Case Management

CaseEntryForm.tsx - Multi-step form for comprehensive case details
CaseDetail.tsx - Complete case view with all related information
SearchCases.tsx - Advanced case search with filters
ExcelUpload.tsx - Bulk import functionality
Hearing & Updates

HearingUpdate.tsx - Manage hearing dates and outcomes
Dashboard.tsx - Overview and statistics
Reporting

Reports.tsx - Generate and export reports in PDF/Excel
Administration

UserManagement.tsx - User CRUD operations (SP only)
ChangePassword.tsx - Password management
UpdateProfile.tsx - Profile editing
State Management
AuthContext

User authentication state
JWT token management
User role and permissions
Login/logout functionality
CaseContext

Case data state
Case operations
Cached case list
Search filters
Utilities
PDF Generation (pdfGenerator.ts)

Generate detailed PDF reports
Case summary PDFs
Multiple report formats
Excel Handling (excelGenerator.ts)

Export cases to Excel
Parse Excel imports
Data validation
🔧 Development
Available Scripts
Frontend:

bash
npm run dev       # Start dev server (port 5173)
npm run build     # Create production build
npm run preview   # Preview production build
Backend:

bash
cd server
npm run dev       # Start dev server with hot reload (tsx watch)
npm run build     # Compile TypeScript
npm start         # Run compiled server
npm run db:init   # Initialize database schema
Code Style & Best Practices
TypeScript for type safety throughout
React Hooks for functional components
Context API for state management
Tailwind CSS for responsive design
ESLint for code quality (recommended)
Prettier for code formatting (recommended)
Database Migrations
To apply schema changes in production:

Create a backup: pg_dump case_monitoring > backup.sql
Apply changes to backend/schema.sql
Run: npm run db:init in server directory
📦 Deployment
Prerequisites
Production PostgreSQL database
Node.js runtime environment
Reverse proxy (Nginx/Apache)
SSL/TLS certificates
Deployment Steps
Build the application:

bash
npm run build
cd server && npm run build && cd ..
Set production environment variables:

bash
export NODE_ENV=production
export FRONTEND_URL=https://your-domain.com
export VITE_API_URL=https://your-domain.com/api
# ... other variables
Start the backend:

bash
cd server
npm start
Serve frontend with Nginx:

Nginx
server {
    listen 80;
    server_name your-domain.com;
    
    root /path/to/dist;
    index index.html;
    
    location / {
        try_files $uri /index.html;
    }
    
    location /api/ {
        proxy_pass http://localhost:3001/api/;
    }
}
Enable HTTPS:

Use Let's Encrypt with Certbot
Configure SSL certificates in Nginx
📝 Contributing
Contributions are welcome! Please follow these guidelines:

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit changes (git commit -m 'Add some AmazingFeature')
Push to branch (git push origin feature/AmazingFeature)
Open a Pull Request
📄 License
This project is currently unlicensed. For licensing inquiries, please contact the project maintainers or Davangere Police Department.
