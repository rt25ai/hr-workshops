# 📤 העלאת קבצים לBOX.CO.IL - שלב אחר שלב

## 🎯 מטרה: להעלות 6 קבצים בלבד לתיקיית hr-workshop

## 📋 רשימת קבצים להעלאה (רק אלה!):
```
✅ להעלות:
1. index.html              (עמוד ראשי)
2. css/liquid-glass.css    (עיצובים)  
3. js/main.js             (פונקציונליות)
4. robots.txt             (SEO)
5. sitemap.xml            (מפת אתר)
6. .htaccess_no_ssl       (הגדרות שרת - בלי SSL זמנית)

❌ לא להעלות:
- כל קבצי ה-.md
- _headers, _redirects  
- CNAME
- .htaccess (הרגיל)
```

## 🚀 צעדי ההעלאה ב-cPanel

### שלב 1: כניסה לFile Manager
1. **התחבר ל-cPanel של BOX.CO.IL**
2. **מצא ולחץ על "File Manager"**
3. **נווט לתיקייה:** `public_html/hr-workshop/`
   - אם התיקייה לא קיימת - צור אותה עם "Create Folder"

### שלב 2: העלאת הקבצים הראשיים
1. **בתיקיית `public_html/hr-workshop/`**
2. **לחץ "Upload" בתפריט העליון**
3. **העלה את הקבצים האלה:**
   - `index.html`
   - `robots.txt` 
   - `sitemap.xml`
   - `.htaccess_no_ssl` (שנה לו שם ל-`.htaccess` אחרי העלאה)

### שלב 3: יצירת תיקיות
1. **ב-File Manager, לחץ "Create Folder"**
2. **צור תיקיית:** `css`
3. **צור תיקיית:** `js`

### שלב 4: העלאת קבצי CSS
1. **כנס לתיקיית `css/`** (double-click)
2. **לחץ "Upload"**
3. **העלה:** `liquid-glass.css`
4. **חזור לתיקייה הראשית** (לחץ "hr-workshop" בנתיב)

### שלב 5: העלאת קבצי JavaScript  
1. **כנס לתיקיית `js/`**
2. **לחץ "Upload"**
3. **העלה:** `main.js`
4. **חזור לתיקייה הראשית**

### שלב 6: שינוי שם .htaccess
1. **ב-File Manager, מצא את הקובץ:** `.htaccess_no_ssl`
2. **לחץ עליו ימין → "Rename"**
3. **שנה שם ל:** `.htaccess`

### שלב 7: הגדרת הרשאות
1. **בחר את כל הקבצים** (Ctrl+A)
2. **לחץ ימין → "Change Permissions"**
3. **הגדר:**
   - **תיקיות (css, js):** 755
   - **קבצים:** 644

## ✅ בדיקה סופית

### המבנה הסופי אמור להיות:
```
public_html/hr-workshop/
├── index.html           ✅
├── robots.txt          ✅  
├── sitemap.xml         ✅
├── .htaccess           ✅ (שם שונה מ-.htaccess_no_ssl)
├── css/
│   └── liquid-glass.css ✅
└── js/
    └── main.js         ✅
```

### בדיקת גישה:
1. **פתח דפדפן במצב פרטי** (`Ctrl + Shift + N`)
2. **נסה:** `http://hr-workshop.rt-ai.co.il`
3. **אמור להציג את דף הסדנה** עם כל העיצוב!

## 🔧 אם משהו לא עובד

### הקובץ index.html לא נטען:
- בדוק שהוא בתיקייה הנכונה
- בדוק הרשאות: 644

### העיצוב לא נטען:
- בדוק ש-`liquid-glass.css` בתיקיית `css/`
- בדוק הרשאות תיקייה: 755

### הטופס לא עובד:
- בדוק ש-`main.js` בתיקיית `js/`
- פתח קונסול (F12) לבדוק שגיאות

## 🎉 הצלחה!
אחרי ההעלאה, האתר יהיה זמין ב:
**`http://hr-workshop.rt-ai.co.il`** (HTTP זמנית עד להפעלת SSL)

---
**זמן העלאה משוער: 10-15 דקות** ⏱️