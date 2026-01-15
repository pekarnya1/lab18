# Домашнее задание к работе 18
## Условие задачи

Вариант 11. Запись «Автомобиль»:
Марка автомобиля
Производитель
Тип
Год выпуска

Дата регистрации
Вывести сведения о машинах марки “Ford” и
зарегистрированных до 2000-го года.

## 1. Алгоритм и блок-схема
## Алгоритм
```
1. Начало программы
2. Создаем структуру Car с полями: марка, производитель, тип, год выпуска, год регистрации
3. Вводим количество автомобилей
4. Заполняем массив структур данными об автомобилях
5. Ищем автомобили Toyota с регистрацией до 2007 года
6. Выводим найденные автомобили или сообщение об их отсутствии
7. Конец программы

```
   
### Блок-схема

<img width="473" height="1476" alt="image" src="https://github.com/user-attachments/assets/28bbfb52-efd0-417b-a144-d097e992df44" />



## 2. Реализация программы

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <string.h>
#include <locale.h>

typedef struct {
    char brand[30];
    char manufacturer[50];
    char type[30];
    int year_made;
    int reg_year;
} Car;

int main() {
    setlocale(LC_ALL, "Rus");

    int n;
    printf("Введите количество автомобилей: ");
    scanf("%d", &n);

    Car cars[10];

    for (int i = 0; i < n; i++) {
        printf("\n--- Автомобиль №%d ---\n", i + 1);
        printf("Марка: ");
        scanf("%s", cars[i].brand);
        printf("Производитель: ");
        scanf("%s", cars[i].manufacturer);
        printf("Тип (кузов): ");
        scanf("%s", cars[i].type);
        printf("Год выпуска: ");
        scanf("%d", &cars[i].year_made);
        printf("Год регистрации: ");
        scanf("%d", &cars[i].reg_year);
    }

    printf("\nРезультаты поиска (Toyota, регистрация до 2007):\n");
    printf("-------------------------------------------------\n");
    int found = 0;
    for (int i = 0; i < n; i++) {
        if (strcmp(cars[i].brand, "Toyota") == 0 && cars[i].reg_year < 2007) {
            printf("Марка: %s | Производитель: %s | Тип: %s | Выпуск: %d | Регистрация: %d\n",
                cars[i].brand, cars[i].manufacturer, cars[i].type, cars[i].year_made, cars[i].reg_year);
            found = 1;
        }
    }

    if (!found) {
        printf("Подходящие автомобили не найдены.\n");
    }

    return 0;
}

```


## 3. Результаты работы программы

```
Введите количество автомобилей: 1

--- Автомобиль №1 ---
Марка: Toyota
Производитель: Kot
Тип (кузов): Kolo
Год выпуска: 2500
Год регистрации: 1999

Результаты поиска (Toyota, регистрация до 2007):
-------------------------------------------------
Марка: Toyota | Производитель: Kot | Тип: Kolo | Выпуск: 2500 | Регистрация: 1999

```

<img width="1201" height="450" alt="image" src="https://github.com/user-attachments/assets/4d2f2d30-ee2e-4ff8-8316-11c3b1dd3350" />
