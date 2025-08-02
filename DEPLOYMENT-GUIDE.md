# 🚀 Complete GitHub Pages Deployment Guide

## Step 1: Create GitHub Repository

### 1.1 Go to GitHub
- Open your web browser
- Navigate to [github.com](https://github.com)
- Sign in to your GitHub account

### 1.2 Create New Repository
- Click the **green "New"** button (or the **"+"** icon in top right → "New repository")
- Fill out the form:
  - **Repository name**: `client-avatar-tool`
  - **Description**: `Simple Client Avatar Discovery Tool for Interior Designers`
  - **Visibility**: Select **Public** (required for free GitHub Pages)
  - **Initialize repository**: Leave ALL checkboxes UNCHECKED
    - ❌ Don't add README file
    - ❌ Don't add .gitignore
    - ❌ Don't choose a license
- Click **"Create repository"**

### 1.3 Copy Repository URL
After creation, GitHub shows a page with setup instructions. Copy the repository URL that looks like:
```
https://github.com/YOUR_USERNAME/client-avatar-tool.git
```

## Step 2: Push Your Local Code to GitHub

### 2.1 Add Remote Origin
Open Command Prompt/Terminal in the project folder and run:
```bash
cd "C:\Users\dougl\client-avatar-tool"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/client-avatar-tool.git
```
**Replace `YOUR_USERNAME` with your actual GitHub username**

### 2.2 Push to GitHub
```bash
git push -u origin main
```

If prompted for credentials:
- **Username**: Your GitHub username
- **Password**: Use a Personal Access Token (not your regular password)

### 2.3 Create Personal Access Token (if needed)
If you don't have a token:
1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click "Generate new token (classic)"
3. Set expiration and select scopes:
   - ✅ `repo` (full repository access)
4. Copy the token and use it as your password

## Step 3: Enable GitHub Pages

### 3.1 Go to Repository Settings
- Navigate to your repository on GitHub
- Click the **"Settings"** tab (rightmost tab in the repository menu)

### 3.2 Find Pages Section
- Scroll down the left sidebar
- Click **"Pages"** (under "Code and automation" section)

### 3.3 Configure Pages
- **Source**: Select **"Deploy from a branch"**
- **Branch**: Select **"main"**
- **Folder**: Select **"/ (root)"**
- Click **"Save"**

### 3.4 Wait for Deployment
- GitHub will show: "Your site is ready to be published at..."
- Wait 1-2 minutes for the first build
- Refresh the page to see: "Your site is live at..."

## Step 4: Configure API Keys

### 4.1 Edit index.html on GitHub
1. In your repository, click **"index.html"**
2. Click the **pencil icon** (Edit this file)
3. Find line ~189: `const CLAUDE_API_KEY = 'your-claude-api-key-here';`
4. Replace with your actual Claude API key:
   ```javascript
   const CLAUDE_API_KEY = 'sk-ant-api03-your-actual-key-here';
   ```

### 4.2 Configure Google Analytics (Optional)
1. Find lines ~10-15 with Google Analytics code
2. Replace `GA_MEASUREMENT_ID` with your actual Google Analytics ID:
   ```html
   <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
   ```
   ```javascript
   gtag('config', 'G-XXXXXXXXXX');
   ```

### 4.3 Commit Changes
- Scroll down to "Commit changes"
- **Commit message**: `Configure API keys for production`
- Select **"Commit directly to the main branch"**
- Click **"Commit changes"**

## Step 5: Test Your Deployment

### 5.1 Access Your Live Site
Your tool is now live at:
```
https://YOUR_USERNAME.github.io/client-avatar-tool/
```

### 5.2 Test Both Access Levels
- **Free access**: `https://YOUR_USERNAME.github.io/client-avatar-tool/`
- **Paid access**: `https://YOUR_USERNAME.github.io/client-avatar-tool/?access=paid`

### 5.3 Test Core Features
1. ✅ Page loads correctly
2. ✅ Chat interface works
3. ✅ Can send messages (with API key configured)
4. ✅ Payment prompt appears after 3 messages (free version)
5. ✅ Can access all phases (paid version)
6. ✅ PDF generation works
7. ✅ Rating system appears after PDF

## Step 6: Set Up Custom Domain (Optional)

### 6.1 Configure DNS (at your domain provider)
Add a CNAME record:
- **Name**: `tools` (or whatever subdomain you want)
- **Value**: `YOUR_USERNAME.github.io`

### 6.2 Add Custom Domain to GitHub
1. In repository Settings → Pages
2. Under "Custom domain", enter: `tools.interiordesignher.com`
3. Click "Save"
4. Wait for DNS check (may take up to 24 hours)
5. Enable "Enforce HTTPS" once available

## Step 7: Update Gumroad Integration

### 7.1 Update Payment Links
In your Gumroad product settings, set the redirect URL to your live site:
```
https://YOUR_USERNAME.github.io/client-avatar-tool/?access=paid
```

### 7.2 Test Payment Flow
1. Complete a test purchase on Gumroad
2. Verify redirect works with `?access=paid` parameter
3. Confirm full access to all 6 phases

## Troubleshooting

### Common Issues

**🔴 "Your site is ready to be published" (not live yet)**
- Wait 1-2 minutes and refresh
- Check that you selected "main" branch and "/ (root)" folder

**🔴 API errors in console**
- Verify Claude API key is correct and has credits
- Check for CORS issues (Claude API should work from GitHub Pages)

**🔴 404 Page Not Found**
- Ensure file is named `index.html` (not `index.htm`)
- Verify repository is public
- Check GitHub Pages settings

**🔴 Changes not appearing**
- GitHub Pages cache can take 1-2 minutes to update
- Try hard refresh (Ctrl+F5) or incognito mode

### Getting Help
- Check GitHub Pages status: [githubstatus.com](https://githubstatus.com)
- Repository Issues: Create an issue in your repository
- Contact: douglas@interiordesignher.com

## Security Notes

⚠️ **Important**: The Claude API key will be visible in your client-side code. For production use:

1. **Restrict API Key**: In Claude console, restrict key to specific domains
2. **Monitor Usage**: Set up usage alerts
3. **Consider Proxy**: For sensitive applications, use a backend proxy

## Success Checklist

- ✅ GitHub repository created and public
- ✅ Code pushed successfully
- ✅ GitHub Pages enabled and live
- ✅ Claude API key configured
- ✅ Google Analytics configured (optional)
- ✅ Custom domain configured (optional)
- ✅ Gumroad payment flow tested
- ✅ All features working on live site

**Your Client Avatar Discovery Tool is now live and ready for users!** 🎉