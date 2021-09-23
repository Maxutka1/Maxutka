# Домашнее задание №1
___Домашнее задание №1 по предмету "Функциональная логика и теория алгоритмов".
Веселов Максим ИУ4-31Б Вариант 3.___
---------------------------------------------------------------------------
2. Пользователь вводит число с плавающей точкой. Считать число и вывести отдельно целую и дробную часть. Предусмотреть возможность наличия ведущих нулей у дробной части.
Бонус: предусмотреть обработку ограничений ввода (например, если число считывается в виде строки, то завершать работу программы при превышении заданной длины).
Пример ввода: 10.05
Пример вывода: 10 | 05
---------------------------------------------------------------------------
#include <stdio.h>
#include <stdlib.h>

#pragma warning(disable: 4996)

int main()
```c
{
    char number[255];                                                         // массив для ввода строки
    int i = 0, limit = 15;                                                    // i - индексная переменная для прохода по строке,
                                                                              // limit - ограничение максимальной длины ввода
    scanf("%s", number);                                                      // ввод строки с клавиатуры
    while (number[i] != '\0') {                                               // пока не дойдём до символа конца строки
        i++;                                                                  // идём вправо
    }                                                                         // цикл заканчивается - мы на последнем введённом символе
    if (i >= limit) {                                                         // если его индекс больше, чем установленное ограничение, то
        printf("You have entered more than 15 signs\n");                      // выводим предупреждение
        return 1;                                                             // и завершаем программу с аварийным кодом выхода
    }
    i = 0;                                                                    // возвращаемся в начало строки
    while (number[i] != '.') {                                                // пока не найдём точку
        printf("%c", number[i]);                                              // выводим все символы подряд
        i++;                                                                  // и переходим к следующему
    }
    printf("|");                                                              // вместо точки выводим вертикальную черту
    i++;                                                                      // пропускаем точку, переходим к началу дробной части
    while (number[i] != '\0') {                                               // идём до конца введённой строки
        printf("%c", number[i]);                                              // выводим символы из дробной части
        i++;                                                                  // и переходим к следующему
    }
    return 0;                                                                 // конец главной функции
}
```
___СБОРКА___

Файл проекта DZ1.c запускается на visual studio 2019
