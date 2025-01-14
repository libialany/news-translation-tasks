---
title: Python .sort() – Як сортувати список у Python
date: 2024-08-28T14:50:49.415Z
author: Dionysia Lemonaki
authorURL: https://www.freecodecamp.org/news/author/dionysialemonaki/
originalURL: https://www.freecodecamp.org/news/python-sort-how-to-sort-a-list-in-python/
posteditor: ""
proofreader: ""
---

У цій статті ви дізнаєтесь, як використовувати метод списку `sort()` у Python.

<!-- more -->

Ви також дізнаєтесь інший спосіб виконання сортування в Python за допомогою функції `sorted()`, щоб зрозуміти, чим вона відрізняється від `sort()`.

До кінця ви знатимете основи сортування списку в Python і як налаштувати сортування відповідно до ваших потреб.

Ось що ми розглянемо:

1.  [Синтаксис методу `sort`][1]
2.  [Сортування елементів списку в порядку зростання][2]
3.  [Сортування елементів списку в порядку спадання][3]
4.  [Сортування елементів списку за допомогою аргументу `key`][4]
5.  [Різниці між `sort()` та `sorted()`][5]
    1.  [Коли використовувати `sort()` і `sorted()`][6]

## Метод `sort()` - Огляд синтаксису

Метод `sort()` є одним із способів, за допомогою якого ви можете сортувати список у Python.

При використанні `sort()` ви сортуєте список _на місці_. Це означає, що початковий список безпосередньо змінюється. Зокрема, початковий порядок елементів змінюється.

Загальний синтаксис методу `sort()` виглядає так:

```
list_name.sort(reverse=..., key=... )
```

Розглянемо деталі:

-   `list_name` — це ім'я списку, з яким ви працюєте.
-   `sort()` — це один з методів списку Python для сортування та зміни списку. Він сортує елементи списку або в _порядку зростання_, або в _порядку спадання_.
-   `sort()` приймає два **необов'язкові** параметри.
-   `reverse` — це перший необов'язковий параметр. Він визначає, чи буде список отсортований в порядку зростання або спадання. Приймає логічне значення, тобто значення буде або True, або False. Значення за замовчуванням — **False**, тобто список сортується в порядку зростання. Встановлення його на True сортує список навпаки, у порядку спадання.
-   `key` — це другий необов'язковий параметр. Він приймає функцію або метод, який використовується для визначення будь-яких детальних критеріїв сортування, які у вас можуть бути.

Метод `sort()` повертає `None`, що означає, що немає повертаємого значення, оскільки він просто змінює початковий список. Він **не** повертає новий список.

## Як сортувати елементи списку в порядку зростання за допомогою методу `sort()`

Як вже згадувалося раніше, за замовчуванням, `sort()` сортує елементи списку в порядку зростання.

Порядок зростання означає, що елементи розташовуються від найнижчого до найвищого значення.

Найменше значення знаходиться зліва, а найбільше - справа.

Загальний синтаксис для цього виглядає приблизно так:

```
list_name.sort()
```

Розглянемо наступний приклад, який показує, як сортувати список цілих чисел:

```
# список чисел
my_numbers = [10, 8, 3, 22, 33, 7, 11, 100, 54]

# відсортувати список на місці у порядку зростання
my_numbers.sort()

# друк зміненого списку
print(my_numbers)

# вихід

#[3, 7, 8, 10, 11, 22, 33, 54, 100]
```

У прикладі вище, числа сортуються від найменшого до найбільшого.

Ви також можете досягти того ж при роботі зі списком рядків:

```
# список рядків
programming_languages = ["Python", "Swift","Java", "C++", "Go", "Rust"]

# відсортувати список на місці в алфавітному порядку
programming_languages.sort()

# друк зміненого списку
print(programming_languages)

# вихід

#['C++', 'Go', 'Java', 'Python', 'Rust', 'Swift']
```

У цьому випадку, кожен рядок, що міститься у списку, був відсортований в алфавітному порядку.

Як ви бачили у обох прикладах, початкові списки були безпосередньо змінені.

## Як сортувати елементи списку в порядку спадання за допомогою методу `sort()`

Порядок спадання є протилежністю порядку зростання - елементи розташовуються від найвищого до найнижчого значення.

