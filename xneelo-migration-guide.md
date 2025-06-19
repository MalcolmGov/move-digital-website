# Move Digital - Xneelo Hosting Migration Guide

## Complete Technical Stack

### Frontend Stack
- **Framework**: React 18.3.1 with TypeScript 5.6.3
- **Build Tool**: Vite 5.4.14
- **Routing**: Wouter 3.3.5 (lightweight client-side routing)
- **Styling**: Tailwind CSS 3.4.17 with PostCSS 8.4.47
- **UI Components**: Radix UI primitives + Shadcn/ui components
- **Animations**: Framer Motion 11.13.1
- **State Management**: TanStack React Query 5.60.5
- **Forms**: React Hook Form 7.55.0 with Zod validation

### Backend Stack
- **Runtime**: Node.js 20+ (ES Modules)
- **Framework**: Express.js 4.21.2
- **Language**: TypeScript with tsx runtime
- **Database ORM**: Drizzle ORM 0.39.1
- **Database**: PostgreSQL (currently using Neon serverless)
- **Session Management**: Express Session with MemoryStore
- **Email**: Nodemailer 7.0.3 (Gmail SMTP)

### Database Requirements
- **PostgreSQL 12+** (recommended 14+)
- **Extensions**: None required
- **Schema**: Simple user authentication table
- **Migration Tool**: Drizzle Kit 0.30.4

### Build Configuration
- **Production Build**: 
  - Frontend: `vite build` → `dist/public/`
  - Backend: `esbuild server/index.ts` → `dist/index.js`
- **Start Command**: `node dist/index.js`
- **Port**: Configurable (default 5000)

### External Dependencies
- **Email**: Gmail SMTP (requires GMAIL_USER, GMAIL_APP_PASSWORD)
- **Optional**: Anthropic AI SDK, Stripe, SendGrid, Slack integration
- **CDN**: None required (all assets bundled)

## Xneelo Hosting Requirements

### Server Specifications
- **Node.js 18+** (ES Module support required)
- **PostgreSQL database** access
- **Memory**: 512MB minimum (1GB recommended)
- **Storage**: 1GB minimum for application files
- **SSL Certificate**: Required for custom domain

### Environment Variables Required
```bash
NODE_ENV=production
DATABASE_URL=postgresql://username:password@host:port/database
GMAIL_USER=your-email@gmail.com
GMAIL_APP_PASSWORD=your-app-password
PORT=80
```

### File Structure for Upload
```
dist/
├── public/           # Frontend build (from vite build)
│   ├── index.html
│   ├── assets/
│   └── ...
├── index.js          # Backend bundle (from esbuild)
└── package.json      # Production dependencies only
```

### Production Dependencies (package.json)
```json
{
  "type": "module",
  "scripts": {
    "start": "NODE_ENV=production node dist/index.js"
  },
  "dependencies": {
    "express": "^4.21.2",
    "drizzle-orm": "^0.39.1",
    "@neondatabase/serverless": "^0.10.4",
    "nodemailer": "^7.0.3",
    "express-session": "^1.18.1",
    "zod": "^3.24.2"
  }
}
```

## Migration Steps for Xneelo

### 1. Database Setup
- Create PostgreSQL database on Xneelo
- Run schema migration: `npm run db:push`
- Note connection details for DATABASE_URL

### 2. Build Application
```bash
npm run build
```

### 3. Prepare Production Package
- Copy `dist/` folder contents
- Create minimal `package.json` with production dependencies
- Configure environment variables in Xneelo control panel

### 4. Upload & Configure
- Upload files to Xneelo hosting
- Set Node.js version to 18+
- Configure start command: `node dist/index.js`
- Set environment variables
- Configure custom domain SSL

### 5. Domain Configuration
- Point DNS to Xneelo servers
- Configure SSL certificate for movedigital.africa
- Update any hardcoded URLs in application

## Current Application Features
- Responsive marketing website
- AI-powered chat assistant
- Contact forms with email integration
- WhatsApp integration
- Social media integration
- SEO optimized
- Mobile-first design
- Performance optimized

## Xneelo Compatibility
✅ **Compatible**: Node.js hosting with PostgreSQL
✅ **SSL**: Custom domain SSL certificates
✅ **Email**: SMTP configuration support
⚠️ **Check**: Node.js 18+ ES Module support
⚠️ **Check**: PostgreSQL version compatibility
⚠️ **Check**: Memory limits for production workload

## Alternative Considerations
If Xneelo limitations are encountered:
- **Static Export**: Convert to static site (lose backend features)
- **Serverless**: Deploy backend to Vercel/Netlify Functions
- **Hybrid**: Static frontend + external API hosting

The application is designed with modern standards and should work on most Node.js hosting providers with PostgreSQL support.