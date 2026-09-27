# UBot Frontend — Deploy ke Vercel

## File (semua FLAT, tanpa folder)
```
index.html      ← auto redirect (cek server dulu)
connect.html    ← login OTP + 2FA
dashboard.html  ← dashboard utama
profile.html    ← profil user
plan.html       ← upgrade plan
style.css       ← semua styling
vercel.json     ← config Vercel routing
```

## Deploy ke Vercel
```bash
# Cara 1: CLI
npm i -g vercel
vercel --prod

# Cara 2: GitHub
# Push ke GitHub repo → import di vercel.com
# Framework: Other (bukan React/Next)
```

## PENTING: Setelah deploy ke Vercel
Update FRONTEND_URL di .env backend:
```
FRONTEND_URL=https://nama-project-kamu.vercel.app
```
Lalu restart backend di Pterodactyl.

## Fix yang sudah dilakukan
- credentials:'include' di semua fetch → cookie cross-origin bisa jalan
- sameSite:'none' + secure:true di session cookie
- trust proxy aktif untuk deteksi HTTPS
- CORS allow credentials dari Vercel URL