Для сортування елементів списку в порядку спадання, вам потрібно використовувати необов'язковий параметр `reverse` з методом `sort()`, і встановити його значення на `True`.

Загальний синтаксис для цього виглядає так:

```
list_name.sort(reverse=True)
```

Давайте використаємо той самий приклад з попередньої секції, але цього разу зробимо так, щоб числа були відсортовані в зворотному порядку:

```
# список чисел
my_numbers = [10, 8, 3, 22, 33, 7, 11, 100, 54]

# відсортувати список на місці в порядку спадання
my_numbers.sort(reverse=True)

# друк зміненого списку
print(my_numbers)

# вихід

#[100, 54, 33, 22, 11, 10, 8, 7, 3]
```

Тепер всі числа розташовані у зворотному порядку, з найбільшим значенням зліва та найменшим - справа.

Ви також можете досягти того ж при роботі зі списком рядків.

```
# список рядків
programming_languages = ["Python", "Swift","Java", "C++", "Go", "Rust"]

# відсортувати список на місці у зворотному алфавітному порядку
programming_languages.sort(reverse=True)

# друк зміненого списку
print(programming_languages)

# вихід

#['Swift', 'Rust', 'Python', 'Java', 'Go', 'C++']
```

Елементи списку тепер розташовані у зворотному алфавітному порядку.

## Як сортувати елементи списку за допомогою параметра `key` з методом `sort()`

Ви можете використовувати параметр `key` для виконання більш налаштованих операцій сортування.

Значення, призначене параметру `key`, повинно щось викликати.



Деякі приклади викликаємих об'єктів є методами та функціями.

Цей метод або функція, призначена для `key`, буде застосована до всіх елементів у списку перед будь-яким сортуванням і буде визначати логіку для критеріїв сортування.

Припустимо, ви хочете відсортувати список рядків на основі їхньої довжини.

Для цього ви призначаєте вбудовану функцію `len()` параметру `key`.

Функція `len()` порахує довжину кожного елемента, що зберігається у списку, підрахувавши символи, які містяться в цьому елементі.

```
programming_languages = ["Python", "Swift", "Java", "C++", "Go", "Rust"]

programming_languages.sort(key=len)

print(programming_languages)

#вихід

#['Go', 'C++', 'Java', 'Rust', 'Swift', 'Python']
```

У наведеному вище прикладі рядки сортуються за замовчуванням у зростаючому порядку, але цього разу сортування відбувається на основі їхньої довжини.

Найкоротший рядок знаходиться зліва, а найдовший — справа.

Параметри `key` і `reverse` також можна комбінувати.

Наприклад, можна відсортувати елементи списку на основі їхньої довжини, але у спадному порядку.

```
programming_languages = ["Python", "Swift", "Java", "C++", "Go", "Rust"]

programming_languages.sort(key=len, reverse=True)

print(programming_languages)

#вихід

#['Python', 'Swift', 'Java', 'Rust', 'C++', 'Go']
```

У наведеному вище прикладі рядки йдуть від найдовшого до найкоротшого.

Ще одне, що варто зазначити, полягає у тому, що ви можете створити власну функцію сортування для створення більш явних критеріїв сортування.

Наприклад, ви можете створити певну функцію, а потім відсортувати список відповідно до значення, яке вона повертає.

Припустимо, у вас є список словників з мовами програмування та роком створення кожної мови.

```
programming_languages = [{'language':'Python','year':1991},
{'language':'Swift','year':2014},
{'language':'Java', 'year':1995},
{'language':'C++','year':1985},
{'language':'Go','year':2007},
{'language':'Rust','year':2010},
]
```

Ви можете визначити власну функцію, яка отримує значення певного ключа зі словника.

💡 Майте на увазі, що ключ словника і параметр `key`, який приймає `sort()`, — це дві різні речі!

Зокрема, функція отримає і поверне значення ключа `year` у списку словників, що вказує рік, коли кожна мова була створена.

Повернене значення потім буде застосовано як критерій сортування для списку.

```
programming_languages = [{'language':'Python','year':1991},
{'language':'Swift','year':2014},
{'language':'Java', 'year':1995},
{'language':'C++','year':1985},
{'language':'Go','year':2007},
{'language':'Rust','year':2010},
]

def get_year(element):
    return element['year']
```

