# Тестовое задание для ООО Сервер в Аренду

## Развертывание проекта

1. Скопировать ```config.tpl.ini``` в ```config.ini``` и заполнить его релевантными данными.
2. Выполнить команду ```php install.php``` в корне сайта (база данных должна быть предварительно создана). Скрипт создает таблицы и заполняет их тестовыми данными.
3. Настроить веб-сервер (Apache, Njinx) на корень сайта.

## Файлы

- ```index.php``` - отображение главной (и единственной) страницы: отбражение владельцев, отправка AJAX-запроса и отображение серверов;
- ```mysql.php``` - "библиотека" из двух функций: создание соединения и выполнение запроса, используя PDO MySql;
- ```servers/index.php``` - отвечает на AJAX-запрос, возвращая список серверов (с пагинацией);
- папки ```css/``` и ```js/``` - соответственно, таблица стилей и jQuery;
- ```config.tpl.ini``` - шаблон файла настроек.

## Примечания
1. в ТЗ указано, что нужно вывести ```servers.description```, но в описании таблиц у ```servers``` есть только ```name```, а ```description``` есть у таблицы ```ip```, так что я вывел ```servers.name``` и ```ip.description```.
2. Вместо фиксированного в константе ```owners.id``` я вывоже всех влдельцев, а пользователь может выбрать нужного.
3. В пагинации я вывожу ссылки на все страницы, что не слишком хорошо, когда страниц очень много. Следует сделать вывод двух-трех первых, двух-трех последних и двух-трех вокруг текущей. Плюс кнопки "предыдущая" и "следующая". Решил, что это уж совсем выходит за рамки ТЗ.
4. Сделано все без каких-либо фреймворков, исключая jQuery.