# 📤 הוראות העלאה ל-BOX.CO.IL

## 🎯 מטרה
העלאת פרויקט סדנת AI PRO לדומיין `hr-workshop.rt-ai.co.il` ב-BOX.CO.IL

## 📋 רשימת קבצים להעלאה

### ✅ קבצים חיוניים (חובה):
```
📁 hr-workshop/ (תיקיית העלאה)
├── 📄 index.html              (עמוד ראשי)
├── 📁 css/
│   └── 📄 liquid-glass.css    (עיצובים)
├── 📁 js/
│   └── 📄 main.js            (פונקציונליות + webhook)
├── 🤖 robots.txt             (SEO)
├── 🗺️ sitemap.xml            (מפת אתר)
└── ⚙️ .htaccess              (הגדרות שרת)
```

### 📋 קבצים אופציונליים (לא חובה להעלאה):
```
❌ אל תעלה את הקבצים הבאים:
├── README.md
├── WEBHOOK_SETUP.md  
├── BOX_CO_IL_SETUP.md
├── DOMAIN_SETUP.md
├── MAKE_TROUBLESHOOTING.md
├── UPLOAD_INSTRUCTIONS.md
├── LOGO_INTEGRATION.md
├── CNAME
├── _headers
└── _redirects
```

## 🚀 צעדי ההעלאה ב-cPanel

### שלב 1: הכנת Subdomain
1. **התחבר ל-cPanel של BOX.CO.IL**
2. **מצא "Subdomains" ולחץ עליו**
3. **צור subdomain חדש:**
   ```
   Subdomain: hr-workshop
   Domain: rt-ai.co.il  
   Document Root: public_html/hr-workshop
   ```
4. **לחץ "Create"**

### שלב 2: העלאת קבצים
1. **פתח "File Manager" ב-cPanel**
2. **נווט לתיקייה:** `public_html/hr-workshop/`
3. **העלה את הקבצים החיוניים בלבד:**

#### העלאה מהירה:
- **לחץ "Upload"**
- **גרור את הקבצים:**
  - `index.html`
  - `robots.txt`  
  - `sitemap.xml`
  - `.htaccess`

#### יצירת תיקיות:
- **לחץ "+ Folder"** וצור:
  - תיקיית `css`
  - תיקיית `js`

#### העלאה לתיקיות:
- **נווט לתיקיית `css/`** והעלה: `liquid-glass.css`
- **נווט לתיקיית `js/`** והעלה: `main.js`

### שלב 3: הגדרת הרשאות
1. **בחר את כל הקבצים**
2. **לחץ "Permissions"**
3. **הגדר הרשאות:**
   ```
   📁 תיקיות: 755
   📄 קבצים: 644
   ⚙️ .htaccess: 644
   ```

## ✅ בדיקה לאחר העלאה

### ⚠️ שגיאת SSL צפויה בהתחלה:
אם מופיעה שגיאה **"This site can't provide a secure connection"** - זה נורמלי!

### בדיקות בסיסיות:
1. **נווט ל:** `http://hr-workshop.rt-ai.co.il` (HTTP בלבד זמנית!)
2. **וודא שהעמוד נטען** עם כל העיצוב  
3. **HTTPS יעבוד רק לאחר** שBOX.CO.IL יפעילו SSL
4. **מלא טופס** ובדוק ששליחה עובדת

### בדיקת Webhook:
1. **הוסף לכתובת:** `?debug=true`
2. **לחץ על כפתור "⚡ בדיקה מהירה"**
3. **בדוק קונסול** (F12) לאישור שליחה ל-Make.com

### בדיקת SEO:
1. **נווט ל:** `hr-workshop.rt-ai.co.il/robots.txt`
2. **נווט ל:** `hr-workshop.rt-ai.co.il/sitemap.xml`  
3. **שניהם אמורים להיפתח כראוי**

## 🔧 פתרון בעיות נפוצות

### 🚨 בעיה: שגיאת SSL (השכיחה ביותר!)
**תסמינים:** "This site can't provide a secure connection"  
**פתרון מיידי:**
1. **גש ל:** `http://hr-workshop.rt-ai.co.il` (HTTP בלבד)
2. **פנה לתמיכת BOX.CO.IL** לבקש הפעלת SSL
3. **זמנית:** השתמש ב-`.htaccess_no_ssl` במקום `.htaccess`
4. **מדריך מלא:** קרא `SSL_FIX.md`

### בעיה: האתר לא נטען (גם ב-HTTP)
**פתרון:**
- בדוק שה-subdomain נוצר כראוי
- וודא שהקבצים בתיקייה הנכונה: `public_html/hr-workshop/`

### בעיה: עיצוב לא נטען  
**פתרון:**
- וודא שתיקיית `css/` קיימת
- בדוק שהקובץ `liquid-glass.css` בתיקיית `css/`
- בדוק הרשאות: תיקיות 755, קבצים 644

### בעיה: טופס לא עובד
**פתרון:**
- וודא שתיקיית `js/` קיימת  
- בדוק שהקובץ `main.js` בתיקיית `js/`
- פתח קונסול (F12) ובדוק שגיאות JavaScript

### בעיה: HTTPS לא עובד (לאחר 24 שעות)
**פתרון:**
- צור קשר עם תמיכת BOX.CO.IL שוב
- בקש בדיקה של תעודת SSL לsubdomain

## 📞 תמיכה

### BOX.CO.IL תמיכה:
- **טלפון:** לפי הפרטים באתר BOX.CO.IL  
- **נושא:** הפעלת SSL ל-subdomain חדש
- **פרטים:** `hr-workshop.rt-ai.co.il`

### בדיקה עצמאית:
- **מהירות אתר:** [PageSpeed Insights](https://pagespeed.web.dev)
- **SSL Test:** [SSL Labs](https://www.ssllabs.com/ssltest/)

---

## 🎉 סיכום
לאחר ביצוע כל השלבים, האתר יהיה זמין ב:
**`https://hr-workshop.rt-ai.co.il`** עם כל הפונקציונליות המלאה!

**זמן העלאה משוער: 10-15 דקות** ⏱️