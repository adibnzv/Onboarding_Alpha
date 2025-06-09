
# 🧠 מדריך למשתמש המתחיל: עבודה עם מערכת SLURM

## מה זה SLURM?

**SLURM** (Simple Linux Utility for Resource Management) היא מערכת ניהול תורים להרצת עבודות חישוב על קלאסטר.  
היא מקצה משאבים (CPU, RAM, זמן) ומאפשרת לך להריץ קוד בצורה מסודרת, גם כשעובדים הרבה משתמשים על אותו השרת.

---

## 🏁 סוגי עבודות ב-SLURM

### 1. עבודה אינטראקטיבית (Interactive Job)

משמשת לבדיקה ידנית:

```bash
srun --pty -p short -c 4 -t 2:00:00 bash
```

- `--pty`: מצב אינטראקטיבי
- `-p short`: תור (partition)
- `-c 4`: מספר ליבות
- `-t`: זמן הרצה (שעות:דקות:שניות)

---

### 2. עבודה דרך סקריפט (Batch Job)

כתיבת סקריפט `job.sh`:

```bash
#!/bin/bash
#SBATCH --job-name=my_job_name
#SBATCH --output=output_%j.txt
#SBATCH --error=error_%j.txt
#SBATCH --ntasks=1
#SBATCH --cpus-per-task=4
#SBATCH --mem=16G
#SBATCH --time=04:00:00
#SBATCH --partition=short

module load python/3.10
python my_script.py
```

הרצה:
```bash
sbatch job.sh
```

---

## 🔍 פקודות שימושיות

| פקודה | תיאור |
|-------|--------|
| `squeue -u $USER` | הצגת העבודות שלך בתור |
| `scancel <job_id>` | ביטול עבודה |
| `sinfo` | מידע על תורים זמינים |
| `sacct -j <job_id>` | היסטוריית עבודה |
| `seff <job_id>` | ניתוח יעילות עבודה |

---

## 📁 נוהל עבודה מומלץ

1. כתוב סקריפט `job.sh` עם כל ההגדרות.
2. שמור קוד ופלטים בתיקיות מסודרות.
3. השתמש ב־`output_%j.txt` כדי לשמור פלט שונה לכל עבודה.
4. בדוק זמינות תורים עם `sinfo`.
5. בחר זמן ריאלי (`--time`) כדי למנוע כישלונות או עיכובים מיותרים.

---

## 🧪 טיפים מתקדמים

- עבודות מקבילות: `--array=1-10`
- להרצת קוד עם GPU: `--gres=gpu:1`
- להרצת קוד כבד בזיכרון: `--mem=64G` ומעלה

---

## 🧠 מקורות נוספים

- [SLURM Quick Start Guide](https://slurm.schedmd.com/quickstart.html)
- [SLURM Cheat Sheet](https://slurm.schedmd.com/pdfs/summary.pdf)
