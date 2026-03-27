# FH Family EDC - GitHub Setup

## Setup Instructions

### 1. Create config.js (LOCAL ONLY - Don't commit to Git)

Create a new file named `config.js` in the same folder as `index.html`:

```javascript
const SUPABASE_URL = 'https://your-project.supabase.co';
const SUPABASE_KEY = 'your-anon-key-here';
```

**Get your credentials from:**
- Supabase Dashboard → Your Project → Settings → API
- Copy "Project URL" and "Anon Key"

### 2. GitHub Pages Setup

#### Step 1: Create GitHub Account
- Go to github.com
- Sign up (free)

#### Step 2: Create New Repository
- Click "+" → "New repository"
- Name: `fh-family-edc` (or any name)
- Description: "Family History Medical Form"
- Set to **PUBLIC**
- Click "Create repository"

#### Step 3: Upload Files
You have 3 options:

**Option A: Via Web Browser (Easiest)**
1. Click "Add file" → "Upload files"
2. Drag & drop these files:
   - `index.html` (your main file)
   - `config.example.js` (example template)
   - `.gitignore` (security file)
   - `README.md` (this file)
3. **IMPORTANT:** Do NOT upload `config.js` - GitHub will reject it
4. Click "Commit changes"

**Option B: Via Git Command Line**
```bash
git clone https://github.com/YOUR-USERNAME/fh-family-edc.git
cd fh-family-edc

# Copy your files here
cp /path/to/index.html .
cp /path/to/config.example.js .
cp /path/to/.gitignore .
cp /path/to/README.md .

# Create config.js locally (NOT in git)
echo "const SUPABASE_URL = 'https://...'" > config.js

# Add and commit
git add index.html config.example.js .gitignore README.md
git commit -m "Initial commit"
git push
```

#### Step 4: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click "Settings" (gear icon)
3. Click "Pages" (left sidebar)
4. Under "Branch", select `main`
5. Click "Save"
6. Wait 1-2 minutes
7. Your site is live at: `https://YOUR-USERNAME.github.io/fh-family-edc`

### 4. Local Testing

Before deploying:

1. Create `config.js` in your local folder:
```javascript
const SUPABASE_URL = 'https://your-project.supabase.co';
const SUPABASE_KEY = 'your-anon-key-here';
```

2. Open `index.html` in your browser
3. Should see login page

### ⚠️ SECURITY NOTES

✅ **DO commit to GitHub:**
- index.html
- config.example.js
- .gitignore
- README.md

❌ **DO NOT commit to GitHub:**
- config.js (your actual credentials)
- .env files
- Any file with secrets

The `.gitignore` file prevents accidents.

### 🔒 Database Security

Your Supabase database is safe because:
1. Credentials are in `config.js` (local only, not on GitHub)
2. `.gitignore` prevents accidental commits
3. Even if someone forks your repo, they won't see your credentials
4. They'll only see `config.example.js` as a template

### Troubleshooting

**Error: "config.js not found"**
- You forgot to create `config.js` locally
- Create it with your actual Supabase credentials

**GitHub Pages not updating**
- Wait 2-3 minutes after push
- Hard refresh your browser (Ctrl+Shift+R)
- Check Settings → Pages to confirm it's enabled

**Can't connect to Supabase**
- Check `config.js` has correct URL and Key
- Verify Supabase project is active
- Check browser console (F12) for errors

---

**Questions?** Check GitHub's Pages documentation: https://pages.github.com/
