---
создал заметку: 2024-10-09
tags:
  - cpp
  - roadmap
  - programming
---
### const_cast
тип приведения который позволяет снимать константность. потенциальное UB

```cpp
const int original_value = 1;
int* non_const_value_ptr = const_cast<int*>(&original_value);
*non_const_value_ptr++;

assert(non_const_value_ptr == &original_value);
```
