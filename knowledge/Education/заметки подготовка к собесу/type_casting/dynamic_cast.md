---
создал заметку: 2024-10-09
tags:
  - cpp
  - programming
  - roadmap
---
### dynamic_cast
каст, использующийся специально для полиморфизма. Он безопасно конвертирует указатели и ссылки базового класса к наследуемому классу и проверяет валидной конвертируемого во время runtime. Если конвертация не валидная возвращаяется nullptr, предотвращая ub. Предотвращает потенциальные краши и ошибки используемые при  полиморфизме. 

```cpp
class Base {
public:
	virtual void display() {
		std::cout << "Base" << std::endl;
	}
};
class Derived : public Base {
public:
	virtual void display() {
		std::cout << "Derived" << std::endl;
	}
};

int main(){
	Base *basePtr = new Derived(); // upcasting
	Derived *derivedPtr;

	derivedPtr = dynamic_cast<Derived*>(basePtr); // downcasting
	if(derivedPtr) {
		derivedPtr->display(); // output: Derived
	} else {
		std::cout << "Invalid type conversion"
	}
	delete basePtr; 
	return 0;
}
```