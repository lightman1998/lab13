# Задание

Написать программы на **C++** для сериализации и десериализации структуры `Person`.

Структура `Person` определяется следующим образом:

```cpp
struct Email {
  std::string nickname;
  std::string server;
};

struct Person {
  std::string  first_name;
  std::string  last_name;
  Email        email;
  size_t       age;
  std::string  phone;
};
```
Формат сериализации и десериалиализации ***yaml***

```ShellSession
https://github.com/jbeder/yaml-cpp
```
Сборка:
```
$ cmake -H. -B_build
$ cmake --build _build
$ cd _build/
$ ./pack <путь_к_файлу.yaml>
Вводим параметры
$ ./unpack <путь_к_файлу.yaml>
```

## Пример:
```
$ ./pack pack
Enter data to fields of the Person structure.
First name:
Arman
Last name:
Asatryan
Email:
kall-lightman@yandex.ru
Age:
19 
Phone:
88005553535

$ ./unpack pack
[Person]
First name: Arman
Last name:  Asatryan
Email:      kall-lightman@yandex.ru
Age:        19
Phone:      88005553535
```

## Проверка валидности :
```
First name: Arman
Last name: Asatryan
Email: kall-lightman@yandex.ru
Phone: 88005553535
Age: 19
```
### Вывод:
``` 
--- 
Age: 19
Email: kall-lightman@yandex.ru
? "First name"
: Arman
? "Last name"
: Asatryan
Phone: 88005553535
```
### Valid YAML!
