# Backend Environment Setup Guide

This document provides step-by-step instructions to set up your backend environment with Firebase, SMTP for Google App, and Prisma ORM for database management.

## 1. Firebase Google Application Credentials

### Step 1: Create a Firebase Project
- Go to the [Firebase Console](https://console.firebase.google.com/).
- Click on "Add Project" and follow the instructions to create a new project.

### Step 2: Generate Service Account Key
- In the Firebase Console, navigate to "Project Settings."
- Select the "Service accounts" tab.
- Click on "Generate new private key" and download the JSON file.
- Save the JSON file in your project directory at `./credentialKey/credentialKey.json`.

### Environment Variable
Set the environment variable in your `.env` file:
GOOGLE_APPLICATION_CREDENTIALS=./credentialKey/credentialKey.json
## 2. Firebase API Key

### Step 1: Access Project Settings
- In the Firebase Console, go to "Project Settings."

### Step 2: Retrieve API Key
- Under the "General" tab, locate the "Your apps" section.
- Find the API key associated with your app.

### Environment Variable
Set the environment variable in your `.env` file:
FIREBASE_API_KEY="your_firebase_api_key_here"
## 3. SMTP Google App

### Step 1: Enable 2-Step Verification
- Go to [Google Account](https://myaccount.google.com/).
- Click on the "Security" tab.
- Under "Signing in to Google," find and enable "2-Step Verification."

### Step 2: Generate App Password
- After enabling 2-Step Verification, go back to the "Security" tab.
- Scroll down to "App passwords."
- Select "Mail" as the app and "Other" as the device, then generate the app password.

### Environment Variables
Set the environment variables in your `.env` file:
EMAIL_USER="your_email_here"
EMAIL_PASS="your_app_password_here"
## 4. Database URL (Using Prisma ORM)

### Step 1: Set Up Database
- Ensure your database is running and accessible.
- Note the database connection details (username, password, host, port, and database name).

### Step 2: Configure Prisma
- In your Prisma schema file, set the datasource block with the database URL.

### Database URL Structure

The database URL in Prisma ORM follows this structure:
mysql://USER@HOST/DATABASE
| Component | Placeholder | Description |
|-----------|-------------|-------------|
| Host      | HOST        | The IP address or domain name of your database server (e.g., `localhost` or `db.example.com`). |
| Port      | PORT        | The port number on which your database server is running (e.g., `3306` for MySQL). |
| User      | USER        | The username of your database user (e.g., `janedoe`). |
| Password  | PASSWORD    | The password associated with your database user. |
| Database  | DATABASE    | The name of the specific database you want to connect to (e.g., `mydb`). |

### Environment Variable
Set the environment variable in your `.env` file:
DATABASE_URL="mysql://USER@HOST/DATABASE"
## Conclusion
Ensure all environment variables are correctly set in your `.env` file. This setup will enable seamless integration with Firebase, SMTP for sending emails, and Prisma ORM for database management.
