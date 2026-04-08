# 👋 Привет, я Daryn

🎓 Студент / начинающий разработчик  
💻 Изучаю Python и базы данных  
📍 Kazakhstan,Almaty

---

## 🚀 Мои навыки
- Python (базовый уровень)
- SQL (PostgreSQL)
- Алгоритмы и сортировки
- Работа с файлами

---

## 📂 Мои проекты

### 🔹 Шифрование/Дешифрование
```python
def deshifr(lan,sdvig):
    a = input("Текст:")
    if lan == "eng":
        for i in range(len(a)):
            if a[i].isalpha():
                if a[i].islower():
                    if ord(a[i]) - k < 97:
                        m = 0
                        while ord(a[i]) - m != 97:
                            m += 1
                        print(chr(122 - k + m+1), end="", sep="")
                    else:
                        print(chr(ord(a[i]) - k), end="", sep="")
                else:
                    if ord(a[i]) - k < 65:
                        m = 0
                        while ord(a[i]) - m != 65:
                            m += 1
                        print(chr(90 - k + m+1), end="", sep="")
                    else:
                        print(chr(ord(a[i]) - k), end="", sep="")
            else:
                print(a[i], end="", sep="")
    else:
        for i in range(len(a)):
            if a[i].isalpha():
                if a[i].islower():
                    if ord(a[i]) - k < 1072:
                        m = 0
                        while ord(a[i]) - m != 1072:
                            m += 1
                        print(chr(1103 - k + m+1), end="", sep="")
                    else:
                        print(chr(ord(a[i]) - k), end="", sep="")
                else:
                    if ord(a[i]) - k < 1040:
                        m = 0
                        while ord(a[i]) - m != 1040:
                            m += 1
                        print(chr(1071 - k + m+1 ), end="", sep="")
                    else:
                        print(chr(ord(a[i]) - k), end="", sep="")
            else:
                print(a[i], end="", sep="")


def shifr(lan,sdvig):
    a = input("Текст:")
    if lan == "eng":
        for i in range(len(a)):
            if a[i].isalpha():
                if a[i].islower():
                    if ord(a[i]) + k > 122:
                        m = 1
                        while ord(a[i]) + m != 122:
                            m += 1
                        print(chr(97 + k - m-1), end="",sep ="")
                    else:
                        print(chr(ord(a[i]) + k), end="",sep ="")
                else:
                    if ord(a[i]) + k > 90:
                        m = 1
                        while ord(a[i]) + m != 90:
                            m += 1
                        print(chr(65 + k-m-1), end="",sep ="")
                    else:
                        print(chr(ord(a[i]) + k), end="",sep ="")
            else:
                print(a[i],end = "",sep = "")
    else:
        for i in range(len(a)):
            if a[i].isalpha():
                if a[i].islower():
                    if ord(a[i]) + k > 1103:
                        m = 0
                        while ord(a[i]) + m != 1103:
                            m += 1
                        print(chr(1072 + k-m), end="",sep ="")
                    else:
                        print(chr(ord(a[i]) + k), end="",sep ="")
                else:
                    if ord(a[i]) + k > 1071:
                        m = 1
                        while ord(a[i]) + m != 1071:
                            m += 1
                        print(chr(1040 + k-m), end="",sep ="")
                    else:
                        print(chr(ord(a[i]) + k), end="",sep ="")
            else:
                print(a[i],end = "",sep = "")




types = input("Направление: ")
language = input("Язык: ")
k = int(input("Сдвиг?: "))
if types == "шифрование":
    shifr(language,k)
elif types == "дешифрование":
    deshifr(language,k)

