# 📤 אפשרויות העלאה ל-BOX.CO.IL

## 🎯 דרכים להעלות קבצים (ללא cPanel)

### אפשרות 1: FTP Client (מומלץ!)
**תוכנות FTP חינמיות:**
- **FileZilla** (הכי פופולרי) - https://filezilla-project.org/
- **WinSCP** (Windows) - https://winscp.net/
- **Cyberduck** (Mac/Windows) - https://cyberduck.io/

#### הגדרת FTP:
```
Host: ftp.rt-ai.co.il (או ftp.box.co.il)
Username: [שם המשתמש שלך]
Password: [הסיסמה שלך]  
Port: 21
Protocol: FTP או SFTP
```

### אפשרות 2: Web-based File Manager
רוב חברות האירוח (כולל BOX.CO.IL) נותנות גישה לFile Manager גם בלי cPanel:
- **בדוק באתר BOX.CO.IL** אם יש "File Manager" נפרד
- **או "Web Files"/"Online File Manager"**

### אפשרות 3: פרסום בשירות חיצוני + הפניה
במקום להעלות ישירות ל-BOX.CO.IL:

#### Netlify (הכי פשוט):
1. **גש ל-netlify.com**
2. **גרור את התיקייה** עם כל הקבצים
3. **קבל כתובת** כמו: `amazing-site.netlify.app`
4. **ב-BOX.CO.IL הגדר redirect/CNAME** מ-hr-workshop.rt-ai.co.il

#### Vercel:
1. **גש ל-vercel.com**  
2. **העלה פרויקט**
3. **קבל כתובת** כמו: `project.vercel.app`
4. **הגדר הפניה מBOX.CO.IL**

## 🔍 איך לבדוק איזה אפשרויות יש לך ב-BOX.CO.IL

### בדוק באימייל הרישום:
- **חפש אימייל מBOX.CO.IL** עם פרטי החשבון
- **בדוק אם יש:**
  - פרטי FTP
  - קישור לפאנל ניהול
  - הוראות העלאה

### בדוק באתר BOX.CO.IL:
1. **היכנס לאזור הלקוחות**
2. **חפש:**
   - "ניהול קבצים"
   - "File Manager" 
   - "FTP Access"
   - "Web Files"

## 📋 מה אתה מעדיף?

### אם יש לך פרטי FTP:
✅ **FileZilla** - הכי פשוט וידידותי  
- הורד והתקן
- הזן פרטי חיבור
- גרור קבצים לתיקיית `hr-workshop`

### אם אין לך גישה כלל:
✅ **Netlify + הפניה**
- פרסם בNetlify (5 דקות)
- בקש מBOX.CO.IL הפניה
- יותר מהיר ואמין

### אם יש Web File Manager:
✅ **גישה דרך הדפדפן**
- כמו cPanel אבל פשוט יותר
- העלאה ישירה דרך הבראוזר

## 🚀 ההמלצה שלי:

### 1. בדוק קודם אם יש לך:
- פרטי FTP באימייל מBOX.CO.IL
- גישה לאזור הלקוחות באתר שלהם

### 2. אם כן - השתמש ב-FileZilla:
- פשוט להתקין
- גרור וזרוק קבצים
- אותו תוצאה כמו cPanel

### 3. אם לא - Netlify:
- אפילו יותר טוב מBOX.CO.IL
- מהיר יותר (CDN גלובלי)
- עדכונים אוטומטיים

## 🤔 איזה נתיב תבחר?

**A.** יש לי פרטי FTP - אשתמש בFileZilla  
**B.** אין לי פרטי FTP - אנסה Netlify  
**C.** אבדוק באזור הלקוחות של BOX.CO.IL  
**D.** אני מעדיף שמישהו יעזור לי עם cPanel  

---
**כל הדרכים מובילות לאותה תוצאה - אתר פעיל!** 🎯