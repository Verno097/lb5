ОТЧЕТ ПО ЛАБОРАТОРНОЙ РАБОТЕ 5

<img width="1010" height="656" alt="Снимок экрана 2026-05-18 в 17 08 20" src="https://github.com/user-attachments/assets/dafb3ec6-f223-435c-82c3-221a3b59fa88" />

 Создаёт SSH-ключ типа ed25519 для привязки к GitHub (email: davenindex@gmail.com). Однако при вводе пути сохранения ключа происходит ошибка: в поле Enter file in which to save the key случайно вводится команда eval "$(ssh-agent -s)". В результате ключ сохраняется в файл с именем eval "$(ssh-agent -s)", что некорректно. Также видно, что ssh-agent не был запущен перед генерацией.

  <img width="1010" height="656" alt="Снимок экрана 2026-05-18 в 17 10 58" src="https://github.com/user-attachments/assets/5d9a808c-f73a-4497-bb95-f6579f1c0b03" />

Удалил ошибочно созданные файлы eval* командой rm -f eval*. Затем повторно генерирует SSH-ключ, на этот раз корректно принимая стандартный путь ~/.ssh/id_ed25519. Ключ перезаписывается (ответ y), задаётся passphrase. Генерация проходит успешно, что подтверждается выводом fingerprint и randomart image.

<img width="1010" height="656" alt="Снимок экрана 2026-05-18 в 17 12 19" src="https://github.com/user-attachments/assets/ab4937a9-31c0-43d9-b5f2-636364af0042" />

Запущен ssh-agent командой eval "$(ssh-agent -s)" (PID 4881). Затем ключ добавляется в агента через ssh-add ~/.ssh/id_ed25519. Пользователь вводит passphrase, и система сообщает об успешном добавлении идентификатора. После этого содержимое публичного ключа копируется в буфер обмена командой pbcopy < ~/.ssh/id_ed25519.pub — это стандартный шаг перед добавлением ключа в аккаунт GitHub.

<img width="1582" height="969" alt="Снимок экрана 2026-05-18 в 17 29 50" src="https://github.com/user-attachments/assets/87fdc2d7-a34d-4c13-9b1d-76ba6bd25ad0" />

Скриншот настроек Xcode-проекта Objectproject. Указаны поддерживаемые платформы (macOS), минимальная версия развёртывания — macOS 15.6. Раздел "Frameworks and Libraries" пуст. Судя по всему, это начальная конфигурация проекта для Objective-C.

<img width="3164" height="1938" alt="image" src="https://github.com/user-attachments/assets/34fd2495-ce02-42f6-b842-9bb4209010a0" />

Код на Objective-C в файле main.m. Создаётся объект класса Rectangular, задаются свойства lengthRectangular = 10 и widthRectangular = 5. Выводятся длина, ширина, площадь (square) и периметр (perimeter). Результат выполнения программы:

Length: 10.00
Width: 5.00
Square: 50.00
Perimeter: 30.00
Программа завершена с кодом 0. Это первый рабочий прототип для расчёта прямоугольника.

<img width="1582" height="969" alt="Снимок экрана 2026-05-18 в 17 38 25" src="https://github.com/user-attachments/assets/7b6180f6-a46d-41dc-9de5-66350df21369" />

В проект добавлен новый класс Trapezoid. В main.m подключены оба заголовочных файла: rectangular.h и trapezoid.h. Для трапеции задаются основания a = 10, b = 6 и высота height = 4. Вычисляются площадь (32.00) и периметр (24.00). Вывод программы дополнен этими значениями. Расширение функциональности проекта.

<img width="1512" height="969" alt="Снимок экрана 2026-05-18 в 17 49 36" src="https://github.com/user-attachments/assets/0ea74012-7e34-4276-bf65-2b48677c3b85" />

Пример кода на Swift (вероятно, отдельное задание или часть lab5task2). Создан словарь Country (страна — столица), который выводится в цикле for-in. Затем объявлен массив Age = [21, 19, 20], к нему добавляется элемент 24. Вывод массива: [21, 19, 20, 24]. Программа отрабатывает без ошибок. Это демонстрация работы с коллекциями в Swift.

<img width="1578" height="962" alt="Снимок экрана 2026-05-18 в 17 49 40" src="https://github.com/user-attachments/assets/31cf0892-fb09-48bd-82b1-a1dd402ffaa3" />

Терминальная сессия, в которой пользователь перестраивает структуру Git-репозитория. Выполняются команды:

cd ~/Desktop/lab5/lab5task1/Objproject — переход в папку проекта.
Перемещение содержимого вложенной папки Objproject на уровень выше.
Удаление пустой папки Objproject.
Добавление изменений в Git (git addИсправление ошибки с вложенным репозиторием. Git предупреждал, что SwiftProject является отдельным репозиторием (внутренний .git). Пользователь удаляет .git внутри SwiftProject командой rm -rf, затем выполняет git rm --cached -r, чтобы убрать некорректную ссылку. После этого все файлы добавляются заново, делается коммит "fix swift project structure" и пуш. В результате Swift-проект включён в основной репозиторий как обычные файлы, а не как submodule. ., git commit -m "fix xcode structure").
Пуш в ветку feature2.
Затем создаётся папка lab5task2 для следующего задания.

<img width="1578" height="962" alt="Снимок экрана 2026-05-18 в 17 52 34" src="https://github.com/user-attachments/assets/dc6ba76e-799f-48ef-94a9-12bec5996ca7" />