Далі ви можете відсортувати відповідно до значення, яке повертає функція, призначивши його параметру `key` і відсортувати за хронологічним порядком за замовчуванням:

```
programming_languages = [{'language':'Python','year':1991},
{'language':'Swift','year':2014},
{'language':'Java', 'year':1995},
{'language':'C++','year':1985},
{'language':'Go','year':2007},
{'language':'Rust','year':2010},
]

def get_year(element):
    return element['year']

programming_languages.sort(key=get_year)

print(programming_languages)
```

Вихід:

```
[{'language': 'C++', 'year': 1985}, {'language': 'Python', 'year': 1991}, {'language': 'Java', 'year': 1995}, {'language': 'Go', 'year': 2007}, {'language': 'Rust', 'year': 2010}, {'language': 'Swift', 'year': 2014}]
```

Якщо ви хочете відсортувати від найновішеї мови до найстарішої, або інакше кажучи у спадному порядку, тоді використайте параметр `reverse=True`:

```
programming_languages = [{'language':'Python','year':1991},
{'language':'Swift','year':2014},
{'language':'Java', 'year':1995},
{'language':'C++','year':1985},
{'language':'Go','year':2007},
{'language':'Rust','year':2010},
]

def get_year(element):
    return element['year']

programming_languages.sort(key=get_year, reverse=True)

print(programming_languages)
```

Вихід:

```
[{'language': 'Swift', 'year': 2014}, {'language': 'Rust', 'year': 2010}, {'language': 'Go', 'year': 2007}, {'language': 'Java', 'year': 1995}, {'language': 'Python', 'year': 1991}, {'language': 'C++', 'year': 1985}]
```

Щоб досягти точно такого ж результату, ви можете створити lambda-функцію.

Замість використання регулярної власної функції, визначеної за допомогою ключового слова `def`, ви можете:

- створити короткий вираз в один рядок,
- і не визначати ім'я функції, як це було зроблено з функцією `def`. Lambda-функції також називаються _анонімними_ функціями.

```
programming_languages = [{'language':'Python','year':1991},
{'language':'Swift','year':2014},
{'language':'Java', 'year':1995},
{'language':'C++','year':1985},
{'language':'Go','year':2007},
{'language':'Rust','year':2010},
]

programming_languages.sort(key=lambda element: element['year'])

print(programming_languages)
```

Lambda-функція, яка визначається рядком `key=lambda element: element['year']`, сортує ці мови програмування від найстарішої до найновішої.

## Відмінності між `sort()` і `sorted()`

Метод `sort()` працює аналогічно до функції `sorted()`.

```sorted(list_name,reverse=...,key=...)```

Давайте розберемо це детальніше:

-   `sorted()` – це вбудована функція, яка приймає ітератор. Потім вона сортує його у зростаючому або спадаючому порядку.
-   `sorted()` приймає три параметри. Один параметр є обов’язковим, а два інші є необов’язковими.
-   `list_name` – це **обов’язковий** параметр. У цьому випадку параметром є список, але `sorted()` також приймає будь-який інший ітератор.
-   `sorted()` також приймає необов’язкові параметри `reverse` та `key`, які є такими ж необов’язковими параметрами, як і метод `sort()`.

Головна різниця між `sort()` та `sorted()` полягає в тому, що функція `sorted()` бере список і **повертає нову відсортовану копію** цього списку.

Нова копія містить елементи оригінального списку у відсортованому порядку.

Елементи в оригінальному списку не змінюються і залишаються як є.

Отже, підсумовуючи відмінності:

-   Метод `sort()` не має значення повернення і безпосередньо змінює оригінальний список, змінюючи порядок елементів у ньому.
-   З іншого боку, функція `sorted()` має значення повернення, яке є відсортованою копією оригінального списку. Та копія містить елементи оригінального списку у відсортованому порядку. Крім того, оригінальний список залишається незмінним.

Давайте розглянемо наступний приклад, щоб побачити, як це працює:

