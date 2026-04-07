# 👋 Привет, я Daryn

🎓 Студент / начинающий разработчик  
💻 Изучаю Python и базы данных  
📍 Riga, Latvia  

---

## 🚀 Мои навыки
- Python (базовый уровень)
- SQL (PostgreSQL)
- Алгоритмы и сортировки
- Работа с файлами

---

## 📂 Мои проекты

### 🔹 Генератор случайных чисел
```python
import random

def write_random_numbers(n):
    with open("random.txt", "w") as f:
        for _ in range(n):
            f.write(f"{random.randint(111,777)}\n")
