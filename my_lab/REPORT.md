1) Создайте скрипт backup_new_files.bash с содержимым:
   ```
   #!/bin/bash
   find /home/<user>/watch -type f -mmin -5 -exec mv {} /home/<user>/backup \; >> /home/<user>/backup.log 2>&1
   ```
   - Поиск файлов:
     - Команда find /path/to/watch -type f -mmin -5 ищет все файлы (-type f) в указанной директории /home/<user>/watch, которые были изменены за последние 5 минут (-mmin -5).
   - Перемещение файлов:
     - Для каждого найденного файла выполняется команда mv {}. Здесь {} представляет собой найденный файл. Команда mv перемещает этот файл в директорию /home/<user>/backup.
   - Логирование:
     - часть >> /home/<user>/backup.log добавляет вывод команды (включая возможные сообщения об ошибках) в файл журнала /home/<user>/backup.log. 
   - Перенаправление ошибок:
     - 2>&1 означает, что стандартный поток ошибок (файловый дескриптор 2) перенаправляется в стандартный поток вывода (файловый дескриптор 1). Это позволяет объединить вывод ошибок и стандартный вывод в одном месте.
       
2) Сделаем скрипт исполняемым:
   ```
   chmod +x backup_new_files.bash
   ```
3) Создадим новые директории:
   ```
   mkdir watch && mkdir backup
   ```
4) Добавим выполнение задачи каждые 5 минут в файл crontab:
   ```
   */5 * * * * /home/<user>/backup_new_files.bash
   ```
   ![image](https://github.com/user-attachments/assets/50cbb908-0fd9-471a-bc66-1be9f338722b)
5) Создадим файл с логами:
   ```
   touch backup.log
   ```
6) Перейдем в папку watch/ и создадим в ней новый файл:
   ```
   cd watch && touch ex.txt
   ```
7) Как видим, все работает успешно. Файл ex.txt был перемещен в 18:30 🕡 из папки watch/ в папку backup/:
   
   ![image](https://github.com/user-attachments/assets/9f32aa81-fabe-4366-ace1-f9c649d61dfe)
   
   ![image](https://github.com/user-attachments/assets/1c0205ab-727f-447a-ba17-a9b950c797d6)


8) Проверим файл с логами:
   