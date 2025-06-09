
# 📓 מדריך: איך להתחבר ל־Jupyter Notebook על הקלאסטר

---

## 🔧 הקדמה קצרה

ה- `Jupyter Notebook` או `Jupyter Lab` רץ על הקלאסטר – ואין אפשרות לפתוח אותו ישירות דרך הדפדפן.  
לכן נבצע סדרת שלבים:

1. פתיחת session עם `TMUX` כדי לא לאבד את העבודה אם תתנתק  
2. הרצת עבודה אינטראקטיבית עם SLURM  
3. הרצת Jupyter Lab על פורט שתבחר  
4. פתיחת חיבור מרוחק (SSH tunnel)  
5. כניסה ל-Jupyter בדפדפן שלך

---

## 🧪 שלבים מפורטים

---

### ✅ 1. פתיחת TMUX session

```bash
tmux new-session -s myname -n notebook
```

📘 **מה זה TMUX?**  
`tmux` היא תוכנה שמאפשרת לפתוח "מסך" על השרת, שאפשר לחזור אליו גם אם סוגרים את הטרמינל.  
- `-s myname` – שם הסשן (אפשר לבחור שם שאתה זוכר)
- `-n notebook` – שם החלונית (window)

🔁 לחזור לסשן פתוח:
```bash
tmux attach-session -t myname
```

🔚 לצאת מ-tmux בלי לסגור את מה שרץ:
```
Ctrl + B ואז D
```

---

### ✅ 2. הרצת עבודה אינטראקטיבית עם SLURM

```bash
srun --pty -p adistzachi --cpus-per-task=1 --mem=30GB --time=06:00:00 /bin/bash
```

📌 אתה מבקש:
- ליבה אחת (`--cpus-per-task=1`)
- 30GB זיכרון (`--mem=30GB`)
- 6 שעות (`--time=06:00:00`)

---

### ✅ 3. בדיקת כתובת ה-IP הפנימית שלך

```bash
hostname -i
```

🔎 פלט לדוגמה:
```
10.45.32.127
```

🧠 חשוב לשמור את כתובת הIP הזו כיוון שנצטרך אותה תכף לחיבור ול-SSH

---

### ✅ 4. הרצת Jupyter Lab על פורט שתבחר

```bash
conda activate relevant_env
jupyter lab --no-browser --port=5566 
```
- relevant_env = סביבת העבודה של פייתון המכילה את החבילות הרלוונטיות
בסיום הפקודה תראה לינק עם token, לדוגמה:
```
http://10.45.32.127:5566/lab?token=abc123...
```

שמור את הקישור – תשתמש בו דרך SSH tunnel.

---

### ✅ 5. פתיחת SSH tunnel מהמחשב האישי

במחשב האישי שלך (לא על השרת), הרץ:

```bash
ssh -N -f -L localhost:10133:localhost:5566 your_username@saved_ip
```

📌 הסבר:
- `your_username`: שם המשתמש שלך בשרת
- `saved_ip`: כתובת השרת (למשל `132.66.112.114`)
- `5566`: הפורט עליו רץ Jupyter בשרת
- `10133`: הפורט המקומי (תוכל לבחור כל מספר פנוי)

---

### ✅ 6. פתיחה בדפדפן המקומי

גש לכתובת:

```
http://localhost:10133
```

והדבק את ה־token שהופיע כשהרצת את Jupyter.

---

## 🛑 לסיום

- עצור את Jupyter עם `Ctrl+C`
- צא מ־TMUX עם `exit`
- לסגירת SSH tunnel (אם צריך):

```bash
ps aux | grep ssh
kill <PID>
```

---

אם אתה משתמש בזה הרבה – אפשר לכתוב סקריפט קטן שמריץ את כל זה אוטומטית.
