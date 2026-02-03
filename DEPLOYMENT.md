# Deployment Instructions

## Step 1: Push to GitHub

Choose one of these methods to authenticate and push:

### Option A: GitHub CLI (Easiest)
```bash
cd /home/claude/openclaw-directory
gh auth login
git push -u origin main
```

### Option B: Personal Access Token
1. Go to GitHub Settings → Developer settings → Personal access tokens
2. Generate new token with `repo` scope
3. Push using token as password:
```bash
cd /home/claude/openclaw-directory
git push -u origin main
# Username: trulykp
# Password: [paste your token]
```

## Step 2: Deploy to Netlify

### Method 1: Netlify UI (Recommended)
1. Go to https://app.netlify.com
2. Click "Add new site" → "Import an existing project"
3. Connect to GitHub
4. Select `trulykp/openclaw-directory`
5. Configure build settings:
   - Build command: (leave empty)
   - Publish directory: `.`
6. Click "Deploy site"

### Method 2: Netlify CLI
```bash
npm install -g netlify-cli
cd /home/claude/openclaw-directory
netlify login
netlify init
netlify deploy --prod
```

### Method 3: Netlify Drop (Quickest for testing)
1. Go to https://app.netlify.com/drop
2. Drag and drop the `openclaw-directory` folder

## Custom Domain (Optional)

Once deployed, you can add a custom domain in Netlify:
1. Site settings → Domain management
2. Add custom domain
3. Configure DNS as instructed

---

Your site will be live at: `https://[site-name].netlify.app`
