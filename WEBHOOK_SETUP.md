# 🔗 הגדרת Webhook לטופס ההרשמה

## 📋 סקירה כללית
המערכת תומכת בשליחת נתוני הרשמה לשלושה סוגי webhooks שונים עם מנגנון fallback אוטומטי:

1. **Webhook ראשי** (Make.com / Integromat)
2. **Webhook גיבוי** (Zapier)  
3. **Email Fallback** (Formspree)

## ⚙️ הגדרת Webhooks

### 1. Make.com (פעיל כעת) ✅
```javascript
// Webhook פעיל מוגדר
primary: 'https://hook.eu2.make.com/p2gjr4ddsffx44yvxeef6wh6532pspd1'
```

**סטטוס:** ✅ **מוגדר ופעיל**
- Webhook ID: `p2gjr4ddsffx44yvxeef6wh6532pspd1`
- כל טופס הרשמה יישלח ישירות ל-Make.com scenario שלך

### 2. Zapier (גיבוי)
```javascript
// החלף את YOUR_ZAPIER_ID ב-ID האמיתי מ-Zapier
backup: 'https://hooks.zapier.com/hooks/catch/YOUR_ZAPIER_ID/'
```

**צעדים:**
1. היכנס ל-[Zapier](https://zapier.com)
2. צור Zap חדש
3. בחר "Webhooks by Zapier" כ-trigger
4. בחר "Catch Hook"
5. העתק את כתובת ה-webhook
6. החלף את `YOUR_ZAPIER_ID` בקוד

### 3. Formspree (Email Fallback)
```javascript
// החלף את YOUR_FORM_ID ב-ID האמיתי מ-Formspree
email: 'https://formspree.io/f/YOUR_FORM_ID'
```

**צעדים:**
1. היכנס ל-[Formspree](https://formspree.io)
2. צור טופס חדש
3. העתק את כתובת הטופס
4. החלף את `YOUR_FORM_ID` בקוד

## 📊 מבנה הנתונים הנשלחים

```json
{
  "fullName": "שם מלא",
  "position": "תפקיד",
  "email": "email@example.com",
  "phone": "052-1234567",
  "organization": "שם הארגון",
  "questions": "שאלות או הערות",
  "timestamp": "2024-01-15T10:30:00.000Z",
  "source": "hr-workshop.rt-ai.co.il",
  "form_type": "registration-form",
  "user_agent": "Mozilla/5.0...",
  "page_url": "https://hr-workshop.rt-ai.co.il#register"
}
```

## 🔄 מנגנון Fallback

המערכת פועלת בסדר הבא:
1. **ניסיון ראשון**: Make.com webhook
2. **במקרה של כשל**: Zapier webhook  
3. **במקרה של כשל נוסף**: Formspree email
4. **אם הכל נכשל**: הודעת שגיאה למשתמש

## 🛠️ עדכון כתובות Webhook

הקונפיגורציה הנוכחית בקובץ `js/main.js` (שורות 377-381):

```javascript
const WEBHOOK_CONFIG = {
    primary: 'https://hook.eu2.make.com/p2gjr4ddsffx44yvxeef6wh6532pspd1', // ✅ Active
    backup: 'https://hooks.zapier.com/hooks/catch/YOUR_ZAPIER_ID/', // Configure if needed
    email: 'https://formspree.io/f/YOUR_FORM_ID' // Configure if needed
};
```

## 📱 דוגמאות לאוטומציות

### Make.com - דוגמת Scenario
1. **Webhook** → קבלת הנתונים
2. **Google Sheets** → שמירה בגיליון
3. **Gmail** → שליחת מייל אישור לנרשם
4. **Slack/Discord** → התראה לצוות
5. **Calendar** → הוספה ליומן

### Zapier - דוגמת Zap
1. **Webhooks** → קבלת הנתונים
2. **Airtable** → שמירה במסד נתונים
3. **Mailchimp** → הוספה לרשימת תפוצה
4. **WhatsApp Business** → שליחת הודעה

## 🔐 אבטחה והגנת פרטיות

- כל הנתונים נשלחים ב-HTTPS
- אין שמירה מקומית של נתונים רגישים
- המשתמש מקבל הודעת פרטיות ברורה
- תמיכה בהגנת GDPR

## 🧪 בדיקות

### בדיקת Webhook - Make.com פעיל ✅
**Webhook מוגדר**: `p2gjr4ddsffx44yvxeef6wh6532pspd1@hook.eu2.make.com`

#### דרכי בדיקה:

**1. בדיקה אוטומטית (מומלץ):**
- הוסף `?debug=true` לכתובת האתר 
- תופיע כפתור "🧪 בדוק Webhook" בפינה הימנית התחתונה
- לחץ לבדיקה מהירה

**2. בדיקה ידנית:**
1. פתח את כלי הפיתוח בדפדפן (F12)
2. מלא את הטופס ושלח
3. בדוק ב-Console את ההודעות:
   - ✅ "נשלח בהצלחה ל-Make.com webhook!"
   - ⚠️ "Make.com webhook החזיר שגיאה"
   - ❌ "כל הwebhooks נכשלו"

**3. בדיקות בקונסול:**
- `testWebhook()` - בדיקה מלאה עם כל השדות
- `testWebhookQuick()` - בדיקה מהירה עם נתונים בסיסיים  
- `testAllFormats()` - בדיקת כל הפורמטים (JSON, FormData, URLEncoded, Email)
- כל הפקודות ישלחו נתוני בדיקה ל-Make.com scenario

## 🔧 פתרון בעיות נפוצות

### בעיה: שדות מגיעים ריקים (empty)
**פתרון מתקן אוטומטי:**
- המערכת כעת בודקת שדות חובה לפני שליחה
- לוגים מפורטים מראים איזה שדות מלאים/ריקים
- אין עוד reset מוקדם של הטופס

### בדיקה מתקדמת:
- פתח קונסול הדפדפן (F12)
- השתמש ב-`testWebhookQuick()` לבדיקה מהירה
- עקב אחר הלוגים המפורטים

### בדיקת תגובת משתמש
- הודעת הצלחה (ירוקה) אחרי שליחה מוצלחת
- הודעת שגיאה (אדומה) אחרי כשל
- מצב טעינה על הכפתור ("שולח...")

## 📞 תמיכה טכנית

במקרה של בעיות:
1. בדוק את ה-Console לשגיאות JavaScript
2. וודא שכתובות ה-webhooks נכונות
3. בדוק שהשירותים (Make/Zapier/Formspree) פעילים
4. במקרה הצורך - צור קשר לתמיכה טכנית

---
*מעודכן לאחרונה: דצמבר 2024*