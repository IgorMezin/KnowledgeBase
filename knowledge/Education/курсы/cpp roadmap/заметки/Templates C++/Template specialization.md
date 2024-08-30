---
создал заметку: 2024-08-20
tags:
  - course
  - cpp
  - roadmap
  - programming
---
### Описание
Это способ реализации поведения шаблона для специализированного типа или набора типов. Есть два типа реализации специализированного шаблона:
- **Полная специализация** - когда мы полностью определяем спецификацию для определённого типа реализации.
- **Частичная специализация** - когда мы частично предоставляем реализацию для определённого подмножества.
### Полная специализация
```cpp
template<typename T>
void printData(const T& data) {
	std::cout << "General Template: " << data << std::endl;
}

template<>
void printData(const char* const & data) {
	std::cout << "Specialized template for const char*: " << data << std::endl;
}
int main() {
    int a = 5;
    const char* str = "Hello, world!";
    printData(a); // General template: 5
    printData(str); // Specialized template for const char*: Hello, world!
}
```

### Частичная специализация
```cpp
template<typename T1, typename T2>
class MyPair {
private:
	T1 key;
	T2 value;
public:
	MyPair(T1 key, T2 value) : key(key), value(value) {};
	void print() const {
		std::cout << "Partial specialization for int values: key = " 
		<< key 
		<< ", value = " 
		<< value 
		<< std::endl;
    }
}

template<typename T1>
class MyPair {
private:
	T1 key;
	int value;
public:
	MyPair(T1 key, int value) : key(key), value(value) {};
	void print() const {
		std::cout << "Partial specialization for int values: key = " 
		<< key 
		<< ", value = " 
		<< value 
		<< std::endl;
    }
}

int main() {
    MyPair<double, std::string> p1(3.2, "example");
    MyPair<char, int> p2('A', 65);
    p1.print(); // General template: key = 3.2, value = example
    p2.print(); // Partial specialization for int values: key = A, value = 65
}

```
### Резюме
Теперь мы знаем отличие полной специализации от частичной, это позволит нам создавать более гибкие приложения и более точные способы специализации шаблона.

Связано с: [[Templates C++]]
