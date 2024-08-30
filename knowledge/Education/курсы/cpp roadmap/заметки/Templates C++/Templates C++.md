---
создал заметку: 2024-08-20
tags:
  - cpp
  - course
  - programming
  - roadmap
---
### Описание
Главное преимущество создания шаблонов является создание generic code для использования различных типов

### Шаблоны функций
Чтобы создать шаблонную функцию достаточно использовать `template` с указанием типа, который мы можем использовать подобно любому доступному нам типу.
```c++
template<typename T>
void func(T arg){
	std::cout << std::type_info(arg) <<std::endl;
}

template<typename T>
void max(T a, T b){
	return a > b ? a : b;
}
```
### Шаблонные классы
Используются подобно шаблонам функций
```c++
template<typename T1, typename T2>
class A{
public:
	T1 first;
	T2 second;
	A(T1 first, T2 second) : first(first), second(second){};
}
```
Ну или мы можем указать явную [[Template specialization|специализацию шаблона]], для специфического кейса
```cpp
template<>
class A<char, char>{
public:
	char first_;
	char second_;
	A(char first, char second) : first_(first), second_(second){
		first_ = std::toupper(first_);
		seccond_ = std::toupper(second_);
	};
}
```
### Резюме
Разобрались с использованием шаблонов для функций, классов, а так же использование для специализированных кейсов. Шаблоны функций это мощный инструмент, предоставляющий возможности для многократного переиспользования кода.

Связано с: [[cpp roadmap]]
