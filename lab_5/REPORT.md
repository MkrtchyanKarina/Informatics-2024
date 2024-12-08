# Отчет по лабораторной работе №5
## Задание №1
1) Создадим репозиторий lab_5 и клонируем его с помощью команды
    ``` git clone <link> ```
   в Git Bash - интерпритатор командной строки bash для раоты с git`ом в Windows
3) Перейдем в папку с репиторием
   ``` cd lab_5 ```
   
5) Проверим наличие папки .git/hooks/ командой ``` ls -la .git/hooks/ ```
   ![Снимок экрана 2024-12-08 142427](https://github.com/user-attachments/assets/25355669-b520-4282-a513-015f882cbfcb)
6) Перейдем в нее и создадим файл pre-commit ``` cd .git/hooks/ && nano pre-commit ```
   ![Снимок экрана 2024-12-08 142713](https://github.com/user-attachments/assets/e30219d6-566e-498e-aef4-43f48b1efc94)
7) Напишем в нем скрипт для проверки файла перед commit`ом
   ![Снимок экрана 2024-12-08 142821](https://github.com/user-attachments/assets/d1a1c81e-2bd6-489f-97f0-fbd336723cc9)
