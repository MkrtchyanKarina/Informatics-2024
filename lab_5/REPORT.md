# Отчет по лабораторной работе №5
## Задание №1
1) Создадим репозиторий lab_5 и клонируем его с помощью команды
   ```
   git clone <link>
   ```
   в Git Bash - интерпритатор командной строки bash для раоты с git`ом в Windows
2) Перейдем в папку с репиторием
   ```
   cd lab_5
   ```
   
3) Проверим наличие папки .git/hooks/ командой ( -a - для отображения скрытых файлов, -l - для отображения подробной информации о каждом файле: права доступа, дата последнего изменения, тип файла )
   ```
   ls -la .git/hooks/
   ```
   ![Снимок экрана 2024-12-08 142427](https://github.com/user-attachments/assets/25355669-b520-4282-a513-015f882cbfcb)
4) Перейдем в нее и создадим файл pre-commit
   ```
   cd .git/hooks/ && nano pre-commit
   ```
   ![Снимок экрана 2024-12-08 142713](https://github.com/user-attachments/assets/e30219d6-566e-498e-aef4-43f48b1efc94)
5) Напишем в нем скрипт для проверки файла перед commit`ом
   ![Снимок экрана 2024-12-08 142821](https://github.com/user-attachments/assets/d1a1c81e-2bd6-489f-97f0-fbd336723cc9)

6)  Сделаем файл исполняемым
   ```
   chmod +x pre-commit
   ```
   ![Снимок экрана 2024-12-08 142914](https://github.com/user-attachments/assets/0fd1b614-fab2-470c-842b-6632e799538b)

7) Вернемся в папку репозитория и создадим новый текстовый файл
   ```
   nano task_11.txt
   ```
   ![Снимок экрана 2024-12-08 143124](https://github.com/user-attachments/assets/04807714-bbea-4b71-997f-846e99773db8)
8) Сохраним файл и попробуем сделать commit
   ```
   git add task_11.txt
   git commit -m "Добавлен верифицированный текстовый файл"
   git push origin master
   ```
   ![Снимок экрана 2024-12-08 143559](https://github.com/user-attachments/assets/e5cd94ae-141b-441a-97e6-c9e5e38101b7)

   Получаем сообщение о том, что файл прошел проверку, и в нем есть слово "Автор"

9) Проверим репозиторий на сайте
    ![Снимок экрана 2024-12-08 143622](https://github.com/user-attachments/assets/2752ef74-1049-4f46-a050-45cd2b1c6706)
   
    ![Снимок экрана 2024-12-08 143632](https://github.com/user-attachments/assets/bfe505e7-3477-4b1d-86b5-f0a30c7aec2c)

    Как видим, файл загружен, все прошло успешно

11) Попробуем создать "плохой" файл и повторим те же команды
    ```
    nano task_12.txt
    git add task_12.txt
    git commit -m "Попытаемся добавить неверифицированный файл"
    ```
    ![Снимок экрана 2024-12-08 143738](https://github.com/user-attachments/assets/3872307e-f0fb-4bc3-97d0-032d3a7ddc71)
    
    ![Снимок экрана 2024-12-08 143914](https://github.com/user-attachments/assets/785108e6-8486-4435-9270-65adc40d7f6f)
    
    Получаем сообщение о том, что слова "Автор" нет в файле -> мы не можем внести изменения в локальный репозиторий (commit), а также отправить их на сайт (push)
    
    ![Снимок экрана 2024-12-08 143930](https://github.com/user-attachments/assets/170a41f7-3045-45cc-968b-7edd89fef90b)
    
    Как видим, ничего не изменилось после выполнения этих команд
12) Чтобы убрать файл из раздела проиндексированных файлов (тех, которые будут закоммичены) отменим предыдущее действие, а также проверим состояние рабочего каалога и статус файлов
    ```
    git reset HEAD task_12.txt
    git status
    ```
    ![Снимок экрана 2024-12-08 144435](https://github.com/user-attachments/assets/bfbfab5c-cd90-4cf8-a3c1-6d9e1c2b3a31)

## Задание №2
1) Проверим, что Git Flow установлен
   
   ![Снимок экрана 2024-12-08 144220](https://github.com/user-attachments/assets/739fcbdd-cd86-4b62-9a12-5f945f68e24b)

2) Инициализируем Git Flow и оставим название веток по-умолчанию
   
   ![Снимок экрана 2024-12-08 144715](https://github.com/user-attachments/assets/8adf1ad1-4b37-4314-97a4-49c9a277e4f2)

3)  Создадим ветку для нового функционала
   ```
   git flow feature start task-management
   ```
4) Создадим новый файл Python-файл и откроем его
   ```
   nano task_manager.py
   ```
   Напишем в файле такой скрипт:

   ![image](https://github.com/user-attachments/assets/4b3bf2e4-e00d-4b29-90b4-1a99a4102f7a)
   

6) Закоммитим это файл с помощью команд
   ```
   git add task_manager.py
   git commit --no-verify -m "Добавлен функционал управления задачами"
   ```
   
   ![image](https://github.com/user-attachments/assets/71fa39ac-8f7c-4124-9dcf-cc6dd0117e3f)

   --no-verify необходимо для того, чтобы отключить проверку файлов из предыдущего задания
   
8) Внесем изменения в файл - добавим вывод описания задачи

   ![image](https://github.com/user-attachments/assets/2d60ca5e-10b0-4bb6-99d1-68c232a27508)

9) Закоммитим файл с изменениями:
    
    ![image](https://github.com/user-attachments/assets/8c715ce1-e845-4d15-a5c4-99bbd27fb47a)

10) Так как мы закончили разработку, то удаляем ветку и переключаемся в ветку develop с помощью команды:
    ```
    git flow feature finish task-management
    ```
    ![image](https://github.com/user-attachments/assets/3eaff158-741f-4d22-bf0e-b75810d7e702)

11) Создадим релиз при помощи команд:
    ```
    git flow release start v1.0.0
    echo "v1.0.0" > version.txt
    git add version.txt
    git commit -m "Обновлена версия для релиза v1.0.0"
    git flow release finish v1.0.0
    ```


   ![image](https://github.com/user-attachments/assets/002ebd6c-1715-4705-b544-cf3051c9f7d3)

   ![image](https://github.com/user-attachments/assets/2fddb6ca-908d-4f27-a3e6-f43cdbeb353b)


12) Создадим ветку для срочного исправления ошибки:
    
    ![image](https://github.com/user-attachments/assets/5b1d9f41-c5bd-45dd-9348-9d8e2d67a6ea)
    

14) "Исправим" файл task_manager.py
    
    ![image](https://github.com/user-attachments/assets/74c8ceed-9dc8-405a-a8e4-afa90bd74685)
    

16) Внесем изменения в локальный репозиторий:
    
    ![image](https://github.com/user-attachments/assets/d57c852a-6aad-4b9d-9c4e-2f5ef45117fa)
    

18) Выгрузим изменения в ветку develop
    
    ![image](https://github.com/user-attachments/assets/767bd5c2-2001-4a69-90d5-965d0bc76fd7)
    

20) Выгрузим изменения в ветку master
    
    ![image](https://github.com/user-attachments/assets/9c0ad867-49bd-41b6-96b5-4fe9b06d3219)