```
# оригінальний список чисел
my_numbers = [10, 8, 3, 22, 33, 7, 11, 100, 54]

# сортування оригінального списку у стандартному зростаючому порядку
my_numbers_sorted = sorted(my_numbers)

# друк оригінального списку
print(my_numbers)

# друк копії оригінального списку, яка була створена
print(my_numbers_sorted)

# вихідні дані

#[10, 8, 3, 22, 33, 7, 11, 100, 54]
#[3, 7, 8, 10, 11, 22, 33, 54, 100]
```

Оскільки до `sorted()` не було надано додаткових аргументів, він упорядкував копію оригінального списку у стандартному зростаючому порядку, від найменшого значення до найбільшого.

І при друку оригінального списку ви бачите, що він залишився таким самим, і елементи мають свій початковий порядок.

Як ви бачили у прикладі вище, копія списку була присвоєна новій змінній, `my_numbers_sorted`.

Подібне не можна зробити з `sort()`.

Перегляньте наступний приклад, щоб побачити, що станеться, якщо це спробувати зробити з методом `sort()`.

```
my_numbers = [10, 8, 3, 22, 33, 7, 11, 100, 54]

my_numbers_sorted = my_numbers.sort()

print(my_numbers)
print(my_numbers_sorted)

# вихідні дані

#[3, 7, 8, 10, 11, 22, 33, 54, 100]
#None
```

Ви бачите, що значення повернення для `sort()` є `None`.

Наостанок, ще одна річ, яку варто зазначити, це те, що параметри `reverse` і `key`, які приймає функція `sorted()`, працюють точно так само, як і метод `sort()` з попередніх розділів.

### Коли використовувати `sort()` і `sorted()`

Нижче перераховані кілька речей, які ви можете враховувати, вирішуючи, чи слід використовувати `sort()` або `sorted()`.

По-перше, врахуйте тип даних, з яким ви працюєте:

-   Якщо ви працюєте виключно зі списком із самого початку, то вам потрібно буде використовувати метод `sort()`, оскільки `sort()` викликається тільки для списків.
-   З іншого боку, якщо ви хочете більшої гнучкості і ще не працюєте зі списком, то можете використовувати `sorted()`. Функція `sorted()` приймає і сортує будь-який ітератор (як-от словники, кортежі та множини), а не лише списки.

Далі, ще одна річ, яку варто врахувати, це те, чи важливо для вас зберегти початковий порядок списку, з яким ви працюєте:

-   Коли викликається `sort()`, оригінальний список буде змінено, і початковий порядок буде втрачено. Ви не зможете відновити початкові позиції елементів списку. Використовуйте `sort()`, коли ви точно впевнені, що хочете змінити список, з яким працюєте, й упевнені, що не хочете зберігати порядок, який він мав.
-   З іншого боку, `sorted()` корисний, коли ви хочете створити новий список, але хочете залишити той список, з яким працюєте. Функція `sorted()` створить новий відсортований список, елементи якого упорядковані у бажаному порядку.

Наостанок, ще одна річ, яку варто враховувати при роботі з великими наборами даних, це ефективність у часі й пам’яті:

-   Метод `sort()` займає й споживає менше пам’яті, оскільки він просто сортує список на місці й не створює зайвий новий список, який вам не потрібен. З цієї ж причини він трохи швидший, оскільки не створює копію. Це може бути корисним, коли ви працюєте з великими списками, які містять більше елементів.

## Висновок

І ось вам! Тепер ви знаєте, як сортувати список у Python за допомогою методу `sort()`.

Ви також розглянули ключові відмінності між сортуванням списку за допомогою `sort()` і `sorted()`.

Сподіваюся, ви знайшли цю статтю корисною.

Щоб дізнатися більше про мову програмування Python, ознайомтеся з безкоштовною сертифікацією freeCodeCamp [Scientific Computing with Python Certification][7].

Ви почнете з основ та навчитеся в інтерактивний і дружній до новачків спосіб. В кінці ви також створите п'ять проектів, щоб практикувати й допомогти закріпити вивчене.

Дякую за прочитання і щасливого кодування!

[1]: #синтаксис
[2]: #зростаючий
[3]: #спадаючий
[4]: #ключ
[5]: #відмінності
[6]: #використання
[7]: https://www.freecodecamp.org/learn/scientific-computing-with-python/
```

