# Анализ результатов решения задачи поиска и подсчёта простых чисел

## Однопоточное решение

Команда запуска:
```shell
java -classpath C:\Users\ip-oe\IdeaProjects\ISSO\programming-concurrency-on-the-jvm\target\classes gu.isso.prime_numbers.SequentialPrimeFinder 10000000
```

Результат выполнения: 
```text
Number of primes under 10000000 is 664579
Time (seconds) taken is 5.9791241
```

Для верхней границы в 10 000 000 получили около 6 секунд времени выполнения.

## Многопоточное решение

Команда запуска:
```shell
java -classpath C:\Users\ip-oe\IdeaProjects\ISSO\programming-concurrency-on-the-jvm\target\classes gu.isso.prime_numbers.ConcurrentPrimeFinder 10000000 16 16
```

Результат выполнения:
```text
Number of primes under 10000000 is 664579
Time (seconds) taken is 0.3882539
```

Для верхней границы в 10 000 000 получили около 2 секунд времени выполнения.

Здесь мы передаём параметры, которые можно варьировать. Число потоков у нас фиксировано (16 потоков по формуле, потому что блокирующий коэффициент - 0, а число ядер - 16), можем увеличить число частей:

Команда запуска:
```shell
java -classpath C:\Users\ip-oe\IdeaProjects\ISSO\programming-concurrency-on-the-jvm\target\classes gu.isso.prime_numbers.ConcurrentPrimeFinder 10000000 16 100
```

Результат выполнения:
```text
Number of primes under 10000000 is 664579
Time (seconds) taken is 0.363238
```

Для моего процессора не сильно ситуация изменилась, однако стало лучше.

