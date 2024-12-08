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
   
3) Проверим наличие папки .git/hooks/ командой
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

2) Инициализируем Git Flow и оставим название папок по-умолчанию
   ![Снимок экрана 2024-12-08 144715](https://github.com/user-attachments/assets/8adf1ad1-4b37-4314-97a4-49c9a277e4f2)

    



