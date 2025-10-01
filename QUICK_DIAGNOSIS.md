# 🔍 אבחון מהיר לבעיית hr-workshop.rt-ai.co.il

## צעדי בדיקה מהירים:

### 1. בדיקת HTTP (ללא SSL)
נסה לגשת ל:
```
http://hr-workshop.rt-ai.co.il
```

**אם עובד:** הבעיה רק ב-SSL ✅
**אם לא עובד:** הבעיה בSubdomain או בקבצים ❌

### 2. בדיקת DNS
פתח Command Prompt וחפש:
```
nslookup hr-workshop.rt-ai.co.il
```

**אם מחזיר IP:** הSubdomain קיים ✅
**אם מחזיר שגיאה:** הSubdomain לא נוצר ❌

### 3. בדיקת Subdomain ב-cPanel
התחבר ל-cPanel של BOX.CO.IL:
- לך ל "Subdomains"
- בדוק אם `hr-workshop` מופיע ברשימה
- בדוק שה-Document Root הוא: `public_html/hr-workshop`

## סיכום אפשרויות:

### 🟢 HTTP עובד + DNS עובד
**משמעות:** הכל תקין, רק חסר SSL
**פעולה:** פנה לBOX.CO.IL לבקש הפעלת SSL

### 🟡 HTTP לא עובד + DNS עובד  
**משמעות:** הSubdomain קיים אבל הקבצים לא הועלו נכון
**פעולה:** בדוק קבצים בtיקייה `public_html/hr-workshop/`

### 🔴 DNS לא עובד
**משמעות:** הSubdomain לא נוצר כלל
**פעולה:** צור את הSubdomain ב-cPanel

## מה לעשות עכשיו?

1. **נסה HTTP:** `http://hr-workshop.rt-ai.co.il`
2. **בדוק DNS:** `nslookup hr-workshop.rt-ai.co.il`  
3. **דווח תוצאות** - איזה מהבדיקות עבדה/לא עבדה

## אם כלום לא עובד - תתחיל מההתחלה:

### צעדי יצירת Subdomain מחדש:
1. **cPanel → Subdomains**
2. **Create New Subdomain:**
   ```
   Subdomain: hr-workshop
   Domain: rt-ai.co.il
   Document Root: public_html/hr-workshop
   ```
3. **לחץ Create**
4. **המתן 5-10 דקות לפרופגציה**

---
**הבדיקות האלה יעזרו לזהות בדיוק איפה הבעיה!**