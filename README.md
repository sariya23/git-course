# Данный репозиторий создан для треннировки работы с Git и консолью bash

## Базовые команды в консоли

1. ```pwd``` - комада возвращает путь к папке, где мы находимся.
2. ```cd path```(change directory) - сменить рабочую директорию на ту, что указана после пробела.
3. ```~``` - обозначение домашней директории. Пример: ```$ cd ~``` - команда вернет нас в домашнюю директорию.
4. ```ls -a```(list directory) - выведет содержимое текущей директории. Если добавить флаг -a,
то выведутся скрыте файлы и папки.
5. ```touch file-name``` - создаст файл в текущей директории.
6. ```mkdir -p dir-name``` - создаст директорию в текущей директории. Создаст папку в текущей директории. С помощью флага -p можно создать целую структуру. Пример:```$ mkdir -p dir1/dir-inside/dir-deeper-inside``` - создали папку dir-deeper-inside в папке dir-inside, которая находится в папке dir1.
7. ```cp что_копируем куда_копируем``` - копирует файл в указоное место. Пример: ```$ index.html src/``` - скопирует файл ```index.html``` в директорию ```src```. Можно указать несколько файлов через пробел.
8. ```mv что_перемещаем куда_перемещаем``` - перемещает файл из одного места в другое. Пример: ```$ mv table.csv ./very-important-files``` - переместит файл ```table.csv``` из текущей директории в директорию ```very-important-files```.
9. ```cat file-name``` - прочитает файл и выведет содержимое.
10. ```rm file_name``` - удалит указанный файл.
11. ```rmdir dir-name``` - удалит указанную папку, если она пуста.
12. ```rm -r dir-name``` - удалит указанную папку со всем содержимым. Флаг ```-r``` значит, что все удаляется рекурсивно.

## Фишки с консолью

### Автозаполнение команд
Можно начать набирать команду и нажать дважды ```Tab```. Он дописывате не только команды, но и пути. Езе один пример использования: если написать команду ```$ cd ~/``` и нажать дважды ```Tab``` можно увидить список, куда мы можем переместиться.

### Несколько команд сразу
Команды в терминале необязательно вбивать и выполнять по очереди. Их можно указывать не по одной, а сразу списком. Для этого их нужно разделить двумя амперсандами (&&).
```
$ mkdir second-project && cd second-project && touch index.html style.css
# создаём папку second-project,
# переходим в папку second-project
# и создаём в ней два файла: index.html и style.css
```

## Установка и настройка Git

### Установка Git
Для усановки Git в linux Ubuntu используется следующая команда: ```$ apt-get install git```.
Чтобы проверить, что Git установился, нужно ввести следующую команду: ```$ git --version```.

### Настройка Git
Конфиг Git'a лежит в файле ```.gitconfig```. Он находится в домашней директории. Чтобы укзать глабаольное имя пользователя нужно ввести слудующую команду: ```$ git config --global user.name "name"```. Чтобы указать почту, нужно ввести слудующую команду: ``` $ git config --global user.email username@yandex.ru```. Чтобы вывести значение конфига, нужно ввести следующую команду: ```$ git config --list```

## Начало работы с Git

### Инициализация репозитория
```git init``` - инициализирует репозиторий(папку, в которой находимся)

### Синхронизация локального и удалённого репозиториев
```git remote add origin <URL>``` - привяжет локальный репозиторий к удаленному
```git remote -v``` - проверит, что репозитории связались
```git push -u origin master``` - запушит все коммиты в удаленный репозиторий в первый раз
```git push origin master``` - запушит все коммиту в удаленный репозиторий

### Подготовка файлов к коммиту
```git add <file name>``` начнет отслеживать изменения в файле
```git add --all``` - начнет отслеживать изменения во всех файлах
```git add .``` - начнет отслеживать изменения в файлах в текузей папке

### Создание коммита
```git commit -m "<message>"``` - создаст коммит с сообщением

### Просмотр информации о коммитах
```git log``` - выведет подробную историю коммитов
```git log --oneline``` - выведет историю коммитов в краткой форме(хэш и сообщение)

### Просмотри состояния файлов
```git status``` - выведет текущее состояние репозитория

### Добавление изменений в полсдений коммит
```git commit --amend --no-edit``` - добавить изменения к последнему коммиту, а сообщение оставит прежним
```git commit --amend -m"<message>"``` - изменит сообщение к последнему коммиту

### Откат файлов и коммитов
```git restore --staged <file name>``` - переведет файл в состояния staged обртано в untracked или modified
```git restore <file name>``` - вернет файл к последней версии, которая была сохранена через ```git commit``` или ``git add```
```git reset --hard <hash>``` - удалит все незакомиченные изменения до указанного коммита

### Просмотр изменений 
```git diff``` - покажет изменения в modified файлах
```git diff <hash1> <hash2>``` - покажет разницу между 2-мя коммитами
```git diff --staged``` - покажет изменения в staged файлах

 	
