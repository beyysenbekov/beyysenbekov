# 👋 Hello, I'm Daryn

🎓 Student of University IITU  
💻 Learning Python  
📍 Kazakhstan,Almaty

---

## 🚀 My skills
- Python (base level)
---

## 📂 My projects

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
```
### Угадайка слов
```python
import random

def get_word(slovo):
    a = random.choice(slovo).upper()
    play(a)
def zhashita(p):
    if p.isalpha():
        return True
    else:
        return False


def play(s):
    print("Давайте играть в угадайку слов!")
    word_completion = ['_' for i  in range(len(s))]
    guessed = False
    guessed_letters = []

    tries = 6
    while "".join(word_completion) != s:
        print(*word_completion,sep = "")
        bukva = input("Введите букву")
        if zhashita(bukva):
            if tries != 0:
                if bukva not in guessed_letters :
                    if bukva in s:
                        for i in range(len(s)):
                            if s[i] == bukva:
                                word_completion[i] = bukva
                                guessed = True
                    else:
                        tries -= 1
                        print("Текущее состояние игры",display_hangman(tries))
                else:
                    print("Вы уже указали эту букву")
                    continue
                guessed_letters.append(bukva)
            else:
                print("Вы проиграли,слово:",s)
                sp = input("Хотите ли сыграть еще разок? ")
                if sp == "Да":
                    get_word(word_list)
                else:
                    print("До встречи")
                    break
        else:
            print("Может поиграем нормально?")
    else:
        print("Поздравляем вы угадали слово")
        sp = input("Хотите ли сыграть еще разок? ")
        if sp == "Да":
            get_word(word_list)
        else:
            print("До встречи")












def display_hangman(tries):
    stages = [  # финальное состояние: голова, торс, обе руки, обе ноги
                '''
                   --------
                   |      |
                   |      O
                   |     \\|/
                   |      |
                   |     / \\
                   -
                ''',
                # голова, торс, обе руки, одна нога
                '''
                   --------
                   |      |
                   |      O
                   |     \\|/
                   |      |
                   |     / 
                   -
                ''',
                # голова, торс, обе руки
                '''
                   --------
                   |      |
                   |      O
                   |     \\|/
                   |      |
                   |      
                   -
                ''',
                # голова, торс и одна рука
                '''
                   --------
                   |      |
                   |      O
                   |     \\|
                   |      |
                   |     
                   -
                ''',
                # голова и торс
                '''
                   --------
                   |      |
                   |      O
                   |      |
                   |      |
                   |     
                   -
                ''',
                # голова
                '''
                   --------
                   |      |
                   |      O
                   |    
                   |      
                   |     
                   -
                ''',
                # начальное состояние
                '''
                   --------
                   |      |
                   |      
                   |    
                   |      
                   |     
                   -
                '''
    ]
    return stages[tries]
word_list = ['КЛЮЧ', 'КНИГА', 'ЕНОТ', 'МАШИНКА', 'КОРОВА', 'ТЕЛЕЖКА', 'ШЛЕМ', 'КНОПКА', 'ШНУР', 'ЧЕРНЫЙ',
'ВЛАСТЕЛИН', 'СКАЙП', 'ДУБ', 'ЧАСЫ', 'ТРУБА', 'ЕЛКА', 'ИНСТИТУТ', 'КОРОБКА', 'ТАБЛИЧКА', 'ВОДА', 'СКОВОРОДА',
'МНОГОНОЖКА', 'ЕВРЕЙ', 'ТЕРМИТ', 'КАЧЕК', 'РУЛОН', 'МАГНИТОФОН', 'НОГА', 'СЛОН', 'МИКРОВОЛНОВКА', 'ТОРТ', 'МАК',
'ДЫМ', 'ЧАЙКА', 'ВАЛЕТ', 'ПЛИНТУС', 'ШАПКА', 'ДИНОЗАВР', 'ТОРШЕР', 'БАЛАЛАЙКА', 'БАНКА', 'ЯХТА', 'ОВЦА', 'БАНАН',
'ДУБ', 'АНИМЕ', 'РАДУГА', 'БУКВА', 'ВЕЛОСИПЕД', 'БАНДЖО', 'ГОЛУБЬ', 'ВИНТОВКА', 'КУБОК', 'ЖАСМИН', 'ТЕЛЕФОН',
'АНДРОИД', 'ГОРА', 'ХАЛАТ', 'ЖЕТОН', 'ОБОД', 'МЫЛО', 'ЙОГ', 'ШИШКА', 'ДОЛЛАР', 'КОЛОНКА', 'КУБИК', 'ОМАР',
'РАКЕТА', 'МОРКОВКА', 'ЗЕРКАЛО', 'МОЛОТ', 'ВОЗДУХ', 'ЗМЕЙ', 'ЁЖ', 'ПАЛЬМА', 'МАСЛО', 'ДИДЖЕЙ', 'МЕШОК', 'ТЮБИК',
'МОЗГ', 'ПОЕЗД', 'РОЗЕТКА', 'ПАРАШЮТИСТ', 'БЕЛКА', 'ШПРОТЫ', 'САМОСВАЛ', 'ПАЗЛ', 'БУТЫЛКА', 'КРЕМЛЬ', 'ПИЦЦА',
'МАКАРОНЫ', 'КОВЕР', 'ЗУБЫ', 'ЯРЛЫК', 'КАШАЛОТ', 'МАРС', 'ШАКАЛ', 'ПОМАДА', 'ДЖИП', 'ЛЕЩ', 'КАМЕНЬ', 'ДИСК']
get_word(word_list)
```
