
# 🧪 מדריך לסטודנט החדש: מבוא ל־Command Line ול־BASH

## 🎯 למי מיועד המדריך?
לסטודנטים חדשים במעבדה שמעולם לא עבדו עם **command line** ורוצים להבין מה זה, למה זה חשוב, ואיך להשתמש בו – בצורה פשוטה וברורה.

---

## 🖥️ מה זה Command Line?
ה- **Command Line** (בעברית: שורת פקודה) זו דרך לתקשר עם המחשב על ידי כתיבת פקודות – במקום ללחוץ עם העכבר.

במקום לפתוח תיקיה עם דאבל-קליק, כותבים פקודה כמו:

```bash
cd /home/adi/Documents
```

וזה מאפשר שליטה הרבה יותר מדויקת, מהירה, ואוטומטית – במיוחד כשעובדים עם הרבה קבצים, נתונים, וסקריפטים מחקריים.

---

## 🐚 ומה זה BASH?
ה-**BASH** הוא אחד הסוגים הנפוצים ביותר של command line, במיוחד ב־Linux ובשרתים מדעיים.  
הוא מאפשר לך:
- לפתוח ולערוך קבצים
- להריץ תוכנות ביואינפורמטיות
- לאוטומט תהליכים שחוזרים על עצמם
- לכתוב סקריפטים

---

## 🔧 איך פותחים את ה־Command Line?

### במחשב אישי:
- **Mac**: פותחים את Terminal
- **Windows**: משתמשים ב־WSL או Git Bash או mobaXterm

### בשרת המעבדה:
מתחברים עם הפקודה:
```bash
ssh username@server.address
```

---

## 📦 פקודות בסיסיות

### ניווט:
```bash
pwd             # מראה את המיקום הנוכחי
ls              # מציג קבצים
cd foldername   # כניסה לתיקיה
cd ..           # חזרה תיקיה אחת אחורה
```

### ניהול קבצים:
```bash
mkdir new_folder
touch file.txt
cp file1.txt file2.txt
mv old.txt new.txt
rm file.txt
rm -r folder
```

### הצגת תוכן וחיפוש:
```bash
cat file.txt
head file.txt
tail file.txt
grep "virus" file.txt
```

---

## 🧠 קיצורי דרך חשובים

- כפתור `Tab`: השלמה אוטומטית
- כפתור `↑`: חזרה לפקודה קודמת
- שילוב הכפתורים `Ctrl+C`: עצירת פעולה
- הפקודה `man command`: עזרה לפקודה - שמים לפני פקודה כלשהי

---

## 🤖 מה זה סקריפט?

סקריפט הוא קובץ טקסט שכתוב בו פקודות BASH. ניתן להריץ אותו כך:

```bash
bash myscript.sh
```

דוגמה:
```bash
#!/bin/bash
cd /home/adi/data/
ls -l
```

---

## 📘 המלצות ללמידה עצמית

- [LearnShell.org](https://www.learnshell.org/)
- [YouTube Crash Courses](https://www.youtube.com/results?search_query=linux+command+line+crash+course)
- [The Linux Command Line (ספר חינם)](https://linuxcommand.org/tlcl.php)

---

## 📣 לסיכום

השליטה ב־Command Line ו־BASH היא מיומנות חיונית לכל סטודנט במדעי החיים החישוביים.  
היא מאפשרת שליטה מדויקת, אוטומציה, עבודה עם קבצים ושרתים, ושחזור תהליכים מחקריים בצורה מדעית.
