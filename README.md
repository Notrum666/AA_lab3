# Lab3 Алгоритм сортировки
## Задание 
В вашу задачу входит разработка обобщенной функции `sort()`, реализующей алгоритм быстрой сортировки со следующими оптимизациями:

- Выбор опорного элемента, как медианы из первого, среднего и последнего элемента сортируемого интервала;
- Исключение хвостовой рекурсии: функция должна определять длины получившихся интервалов после разбиения и рекурсивно сортировать интервал меньшей длины, итеративно обрабатывая интервал большей длины;
- Использование алгоритма сортировки вставками для коротких интервалов (длину такого интервала необходимо подобрать экспериментально).
- Использовать move-семантику для обмена элементов в процессе разбиения и при сортировке вставками.

Функция должна принимать три аргумента: начало `first` и конец `last` сортируемого интервала и предикат сортировки comp,который принимает два аргумента – элементы массива `a` и `b`, и возвращает true, если `a < b`, то есть в отсортированном массиве элемент `a` должен располагаться *перед* `b`.
```
template<typename T, typename Compare>
void sort(T \*first, T \*last, Compare comp)
```
где предикат упорядочивания должен удовлетворять прототипу 
```
template<typename T>
bool comp(const T &a, const T &b)
```
Сортировка массива из 100 целых чисел при помощи разработанной функции будет выглядеть следующим образом:
```
int a[100];
sort(a, a + 100, [](int a, int b) { return a < b; });
```
Для разработанной функции необходимо создать набор модульных тестов (например, Google Test или CppUnit). Тесты должны быть репрезентативными, покрывать общий и максимальное количество граничных случаев. Тесты должны покрывать случаи сортировки массивов из элементов как примитивных, так и нетривиальных типов.
## Результаты
![2022-12-17_06-02-14](https://user-images.githubusercontent.com/30927048/208220901-bd84eb98-46bb-45e0-be39-d18c5ddc26c5.png)
Быстрая сортировка становится эффективнее сортировки вставки на 10 элементах (тесты проводились на худшем случае - массиве, отсортированном в обратном порядке)