#  MySQL: Backup + Репликация

## Цели: 
- снимать резервные копии;
- восстанавливать базу после сбоя;
- настраивать master-slave репликацию.

## Задачи домашнего задания:
В материалах приложен дамп базы bet.dmp
1) Базу развернуть на мастере и настроить так, чтобы реплицировались таблицы:

| bookmaker |
| competition |
| market |
| odds |
| outcome |

2) Настроить GTID репликацию.

### Описание домашнего задания
Запускаем ansible и разварачиваем 2 машины с установленным Percona Server for MySQL и настроенными конфигами.
Дальше потребуется загрузить дамп базы на мастер сервер, и настроить репликацию на слэйв сервере.

#### Проверка задания
К репозиторию прикреплен вывод команд script с каждого сервера.
Все команды сопровождаются комментариями.
