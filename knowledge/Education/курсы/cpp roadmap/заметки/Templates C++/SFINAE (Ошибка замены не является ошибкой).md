---
создал заметку: 2024-08-21
tags:
  - cpp
  - roadmap
  - programming
  - course
---
### Описание
Принцип [[Metaprogramming|метапрограммирования]] шаблонов С++, который позволяет компилятору самому выбирать соответствующую функцию или класс, удовлетворяющий условию подстановки.

**Пример**
```cpp
template <typename T, typename = void>
struct foo_impl {
    void operator()(T t) {
        std::cout << "Called when T is not arithmetic" << std::endl;
    }
};

template <typename T>
struct foo_impl<T, std::enable_if_t<std::is_arithmetic<T>::value>> {
    void operator()(T t) {
        std::cout << "Called when T is arithmetic" << std::endl;
    }
};

template <typename T>
void foo(T t) {
    foo_impl<T>()(t);
}

int main() {
    int a = 5;
    foo(a); // output: Called when T is arithmetic

    std::string s = "example";
    foo(s); // output: Called when T is not arithmetic
}
```
В данном случае определены две функции `foo_impl`, отвечающие за нужный вывод на основе логического значения `std::is_arithmetic<T>` Первая из них включается, когда `T`является арифметическим типом, а вторая включается, когда `T`не является арифметическим типом. `foo`Затем функция вызывает соответствующую `foo_impl`специализацию на основе результата признака типа. Если допустимой специализации нет, то код не скомпилируется. 
### Резюме
Ну аа типа, рассмотрели (==Substitution Failure is not an error==), что означает что (==ошибка замены не является ошибкой==). Это принцип метапрограммирования шаблонов С++ когда конкретная специализация шаблона терпит неудачу во время подстановки.

Связано с: [[Templates C++]]