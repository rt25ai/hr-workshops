# הוראות שילוב לוגו - AI PRO

## 📸 הלוגו הנוכחי
הלוגו שלך זמין בקישור: `https://i.imgur.com/lOLiTah.png`

## 🔄 איך להחליף את הלוגו הזמני

### בקובץ index.html:

1. **הורד את הלוגו מהקישור לתיקיית images:**
   ```bash
   mkdir images
   curl -o images/logo.png https://i.imgur.com/lOLiTah.png
   ```

2. **החלף בקובץ HTML את הקוד הזמני:**
   
   **מצא את השורות 186-190:**
   ```html
   <div class="w-12 h-12 rounded-xl liquid-glass flex items-center justify-center">
       <div class="professional-icon w-10 h-10">
           <i class="fas fa-brain"></i>
       </div>
   </div>
   ```

   **החלף ב:**
   ```html
   <div class="w-12 h-12 rounded-xl liquid-glass flex items-center justify-center p-2">
       <img src="images/logo.png" alt="לוגו רועי טל AI PRO" 
            class="w-full h-full object-contain">
   </div>
   ```

3. **גם בפוטר - מצא את השורות 713-717:**
   ```html
   <div class="w-12 h-12 rounded-xl liquid-glass flex items-center justify-center">
       <div class="professional-icon w-10 h-10">
           <i class="fas fa-brain"></i>
       </div>
   </div>
   ```

   **החלף ב:**
   ```html
   <div class="w-12 h-12 rounded-xl liquid-glass flex items-center justify-center p-2">
       <img src="images/logo.png" alt="לוגו רועי טל AI PRO" 
            class="w-full h-full object-contain">
   </div>
   ```

## 🎨 התאמות אופציונליות

### אם הלוגו צריך עיצוב שונה:

```css
/* הוסף ל-CSS אם צריך */
.logo-container img {
    filter: brightness(1.1) contrast(1.05);
    transition: all 0.3s ease;
}

.logo-container:hover img {
    transform: scale(1.05);
    filter: brightness(1.2) contrast(1.1);
}
```

### Favicon (אייקון בטאב הדפדפן):

**החלף את השורה 18 בקובץ HTML:**
```html
<!-- מ: -->
<link rel="icon" type="image/x-icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>🤖</text></svg>">

<!-- ל: -->
<link rel="icon" type="image/png" href="images/logo.png">
```

## 📐 גדלים ופרופורציות

- **Header**: 48px x 48px (w-12 h-12)
- **Footer**: 48px x 48px (w-12 h-12)
- **Favicon**: רצוי 32x32px או 64x64px

## ✅ בדיקות אחרי השילוב

1. וודא שהלוגו נטען כהלכה בכל הדפדפנים
2. בדוק ברזולוציות שונות (מובייל/דסקטופ)  
3. וודא שה-Alt text מדויק לנגישות
4. בדוק שהלוגו נראה טוב על רקעי הזכוכית השונים

## 🔧 פתרון בעיות

**אם הלוגו לא נטען:**
- וודא שהקובץ בנתיב הנכון: `images/logo.png`
- בדוק הרשאות קובץ (644)
- נסה לטעון בדפדפן ישירות: `yoursite.com/images/logo.png`

**אם הלוגו נראה מטושטש:**
- השתמש בגירסה ברזולוציה גבוהה יותר
- הוסף: `loading="lazy"` לתג img
- שקול שימוש ב-SVG במקום PNG

## 📱 מובייל

הלוגו מותאם אוטומטית למובייל עם אותו גודל ואפקטי זכוכית.