# Двойное подключение
Следующий фрагмент кода на языке Си демонстрирует потенциальные проблемы, которые могут возникнуть, если пропустить #include guards:
```C++
Файл grandfather.h
 struct foo {
     int member;
 };
Файл father.h
 #include "grandfather.h"
Файл child.c
 #include "grandfather.h"
 #include "father.h"
Здесь к файлу «child.c» напрямую подключаются две копии заголовочного файла «grandfather.h». Это может вызвать ошибку компиляции, так как структура типа foo явным образом определяется дважды.
Применение #include guards
Файл grandfather.h
 #ifndef H_GRANDFATHER
 #define H_GRANDFATHER

 struct foo
 {
     int member;
 };

 #endif
Файл father.h
 #include "grandfather.h"
Файл child.c
 #include "grandfather.h"
 #include "father.h"
 ```
В данном примере первое включение файла «grandfather.h» делает идентификатор макроса H_GRANDFATHER определённым. Далее, когда к «child.c» подключается «grandfather.h» второй раз, проверка этого идентификатора на неопределенность директивой #ifndef не проходит, и препроцессор пропускает всё вплоть до директивы #endif, таким образом избегая второго определения struct foo. В результате программа компилируется корректно.
Проблемы использования
Чтобы #include guards работали корректно, в каждом из них должен использоваться (проверяться и определяться) свой уникальный идентификатор макроса препроцессора. Поэтому в проекте с использованием #include guards должна соблюдаться единая система назначения имён идентификаторам макросов и все используемые идентификаторы не должны пересекаться (совпадать) как друг с другом, так и с идентификаторами из используемых в проекте сторонних заголовочных файлов и идентификаторами макросов с глобальной видимостью.
Для решения этих проблем в большинстве реализаций языков Си и C++ поддерживается нестандартная директива #pragma once. Вставленная в начало заголовочного файла, эта директива будет ограничивать количество подключений этого файла одним. Этот подход, однако, может плохо сказаться в виде потенциальной сложности определения ситуации, когда две директивы #include с разными параметрами на самом деле ссылаются на один заголовочный файл (например, с использованием символьной ссылки в Unix-подобных системах). Более того, так как #pragma once не является стандартной директивой, её семантика может серьёзно изменяться в зависимости от применения.

Источник: https://ru.wikipedia.org/wiki/Include_guard