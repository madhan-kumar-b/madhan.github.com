# Portfolio Application

## Overview

This is a modern, single-page portfolio website built with a full-stack architecture. The application showcases a creative developer's work, skills, and provides a contact form for potential clients or collaborators. The frontend delivers a smooth, animated user experience with sections for hero introduction, about/skills, projects showcase, and contact form. The backend provides API endpoints for form submission with validation.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Build Tools**
- **React with TypeScript**: Component-based UI using functional components and hooks
- **Vite**: Fast development server and optimized production builds
- **Wouter**: Lightweight client-side routing (currently single-page with 404 fallback)

**UI Component System**
- **shadcn/ui**: Comprehensive component library built on Radix UI primitives
- **Tailwind CSS**: Utility-first styling with custom design tokens
- **Framer Motion**: Animation library for smooth page transitions and interactions
- Uses "new-york" style variant with custom color scheme (dark theme with primary purple/blue accent)

**State Management & Data Fetching**
- **React Query (@tanstack/react-query)**: Server state management and caching
- **React Hook Form**: Form state and validation with Zod schema integration
- Custom query client configured with infinite stale time and disabled refetching

**Page Structure**
- Single-page application with smooth scroll navigation
- Sections: Navigation (sticky header), Hero, About, Projects, Contact, Footer
- Mobile-responsive design with conditional rendering

### Backend Architecture

**Server Framework**
- **Express.js**: Minimal REST API server
- **TypeScript**: Type-safe server-side code
- **ESM modules**: Modern JavaScript module system

**Development & Production**
- Development: tsx for TypeScript execution with hot reload
- Production: esbuild bundles server code for deployment
- Vite middleware integration for serving frontend in development

**API Structure**
- `/api/contact`: POST endpoint for contact form submissions
- Form validation using Zod schemas shared between client and server
- Error handling with appropriate HTTP status codes
- Request/response logging middleware for API routes

### Data Storage

**Database Setup**
- **Drizzle ORM**: Type-safe SQL query builder
- **PostgreSQL**: Primary database (configured via DATABASE_URL)
- **Neon Database Serverless**: PostgreSQL driver (@neondatabase/serverless)

**Schema Design**
- `contacts` table: Stores contact form submissions (id, name, email, subject, message, createdAt)
- Shared schema definitions in `/shared/schema.ts` for type safety across stack
- Drizzle-Zod integration for automatic validation schema generation

**Current Implementation**
- Database schema defined but contact storage not yet implemented
- Currently logs submissions to console (placeholder for email/database persistence)
- In-memory storage interface created for future extensions

### Authentication & Authorization

Not currently implemented. The application is a public portfolio with no user authentication requirements.

### Form Validation

**Validation Strategy**
- **Zod schemas**: Runtime type validation and parsing
- Client-side validation via React Hook Form resolver
- Server-side validation before processing
- Shared validation rules between frontend and backend

**Contact Form Rules**
- Name: minimum 2 characters
- Email: valid email format required
- Subject: minimum 3 characters
- Message: minimum 10 characters

## External Dependencies

### Third-Party UI Libraries
- **Radix UI**: Unstyled, accessible component primitives (dialogs, dropdowns, tooltips, etc.)
- **Lucide React**: Icon library
- **React Icons**: Additional icons (specifically SiDribbble for social links)
- **Embla Carousel**: Carousel/slider functionality

### Utility Libraries
- **class-variance-authority**: CSS variant management
- **clsx & tailwind-merge**: Conditional className composition
- **cmdk**: Command palette component
- **date-fns**: Date formatting and manipulation
- **nanoid**: Unique ID generation

### Development Tools
- **@replit/vite-plugin-runtime-error-modal**: Development error overlay
- **@replit/vite-plugin-cartographer**: Replit-specific development tooling
- **@replit/vite-plugin-dev-banner**: Development environment banner

### Database & Session Management
- **connect-pg-simple**: PostgreSQL session store (for future authentication)
- **drizzle-kit**: Database migration and management CLI

### Build & Type Safety
- **esbuild**: Fast JavaScript bundler for production builds
- **tsx**: TypeScript execution for development
- **PostCSS & Autoprefixer**: CSS processing pipeline