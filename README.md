# pascal.js -- pascal interpreter in javascript

## Разработка

Устанавливаем зависимости:

```shell
npm ci
```

Запуск:

```shell
node --es-module-specifier-resolution=node run.js 
```

Запуск всех тестов:

```shell
npm test
```
### Запуск текущего файла теста с отладкой (vscode)

* Откройте файл теста
* В разделе запуска/отладки (слева вверху) переключитесь на `Jest Current`
* Далее на любом открытом файле текста последовательно нажимите `Ctrl+Shift+D` и затем `Enter`


## О программе 

Интерпретатор работает как конвейер, передавая промежуточный результат следующему модулю:
* **Модуль ввода-вывода (МВВ)** `FileIO` -- разбивает исходных текст на отдельные буквы.
* **Лексический анализатор (ЛА)** `LexicalAnalyzer` -- из букв строит слова программы.
* **Синтаксический анализатор (СА)** `SyntaxAnalyzer` -- строит дерево выполнения.
* **Движок** `Engine` -- выполняет дерево, полученное из `SyntaxAnalyzer`, это и есть процесс выполнения программы.

Можно сравнить эту структуру интерпретатора с возможной структурой компилятора: http://fkn.ktu10.com/?q=node/12395


### SyntaxAnalyzer

ДАС - дерево абстрактного синтаксиса, структура, которая строится СА на основе исходной программы, 
потом это структуру будет выполнять Движок `Engine`.

* `SyntaxAnalyzer/Tree/` - директория хранит описания типов узлов для ДАС

TODO

 Тесты:
 * Логический тип - есть
 * Логические операции -- вроде есть (тест не проходит)
 * Порядок арифм. операций -- есть
 * Массивы (в т.ч. многомерные, ключи как числа, символы, диапазоны enum)
 * Пользовательские процедуры и функции 
 
