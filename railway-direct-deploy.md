# Railway Direct Deployment (No GitHub Required)

## Step 1: Install Railway CLI
```bash
npm install -g @railway/cli
```

## Step 2: Login to Railway
```bash
railway login
```
This opens a browser tab to authenticate with Railway.

## Step 3: Initialize Railway Project
```bash
railway init
```
- Choose "Empty Project"
- Name it: "move-digital"

## Step 4: Deploy
```bash
railway up
```
This uploads your entire project directly to Railway.

## Step 5: Add PostgreSQL
```bash
railway add postgresql
```

## Step 6: Set Environment Variables
```bash
railway variables set NODE_ENV=production
railway variables set GMAIL_USER=your-email@gmail.com
railway variables set GMAIL_APP_PASSWORD=your-app-password
```

## Step 7: Run Database Migration
```bash
railway run npm run db:push
```

## Step 8: Get Your URL
```bash
railway status
```
This shows your live application URL.

## Step 9: Add Custom Domain
1. Go to Railway dashboard
2. Settings → Domains → Add Domain
3. Enter: movedigital.africa
4. Add CNAME record at your registrar

## Advantages of Direct Deploy
- No GitHub setup required
- Faster deployment (5 minutes)
- Direct from Replit environment
- Automatic builds and deployments

## Commands Summary
```bash
npm install -g @railway/cli
railway login
railway init
railway up
railway add postgresql
railway variables set NODE_ENV=production
railway variables set GMAIL_USER=your-email
railway variables set GMAIL_APP_PASSWORD=your-password
railway run npm run db:push
railway status
```

This gets your site live in under 10 minutes without any GitHub setup.