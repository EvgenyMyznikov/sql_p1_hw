# Домашнее задание к занятию «SQL. Часть 1» - Evgeny Myznikov

### Задание 1
Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

SELECT DISTINCT district FROM address
WHERE district  NOT LIKE '% %' AND district LIKE 'K%a';
![task1](https://github.com/EvgenyMyznikov/sql_p1_hw/blob/main/img/task1.png?raw=true)

### Задание 2
Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

SELECT amount, payment_date 
FROM payment p 
WHERE (payment_date BETWEEN "2005-06-15" AND "2005-06-19") AND amount > ROUND(10,00);
![task2](https://github.com/EvgenyMyznikov/sql_p1_hw/blob/main/img/task2.png?raw=true)

### Задание 3
Получите последние пять аренд фильмов.

SELECT film_id, title FROM film f ORDER BY film_id DESC LIMIT 5;
![task3](https://github.com/EvgenyMyznikov/sql_p1_hw/blob/main/img/task3.png?raw=true)

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

SELECT LOWER(REPLACE(first_name, 'LL', 'PP')) , LOWER(last_name)
FROM customer c 
WHERE first_name LIKE '%Willie%' AND active = 1 OR first_name LIKE '%Kelly%' AND active = 1;
![task4](https://github.com/EvgenyMyznikov/sql_p1_hw/blob/main/img/task4.png?raw=true)