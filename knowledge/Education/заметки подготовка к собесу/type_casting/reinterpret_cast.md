---
создал заметку: 2024-10-09
tags:
  - cpp
  - programming
  - roadmap
---
### reinterpret_cast (приведение переосмысление)
приведение типа указателя без изменения представления данных.
т.е. условно мы кастим указатель на интовое значение в указатель на символы и мы можем распечатать байты целочисленного значения как символы.
```cpp
#include <iostream>

int main() {
    int num = 42;
    int *num_ptr = &num;

    // Disguise the integer pointer as a char pointer
    char *char_ptr = reinterpret_cast<char *>(num_ptr);

    for (size_t i = 0; i < sizeof(int); ++i) {
        // Print the individual bytes of the integer as characters
        std::cout << "Byte " << i << ": " << char_ptr[i] << std::endl;
    }

    return 0;
}
```