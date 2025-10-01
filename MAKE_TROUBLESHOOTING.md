# 🔧 פתרון בעיות Make.com Webhook

## 🚨 **בעיה מזוהה: Make.com מקבל נתונים ריקים**

### ❓ **מה קורה:**
Make.com מראה:
```
Subject: empty
Text: empty  
HTML content: empty
Sender: empty
Recipients: empty
```

במקום הנתונים האמיתיים שאנחנו שולחים.

## 🔍 **אבחון הבעיה**

### 1. **בדוק את סוג ה-Webhook ב-Make.com:**
- האם יצרת **Custom Webhook** או **Email Webhook**?
- אם זה Email Webhook, זה מסביר למה הוא מחפש Subject, Recipients וכו'

### 2. **הגדרת Webhook נכונה ב-Make.com:**

#### **פתרון A: יצירת Custom Webhook חדש**
1. במ-Make.com, צור Scenario חדש
2. בחר **Webhooks** → **Custom webhook** (לא Email!)
3. לחץ **Add** ויצור webhook חדש  
4. העתק את הכתובת החדשה
5. החלף בקוד:

```javascript
const WEBHOOK_CONFIG = {
    primary: 'הכתובת_החדשה_כאן',
    // ...
};
```

#### **פתרון B: שינוי פורמט הנתונים למייל**
אם אתה רוצה להשאיר Email Webhook, נוכל לשנות את הפורמט:

```javascript
// במקום לשלוח JSON, נשלח כמו מייל
const emailData = {
    to: 'roi@rt-ai.co.il',
    subject: `הרשמה חדשה מ-${data.fullName}`,
    text: `
        שם מלא: ${data.fullName}
        תפקיד: ${data.position}
        אימייל: ${data.email}
        טלפון: ${data.phone}
        ארגון: ${data.organization || 'לא צוין'}
        שאלות: ${data.questions || 'אין'}
        
        זמן הרשמה: ${data.timestamp}
        מקור: ${data.source}
    `,
    html: `
        <h2>הרשמה חדשה לסדנת AI PRO</h2>
        <p><strong>שם מלא:</strong> ${data.fullName}</p>
        <p><strong>תפקיד:</strong> ${data.position}</p>
        <p><strong>אימייל:</strong> ${data.email}</p>
        <p><strong>טלפון:</strong> ${data.phone}</p>
        <p><strong>ארגון:</strong> ${data.organization || 'לא צוין'}</p>
        <p><strong>שאלות:</strong> ${data.questions || 'אין'}</p>
        <hr>
        <small>זמן הרשמה: ${data.timestamp}</small>
    `
};
```

## 🧪 **פונקציות בדיקה חדשות**

הוספתי 3 פונקציות בדיקה:

### 1. **בדיקה בסיסית:**
```javascript
testWebhookQuick()
```

### 2. **בדיקה מלאה:**
```javascript  
testWebhook()
```

### 3. **בדיקת כל הפורמטים:**
```javascript
testAllFormats()
```
יבדוק JSON, FormData, ו-URLEncoded

## 🎯 **צעדי פתרון מומלצים:**

### **שלב 1: זהה את סוג ה-Webhook**
1. היכנס ל-Make.com scenario שלך
2. בדוק איזה סוג webhook יצרת
3. אם זה "Email", זו הסיבה לבעיה

### **שלב 2: בחר פתרון**
- **מומלץ:** צור Custom Webhook חדש
- **חלופי:** שנה לפורמט מייל

### **שלב 3: בדוק עם הכלים החדשים**
1. הוסף `?debug=true` לכתובת
2. השתמש בכפתור "🔄 בדוק כל הפורמטים"
3. עקוב אחר הלוגים בקונסול

## 📞 **אם עדיין לא עובד:**

1. **שתף צילום מסך** של ההגדרת Webhook במ-Make.com
2. **הרץ** `testAllFormats()` ושתף את התוצאות מהקונסול
3. **בדוק** האם Make.com מראה שגיאות בלוג ה-executions

---

**המטרה:** לקבל ב-Make.com את כל השדות עם הערכים האמיתיים במקום "empty"!