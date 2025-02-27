Описание
tnine — это консольная утилита на языке C для поиска контактов с использованием алгоритма, похожего на T9-предиктивный ввод. Программа считывает список контактов из стандартного ввода, где каждый контакт задаётся двумя строками (имя и номер телефона), и позволяет выполнять поиск как по номеру, так и по имени.

Особенности

Чтение контактов:
Программа принимает на вход до 100 контактов. Каждый контакт состоит из имени и номера телефона, вводимых последовательно.

Поиск контактов:

NORMAL_MODE: Поиск выполняется с использованием стандартных алгоритмов findNumber и findText.
S_MODE: Альтернативный режим поиска, активируемый флагом -s, использующий функции findNumberS и findTextS.
T9-кодирование:
Для сопоставления цифровых клавиш с буквами используется массив string_map (например, цифра 2 соответствует строке "abc").

Компиляция

bash
Copy
gcc tnine.c -o tnine
Использование

Вывод всех контактов:
Если программа запускается без аргументов, она выводит список всех считанных контактов:

bash
Copy
./tnine < contacts.txt
Поиск по цифровой строке:
Передайте цифровую строку как аргумент для поиска:

bash
Copy
./tnine 123
Активация S_MODE:
Для использования альтернативного режима поиска запустите программу с флагом -s:

bash
Copy
./tnine -s 123
Формат входных данных

Контакты вводятся в виде пар строк:
Первая строка — имя контакта.
Вторая строка — номер телефона.
Пример файла contacts.txt:

diff
Copy
Ivan Ivanov
+123456789
Maria Petrova
+987654321
Алгоритм работы

Декодирование ввода:
Функция decodeString преобразует входящую цифровую строку в массив строк, соответствующих буквам на клавиатуре телефона.
Поиск:
Функции findNumber и findText (а также их аналоги в S_MODE) ищут совпадения в номере или имени контакта.
Проверка корректности ввода:
Функция parseUserInput обрабатывает аргументы командной строки и проверяет, что введена корректная цифровая строка.
Автор и контакты

Автор: Shynggys Baimukhammedov
Учебное заведение: FIT VUT
Дата завершения: 18.09.2024
Время разработки: 19+ часов