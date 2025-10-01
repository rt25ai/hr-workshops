# 🌐 הגדרת דומיין hr-workshop.rt-ai.co.il

## 📋 סקירה כללית
מדריך להגדרת הדומיין `hr-workshop.rt-ai.co.il` לפרויקט סדנת AI PRO.

## 🔧 שלבי ההגדרה

### 1. הגדרת DNS ב-Cloudflare

#### א. הוספת רשומת CNAME:
```
Type: CNAME
Name: hr-workshop
Content: [כתובת שרת הפרסום - יתמלא לפי פלטפורמה]
Proxy status: Proxied (☁️)
```

#### ב. דוגמאות לפי פלטפורמות שונות:

**Netlify:**
```
Type: CNAME  
Name: hr-workshop
Content: [site-name].netlify.app
```

**Vercel:**
```
Type: CNAME
Name: hr-workshop  
Content: cname.vercel-dns.com
```

**GitHub Pages:**
```
Type: CNAME
Name: hr-workshop
Content: [username].github.io
```

**Surge.sh:**
```
Type: CNAME
Name: hr-workshop
Content: na-west1.surge.sh
```

### 2. הגדרת הפרויקט

#### קבצי הפרויקט מוכנים לפרסום:
- ✅ `index.html` - מעודכן עם הדומיין החדש
- ✅ `js/main.js` - webhook פעיל למ-Make.com  
- ✅ `css/liquid-glass.css` - עיצובים מתקדמים
- ✅ מטא תגים מעודכנים לדומיין החדש

#### הגדרות נוכחיות:
```javascript
// ב-js/main.js
data.source = 'hr-workshop.rt-ai.co.il';

// במטא תגים
<meta property="og:url" content="https://hr-workshop.rt-ai.co.il">
```

### 3. פלטפורמות פרסום מומלצות

#### **Netlify (מומלץ):**
1. **Drag & Drop Deploy:**
   - הכנס ל-[netlify.com](https://netlify.com)
   - גרור את תיקיית הפרויקט לאזור ההעלאה
   - העתק את כתובת ה-.netlify.app

2. **הגדרת דומיין:**
   - Site settings → Domain management
   - Add custom domain: `hr-workshop.rt-ai.co.il`
   - העתק את הרשומות CNAME שנלקחת

#### **Vercel:**
1. **Deploy:**
   - הכנס ל-[vercel.com](https://vercel.com)
   - Import repository או Drag & Drop
   - העתק את כתובת הפרויקט

2. **הגדרת דומיין:**
   - Project Settings → Domains
   - Add: `hr-workshop.rt-ai.co.il`

#### **GitHub Pages:**
1. **העלאת קבצים:**
   - צור repository חדש
   - העלה את כל קבצי הפרויקט
   - Settings → Pages → Deploy from branch

2. **הגדרת דומיין:**
   - הוסף קובץ `CNAME` עם התוכן: `hr-workshop.rt-ai.co.il`

### 4. בדיקת החיבור

#### לאחר הפרסום:
1. **בדוק DNS פרופגיישן:**
   ```bash
   nslookup hr-workshop.rt-ai.co.il
   ```

2. **בדוק HTTPS:**
   - הכנס ל-`https://hr-workshop.rt-ai.co.il`
   - וודא שהתעודה תקינה (ירוק בדפדפן)

3. **בדוק Webhook:**
   - הוסף `?debug=true` לכתובת
   - הרץ `testWebhookQuick()`
   - וודא שהנתונים מגיעים ל-Make.com

### 5. אופטימיזציות Cloudflare

#### הגדרות מומלצות:
- **SSL/TLS:** Full (Strict)
- **Always Use HTTPS:** On
- **Auto Minify:** HTML, CSS, JS
- **Brotli:** On
- **Page Rules:** Browser Cache TTL = 1 month

#### Security Headers:
```
X-Frame-Options: SAMEORIGIN
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
```

## 🚀 צעדים מהירים לפרסום

### אם אתה משתמש ב-Netlify:
1. **הכנס ל-[netlify.com](https://netlify.com)**
2. **Drag & Drop** את תיקיית הפרויקט
3. **העתק את כתובת ה-.netlify.app**
4. **ב-Cloudflare DNS הוסף:**
   ```
   Type: CNAME
   Name: hr-workshop  
   Content: [site-name].netlify.app
   Proxy: ☁️ Proxied
   ```
5. **ב-Netlify הוסף Custom Domain:** `hr-workshop.rt-ai.co.il`

### בדיקה סופית:
- ✅ האתר נטען ב-`https://hr-workshop.rt-ai.co.il`
- ✅ הטופס שולח נתונים ל-Make.com
- ✅ כל הקישורים עובדים תקין
- ✅ עיצוב Liquid Glass מוצג כראוי

## 📞 תמיכה

אם יש בעיות בהגדרה:
1. **בדוק את שגיאות ה-DNS** עם כלים כמו [whatsmydns.net](https://whatsmydns.net)
2. **וודא שהפרויקט עבד מקומית** לפני הפרסום
3. **בדוק לוגים** בפלטפורמת הפרסום

---
*הפרויקט מוכן לפרסום עם דומיין hr-workshop.rt-ai.co.il* 🚀