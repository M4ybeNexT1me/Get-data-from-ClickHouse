
Этот алгоритм позволит подключаться к бд ClickHouse и вытаскивать большие объемы данных. В данный момент настроен на выгрузку по дням.

## Содержание
* [Технологии](#technologies)
* [Начало работы](#start_working)
  * [Библиотеки](#library)
  * [Описание файлов](#files)
* [Пробный запуск и проверка данных](#try_run)
* [Постобработка выгруженных файлов](#post_processing)
* [Планируемые обновления](#updates)
* [FAQ](#FAQ)
* [Команда проекта](#project_team)


<a name="technologies"><h2>Технологии</h2></a>
* [Official_ClickHouse_site](https://clickhouse.com/docs/en/integrations/python)
* [github_ClickHouse_helper](https://github.com/ClickHouse/clickhouse-connect)



<a name="start_working"><h2>Начало работы</h2></a>

<a name="library"><h3>Библиотеки</h3></a>

Убедитесь, что у вас есть все необходимые библиотеки:
1. Numpy
2. Pandas
3. clickhouse_connect
4. tqdm
5. time

для установки соответвующей библиотеки используйте команды:
1. ```pip install Numpy``` или ```pip3 install Numpy```
2. ```pip install Pandas``` или ```pip3 install Pandas```
3. ```pip install clickhouse-connect``` или ```pip3 install clickhouse-connect```
4. ```pip install tqdm``` или ```pip3 install tqdm```
5. ```pip install time``` или ```pip3 install time```

- при возникновении проблем - ищите ответы на "Stack Overflow"

<a name="files"><h3>Описание файлов</h3></a>
1. "ClickHouse_code.py" - содержит актуальный код для конкретной выгрузке (заменяется для каждой задачи)

```
__QUERY__= """
with
'{date_begin}' as beg_,
'{date_end}' as end___QUERY__= """
with 
'{date_begin}' as beg_,
'{date_end}' as end_
[вставьте здесь Select]
"""
```

3. "ClickHouse_database_configuration.py" - хранит конфигурации для подключения к ClickHouse (один раз заполнили и не трогаем)
```
__HOST__ = 'c-c9qsfmhkl42nof95hnh3.rw.mdb.yandexcloud.net'
__PORT__ = 8443
__CA_CERT__ = ''
__USERNAME__ = ''
__PASSWORD__ = ''
```

__CA_CERT__ - путь до файла дешифровщика RootCA.pem, который вы скачали с [Яндекса](https://yandex.cloud/ru/docs/managed-clickhouse/operations/connect/?utm_referrer=about%3Ablank);
    
__USERNAME__ - ваш LDAP;
    
__PASSWORD__ - пароль, который выдал руководитель (Дарья Голубева).
    
5. "ClickHouse_database.py" - содержит класс с методами для подключения к ClickHouse и сопутствующими обработками (не открываем)
6. "ClickHouse_get_data.py" - основной файл для выгрузки данных, в котором работаем 
7. "fetch_data" - папка, в которую сохраняем выгруженные файлы
8. "test.py" - сборка выгруженных файлов

<a name="try_run"><h2>Пробный запуск и проверка данных</h2></a>




<a name="post_processing"><h2>Постобработка выгруженных файлов</h2></a>




<a name="updates"><h2>Планируемые обновления</h2></a>

1.	Выгрузка не только по дням, но и по неделям/выставленным границам/от объема итерации;
2.	Формирование файлов не только по неделям, а в зависимости от объема одной итерации выгрузки;
3.	Исправление ошибок, при которых останавливается выгрузка:

     *	Ошибка на стороне бд;
     *	Ошибка на стороне запроса;
     *	Ошибка на стороне пользователя;

4.	Более корректное логирование ошибок (реализовано: день – ошибка выгрузки; сделать точное описание ошибки)
5.	Сделать автоматическую проверку на консистентность и полноценность выгрузки
6.	Возможность выгружать не только в csv, но и сразу в google sheets
7.	Вынести пути в отдельную переменную, чтобы все переменные вводились в начале файла
8.	Автоматическое обновление пути к файлам в зависимости от расположения репозитория
9.	Добавить tqdm для отслеживания время отработки кода

**Выставить приоритезацию по обновлениям**


<a name="FAQ"><h2>FAQ</h2></a>
* Здесь будут часто-задаваемые вопросы (добавляйте)

<a name="project_team"><h2>Команда проекта</h2></a>
* [Саитов Владислав](https://portal.vseinstrumenti.ru/profile/6fd3a804-7554-b745-9521-80d154d9b4de)

## Подсказки по написанию readme

ПРАВИЛА ОФОРМЛЕНИЯ ФАЙЛА - [Первая ссылка](https://github.com/sandino/Markdown-Cheatsheet/blob/master/README.md)

Шпаргалка по Markdown - [Вторая ссылка](https://gist.github.com/alinastorm/8a04cdbc36be9c051a66f90ae6d6df35)
