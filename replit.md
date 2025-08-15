# Overview

This is a typing practice application that helps users improve their typing speed and accuracy through structured drills and AI-powered insights. The system provides real-time feedback during typing sessions, analyzes user performance patterns, and offers personalized recommendations for improvement. Key features include various difficulty-based typing drills, performance tracking with charts, AI-driven weakness analysis, and a modern responsive interface with dark/light theme support.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool and development server
- **Styling**: Tailwind CSS with shadcn/ui component library for consistent UI patterns
- **State Management**: React Query (TanStack Query) for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Theme System**: Custom theme provider supporting light/dark modes with CSS variables

## Backend Architecture
- **Runtime**: Node.js with Express.js REST API server
- **Storage**: In-memory storage implementation (MemStorage class) with interface for future database integration
- **Real-time Processing**: Custom TypingEngine class for live typing analysis and statistics calculation
- **AI Analysis**: AIAnalyzer class for keystroke pattern analysis and weakness identification

## Data Storage Design
- **Database ORM**: Drizzle ORM configured for PostgreSQL with migration support
- **Schema Structure**: 
  - Users table for profile and performance stats
  - DrillTypes table for typing exercise content and difficulty levels
  - TypingSessions table for completed practice records with detailed keystroke data
  - UserWeaknesses table for AI-generated improvement suggestions
- **Current Implementation**: Memory-based storage for demo purposes with full database schema ready for production

## Component Architecture
- **Modular Design**: Separated UI components (typing interface, performance charts, drill selector, AI insights)
- **Custom Engines**: 
  - TypingEngine for real-time input processing and WPM/accuracy calculation
  - AIAnalyzer for post-session analysis and personalized recommendations
- **Performance Visualization**: Custom canvas-based charts without external charting dependencies

## API Structure
- **RESTful Endpoints**: 
  - User management and statistics (`/api/user/*`)
  - Drill management (`/api/drills/*`) 
  - Session tracking (`/api/sessions`)
- **Data Flow**: React Query handles caching and synchronization between client and server state

# External Dependencies

## Core Framework Dependencies
- **@neondatabase/serverless**: PostgreSQL database driver for Neon cloud database
- **drizzle-orm & drizzle-kit**: Type-safe ORM and migration toolkit
- **@tanstack/react-query**: Server state management and caching
- **express**: Web server framework
- **wouter**: Lightweight React routing

## UI and Styling
- **@radix-ui/***: Comprehensive set of unstyled, accessible UI primitives
- **tailwindcss**: Utility-first CSS framework
- **class-variance-authority & clsx**: Dynamic className utilities
- **lucide-react**: Icon library

## Development and Build Tools
- **vite**: Fast build tool and development server with HMR
- **typescript**: Type safety and enhanced developer experience
- **@replit/vite-plugin-***: Replit-specific development enhancements
- **esbuild**: Fast JavaScript bundler for production builds

## Form and Validation
- **react-hook-form**: Form state management
- **@hookform/resolvers**: Form validation resolvers
- **zod**: Schema validation and type inference

## Additional Utilities
- **date-fns**: Date manipulation and formatting
- **embla-carousel-react**: Carousel component functionality
- **connect-pg-simple**: PostgreSQL session store for Express