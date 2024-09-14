# Практическое задание 1
## Задание 1
Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).

Код:
```
cut -d: -f1 /etc/passwd
```
<img width="969" alt="image" src="https://github.com/user-attachments/assets/86b2dc0e-eeae-4443-be90-337f0297540c">

## Задание 2

Вывести данные /etc/protocols в отформатированном и отсортированном порядке для 5 наибольших портов, как показано в примере ниже:

Код:
```
cat /etc/protocols | sort -k2,2 -n -r | awk '{print $2, $1}' | head -5
```
<img width="670" alt="image" src="https://github.com/user-attachments/assets/59e7eb79-c960-46c7-b0e9-ea7c0c628dd5">

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
<img width="995" alt="image" src="https://github.com/user-attachments/assets/078cdaad-4218-4b6b-89ca-4acaa40537a6">

## Задание 4

Написать программу для вывода всех идентификаторов (по правилам C/C++ или Java) в файле (без повторений).

Код консольный:
```
grep -E -o '\b[a-zA-Z_][a-zA-Z0-9_]*\b' hello.c | sort | uniq
```
![image](https://github.com/user-attachments/assets/0ddfa722-bde1-4155-a855-1478fa1258ce)


## Задание 5

Файл reg
```
chmod +x $1
sudo cp $1 /usr/local/bin
```

## Задание 6

```py
#!/usr/bin/env python3
import os
import sys

if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Неверный ввод")
    else:
        directory = sys.argv[1]
        extensions = {
            '.c': '//',
            '.js': '//',
            '.py': '#'
        }
        for finded in os.scandir(directory):
            if finded.is_file():
                file = os.path.splitext(finded.name)[-1]
                if file in extensions:
                    with open(finded.path, 'r') as f:
                        first_line = f.readline().strip()
                        if first_line.startswith(extensions[file]):
                            print(f"{finded.name} - есть")

```

```
./script6.py "./"
```

![Uploading image.png…]()


## Задание 7

```py
#!/usr/bin/env python3
import os
import hashlib

import hashlib
import os


def compute_file_hash(file_path):
    sha256_hasher = hashlib.sha256()
    with open(file_path, 'rb') as file:
        buffer = file.read(65536)  # Размер буфера
        while len(buffer) > 0:
            sha256_hasher.update(buffer)
            buffer = file.read(65536)
    return sha256_hasher.hexdigest()


def search_duplicate_files(directory):
    hash_map = {}
    duplicate_files = []

    for root_dir, subdirs, files in os.walk(directory):
        for file_name in files:
            full_path = os.path.join(root_dir, file_name)
            hash_value = compute_file_hash(full_path)
            if hash_value in hash_map:
                hash_map[hash_value].append(full_path)
            else:
                hash_map[hash_value] = [full_path]

    for file_paths in hash_map.values():
        if len(file_paths) > 1:
            duplicate_files.append(file_paths)

    return duplicate_files


if __name__ == "__main__":
    import sys
    if len(sys.argv) > 1:
        directory = sys.argv[1]
        found_duplicates = search_duplicate_files(directory)
        if found_duplicates:
            print("Duplicates:")
            for duplicate_group in found_duplicates:
                for filepath in duplicate_group:
                    print(filepath)
    else:
        print("Неверный ввод")
```

```
./script7.py "./"
```

![Uploading image.png…]()

## Задание 8

python script

```py
#!/usr/bin/env python3
import os
import tarfile
import sys

if __name__ == "__main__":
    dir, ext = sys.argv[1], sys.argv[2]
    tararchive = f"archive_{ext.replace('.', '')}.tar"

        with tarfile.open(tararchive, "w") as tar:
            for file in os.listdir(dir):
                if file.endswith(ext):
                    tar.add(os.path.join(dir, file))
        print(f"Архив {tararchive} создан.")
```

Ввод и вывод
```
./script8.py "./" ".py"
ls
```
```
Создан: arr_py.tar

arr_py.tar  bench.py    hello.c     hello.js    readme.txt  script8.py
```


## Задание 8

python script
```py
#!/usr/bin/env python3
import sys

if __name__ == "__main__":
    input, output = sys.argv[1], sys.argv[2]
    with open(input) as w:
        isxod = w.read()
        red = isxod.replace("    ", "\t")
        with open(res, "w") as w:
            w.write(red)
        print(f"результат: {output}")
```

Ввод и вывод
```
./script8.py "text.txt" "res.txt"
```
```
Результат: res.txt
```
