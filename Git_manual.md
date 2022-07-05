
# Термини и определения

**Git** - Программа контроля версий (сохраняет не файл целиком, а разницу версий программы)

Принципы:

* сохранять разные версии и не только
* перемещение между ними

 _**Visual Studio Code**_ - Рекомендованная программа для даботы с Git

 **Репозиторий** - папка с настройкой контроля версий

**commit** - фиксация изменений

 # Полезные ссылки
 
 + Ссылка для скачивания [Visual Studio Code](https://code.visualstudio.com/)  
 + Ссылка для скачивания [Git](https://git-scm.com/) 
 + Ссылка на документацию [Git Book](https://git-scm.com/book/ru/v2)
 + Ссылка на гайд [Markdown](https://paulradzkov.com/2014/markdown_cheatsheet/)
 + Еще одна ссылка на [Markdown](http://ilfire.ru/kompyutery/shpargalka-po-sintaksisu-markdown-markdaun-so-vsemi-samymi-populyarnymi-tegami/?upm_export=print#link5)
 + Ссылка на интерактивный тренажер по Git [Тренажер Git](https://learngitbranching.js.org/?locale=ru_RU)


# Начало работы

## _Проверка версии_

Перед началом работу проверить установку Git на ПК выполнив комманду: `git --version`

## _Педставление в Git_
### Глобальное:

+ **git config --global user.name** "Name" - имя английскими буквами

+ **git config --global user.email** "email" - ваша_почта@example.com

### Локальное:

+ **git config user.email** "you@example.com"

+ **git config user.name** "Your Name"

+ **git config user.password** "your password"

**git config --list** - чтобы проверить текущее имя пользователя и адрес электронной почты в вашем локальном репо

## _Создание репозитория_

Последовательнойть действий:

1. Создать новую папку
2. Создать новый файл (например расширение _.md_ - Markdown)
3. Подключить папку к системе контроля весий коммандой: `git init`
4. Создать  `.gitignore` - для помещения туда файлов который можно игнорировать (например: картинки)
5. Выполнить команду `git add` <file.txt>
6. Выполнить комманду `git add .gitignore`
7. Сделать коммит: `git commit -m` "Text commit" 
8. Сделать коммит: `git commit -m` "Добавлен файл .gitignore"

# Основные команды

## Команды Git 

**git init** - инициализация репозитория

**git status** - показать текущий статус проекта

**git add** - добавление файлов в ветку
+ **git add .** - Для добавления всех файлов 

**git commit** -m "message" - сделать коммит с сообщением "message" 

+ -am - add и commit одной строкой

**git log** - получить историю коммитов в репозитории

+ **git log --graph** - отображение веток коммитов в виде "дерева"

**git checkout** - для перемещения между коммитами, версиями отдельных файлов и ветками (можно выбрать какое изменения загрузить - достаточно 4х символов из commit)

+ **git checkout master (main)** - вернуться в самое актуальное состояние 
+ **git checkout** <branch_name> - переход на ветку branch_name
+ **git checkout** -b <branch_name> - создать новую ветку и сразу на нее перейти

**git diff** - разница между текущем состоянием и что уже сделано

**git branch** - получить список всех имеющихся веток и показывает на текущий HEAD

+ **git branch** branch_name - создание ветки branch_name 
+ **git branch -d** branch_name - удаление ветки branch_name 

**git merge** branch - слить ветку с текущей (куда указывает HEAD) веткой

**git clone** - создании копии на локальном репозитории

**git push** - используется для выгрузки содержимого локального репозитория в удаленный репозиторий. Она позволяет передать коммиты из локального репозитория в удаленный

**git fetch** - получить информацию об изменениях в удаленном репозитории

**git pull** - используется для извлечения и загрузки содержимого из удаленного репозитория и немедленного обновления локального репозитория этим содержимым

## Shell команды терминала 

**q** - выйти из режима отображения

**clear** - очистить окно репозитория

**cd** - смена директории 

+ **cd..** - перход в родительскую папку

# Слияние веток

Работы с ветками начинается:

+  `git init` и `git status` - убедиться в создании репозитория
+ Повторить комманды `git add`, `git log`, `git status`

Чтобы слить любую ветку с текущей, вызываем команду 
`git merge` <имя ветки для слияния с текущей>

# Удаленный репозиторий GitHub

## Скачивание из удаленного репозитория в локальный

1. Выполнить регистрацию на GitHub (при необходимости)
2. Содать новую папки на локальном компютере (локальный репозиторий)
3. На GitHub вабрать нужный репозиторий - кнопка `Code`
4. Скопировать ссылку HTTPS
5. В VSC открыть созданный папку (см. п.2)
6. Выполнить команду `git status`
7. Выполнить команду `git clone` <ссылка из GitHub>
8. Выполнить команду `cd` для перехода в директорию скаченного репозитория

**ВАЖНО**: Рекомендуется, в локальном репозитории, создать отдельную branch и работать в ней.

## Загрузка на удаленный репозиторий

1. В аккаунте GitHub, в правом верхнем углу выбрать <+>
2. Далее _New repository_
3. Ввести имя репозитория и нажать `Create repository`
4. Выбрать один из вариантов предлагаемых GitHub
    + создать новый резозиторий через терминал
    + существующий локальный привязать к удаленному
    + импортировать код из другого репозитория
5. Последовательно выполнить команды, указанные на GitHub, в локальном репозитории
6. Отправить (команда `git push`) локальный репозиторий в удаленный (GitHub), при это возможно нужно будет авторизоваться на удаленном репозитории
7. Чтобы выкачать актуальное состояние из удаленного репозитория - выполнить `git pull` (также команда выполнит merge веток)

## Выполнение pull request

1. Делаем `Fork` интересующего нас аккаунта
2. Делаем `git clone` для нашей версии этого репозитория

**ВАЖНО:** команду `git clone` делаем в пустой папке (не в репозитории)

3. Выполнить команду `cd` для перехода в папку с репозиторием

4. Мы создаем ветку с предлагаемыми изменениями
5. Производим все изменения только в этой ветке
6. Отправляем эти изменения на свой аккаунт (`git push`)
7. В окне на Github появляется возможность выполнения `pull request`





