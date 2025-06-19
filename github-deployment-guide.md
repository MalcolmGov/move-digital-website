# Deploy Move Digital to GitHub - Complete Guide

## Method 1: Direct GitHub Upload (Recommended)

### Step 1: Create GitHub Repository
1. Go to [github.com](https://github.com) and sign in
2. Click "New repository" (green button)
3. Repository name: `move-digital-website`
4. Description: `AI-powered digital marketing website for Move Digital`
5. Set to Public or Private (your choice)
6. Do NOT initialize with README (since you have existing code)
7. Click "Create repository"

### Step 2: Prepare Project Files
Create a zip file of your project excluding unnecessary files:
- node_modules/ (will be reinstalled)
- .git/ (Git history - we'll create fresh)
- dist/ (build output)
- *.log files

### Step 3: Upload to GitHub
**Option A: Web Upload**
1. In your new GitHub repository
2. Click "uploading an existing file"
3. Drag/drop your project files or select them
4. Commit message: "Initial commit - Move Digital website"
5. Click "Commit changes"

**Option B: GitHub CLI (if available)**
```bash
# Download your files to local machine
# Then in terminal:
git clone https://github.com/yourusername/move-digital-website.git
cd move-digital-website
# Copy your project files here
git add .
git commit -m "Initial commit - Move Digital website"
git push origin main
```

### Step 4: Verify Upload
Check that these key files are present:
- package.json
- server/index.ts
- client/src/App.tsx
- railway.json
- shared/schema.ts

## Method 2: Download & Re-upload

If direct Git operations fail:

### Download Project Files
1. In Replit, select all files in file explorer
2. Right-click → Download as ZIP
3. Extract ZIP file locally
4. Remove node_modules, .git, dist folders
5. Upload clean project to GitHub

## Files to Include in GitHub

### Essential Files
```
├── client/
├── server/
├── shared/
├── package.json
├── package-lock.json
├── tsconfig.json
├── vite.config.ts
├── tailwind.config.ts
├── drizzle.config.ts
├── railway.json
├── .gitignore
└── README.md (optional)
```

### Files to Exclude
```
node_modules/
dist/
.git/
*.log
.env
.replit
replit.nix
```

## After GitHub Deployment

### Connect to Railway
1. Railway dashboard → "New Project"
2. "Deploy from GitHub repo"
3. Select your move-digital-website repository
4. Railway auto-detects Node.js and builds

### Environment Variables
Add in Railway settings:
```
NODE_ENV=production
GMAIL_USER=your-email@gmail.com
GMAIL_APP_PASSWORD=your-app-password
```

### Database Setup
1. Add PostgreSQL service in Railway
2. Run migration: `npm run db:push`
3. Verify deployment at Railway-provided URL

### Custom Domain
1. Railway Settings → Domains
2. Add: movedigital.africa
3. Configure CNAME at domain registrar

## Benefits of GitHub → Railway
- Version control for future updates
- Automatic deployments on code changes
- Easy collaboration and backup
- Professional development workflow

## Timeline
- GitHub upload: 5-10 minutes
- Railway connection: 2-3 minutes
- Environment setup: 5 minutes
- Custom domain: 15 minutes
- **Total: 30 minutes to live website**

This approach gives you full control and a professional deployment pipeline.