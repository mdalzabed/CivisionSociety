╔══════════════════════════════════════════════════════════════╗
║          CIVISION SOCIETY — RENDER DEPLOYMENT GUIDE         ║
╚══════════════════════════════════════════════════════════════╝

FILES TO UPLOAD TO GITHUB:
  app.py
  requirements.txt
  Procfile
  runtime.txt

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STEP 1 — PUSH TO GITHUB
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
1. Go to github.com → New Repository
2. Name: civision-society → Create
3. Upload all 4 files above

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
STEP 2 — DEPLOY ON RENDER
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
1. Go to render.com → New → Web Service
2. Connect your GitHub repo
3. Name: civision-society
4. Build Command: pip install -r requirements.txt
5. Start Command: gunicorn app:app
6. Click "Advanced" → Add Environment Variables:

   FIREBASE_JSON    = (paste your full Firebase JSON — one line)
   CLOUDINARY_NAME  = dpe578l7l
   CLOUDINARY_KEY   = 431724452151479
   CLOUDINARY_SECRET= (your Cloudinary API secret)

7. Click "Create Web Service"
8. Wait 2-3 minutes → your app is live!

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
HOW TO SET FIREBASE_JSON AS ONE LINE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Your Firebase JSON must be on a single line.
In the Render environment variable field, paste
the entire JSON content — Render handles it fine
even if it looks long.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ADMIN LOGIN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
URL      : https://your-app.onrender.com/admin
Password : Zabed

You can change the admin password from:
Admin → Logo & Settings → Change Admin Password

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
DATA STORAGE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Members, Payments, Events, Gallery → Firestore
Images, Logo → Cloudinary
Data NEVER deletes on server restart.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ENTER MEMBER DATA
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Admin → DB Editor tab → Load member by ID
Edit any field → Save

Or members can join via /join and admin approves them.
