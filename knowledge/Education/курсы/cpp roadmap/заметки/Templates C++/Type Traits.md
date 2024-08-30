---
создал заметку: 2024-08-20
tags:
  - cpp
  - course
  - roadmap
  - programming
---
### Описание
Способ определения черт Типа, для дальнейшего корректирования его поведения в коде

Некоторые общие черты типа:
- `std::is_pointer`: Проверяет, является ли заданный тип типом указателя.
- `std::is_arithmetic`: Проверяет, является ли заданный тип арифметическим типом.
- `std::is_function`: Проверяет, является ли заданный тип типом функции.
- `std::decay`: Применяет правила decltype к типу входных данных (удаляет ссылки, cv-квалификаторы и т. д.).
### Пример
```cpp
#include <iostream>
#include <type_traits>

int main() {
    int a;
    int* a_ptr = &a;

    std::cout << "Is 'a' a pointer? " << std::boolalpha << std::is_pointer<decltype(a)>::value << std::endl;
    std::cout << "Is 'a_ptr' a pointer? " << std::boolalpha << std::is_pointer<decltype(a_ptr)>::value << std::endl;

    return 0;
}
```
данный пример проверяет является ли указанная переменная и указатель на переменную указателем. [[boolapha|что такое boolalpha?]]

### Составление типовых черт
- `std::conditional` - Если заданное логическое значение истинно, используйте тип A; в противном случае используйте тип B.
```cpp
template<typename T, typename B>
using type = std::conditional<std::is_arithmetic<T>::value, T, B> 

type func() {...};
}

```
- `std::enable_if` - Если заданное значение истинно, применяет тип, иначе вложенный тип отсутствует
```cpp
template<typename T>
typename std::enable_if<std::is_arithmetic<T>::value, T>::typefind_max(T a, T b) {
	return a > b ? a : b;
}

int main() {
    int max = find_max(10, 20);
    std::cout << "Max: " << max << std::endl;

    return 0;
}
```
В данном случае сработают только арифметические типы, в остальных кейсах это просто не будет воспроизводиться.

### Резюме
Более универсальный, расширяемый и эффективный код на основе характеристик типов.

Связано с: [[Templates C++]]
