---
создал заметку: 2024-10-08
tags:
  - cpp
  - programming
  - roadmap
---
### Виртуальные таблицы 
Vtable механизм используемый компилятором cpp для поддержки динамического полизморфизма. Когда класс содержит [[Virtual Methods|виртуальную функцию]], компилятор создает виртуальную таблицу с указателями на функции определенные в классе.

```cpp
class Base {
	virtual void print(){/*print Base*/};
	virtual void print2(){/*print2 Base*/};
}
class Derrived : public Base{
	void print() override{/*print Derrived*/};
	void print3() {/*print3 Derrived*/};
}
```

| Derrived vtable   |
| ----------------- |
| Derrived::print() |
| Base::print2()    |
 Нашлась отличная картинка с описанием устройства виртуальных таблиц
 ![[VTable.gif]]