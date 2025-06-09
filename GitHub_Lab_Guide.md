
# 🧬 מדריך ראשוני: עבודה עם Git ו־GitHub במעבדה

---

## 🧠 מה זה Git ומה זה GitHub?

- **Git** היא מערכת לניהול גרסאות של קבצים – במיוחד קוד.
- **GitHub** הוא אתר לניהול פרויקטים מבוססי Git בענן, כולל שיתוף, תיעוד, עבודה בצוות ועוד.

---

## 🚀 למה להשתמש בזה?

- שמירה על גרסאות שונות של הקוד שלך
- שיתוף מסודר עם חברי מעבדה
- תיעוד שינויים לאורך זמן
- כלי הכרחי בכל פרויקט חישובי או מדעי

---

## 🔧 הגדרות ראשוניות

### הזדהות מקומית:
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

---

## 📦 יצירת פרויקט חדש (repository)

```bash
mkdir my_project
cd my_project
git init
```

הוספת קבצים ראשונית:
```bash
touch script.py
git add script.py
git commit -m "קובץ ראשוני"
```

---

## ☁️ חיבור ל-GitHub

1. פתח ריפוזיטורי חדש באתר [https://github.com](https://github.com)
2. חיבור מרחוק לפרויקט:
```bash
git remote add origin https://github.com/your_user/my_project.git
git push -u origin main
```

---

## 🔁 עבודה יומיומית

שמירת שינויים:
```bash
git add .
git commit -m "עדכון הסקריפט"
```

שליחה ל-GitHub:
```bash
git push
```

---

## ⬇️ קבלת פרויקט קיים מהGitHub

```bash
git clone https://github.com/other_user/project_name.git
```

---

## 🧪 טיפים לעבודה מסודרת

✅ תשתמש ב־`.gitignore` כדי לא לכלול קבצים זמניים או כבדים  
✅ אל תעלה קבצי נתונים ענקיים (כמו FASTQ/BAM)  
✅ כתוב הודעות `commit` ברורות (מה עשית ולמה)  
✅ תשתמש ב־README.md להסבר על הפרויקט

---

## 📘 מושגים חשובים

| מונח     | הסבר                            |
|----------|----------------------------------|
| `commit` | צילום מצב של הקוד               |
| `push`   | שליחת שינויים ל־GitHub          |
| `pull`   | קבלת שינויים מהשרת              |
| `branch` | גרסה נפרדת (לבדיקות/פיתוח)     |
| `merge`  | איחוד שינויים בין סניפים        |

---

## 🔐 התחברות עם Token (מפתח אישי)

כיום אי אפשר יותר להתחבר ל־GitHub עם סיסמה רגילה.  
במקום זה משתמשים ב־**Personal Access Token**.

### איך מפיקים טוקן?

1. כנס ל־[https://github.com/settings/tokens](https://github.com/settings/tokens)
2. לחץ על "Generate new token"
3. תן שם, תוקף (expiration) ו־scope (סמן `repo`)
4. העתק את הטוקן שנוצר (אי אפשר לראות אותו שוב!)

### שימוש בטוקן:
בפעם הראשונה שתתבקש להזין סיסמה, הדבק את הטוקן במקום הסיסמה.

---

## 🧰 כלים מומלצים

- GitHub Desktop (GUI נוח): https://desktop.github.com  
- Visual Studio Code עם תוסף Git
- שימוש ב־Jupyter + git דרך `jupyterlab-git`

---

