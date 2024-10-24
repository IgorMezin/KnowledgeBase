---
создал заметку: 2024-10-13
tags:
  - cpp
  - programming
---
### std::unique_ptr

удобно использовать для перемещения между скопами владения, запрещён конструктор копирования 

```cpp 
std::unique_ptr<Jopa> = std::make_unique<Jopa>({"Big", "Puk"})
```

### std::shared_ptr
### std::weak_ptr
