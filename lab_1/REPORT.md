Отчёт по лабораторной работе №1: 

1) Устанавливаем виртуальную машину (VirtualBox) и Ubuntu (дистрибутив Linux из семейства Debian)
2) Создаем в VirtualBox новую виртуальную машину, название - Ubuntu, образ ISO - путь к файлу-установщику операционной системы
   ![Снимок экрана 2024-09-13 222320](https://github.com/user-attachments/assets/da5535c5-0a6d-4801-9176-ed8d03001035)
3) Настраиваем виртуальную машину следующим образом: видеопамять - 128мб, оперативная память - более 5000мб и память, которая будет выделяться на жестком диске - 50гб.
   ![Снимок экрана 2024-09-13 221553](https://github.com/user-attachments/assets/3553e736-4586-480f-82ea-a114fc3ad8c1)
4) После скачивания всех пакетов перезапускаем виртуальную машину
   Перед нами открывается окно для ввода имени пользователя и пароля, после входа мы видим рабочий стол.
   ![image](https://github.com/user-attachments/assets/a9178d0f-362e-4bf0-a461-31974bf12302)

5) Нам нужно зайти в меню с программами и поиском и найти терминал
6) Открываем терминал и вводим 2 команды: touch - для создания файла, а gedit - для открытия файла
   ![image](https://github.com/user-attachments/assets/a35d1f47-2923-48b6-b96f-b77f7bee66f9)
7) Записываем текст в файл для вывода в терминал
   ![image](https://github.com/user-attachments/assets/401fb285-2cde-4581-ad5e-6d48620def0b)
8) Сохраняем файл и запускаем его через терминал ( команда - bash ). Получаем вывод:
    ![-2147483648_-210331](https://github.com/user-attachments/assets/73c78eca-46de-401e-b1db-660d6ce18162)
9) Снова откроем файл и немного изменим его, заменив все слова, кроме "Welcome" на $*. С помощью это символа мы считаем и выведем в терминал всю информацию, которую передал пользователь ( эту информацию и будем считать полным именем пользователя ).
    ![image](https://github.com/user-attachments/assets/469b1ec6-f9bd-46a6-a4e2-528059df07f4)
10) Запускаем файл и вводим полное имя
    ![image](https://github.com/user-attachments/assets/311e9fec-4092-4e44-bcf5-2b8f22cb3000)
11) Любуемся нашим приветствием и идем пить кофе :)
   ![image](https://github.com/user-attachments/assets/6b2c6b0b-6709-427f-9878-e593e2af46d0)
