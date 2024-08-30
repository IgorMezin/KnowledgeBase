---
создал заметку: 2024-08-20
tags:
  - cpp
  - course
  - programming
  - roadmap
---
### Описание
Те же шаблоны, только добавляется вариативность в виде `template<typename... Args>` или 
`template<typename Head, typename... Tail>` .

### Примеры
**Суммирование нескольких аргументов**
```cpp
// Base case for recursion
template <typename T>
T sum(T t) {
  return t;
}

// Variadic template
template <typename T, typename... Args>
T sum(T t, Args... args) {
  return t + sum(args...);
}
```
**Класс кортежа с использованием вариативных функций**
```cpp
// Recursive case: Tuple with one or more elements
template <typename Head, typename... Tail>
class Tuple<Head, Tail...> : public Tuple<Tail...> {
 public:
  Tuple(Head head, Tail... tail) : Tuple<Tail...>(tail...), head_(head) {}

  Head head() const { return head_; }

 private:
  Head head_;
};

int main() {
  Tuple<int, float, double> tuple(1, 2.0f, 3.0);
  std::cout << "First element: " << tuple.head() << std::endl;
  return 0;
}
```
### Резюме
Посмотрели как выглядят вариации в шаблонах, удобно использовать при создании сложных синтаксических [[AST деревья|AST деревьев]]

***Начиная с 17 стандарта существуют более лаконичные способы для [[Обработка Variadic Templates|обработки вариативных шаблонов]]***

Связано с: [[Templates C++]]
