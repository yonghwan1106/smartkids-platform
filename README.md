# SmartKids Platform

A comprehensive child management application built with React and Node.js.

## Features

- Child profile management
- Health tracking and medical records
- Learning progress monitoring
- Meal planning and nutrition tracking
- School life management
- User authentication and security

## Technology Stack

- **Frontend**: React 19.1, TypeScript, Vite, Tailwind CSS
- **Backend**: Node.js, Express, PostgreSQL
- **Database**: Neon PostgreSQL (cloud)
- **Authentication**: JWT with bcrypt
- **Deployment**: Vercel

## Run Locally

**Prerequisites:** Node.js

1. Install dependencies:
   ```bash
   npm install
   ```

2. Set up environment variables:
   - Copy `.env.example` to `.env`
   - Add your database connection string and JWT secret

3. Run the development server:
   ```bash
   npm run dev
   ```

4. Run the backend server:
   ```bash
   cd server && npm start
   ```

## Deployment

This application is configured for deployment on Vercel with serverless functions.

## Database Schema

The application uses PostgreSQL with tables for:
- Users and authentication
- Children profiles
- Health records and vaccinations
- Learning activities and progress
- Meal records and nutrition
- School activities and events