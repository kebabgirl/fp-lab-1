<p align="center"><b>МОНУ НТУУ КПІ ім. Ігоря Сікорського ФПМ СПіСКС</b></p>

<p align="center">
<b>Звіт з лабораторної роботи 1</b><br/>
"Обробка списків з використанням базових функцій"<br/>
дисципліни "Вступ до функціонального програмування"
</p>

<p align="right">**Студентка**: *Петрук Ольга Сергіївна КВ-11*<p>
<p align="right">**Рік**: *2024*<p>

## Загальне завдання

### Пункт 1

Створіть список з п'яти елементів, використовуючи функції LIST і CONS . Форма створення списку має бути одна — використання SET чи SETQ (або інших допоміжних форм) для збереження проміжних значень не допускається. Загальна кількість елементів (включно з підсписками та їх елементами) не має перевищувати 10-12 шт. (дуже великий список робити не потрібно). Збережіть створений список у якусь змінну з SET або SETQ . Список має містити (напряму або у підсписках):

- хоча б один символ

- хоча б одне число

- хоча б один не пустий підсписок

- хоча б один пустий підсписок

```lisp
(defvar new-list nil)
(setq new-list (list 'a 1 (list 1 2) () 'b))
```

##### Результат:

```lisp
(A 1 (1 2) NIL B)
```

#### Пункт 2

Отримайте голову списку.

```lisp
(defvar head nil)
(setq head (first new-list))
```

##### Результат:

```lisp
A
```

#### Пункт 3

Отримайте хвіст списку.

```lisp
(defvar tail nil)
(setq tail (cdr new-list))
```

##### Результат:

```lisp
(1 (1 2) NIL B)
```

#### Пункт 4

Отримайте третій елемент списку.

```lisp
(defvar third-el nil)
(setq third-el (nth 2 new-list))
```

##### Результат:

```lisp
(1 2)
```

#### Пункт 5

Отримайте останній елемент списку.

```lisp
(defvar last-el nil)
(setq last-el (first (last new-list)))
```

##### Результат:

```lisp
B
```

#### Пункт 6

Використайте предикати ATOM та LISTP на різних елементах списку (по 2-3 приклади для кожної функції).

```lisp
(format t "Is first el atom: ~a~%" (atom (first new-list)))
(format t "Is second el atom: ~a~%" (atom (nth 1 new-list)))
(format t "Is third el atom: ~a~%" (atom (nth 2 new-list)))
(format t "Is fourth el atom: ~a~%" (atom (nth 3 new-list)))
(format t "Is first el list: ~a~%" (listp (first new-list)))
(format t "Is second el list: ~a~%" (listp (nth 1 new-list)))
(format t "Is third el list: ~a~%" (listp (nth 2 new-list)))
(format t "Is fourth el list: ~a~%" (listp (nth 3 new-list)))
```

##### Результат:

```lisp
Is first el atom: T
Is second el atom: T
Is third el atom: NIL
Is fourth el atom: T
Is first el list: T
Is second el list: NIL
Is third el list: T
Is fourth el list: T
```

#### Пункт 7

Використайте на елементах списку 2-3 інших предикати з розглянутих у розділі 4 навчального посібника.

```lisp
(format t "Second el is number: ~a~%" (numberp (nth 1 new-list)))
(format t "Fifth el equalp to 'b': ~a~%" (equalp (nth 4 new-list) 'b))
```

##### Результат:

```lisp
Second el is number: T
Fifth el equalp to 'b: T
```

#### Пункт 8

Об'єднайте створений список з одним із його непустих підсписків. Для цього використайте функцію APPEND.

```lisp
(defvar sublist (nth 2 new-list))
(defvar combined-list (append new-list sublist))
(format t "Combined list: ~a~%" combined-list)
```

##### Результат:

```lisp
Combined list: (A 1 (1 2) NIL B 1 2)
```

## Варіант 3

<p align="center">
<img src="lab-1-variant3.png">
</p>

```lisp
(defvar sublist nil)
(defvar main-list nil)
(setq sublist (list 3 'c 'b))
(setq main-list (list 1 'a (last sublist) sublist))
```

##### Результат:

```lisp
(1 A (B) (3 C B))
```
