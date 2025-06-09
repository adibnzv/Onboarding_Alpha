
# 🔁 פרק 3: לולאות בפייתון – הסבר תיאורטי + Cheatsheet

---

## 🧠 למה צריך לולאות?

לולאות משמשות כדי **לחזור על פעולה מספר פעמים** – בין אם זו פעולה קבועה (for) או תלויה בתנאי (while).  
כך אנחנו חוסכים קוד כפול ויכולים לעבור על רשימות, מילונים, טווחים ועוד.

---

## 🔷 לולאת `for`

```python
for i in range(5):
    print(i)
```

⬅️ תדפיס את המספרים 0 עד 4.  
הפונקציה `range(n)` מייצרת סדרת מספרים מ־0 עד n-1.

```python
names = ["Dana", "Yossi", "Adi"]
for name in names:
    print(name)
```

---

## 🔁 לולאת `while`

```python
x = 0
while x < 3:
    print(x)
    x += 1
```

⬅️ תמשיך להריץ כל עוד התנאי מתקיים.

---

## 🛑 מילות מפתח חשובות

| מילה | תפקיד |
|------|--------|
| `break` | יציאה מיידית מהלולאה |
| `continue` | קפיצה לסיבוב הבא |
| `pass` | לא עושה כלום, placeholder |

דוגמה:
```python
for i in range(5):
    if i == 3:
        break
    print(i)
```

---

## 🧾 Cheatsheet – לולאות

### 🔁 for עם טווח
```python
for i in range(10):
    print(i)
```

### 🔁 for על רשימה
```python
my_list = [1, 2, 3]
for item in my_list:
    print(item)
```

### 🔁 while
```python
x = 0
while x < 5:
    print(x)
    x += 1
```

### ⛔ break
```python
for i in range(10):
    if i == 5:
        break
```

### 🔄 continue
```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

---

## 🧠 טיפים

- אל תשכח לעדכן את התנאי בתוך `while`, אחרת תקבל לולאה אינסופית.
- כשאתה לא בטוח בכמות החזרות – `while`.  
- כשאתה עובר על רשימה/טווח – `for`.

