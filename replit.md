# Move Digital - AI-Powered Digital Marketing Website

## Overview

This is a modern full-stack web application for Move Digital, a digital marketing agency specializing in AI-powered solutions. The application is built as a marketing website with a focus on showcasing services, testimonials, and providing an interactive AI chatbot for customer engagement.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for lightweight client-side routing
- **Styling**: Tailwind CSS with custom design system
- **UI Components**: Shadcn/ui component library with Radix UI primitives
- **State Management**: TanStack React Query for server state management
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture
- **Runtime**: Node.js 20 with Express.js
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM
- **Database**: PostgreSQL (configured for Neon serverless)
- **Session Management**: In-memory storage with planned database persistence

### Development Environment
- **Platform**: Replit with Node.js 20, Web, and PostgreSQL 16 modules
- **Hot Reload**: Vite development server with HMR
- **Error Handling**: Runtime error overlay for development

## Key Components

### Frontend Components
1. **Landing Page Sections**:
   - Navigation with smooth scrolling
   - Hero section with gradient backgrounds
   - Value propositions showcase
   - Services grid with icons and descriptions
   - About section with statistics
   - Testimonials carousel
   - Contact form with validation
   - Footer with social links

2. **Interactive Features**:
   - Floating AI chatbot with contextual responses
   - Smooth scrolling navigation
   - Responsive mobile design
   - Form validation with toast notifications

3. **Design System**:
   - Custom color palette with CSS variables
   - Consistent spacing and typography
   - Interactive hover effects and animations
   - Mobile-first responsive design

### Backend Structure
1. **Server Setup**:
   - Express.js with middleware for JSON parsing and logging
   - Vite integration for development mode
   - Static file serving for production builds
   - Request/response logging with timing

2. **Database Schema**:
   - Users table with username/password authentication
   - Drizzle schema with Zod validation integration
   - Migration system for database changes

3. **Storage Interface**:
   - Abstract storage interface for CRUD operations
   - In-memory implementation for development
   - Prepared for PostgreSQL integration

## Data Flow

1. **Client Requests**: React components make API calls through TanStack Query
2. **API Layer**: Express routes handle business logic and data validation
3. **Storage Layer**: Abstract storage interface manages data persistence
4. **Database**: PostgreSQL stores user data and application state
5. **Response**: JSON responses with consistent error handling

## External Dependencies

### Core Dependencies
- **Database**: Neon PostgreSQL serverless database
- **AI Integration**: Anthropic SDK for chatbot functionality
- **UI Library**: Radix UI primitives for accessible components
- **Styling**: Tailwind CSS for utility-first styling
- **Validation**: Zod for runtime type validation

### Development Dependencies
- **Build Tools**: Vite, ESBuild for production builds
- **Type Checking**: TypeScript with strict configuration
- **Development**: TSX for TypeScript execution, hot reloading

## Deployment Strategy

### Production Build
- **Frontend**: Vite builds optimized static assets to `dist/public`
- **Backend**: ESBuild bundles server code to `dist/index.js`
- **Assets**: Static files served from build output directory

### Replit Deployment
- **Target**: Autoscale deployment on Replit infrastructure
- **Port Configuration**: Internal port 5000, external port 80
- **Environment**: Production mode with NODE_ENV=production

### Database Migration
- **Schema**: Drizzle kit manages database schema changes
- **Migrations**: Generated migration files in `./migrations` directory
- **Deployment**: `npm run db:push` applies schema changes

## User Preferences

Preferred communication style: Simple, everyday language.

## Changelog

