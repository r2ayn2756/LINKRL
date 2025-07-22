# GigRL - Musicians' Social Network Platform

## Overview

GigRL is a social networking platform designed specifically for musicians, venues, and music industry professionals. It combines social media features with professional networking and gig discovery, built as a full-stack web application with modern technologies.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript
- **Routing**: Wouter for lightweight client-side routing
- **Styling**: Tailwind CSS with custom theming (forest/green color scheme)
- **UI Components**: Shadcn/ui component library with Radix UI primitives
- **State Management**: TanStack Query for server state and caching
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database**: PostgreSQL with Drizzle ORM
- **Authentication**: Replit Auth with OpenID Connect
- **Session Management**: Express sessions with PostgreSQL store
- **API Design**: RESTful API endpoints

### Data Storage Solutions
- **Primary Database**: PostgreSQL via Neon Database
- **ORM**: Drizzle ORM with schema-first approach
- **Session Storage**: PostgreSQL table for session persistence
- **Database Migrations**: Drizzle Kit for schema management

## Key Components

### User Management
- User profiles with professional information (title, bio, location)
- Profile images and personal branding
- Connection system for networking between musicians

### Content Management
- Post creation system supporting multiple content types:
  - Text posts
  - Video performances
  - Gig announcements
  - Band formation posts
- Like and comment functionality
- Feed algorithm for personalized content

### Professional Features
- **Gigs**: Venue posting and musician application system
- **Bands**: Band formation and member recruitment
- **Networking**: Connection requests and suggestions
- **Messaging**: Direct messaging between users

### UI/UX Design
- Dark theme optimized for musicians
- Responsive design with mobile-first approach
- Custom forest/green gradient branding
- Professional layout with sidebar navigation

## Data Flow

1. **Authentication**: Users authenticate via Replit Auth (Google OAuth)
2. **Session Management**: Sessions stored in PostgreSQL with automatic cleanup
3. **API Requests**: Frontend makes authenticated requests to Express API
4. **Data Fetching**: TanStack Query manages caching and synchronization
5. **Real-time Updates**: Optimistic updates with automatic cache invalidation

### Database Schema
- `users`: Core user profile information
- `posts`: Multi-type content system with metadata
- `connections`: User networking relationships
- `bands` & `band_members`: Band management
- `gigs` & `gig_applications`: Gig marketplace
- `likes` & `comments`: Social interaction features
- `sessions`: Session storage for authentication

## External Dependencies

### Core Framework Dependencies
- React ecosystem (React, React DOM, Vite)
- Express.js with TypeScript support
- PostgreSQL with Neon Database serverless driver

### Authentication & Security
- Replit Auth with OpenID Connect
- Express sessions with PostgreSQL store
- CORS and security middleware

### UI & Styling
- Tailwind CSS for styling
- Radix UI for accessible components
- Lucide React for icons
- Custom CSS variables for theming

### Development Tools
- TypeScript for type safety
- ESBuild for production bundling
- Drizzle Kit for database operations
- PostCSS for CSS processing

## Deployment Strategy

### Development Environment
- Vite dev server with HMR for frontend
- TSX for TypeScript execution in development
- Replit integration with cartographer and error overlay

### Production Build
- Vite builds frontend to `dist/public`
- ESBuild bundles backend to `dist/index.js`
- Static file serving through Express
- Environment variable configuration for database and auth

### Database Management
- Drizzle migrations in `migrations/` directory
- Schema definitions in `shared/schema.ts`
- Push-based deployment with `db:push` command

### Hosting Requirements
- Node.js runtime environment
- PostgreSQL database access
- Environment variables for DATABASE_URL and auth configuration
- Static file serving capability for frontend assets

The application follows a monorepo structure with clear separation between client, server, and shared code, making it maintainable and scalable for a music-focused social platform.