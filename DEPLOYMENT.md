# Deployment Guide

## GitHub Setup

### Step 1: Create a GitHub Repository
1. Go to [GitHub](https://github.com/new)
2. Create a new repository named `AIReadySchoolRedesign`
3. Don't initialize with README (we already have one)

### Step 2: Add Remote and Push Code
```bash
cd path/to/AIReadySchoolRedesign

# Add GitHub remote
git remote add origin https://github.com/yourusername/AIReadySchoolRedesign.git

# Rename branch to main (GitHub default)
git branch -M main

# Push code to GitHub
git push -u origin main
```

### Step 3: Verify on GitHub
Visit `https://github.com/yourusername/AIReadySchoolRedesign` to see your code

---

## Vercel Deployment

### Option A: Deploy via GitHub Integration (Recommended)

1. **Connect GitHub to Vercel**:
   - Go to [vercel.com](https://vercel.com)
   - Sign up or log in
   - Click "New Project"
   - Select "Import Git Repository"
   - Authorize Vercel to access your GitHub account
   - Select the `AIReadySchoolRedesign` repository

2. **Configure Project**:
   - Framework: `Other` (or leave blank)
   - Root Directory: `./` (default)
   - Build Command: Leave empty
   - Output Directory: Leave as-is
   - Environment Variables: None needed

3. **Deploy**:
   - Click "Deploy"
   - Wait for deployment to complete
   - Your site will be live at `your-project-name.vercel.app`

4. **Auto-Deployments**:
   - Every push to `main` branch automatically deploys
   - Preview deployments created for pull requests

### Option B: Deploy via Vercel CLI

1. **Install Vercel CLI**:
   ```bash
   npm install -g vercel
   ```

2. **Deploy from Project Directory**:
   ```bash
   cd AIReadySchoolRedesign
   vercel
   ```

3. **Follow Prompts**:
   - Link to existing project or create new one
   - Confirm build settings
   - Wait for deployment to complete

### Option C: Deploy Manually via Vercel Dashboard

1. Go to [vercel.com/new](https://vercel.com/new)
2. Select "Static Site"
3. Upload your project files or connect GitHub
4. Configure and deploy

---

## Custom Domain (Optional)

After deployment, add a custom domain:

1. In Vercel project settings → Domains
2. Add your domain
3. Update DNS records per Vercel instructions
4. Wait for SSL certificate (automatic)

---

## Continuous Deployment Setup

Your site automatically redeploys when you:

```bash
# Make changes locally
git add .
git commit -m "Update homepage styling"
git push origin main

# Vercel automatically detects changes and deploys
# Check deployment status at https://vercel.com/dashboard
```

---

## Testing Before Deployment

### Local Testing
```bash
# Start local server
python -m http.server 8000

# Visit http://localhost:8000
# Test on mobile using: http://[your-ip]:8000
```

### Testing Checklist
- [ ] Navigation works on desktop and mobile
- [ ] Hero section looks good on all screen sizes
- [ ] Product cards display correctly
- [ ] Mobile hamburger menu toggles
- [ ] All links work (both internal and external)
- [ ] Forms/CTAs function properly
- [ ] Load time is acceptable
- [ ] No console errors

---

## Troubleshooting

### Vercel says "Build Error"
- Check that `vercel.json` is in root directory
- Ensure all files are pushed to GitHub
- Check Vercel logs for specific error messages

### Page shows 404
- Verify `index.html` is in root directory
- Check that `vercel.json` is configured correctly
- Try rebuilding the project from Vercel dashboard

### Styles not loading
- Clear browser cache (Ctrl+Shift+Delete)
- Check that `styles.css` is in root directory
- Verify relative paths are correct

---

## Deployment Checklist

Before submitting:

- [ ] GitHub repository created and code pushed
- [ ] Vercel deployment successful
- [ ] Custom domain configured (optional)
- [ ] All links tested and working
- [ ] Mobile responsiveness verified
- [ ] README.md includes audit findings
- [ ] README includes deployment links
- [ ] No broken images or missing assets

---

**Need Help?**
- Vercel Docs: https://vercel.com/docs
- GitHub Guides: https://guides.github.com
- Contact Vercel Support: https://vercel.com/support
