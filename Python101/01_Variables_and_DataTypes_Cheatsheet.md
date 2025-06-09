
# 🧾 Cheatsheet – משתנים וסוגי נתונים בפייתון

---

## 🟢 הצהרת משתנים

```python
name = "Adi"          # str
age = 28              # int
height = 1.75         # float
is_student = True     # bool
```

---

## 🔍 בדיקת סוג משתנה

```python
type(age)             # <class 'int'>
type(name)            # <class 'str'>
```

---

## 🔄 המרת טיפוסים (Type Casting)

```python
int("5")              # 5
float("3.14")         # 3.14
str(100)              # "100"
bool(0)               # False
```

---

## 📚 רשימות – list

```python
my_list = [1, 2, 3]
my_list.append(4)     # הוספת איבר
print(my_list[0])     # גישה לפי אינדקס
```

---

## 🗃️ מילונים – dict

```python
person = {
    "name": "Dana",
    "age": 30
}
print(person["name"])  # "Dana"
person["city"] = "Tel Aviv"  # הוספת שדה חדש
```

---

## 💡 מחרוזות – str

```python
text = "Hello"
print(text.upper())     # HELLO
print(text.lower())     # hello
print(len(text))        # 5
```

---

## 🧠 ערכים בוליאניים – bool

```python
is_valid = True
print(is_valid)         # True

# ערכים שהופכים ל-False:
bool("")     # False
bool(0)      # False
bool([])     # False
```

---

## 🛠️ טיפים

- שמות משתנים: אותיות קטנות, קו תחתון אם צריך (`user_name`)
- אל תשתמש במילים שמורות (`list`, `int`, `if`)
- עדיף לשמור על סוג משתנה קבוע לאורך התוכנית
