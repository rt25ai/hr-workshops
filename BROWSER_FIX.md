# 🔧 פתרון בעיית הדפדפן - הפניה אוטומטית ל-HTTPS

## 🚨 הבעיה
הדפדפן מנסה אוטומטית לגשת ל-HTTPS גם כשאתה מקליד HTTP.

## ✅ פתרונות מיידיים

### פתרון 1: נקה Cache והיסטוריה
1. **Chrome/Edge:**
   - לחץ `Ctrl + Shift + Delete`
   - בחר "All time"
   - סמן: "Cookies", "Cached images", "Browsing history"
   - לחץ "Clear data"

2. **Firefox:**
   - לחץ `Ctrl + Shift + Delete`
   - בחר "Everything"
   - סמן הכל
   - לחץ "Clear Now"

### פתרון 2: מצב פרטי (Incognito)
1. **פתח חלון פרטי:** `Ctrl + Shift + N`
2. **נסה שוב:** `http://hr-workshop.rt-ai.co.il`

### פתרון 3: השבת HTTPS Strict Transport Security
1. **Chrome:** 
   - גש ל: `chrome://net-internals/#hsts`
   - בתחתית בחלק "Delete domain security policies"
   - הקלד: `hr-workshop.rt-ai.co.il`
   - לחץ "Delete"

2. **Edge:**
   - גש ל: `edge://net-internals/#hsts`
   - עשה אותו תהליך

### פתרון 4: שינוי DNS זמני
אם עדיין לא עובד, ייתכן שיש בעיית DNS.
1. **שנה DNS ל-Google:**
   - Settings → Network → Change adapter options
   - לחץ ימין על החיבור → Properties
   - בחר "Internet Protocol Version 4"
   - שנה ל: `8.8.8.8` ו-`8.8.4.4`

### פתרון 5: בדוק עם כלי אונליין
אם הדפדפן עדיין לא עובד, בדוק עם כלי חיצוני:
- **Down For Everyone:** https://downforeveryoneorjustme.com/hr-workshop.rt-ai.co.il
- **Website Checker:** https://www.websiteplanet.com/webtools/down-or-not/

## 🔍 אבחון נוסף

### בדיקת nslookup (Windows):
1. פתח Command Prompt (`cmd`)
2. הקלד: `nslookup hr-workshop.rt-ai.co.il`
3. **אם מחזיר IP:** הDNS עובד ✅
4. **אם מחזיר שגיאה:** הSubdomain לא קיים ❌

### בדיקת ping:
```
ping hr-workshop.rt-ai.co.il
```
אם מחזיר תגובה - השרת זמין.

## 🎯 צעדים לפי סדר עדיפות:

### 1. נסה מצב פרטי
**הכי מהיר:** פתח Incognito ונסה `http://hr-workshop.rt-ai.co.il`

### 2. אם עדיין לא עובד - nslookup
```
nslookup hr-workshop.rt-ai.co.il
```

### 3. לפי התוצאה:
- **יש IP:** הבעיה בדפדפן/SSL
- **אין IP:** הSubdomain לא נוצר ב-BOX.CO.IL

## 📞 אם כלום לא עובד

### צור קשר עם BOX.CO.IL:
```
נושא: Subdomain לא עובד

שלום,
יצרתי subdomain: hr-workshop.rt-ai.co.il
אבל הוא לא נגיש.

אנא בדקו:
1. האם הSubdomain נוצר כראוי
2. האם DNS מוגדר נכון  
3. הפעלת SSL לSubdomain

תודה!
```

---
## 💡 טיפ מהיר
**נסה מצב פרטי קודם כל** - זה פותר 80% מהבעיות!