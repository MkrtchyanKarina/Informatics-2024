# Лабораторная работа: "Планировщик задач CRON"
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
   echo date >> /home/<user>/time.log
   ```
   ![Снимок экрана 2024-12-22 164757](https://github.com/user-attachments/assets/a629345c-95e9-450b-bbc5-e08c9df625c0)

3) Сделаем файл исполняемым:
   ```
   chmod +x log_time.bash
   ```
4) Откроем файл crontab
   crontab -e
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
Вместо 5-ти * можем оставить одну:
```
* /home/<user>/time.log
```
## Основное задание