# Tennis AI Coach - Deployment Instructions

## Files Included
- `index.html` - Main application (frontend)
- `api/chat.js` - Serverless API endpoint (backend with Google Gemini)
- `vercel.json` - Vercel configuration
- `package.json` - Node.js package info

## Step-by-Step Deployment to Vercel (FREE)

### 1. Get Your Google Gemini API Key (100% FREE)
1. Go to https://aistudio.google.com/app/apikey
2. Sign in with your Google account
3. Click "Create API Key"
4. Click "Create API key in new project" (or select existing project)
5. Copy the key (it will look like: `AIzaSy...`)
6. **Save it securely** - you'll need it in step 4

**Note:** Gemini's free tier includes:
- 60 requests per minute
- 1,500 requests per day
- Completely free forever!

### 2. Install Vercel CLI (Optional but recommended)
```bash
npm install -g vercel
```

### 3. Deploy via Vercel Website (Easiest Method)

**Option A: Using Vercel CLI**
1. Open terminal in the project folder
2. Run: `vercel`
3. Follow the prompts:
   - "Set up and deploy?" → Yes
   - "Which scope?" → Your account
   - "Link to existing project?" → No
   - "What's your project's name?" → tennis-ai-coach (or whatever you want)
   - "In which directory is your code located?" → ./
4. After deployment, add your API key:
   - Run: `vercel env add GEMINI_API_KEY`
   - Choose "Production"
   - Paste your Gemini API key
5. Redeploy: `vercel --prod`

**Option B: Using Vercel Dashboard (Easier)**
1. Go to https://vercel.com/
2. Sign up with GitHub (or email) - completely free!
3. Click "Add New" → "Project"
4. Click "Import Git Repository" or drag the folder
5. If using GitHub:
   - Create a new repository on GitHub
   - Upload all files (index.html, api folder, vercel.json, package.json)
   - Connect it to Vercel
6. Before deploying, click "Environment Variables"
7. Add: 
   - Name: `GEMINI_API_KEY`
   - Value: Your Gemini API key (from step 1)
   - Environment: Production
8. Click "Deploy"

### 4. Your Site is Live! 🎉
- Vercel will give you a URL like: `tennis-ai-coach.vercel.app`
- Share this URL with anyone!
- (Optional) Add a custom domain in Vercel settings

## Troubleshooting

**Problem: "API request failed"**
- Make sure you added the `GEMINI_API_KEY` environment variable
- Check that your API key is valid at https://aistudio.google.com/app/apikey
- Redeploy after adding the key

**Problem: "404 Not Found"**
- Make sure `index.html` is in the root directory
- Check that `api/chat.js` is in an `api` folder

**Problem: Deployment fails**
- Make sure all files are uploaded
- Check that `vercel.json` and `package.json` are present

## Cost Management
- Google Gemini API is completely FREE
- Free tier: 60 requests/minute, 1,500 requests/day
- No credit card required
- Monitor usage at: https://aistudio.google.com/app/apikey

## Need Help?
Check the console in your browser (F12) for error messages.

## Important Notes
- The app now uses Google Gemini 1.5 Flash (fast and free!)
- Quality is excellent for tennis coaching use cases
- If you need more requests, you can upgrade to paid tier later (but free tier is very generous)

