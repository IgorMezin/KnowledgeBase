---
создал заметку: 2024-10-09
tags:
  - cpp
  - programming
  - roadmap
---
### static_cast
один из типов операции приведения типов в C++, которое выполняет проверку на этапе компиляции и возвращает ошибку, если между данными нет допустимого преобразования. Безопаснее приведения типов в C-style т.к. проверяет возможность приведения типов и безопасно интерпретирует данные
```cpp
	static_cast<T>(expression);
```

```cpp
	enum class Color : int {
	red, green, blue
	};
	int value = 1;
	Color color = static_cast<Color>(value);
```
