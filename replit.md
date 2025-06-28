# ASTARTA CAPITAL - 3D Web Application

## Overview

This is a modern full-stack web application featuring a 3D interactive logo for ASTARTA CAPITAL. The application combines a React Three.js frontend with an Express.js backend, utilizing PostgreSQL for data storage and modern UI components for a premium user experience.

## System Architecture

The application follows a monorepo structure with clear separation between client and server:

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **3D Rendering**: React Three Fiber (@react-three/fiber) with Three.js
- **UI Components**: Radix UI primitives with custom styling
- **Styling**: Tailwind CSS with CSS variables for theming
- **State Management**: Zustand for game state and audio management
- **Build Tool**: Vite with hot module replacement

### Backend Architecture
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js
- **Database**: PostgreSQL with Drizzle ORM
- **Session Storage**: Connect-pg-simple for PostgreSQL session storage
- **Environment**: ESM modules throughout

### Database Layer
- **ORM**: Drizzle with PostgreSQL dialect
- **Connection**: Neon Database serverless driver
- **Schema Management**: Drizzle Kit for migrations
- **Current Schema**: Users table with username/password authentication

## Key Components

### 3D Logo System
- **Logo3D**: Main logo component with animation phases (intro → assembly → complete)
- **PyramidSegment**: Individual triangular segments that form the pyramid logo
- **Scene**: Container for 3D elements, lighting, and atmospheric effects
- **Animation**: Smooth transitions between phases with audio feedback

### State Management
- **useGame**: Game phase management (ready → playing → ended)
- **useAudio**: Audio control with mute/unmute functionality and sound effects

### UI System
- Complete shadcn/ui component library implementation
- Custom interface components for game controls
- Responsive design with mobile-first approach

### Storage Layer
- **IStorage Interface**: Abstract storage interface for CRUD operations
- **MemStorage**: In-memory implementation for development
- **Database Schema**: User management with Drizzle ORM integration

## Data Flow

1. **Application Boot**: Vite serves the React application with 3D canvas
2. **Logo Animation**: Automatic sequence from intro → assembly → complete phases
3. **User Interaction**: Game state management through Zustand stores
4. **Audio System**: Conditional audio playback based on mute state
5. **Backend API**: Express routes handle data operations through storage interface

## External Dependencies

### Core Runtime
- **Database**: Neon PostgreSQL serverless
- **Deployment**: Replit-optimized with runtime error overlay

### 3D Graphics
- **Three.js Ecosystem**: Core 3D library with React bindings
- **Post-processing**: Advanced visual effects support
- **GLSL Shaders**: Custom shader support via vite-plugin-glsl

### UI/UX
- **Radix UI**: Accessible component primitives
- **Lucide Icons**: Modern icon library
- **Inter Font**: Typography via Fontsource

## Deployment Strategy

### Development
- **Hot Reloading**: Vite dev server with middleware integration
- **Error Handling**: Runtime error modal overlay for debugging
- **Asset Pipeline**: Support for 3D models (.gltf, .glb) and audio files

### Production Build
- **Frontend**: Vite build output to `dist/public`
- **Backend**: esbuild compilation to `dist/index.js`
- **Static Assets**: Served through Express in production mode

### Database
- **Environment**: DATABASE_URL environment variable required
- **Migrations**: Drizzle Kit push command for schema updates
- **Session Storage**: PostgreSQL-backed sessions in production

## Changelog

```
Changelog:
- June 28, 2025. Initial setup
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```