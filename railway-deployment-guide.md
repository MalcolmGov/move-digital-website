# Railway Deployment Guide for Move Digital

## Step 1: Prepare for Railway

### Create Railway Account
1. Go to [railway.app](https://railway.app)
2. Sign up with GitHub (recommended for easy deployments)
3. Connect your GitHub account

### Pricing
- **Hobby Plan**: $5/month
- Includes: 512MB RAM, 1GB storage, custom domains, SSL certificates
- PostgreSQL database included

## Step 2: Deploy Application

### Option A: Deploy from GitHub (Recommended)
1. Push your project to GitHub repository
2. In Railway dashboard, click "New Project"
3. Select "Deploy from GitHub repo"
4. Choose your Move Digital repository
5. Railway will auto-detect the Node.js app

### Option B: Deploy from Local Files
1. Install Railway CLI: `npm install -g @railway/cli`
2. Login: `railway login`
3. In project directory: `railway deploy`

## Step 3: Configure Environment Variables

In Railway dashboard, add these environment variables:

### Required Variables
```
NODE_ENV=production
GMAIL_USER=your-email@gmail.com
GMAIL_APP_PASSWORD=your-app-password
```

### Database Configuration
Railway will automatically provide:
```
DATABASE_URL=postgresql://...
```
(This is generated automatically when you add PostgreSQL service)

## Step 4: Add PostgreSQL Database

1. In Railway project dashboard
2. Click "Add Service" → "Database" → "PostgreSQL"
3. Railway automatically creates DATABASE_URL environment variable
4. Run database migration: In Railway console, run `npm run db:push`

## Step 5: Configure Custom Domain

### Add Domain
1. Go to project Settings → Domains
2. Click "Add Domain"
3. Enter: `movedigital.africa`
4. Railway provides CNAME record to add at your registrar

### DNS Configuration at Registrar
```
Type: CNAME
Name: movedigital.africa (or @)
Value: [railway-provided-domain].railway.app
```

### SSL Certificate
- Railway automatically provisions SSL certificates
- Usually active within 5-15 minutes
- No additional configuration needed

## Step 6: Deployment Configuration

### Build Commands
Railway auto-detects from package.json:
```json
{
  "scripts": {
    "build": "vite build && esbuild server/index.ts --platform=node --packages=external --bundle --format=esm --outdir=dist",
    "start": "NODE_ENV=production node dist/index.js"
  }
}
```

### Port Configuration
Railway automatically assigns PORT environment variable.
Your Express app should use: `process.env.PORT || 5000`

## Step 7: Verify Deployment

### Check Deployment Status
1. Railway dashboard shows build logs
2. Green checkmark indicates successful deployment
3. Click generated URL to test application

### Test Features
- Homepage loads correctly
- Contact forms work (email sending)
- Database connectivity
- All static assets load

## Step 8: Monitor Application

### Railway Dashboard Features
- Real-time logs
- Resource usage metrics
- Deployment history
- Environment variable management

### Custom Domain SSL
- Check SSL certificate status in domains section
- Should show "Active" with green indicator
- Test https://movedigital.africa

## Migration Timeline

### Immediate (0-5 minutes)
- Railway account creation
- Repository connection
- Initial deployment

### Short-term (5-30 minutes)
- Environment variables configuration
- Database setup and migration
- Build completion and first deploy

### Medium-term (30 minutes - 2 hours)
- Custom domain configuration
- DNS propagation
- SSL certificate activation

## Advantages of Railway

### Technical Benefits
- Zero code changes required
- Automatic PostgreSQL database
- Built-in SSL certificates
- Git-based deployments

### Operational Benefits
- Simple pricing ($5/month total)
- Excellent developer experience
- Real-time monitoring
- Easy rollbacks

## Troubleshooting

### Common Issues
- **Build fails**: Check Node.js version in package.json
- **Database connection**: Verify DATABASE_URL is set
- **Email not working**: Confirm GMAIL credentials are correct
- **Domain not working**: Check CNAME record at registrar

### Support Resources
- Railway documentation: [docs.railway.app](https://docs.railway.app)
- Community Discord for help
- Twitter support: [@Railway](https://twitter.com/Railway)

## Cost Breakdown
- Railway Hobby: $5/month
- Custom domain SSL: Included
- PostgreSQL database: Included
- **Total**: $5/month

This provides professional hosting with zero maintenance overhead and full feature support for your Move Digital website.