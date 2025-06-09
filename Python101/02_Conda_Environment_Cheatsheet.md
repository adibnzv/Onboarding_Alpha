
# 🧠 פרק 2: סביבות עבודה בפייתון עם Conda – הסבר תיאורטי + Cheatsheet

---

## 📌 מה זה Conda?

**Conda** היא מערכת לניהול:
- 📦 חבילות (Packages)
- 🌱 סביבות עבודה (Environments)

היא נוחה מאוד למשתמשים מדעיים, תומכת גם ב־Python וגם ב־R, וכוללת מנגנון ניהול תלויות חזק יותר מ־pip.

---

## 🧰 מה זה Anaconda / Miniconda?

- **Anaconda** – הפצה כבדה שכוללת את Conda + המון ספריות מדעיות מותקנות מראש.
- **Miniconda** – גרסה קלה של Conda שמתקינים עליה רק מה שצריך.

---

## 🌱 יצירת סביבה חדשה

```bash
conda create -n myenv python=3.10
```

📌 כאן אנחנו יוצרים סביבה בשם `myenv` עם פייתון בגרסה מסוימת.  
אפשר לשנות את השם והגרסה לפי הצורך.

---

## ▶️ הפעלת הסביבה

```bash
conda activate myenv
```

---

## ⛔ יציאה מהסביבה

```bash
conda deactivate
```

---

## 📦 התקנת ספריות עם conda

```bash
conda install numpy pandas matplotlib
```

🔍 אפשר גם לחפש ספריות:
```bash
conda search seaborn
```

---

## 📦 התקנה עם pip בתוך סביבה conda

אם ספרייה לא קיימת ב־conda, אפשר להשתמש ב־pip:

```bash
pip install plotly
```

(חשוב: עשה זאת **רק אחרי שהפעלת סביבה conda**)

---

## 🧾 קובץ `environment.yml`

קובץ שמגדיר את כל הסביבה (כולל גרסת פייתון וספריות).

דוגמה:
```yaml
name: myenv
channels:
  - defaults
dependencies:
  - python=3.10
  - numpy
  - pandas
  - matplotlib
```

### יצירת קובץ כזה מסביבה קיימת:
```bash
conda env export > environment.yml
```

### שחזור סביבה:
```bash
conda env create -f environment.yml
```

---

## 📓 התקנת Jupyter בסביבת Conda

```bash
conda install jupyter
```

ולאחר מכן:
```bash
jupyter notebook
```

או:
```bash
conda install jupyterlab
jupyter lab
```

---

## 🧠 יתרונות Conda במעבדה

- תומך בספריות שלא מותקנות טוב עם pip (כמו `biopython`, `h5py`, `opencv`)
- מאפשר בידוד מוחלט בין פרויקטים
- נוח לעבודה עם מערכות HPC / קלאסטרים

---

## 🧾 Cheatsheet – סיכום Conda

### 🌱 יצירת סביבה חדשה
```bash
conda create -n myenv python=3.10
```

### ▶️ הפעלת סביבה
```bash
conda activate myenv
```

### ⛔ יציאה מהסביבה
```bash
conda deactivate
```

### 📦 התקנת ספריות עם conda
```bash
conda install numpy pandas matplotlib
```

### 📦 חיפוש ספריות
```bash
conda search seaborn
```

### 📦 התקנה עם pip בתוך סביבה
```bash
pip install plotly
```

### 🧾 ייצוא הסביבה
```bash
conda env export > environment.yml
```

### 📥 שחזור סביבה
```bash
conda env create -f environment.yml
```

### 📓 התקנת Jupyter ו־JupyterLab
```bash
conda install jupyter
conda install jupyterlab
```

---

## 🛠️ טיפים חשובים

- הפעל את הסביבה לפני התקנת חבילות!
- העדף `conda install` על `pip install` כשאפשר.
- שמור קובץ `environment.yml` לכל פרויקט.
