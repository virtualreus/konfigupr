# Практическое задание 1
## Задание 1
Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).

Код:
```
cut -d: -f1 /etc/passwd
```

## Задание 2

Вывести данные /etc/protocols в отформатированном и отсортированном порядке для 5 наибольших портов, как показано в примере ниже:

Код:
```
cat /etc/protocols | sort -k2,2 -n -r | awk '{print $2, $1}' | head -5
```

## Задание 3

Написать программу banner средствами bash для вывода текстов, как в следующем примере (размер баннера должен меняться!):
```
[root@localhost ~]# ./banner "Hello from RTU MIREA!"
+-----------------------+
| Hello from RTU MIREA! |
+-----------------------+
```
Перед отправкой решения проверьте его в ShellCheck на предупреждения.

Код:

Консоль:
```
./script3.py "privet"
```

Python:
```py
#!/usr/bin/env python3
import sys

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Введите текст")
    else:
        input_text = sys.argv[1]
        line = '+' + '-' * (len(input_text) + 2) + '+'
        print(line)
        print('| ' + input_text + ' |')
        print(line)
```

