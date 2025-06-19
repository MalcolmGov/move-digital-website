# Cloudflare Setup Guide for movedigital.africa

## Step 1: Connect Your Domain
1. Click **"Connect a domain"** in your Cloudflare dashboard
2. Enter: `movedigital.africa`
3. Click "Add domain"
4. Choose **Free plan** (sufficient for SSL and CDN)

## Step 2: DNS Configuration
Once domain is added, configure these DNS records:

### Primary Domain
```
Type: A
Name: movedigital.africa (or @)
IPv4 address: 34.117.33.233
Proxy status: Proxied (orange cloud)
```

### WWW Subdomain
```
Type: CNAME
Name: www
Target: movedigital.africa
Proxy status: Proxied (orange cloud)
```

### App Subdomain (optional)
```
Type: CNAME
Name: app
Target: movedigital.africa
Proxy status: Proxied (orange cloud)
```

## Step 3: Update Nameservers
Cloudflare will provide nameservers like:
- `ns1.cloudflare.com`
- `ns2.cloudflare.com`

1. Go to your domain registrar (where you bought movedigital.africa)
2. Find DNS/Nameserver settings
3. Replace existing nameservers with Cloudflare's
4. Save changes

## Step 4: SSL Configuration
In Cloudflare dashboard:
1. Go to **SSL/TLS** tab
2. Set SSL mode to **"Full (strict)"**
3. Enable **"Always Use HTTPS"**
4. Enable **"Automatic HTTPS Rewrites"**

## Step 5: Page Rules (Optional)
To redirect www to non-www:
1. Go to **Rules** > **Page Rules**
2. Create rule: `www.movedigital.africa/*`
3. Setting: **Forwarding URL** (301 redirect)
4. Destination: `https://movedigital.africa/$1`

## Step 6: Remove Replit Domain Configuration
Once Cloudflare is working:
1. Go to Replit Deployments
2. Remove `app.movedigital.africa` and `www.movedigital.africa`
3. Keep only the default replit.app domain

## Timeline Expectations
- Nameserver update: 5-15 minutes
- DNS propagation: 15 minutes - 2 hours
- SSL certificate: Active immediately once DNS propagates
- Full functionality: Within 2 hours maximum

## Verification Steps
1. Check nameservers: Use DNS checker tools
2. Test domain: Visit https://movedigital.africa
3. Verify SSL: Check for green padlock in browser
4. Test redirects: Ensure www redirects to non-www (if configured)

## Benefits Once Active
- Free SSL certificates with auto-renewal
- Global CDN for faster loading worldwide
- DDoS protection and security features
- Cache optimization for better performance
- No more dependency on Replit's SSL verification

## Troubleshooting
- If SSL shows "insecure": Wait for DNS propagation
- If site doesn't load: Double-check DNS records
- If redirect loops: Verify SSL mode is "Full (strict)"
- If slow activation: DNS propagation can take up to 24 hours

This approach completely bypasses Replit's SSL issues while keeping your hosting on Replit.