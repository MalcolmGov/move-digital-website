# Railway Web Deployment Steps

## Step 1: Create Railway Account & Project
1. Go to [railway.app](https://railway.app)
2. Sign up with GitHub or email
3. Click "New Project"
4. Select "Empty Project"
5. Name it: "move-digital"

## Step 2: Deploy via File Upload
Since CLI requires browser login, use web interface:
1. In your new Railway project
2. Click "Deploy from Local Directory"
3. Upload your project files (or use GitHub if you prefer)

## Step 3: Add Services
1. Click "Add Service" → "Database" → "PostgreSQL"
2. Railway auto-creates DATABASE_URL environment variable

## Step 4: Configure Environment Variables
In Railway Settings → Variables:
```
NODE_ENV=production
GMAIL_USER=your-email@gmail.com
GMAIL_APP_PASSWORD=your-app-password
```

## Step 5: Deploy & Test
1. Railway automatically builds and deploys
2. Click the generated URL to test
3. Check logs for any issues

## Step 6: Add Custom Domain
1. Settings → Domains → "Add Domain"
2. Enter: movedigital.africa
3. Add provided CNAME record at your registrar

Your site will be live at both the Railway URL and your custom domain once DNS propagates.