Changelog:
- June 13, 2025. Initial setup
- June 13, 2025. Implemented advanced animations and 3D interactive elements
- June 13, 2025. Added comprehensive social media integration with live feeds
- June 13, 2025. Updated social media links to actual business profiles
- June 13, 2025. Removed Twitter and LinkedIn, keeping Facebook, Instagram, and YouTube
- June 14, 2025. Implemented comprehensive SEO strategy with enhanced meta tags, structured data, and content optimization
- June 14, 2025. Added viral marketing features including conversion optimization, growth hacking components, and customer acquisition strategies
- June 14, 2025. Implemented ROI calculator, case studies showcase, and live AI chat assistant with runtime error fixes
- June 14, 2025. Production optimization: security headers, rate limiting, input validation, mobile responsiveness, PWA features, service worker caching
- June 14, 2025. Prepared for domain migration from Xneelo to Replit hosting with custom domain www.movedigital.africa
- June 14, 2025. Successfully deployed to production at https://move-digital-malcolm36.replit.app and configured DNS migration from Xneelo
- June 14, 2025. DNS migration in progress: nameservers updated for www.movedigital.africa, awaiting global DNS propagation and SSL certificate provisioning (24-48 hours typical)
- June 14, 2025. Implemented subtle page load animations with smooth loading screen, progress indicators, entrance animations, and scroll-triggered reveals for enhanced user engagement
- June 14, 2025. Enhanced footer with premium "Powered by Move Digital" branding featuring animated gradient text, rotating icons, floating particles, glassmorphism design, and interactive hover effects
- June 14, 2025. Completely modernized footer sections with glassmorphism cards, interactive animations, visual icons, enhanced services descriptions, clickable contact methods, and quick action buttons for improved user engagement
- June 14, 2025. Streamlined footer to 3-column layout by removing "Discover More" section, maintaining focus on brand, services, and contact information with all modern styling intact
- June 14, 2025. Fixed services section layout and display issues by simplifying complex animations, improving responsive grid layout, and ensuring consistent card rendering across all devices
- June 14, 2025. Implemented comprehensive brand-themed loading spinner system with Move Digital branding, including mini spinners for forms, AI chat indicators, full-page loaders with progress tracking, and enhanced contact form submission states
- June 14, 2025. Enhanced value proposition cards with advanced visual design featuring gradient backgrounds, floating particles, glow effects, statistical highlights, progress indicators, and interactive hover animations for improved user engagement
- June 14, 2025. Integrated authentic Move Digital logo across all website components including navigation header, footer branding, page loader, mobile navigation, and floating AI chat assistant for consistent brand identity throughout the user experience
- June 14, 2025. Enhanced logo implementation with transparent background removal and increased sizes: navigation (16x16), footer (20x20), page loader (32x32), mobile navigation (12x12), and AI chat (8x8) for improved visual prominence and seamless background blending
- June 14, 2025. Optimized navigation header design with improved visual hierarchy: increased header height to 20px, refined logo size to 12x12, enhanced spacing, added "AI-Powered Marketing" tagline, and implemented professional text stacking with balanced proportions
- June 14, 2025. Confirmed WhatsApp integration with business number +27834654639 across all website components (mobile navigation, footer, conversion sections, AI chat) and updated video marketing script with correct contact information
- June 15, 2025. Implemented dynamic typing effect for hero section heading with realistic character-by-character animation, blinking cursor, gradient text styling, and 1-second delay for enhanced visual engagement
- June 15, 2025. Optimized typing animation to ultra-fast speed: 100ms delay + 1ms per character completes full sentence in 0.17 seconds total for optimal mobile performance
- June 15, 2025. Reverted business card components and restored website to previous stable state with all core functionality intact
- June 15, 2025. Enhanced value proposition cards visibility with white backgrounds, strong borders, solid text colors, and improved contrast for mobile readability
- June 15, 2025. Implemented comprehensive service detail modals with full project information, technologies, benefits, and direct WhatsApp/contact integration
- June 15, 2025. Removed all pricing and timeline information from services and case studies throughout the entire application
- June 15, 2025. Added engaging eye-catching CTAs across homepage: enhanced hero buttons with animations, floating sticky CTA bar, and compelling value proposition call-to-action section
- June 17, 2025. Removed urgency banner per user request - cleaner homepage layout with floating CTA bar remaining for conversion optimization
- June 19, 2025. DNS Migration Status: app.movedigital.africa CNAME configured and resolving correctly, but SSL certificate verification experiencing extended delays beyond initial estimates. Website remains fully operational at move-digital-malcolm36.replit.app
- June 19, 2025. Prepared project for Railway deployment: configured PORT environment variable, added railway.json configuration, installed Railway CLI. Ready for $5/month hosting solution with immediate SSL and custom domain support

## Viral Marketing Implementation

### Growth Hacking Features Added:
- **Viral Alert Banner**: Fixed top banner showing live business sign-ups with trending counter
- **Referral Explosion System**: Automated referral tracking and social proof display
- **Instant Callback System**: High-conversion phone callback buttons with WhatsApp integration
- **Scarcity Indicators**: Live spot counters and urgency timers to drive immediate action
- **Social Sharing Integration**: Viral sharing buttons with pre-written compelling messages
- **Free Value Proposition**: R25,000 AI Business Transformation offer with limited availability
- **Multi-Touch Contact**: Phone, WhatsApp, and form submission options for maximum conversion
- **Live Social Proof**: Real-time display of applications, ratings, and response times
- **Psychological Triggers**: FOMO, social proof, authority, and urgency principles integrated

### Customer Acquisition Strategy:
- **Lead Magnets**: Free AI marketing audit worth R15,000 and business transformation worth R25,000
- **Conversion Optimization**: Multiple call-to-action buttons with different messaging approaches
- **Mobile-First Design**: Optimized for mobile users with easy-tap contact options
- **Geographic Targeting**: Johannesburg-focused messaging with local business appeal
- **Multi-Channel Approach**: Website, WhatsApp, phone, and social media integration

## SEO Implementation

### Core SEO Features Added:
- **Enhanced Meta Tags**: Complete title, description, keywords, robots, canonical URLs
- **Geographic SEO**: Location-specific tags for Johannesburg targeting  
- **Open Graph & Twitter Cards**: Optimized social media sharing
- **Structured Data**: JSON-LD schema markup for Organization, LocalBusiness, Services
- **Technical SEO**: Sitemap.xml, robots.txt, web manifest
- **Content Optimization**: Keyword-rich headings, semantic HTML, accessibility improvements
- **Internal Linking**: Proper navigation structure and breadcrumb implementation
- **SEO Blog Section**: Fresh content strategy with relevant articles for search visibility

### Target Keywords:
- Primary: "AI-powered digital marketing agency Johannesburg"
- Secondary: "web development South Africa", "mobile app development", "digital strategy consulting"
- Local: "digital marketing Johannesburg", "SEO services South Africa"

### Technical Improvements:
- Semantic HTML5 structure with proper heading hierarchy
- Schema.org markup for local business, services, and articles
- Optimized images with alt text and performance loading
- Mobile-first responsive design with fast loading times
- Accessibility enhancements with ARIA labels and screen reader support