
# Практическое занятие №3. Конфигурационные языки

П.Н. Советов, РТУ МИРЭА

Разобраться, что собой представляют программируемые конфигурационные языки (Jsonnet, Dhall, CUE).

## Задача 1

Реализовать на Jsonnet приведенный ниже пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY.

Решение:
```
local create_student(name, group, age) = {
  age: age,
  group: group,
  name: name,
};

{
  groups: ["ИКБО-%d-20" % i for i in std.range(1, 24)],
  "students": [
    create_student("Иванов И.И.", "ИКБО-4-20", 19),
    create_student("Петров П.П.", "ИКБО-5-20", 18),
    create_student("Сидоров С.С.", "ИКБО-5-20", 18),
    create_student("Маркаданов А.А.", "ИКБО-10-23", 19),
  ],
  "subject": "Конфигурационное управление"
}
```

## Задача 2

Реализовать на Dhall приведенный ниже пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY.

```
{
  "groups": [
    "ИКБО-1-20",
    "ИКБО-2-20",
    "ИКБО-3-20",
    "ИКБО-4-20",
    "ИКБО-5-20",
    "ИКБО-6-20",
    "ИКБО-7-20",
    "ИКБО-8-20",
    "ИКБО-9-20",
    "ИКБО-10-20",
    "ИКБО-11-20",
    "ИКБО-12-20",
    "ИКБО-13-20",
    "ИКБО-14-20",
    "ИКБО-15-20",
    "ИКБО-16-20",
    "ИКБО-17-20",
    "ИКБО-18-20",
    "ИКБО-19-20",
    "ИКБО-20-20",
    "ИКБО-21-20",
    "ИКБО-22-20",
    "ИКБО-23-20",
    "ИКБО-24-20"
  ],
  "students": [
    {
      "age": 19,
      "group": "ИКБО-4-20",
      "name": "Иванов И.И."
    },
    {
      "age": 18,
      "group": "ИКБО-5-20",
      "name": "Петров П.П."
    },
    {
      "age": 18,
      "group": "ИКБО-5-20",
      "name": "Сидоров С.С."
    },
    <добавьте ваши данные в качестве четвертого студента>
  ],
  "subject": "Конфигурационное управление"
} 
```
Решение:
```
let Group = Text
let Student = { age : Natural, group : Group, name : Text }

let create_student : Natural -> Text -> Text -> Student =
	\(age : Natural) -> \(group : Text) -> \(name : Text) ->
  { age = age, group = group, name = name }

let create_group : Natural -> Group =
	\(num : Natural) ->
	"ИКБО-" ++ (Natural/show num) ++ "-20"

let groups : List Group = [ 
	create_group 1,
	create_group 2,
	create_group 3,
	create_group 4,
        create_group 5,
	create_group 6,
	create_group 7,
	create_group 8,
	create_group 9,
	create_group 10,
	create_group 11,
	create_group 12,
	create_group 13,
	create_group 14,
	create_group 15,
	create_group 16,
	create_group 17,
	create_group 18,
	create_group 19,
	create_group 20,
	create_group 21,
	create_group 22,
	create_group 23,
	create_group 24,
]

let students : List Student = [ 
	create_student 19 (create_group 4) "Иванов И.И.", 
	create_student 18 (create_group 4) "Петров П.П.",
	create_student 18 (create_group 5) "Сидоров С.С.",
	create_student 19 (create_group 10) "Маркаданов А.А."
]

let subject = "Конфигурационное управление"

in { groups = groups, students = students, subject = subject }
```



Для решения дальнейших задач потребуется программа на Питоне, представленная ниже. Разбираться в самом языке Питон при этом необязательно.

```Python
import random


def parse_bnf(text):
    '''
    Преобразовать текстовую запись БНФ в словарь.
    '''
    grammar = {}
    rules = [line.split('=') for line in text.strip().split('\n')]
    for name, body in rules:
        grammar[name.strip()] = [alt.split() for alt in body.split('|')]
    return grammar


def generate_phrase(grammar, start):
    '''
    Сгенерировать случайную фразу.
    '''
    if start in grammar:
        seq = random.choice(grammar[start])
        return ''.join([generate_phrase(grammar, name) for name in seq])
    return str(start)


BNF = '''
E = a
'''

for i in range(10):
    print(generate_phrase(parse_bnf(BNF), 'E'))

```

Реализовать грамматики, описывающие следующие языки (для каждого решения привести БНФ). Код решения должен содержаться в переменной BNF:

## Задача 3

Язык нулей и единиц.

```
10
100
11
101101
000
```

## Задача 4

Язык правильно расставленных скобок двух видов.

```
(({((()))}))
{}
{()}
()
{}
```

## Задача 5

Язык выражений алгебры логики.

```
((~(y & x)) | (y) & ~x | ~x) & x
y & ~(y)
(~(y) & y & ~y)
~x
~((x) & y | (y) | (x)) & x | x | (y & ~y)
```
