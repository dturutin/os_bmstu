Пример выполнения лабы 1 для тебя

---

### Код самой программы

```cpp
#include <iostream>
#include <omp.h> // подключаем open mp

int main() {
    #pragma omp parallel // чтобы выполнялось параллельно
    {
        int thread_num = omp_get_thread_num(); // записываем в переменную # текущего потока
        std::cout << "Привет мир! Я поток " << thread_num << std::endl; // выводим сообщения "Привет мир" и номер потока, который выполнил
    }
    return 0;
}
```

### Как компилить с помощью g++??

```shell
g++ -fopenmp hello.cpp -o hello && ./hello
```

`пример вывода:`

```shell
Привет мир! Я поток 0
Привет мир! Я поток 1
Привет мир! Я поток 2
Привет мир! Я поток 4
```

### Как поменять кол-во потоков?

Данную строчку нужно ввести в терминале

```bash
export OMP_NUM_TREADS=2
```

меняет переменную окружения, в которую записывается кол-во потоков твоей системы. В примере установили кол-во = 2

`вывод после измененной переменной окружения:`

```shell
./hello
```

```shell
Привет мир! Я поток 0
Привет мир! Я поток 1
```
