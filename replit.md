# ReportPro Mobile Application

## Overview

This is a comprehensive mobile report management application built with React, TypeScript, and Firebase. The system allows users to create, manage, and track various types of reports including safety inspections, maintenance logs, and incident reports. The application features a mobile-first design with signature capture capabilities, image uploads, and real-time data synchronization.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client-side application is built using React with TypeScript and employs a modern component-based architecture. The UI is constructed using shadcn/ui components built on top of Radix UI primitives, providing accessible and customizable interface elements. The application uses Wouter for lightweight client-side routing and TanStack React Query for efficient data fetching and state management. The design system utilizes Tailwind CSS for styling with a comprehensive design token system defined in CSS variables.

The mobile-first approach ensures optimal user experience across different screen sizes, with a bottom navigation pattern for easy thumb navigation. The application implements a protected route system that redirects unauthenticated users to the login page.

### Backend Architecture
The backend follows a hybrid serverless architecture combining Express.js for API routes with Firebase services for authentication and data storage. The server uses in-memory storage for development with a clean storage interface that can be easily swapped for production databases. The application is configured to use Drizzle ORM with PostgreSQL schemas, though the current implementation uses Firebase Firestore for data persistence.

The server implements middleware for request logging and error handling, with development-specific features like Vite integration for hot module replacement during development.

### Data Storage Solutions
The application uses a dual-storage approach:
- **Development**: In-memory storage with a clean interface pattern
- **Production**: Firebase Firestore for real-time data synchronization and offline capabilities
- **Database Schema**: Defined using Drizzle ORM with PostgreSQL-compatible schemas including users and reports tables with comprehensive field definitions

The schema includes support for JSON data types for flexible storage of arrays (images) and complex objects (signatures), with proper type safety through Zod validation schemas.

### Authentication and Authorization
Authentication is handled through Firebase Auth, providing secure user registration and login functionality. The system stores additional user profile information in Firestore, including role-based access control with admin and user roles. The authentication context provides global access to user state throughout the application with automatic session persistence.

### External Dependencies
- **Firebase Services**: Authentication, Firestore database, and Cloud Storage for image uploads
- **shadcn/ui + Radix UI**: Comprehensive component library for accessible UI elements
- **TanStack React Query**: Server state management and data synchronization
- **Signature Capture**: Custom HTML5 Canvas implementation for digital signatures
- **Image Handling**: File upload capabilities with Firebase Storage integration
- **PDF Generation**: jsPDF for report export functionality
- **Development Tools**: Vite for fast development builds and hot reloading, with ESBuild for production bundling

The application is configured for deployment on Replit with specific plugins and error handling for the development environment. The build system supports both development and production modes with appropriate optimizations for each environment.