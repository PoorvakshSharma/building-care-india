# Building Care India - Full Stack Web Application

## Overview

This is a full-stack web application for Building Care India, a company specializing in premium cleaning solutions including room fresheners, tile cleaners, and other household cleaning products. The application serves as a product showcase and contact platform for potential customers.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Styling**: Tailwind CSS with custom design system
- **UI Components**: Radix UI primitives with shadcn/ui components
- **Animation**: Framer Motion for smooth animations and interactions
- **State Management**: React Query (TanStack Query) for server state management
- **Routing**: Wouter for lightweight client-side routing

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: PostgreSQL sessions with connect-pg-simple
- **API Design**: RESTful API with proper error handling

### Development Setup
- **Monorepo Structure**: Client, server, and shared code in single repository
- **Type Safety**: Shared TypeScript schemas between frontend and backend
- **Hot Reload**: Vite dev server with HMR for frontend development
- **Build Process**: Separate build steps for client (Vite) and server (esbuild)

## Key Components

### Database Schema
- **Products Table**: Stores product information including name, category, description, price, images, available fragrances, strengths, and features
- **Contact Inquiries Table**: Stores customer inquiries with contact information and product interest

### Frontend Components
- **Navigation**: Responsive navigation with smooth scrolling
- **Hero Section**: Animated landing section with call-to-action
- **Product Categories**: Dynamic product display grouped by categories
- **Features Section**: Company value propositions with animated cards
- **About Section**: Company information and statistics
- **Contact Form**: Customer inquiry form with validation
- **UI Components**: Comprehensive set of reusable components based on Radix UI

### Backend Services
- **Storage Layer**: Abstract storage interface with in-memory implementation for development
- **API Routes**: RESTful endpoints for products and contact inquiries
- **Error Handling**: Centralized error handling with proper HTTP status codes
- **Request Logging**: Middleware for API request logging

## Data Flow

1. **Product Data**: Products are seeded in memory storage (development) or loaded from PostgreSQL (production)
2. **API Requests**: Frontend makes HTTP requests to Express backend
3. **Database Operations**: Backend uses Drizzle ORM to interact with PostgreSQL
4. **Client State**: React Query manages server state with caching and synchronization
5. **Form Submissions**: Contact forms validate data and submit to backend API

## External Dependencies

### Frontend Dependencies
- **@radix-ui/***: Accessible UI primitives
- **@tanstack/react-query**: Server state management
- **framer-motion**: Animation library
- **wouter**: Lightweight routing
- **react-hook-form**: Form handling
- **zod**: Schema validation

### Backend Dependencies
- **drizzle-orm**: Type-safe ORM
- **@neondatabase/serverless**: Serverless PostgreSQL client
- **express**: Web framework
- **zod**: Schema validation
- **connect-pg-simple**: PostgreSQL session store

### Development Dependencies
- **vite**: Build tool and dev server
- **typescript**: Type checking
- **tailwindcss**: Utility-first CSS framework
- **tsx**: TypeScript execution for development

## Deployment Strategy

### Development
- **Local Development**: Vite dev server for frontend, tsx for backend hot reload
- **Database**: Uses Neon Database with connection string from environment variables
- **Build**: `npm run build` creates production-ready client and server bundles

### Production
- **Frontend**: Built with Vite, static assets served from `dist/public`
- **Backend**: Compiled with esbuild, runs on Node.js
- **Database**: PostgreSQL with Drizzle migrations
- **Environment**: Requires `DATABASE_URL` environment variable

### Build Process
1. Frontend builds to `dist/public` directory
2. Backend builds to `dist/index.js` with external dependencies
3. Static assets are served by Express in production
4. Database migrations can be run with `npm run db:push`

## User Preferences

Preferred communication style: Simple, everyday language.

## Changelog

Changelog:
- July 03, 2025. Initial setup