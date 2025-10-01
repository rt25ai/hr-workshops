# 🇮🇱 הגדרת דומיין ב-BOX.CO.IL

## 📋 סקירה כללית
מדריך לחיבור הפרויקט לדומיין `hr-workshop.rt-ai.co.il` המתארח ב-BOX.CO.IL.

## 🔧 אפשרויות פרסום עם BOX.CO.IL

### אפשרות 1: אירוח ישיר ב-BOX.CO.IL (מומלץ)

#### א. העלאת קבצים ב-cPanel:
1. **התחבר ל-cPanel של BOX.CO.IL**
2. **פתח File Manager**
3. **נווט לתיקייה:** `public_html/hr-workshop/` (או כפי שהגדרת)
4. **העלה את כל הקבצים:**
   ```
   index.html
   css/liquid-glass.css
   js/main.js
   robots.txt
   sitemap.xml
   ```

#### ב. הגדרת Subdomain ב-BOX.CO.IL:
1. **ב-cPanel → Subdomains**
2. **צור subdomain חדש:**
   ```
   Subdomain: hr-workshop
   Domain: rt-ai.co.il
   Document Root: public_html/hr-workshop
   ```
3. **השדה יהיה זמין ב:** `hr-workshop.rt-ai.co.il`

### אפשרות 2: הפניה לפלטפורמה חיצונית

#### א. פרסום בNetlify/Vercel + הפניה מBOX.CO.IL:
1. **פרסם ב-Netlify:**
   - העלה לNetlify → קבל כתובת כמו `amazing-site-123.netlify.app`

2. **ב-cPanel של BOX.CO.IL:**
   - **DNS Zone Editor** או **Redirects**
   - **הוסף CNAME או Redirect:**
   ```
   hr-workshop.rt-ai.co.il → amazing-site-123.netlify.app
   ```

#### ב. יתרונות הפניה חיצונית:
- 🚀 ביצועים מהירים יותר (CDN גלובלי)
- 🔄 עדכונים אוטומטיים מGit
- 📊 סטטיסטיקות מתקדמות
- 🛡️ אבטחה מתקדמת

## 📁 הכנת קבצים ל-BOX.CO.IL

### קבצים מוכנים להעלאה:
```
hr-workshop/ (תיקיית העלאה)
├── index.html              ✅ מוכן
├── css/
│   └── liquid-glass.css    ✅ מוכן
├── js/
│   └── main.js            ✅ מוכן עם webhook
├── robots.txt             ✅ מוכן
├── sitemap.xml            ✅ מעודכן לדומיין
└── .htaccess              🆕 ייווצר עכשיו
```

### הגדרות Apache (.htaccess):
```apache
# Security Headers
Header always set X-Frame-Options "SAMEORIGIN"
Header always set X-Content-Type-Options "nosniff"
Header always set X-XSS-Protection "1; mode=block"
Header always set Referrer-Policy "strict-origin-when-cross-origin"

# Force HTTPS
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]

# Cache Control
<FilesMatch "\.(css|js|png|jpg|jpeg|gif|svg|woff|woff2)$">
    ExpiresActive On
    ExpiresDefault "access plus 1 year"
    Header set Cache-Control "public, immutable"
</FilesMatch>

# Compression
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE text/plain
    AddOutputFilterByType DEFLATE text/html
    AddOutputFilterByType DEFLATE text/xml
    AddOutputFilterByType DEFLATE text/css
    AddOutputFilterByType DEFLATE application/xml
    AddOutputFilterByType DEFLATE application/xhtml+xml
    AddOutputFilterByType DEFLATE application/rss+xml
    AddOutputFilterByType DEFLATE application/javascript
    AddOutputFilterByType DEFLATE application/x-javascript
</IfModule>

# Error Pages
ErrorDocument 404 /index.html
```

## 🚀 צעדי הפרסום המומלצים

### שיטה A: אירוח ישיר (פשוט ויציב)

1. **ב-cPanel של BOX.CO.IL:**
   - צור subdomain: `hr-workshop`
   - נווט לתיקיית `public_html/hr-workshop/`

2. **העלה קבצים:**
   - `index.html` (עמוד ראשי)
   - תיקיית `css/` עם `liquid-glass.css`
   - תיקיית `js/` עם `main.js`
   - `robots.txt`, `sitemap.xml`
   - `.htaccess` (אבטחה וביצועים)

3. **בדוק:**
   - `https://hr-workshop.rt-ai.co.il`
   - פונקציית webhook עם `?debug=true`

### שיטה B: Netlify + הפניה (מתקדם יותר)

1. **פרסום בNetlify:**
   - העלה פרויקט לNetlify
   - קבל כתובת: `hr-workshop-123.netlify.app`

2. **הפניה מBOX.CO.IL:**
   - ב-cPanel → DNS/Redirects
   - הפנה `hr-workshop.rt-ai.co.il` → כתובת Netlify

## 🔍 בדיקות לאחר פרסום

### בדיקות בסיסיות:
1. **נגישות:** `https://hr-workshop.rt-ai.co.il` נטען כראוי
2. **HTTPS:** נעילה ירוקה בדפדפן
3. **טופס:** מילוי ושליחה עובדים
4. **Webhook:** `testWebhookQuick()` מחזיר הצלחה

### בדיקות מתקדמות:
1. **מהירות:** [PageSpeed Insights](https://pagespeed.web.dev)
2. **SEO:** [Google Search Console](https://search.google.com/search-console)
3. **אבטחה:** [SSL Labs Test](https://www.ssllabs.com/ssltest/)

## 📞 תמיכה טכנית

### בעיות נפוצות עם BOX.CO.IL:
1. **Subdomain לא עובד:** בדוק הגדרות DNS
2. **קבצים לא נטענים:** בדוק הרשאות (755 לתיקיות, 644 לקבצים)
3. **HTTPS לא עובד:** וודא שיש תעודת SSL לsubdomain

### איש קשר:
- **תמיכת BOX.CO.IL:** לעזרה בהגדרת subdomain
- **תמיכה טכנית:** למדריך cPanel ו-DNS

---

**הפרויקט מוכן לפרסום ב-BOX.CO.IL עם כל האופטימיזציות הנדרשות!** 🚀