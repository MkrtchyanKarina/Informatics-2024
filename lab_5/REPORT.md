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
