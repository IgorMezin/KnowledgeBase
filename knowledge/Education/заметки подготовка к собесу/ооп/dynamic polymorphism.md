---
создал заметку: 2024-10-08
tags:
  - cpp
  - programming
  - roadmap
---
### Динамический полиморфизм
Динамический полиморфизм - концепт ооп яп который позволяет переопределять или переписывать реализацию методов базового класса. Это означает что один метод может иметь несколько реализаций в зависимости от объекта, который его вызывает.

Динамический полиморфизм достигается через виртуальные функции, которыми мы определяем методы базового класса. 
```cpp
class Base{
public:
	virtual void print(){
		std::cout << "Base" << std::endl;
	}
};

class A : public Base{
public:
	void print() override {
		std::cout << "A" << std::endl;
	}
};

class B : public Base{
public:
	void print() override {
		std::cout << "B" << std::endl;
	}
};

int main(){
	Base* base;
	A a;
	B b;
	base = &a;
	base->print(); // print A;
	base = &b;
	base->print(); // print B;
	
	return 0;

}
```
