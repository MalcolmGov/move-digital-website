# Nameserver Update Guide for Domain Registrar

## Step 1: Find Your Cloudflare Nameservers

In your Cloudflare dashboard:
1. Look for a section called **"Review your DNS records"** or **"Complete setup"**
2. You should see nameservers that look like:
   ```
   ns1.cloudflare.com
   ns2.cloudflare.com
   ```
   (The exact names will be provided by Cloudflare)

OR

Go to **DNS** tab in Cloudflare and look for nameserver information at the top.

## Step 2: Update at Your Domain Registrar

Based on your previous screenshots showing you're using a domain management interface:

### Look for these sections in your registrar:
- **"DNS Settings"**
- **"Nameservers"** 
- **"DNS Management"**
- **"Name Server Records"**

### Current Setup (what you probably have now):
```
ns1.yourdomain.com
ns2.yourdomain.com
```
OR
```
Default nameservers from your registrar
```

### Replace with Cloudflare nameservers:
```
ns1.cloudflare.com
ns2.cloudflare.com
```
(Use the exact ones Cloudflare shows you)

## Step 3: Save Changes

1. Replace ALL existing nameservers with the Cloudflare ones
2. Remove any old nameserver entries
3. Click **"Save"** or **"Update"**
4. Changes take 15 minutes to 2 hours to propagate

## Step 4: Verify Update

After 15-30 minutes, check if the update worked:
- Go back to Cloudflare dashboard
- The warning triangles should disappear
- DNS status should show "Active"

## What This Does

- Transfers DNS control from your registrar to Cloudflare
- Enables Cloudflare's SSL certificates
- Activates CDN and security features
- Your domain registration stays with your current provider

## Important Notes

- Keep your domain registration with current provider
- Only DNS management moves to Cloudflare
- You can always revert by changing nameservers back
- No risk to your domain ownership