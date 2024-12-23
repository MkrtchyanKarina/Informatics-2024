# Лабораторная работа: "Планировщик задач cron"
Для решения лабораторной работы понадобится ОС Linux на компьютере (вирутальной машине)
## Пример
Задача: Настройте cron для выполнения скрипта, который выводит текущее время в файл time.log каждую минуту.

0) Создадим файл time.log:
   ```
   touch time.log
   ```
1) Создадим файл log_time.bash:
   ```
   nano log_time.bash
   ```
2) Напишем скрипт, при запуске которого текущее время будет записано в файл time.log:
   ```
   #!/bin/bash
      date >> /home/<user>/time.log
   ```
   ![Снимок экрана 2024-12-22 171537](https://github.com/user-attachments/assets/50aaa30a-4b79-4534-ba69-d5017cf69449)


3) Сделаем файл исполняемым:
   ```
   chmod +x log_time.bash
   ```
4) Откроем файл crontab
   ```
   crontab -e
   ```
5) Запишем время выполнения и путь до файла, имя файла:
   
   ```
   minute hour day month weekday command
   ```
   
   Время и дата записываются в формате:
   
   | Поле     | Диапазон значений | Описание                                                                                                                 |
   |----------|-------------------|--------------------------------------------------------------------------------------------------------------------------|
   | minute   | 0-59              | Минута запуска команды                                                                                                   |
   | hour     | 0-23              | Час запуска                                                                                                              |
   | day      | 1-31              | Число (день) запуска                                                                                                     |
   | month    | 1-12              | Месяц запуска                                                                                                            |
   | weekday  | 0-6               | День недели запуска (воскресенье = 0, понедельник = 1, вторник = 2 и т.д.)                                             |
   | command  |                   | Последовательность команд для выполнения. Это могут быть команды, исполняемые файлы (например, скрипты) или комбинации файлов. |

   Если нам нужно выполнять задачу каждую минуту/час/день и тд, то вместо конкретных значений поставим знак * у соответствующего поля. 
   Тогда запись нашей задачей будет состоять из 5-ти * и пути к файлу:
   ```
   * * * * * /home/<user>/time.log
   ```
6) Проверим работу - выведем содержимое файла с логами - time.log:
   
   ![image](https://github.com/user-attachments/assets/d8dbab26-baeb-4387-a6a0-45b2d81ab743)

7) Все работает верно :) Для того, чтобы установить для планировщика задач подходящий вам часовой пояс, нужно набрать команду:
   ```
   sudo timedatectl set-timezone Europe/Moscow
   ```
   Посмотреть список доступных часовых поясов можно при помощи команды:
   ```
   timedatectl list-timezones
   ``` 

## Основное задание

Задача: Настройте cron для выполнения скрипта, который проверяет наличие новых файлов в директории /path/to/watch каждые 5 минут и перемещает их в директорию /path/to/backup, если они были созданы за последние 5 минут. Также добавьте логирование результатов выполнения скрипта.

##  Материалы

[Настройка планировщика задач cron](https://1cloud.ru/help/linux/kak-nastroit-planirovshchik-cron-na-crontab-linux)

[Применение на практике](https://habr.com/ru/companies/skillfactory/articles/656423/)
