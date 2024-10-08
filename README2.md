# Инструкция по работе с Git на macOS

## Установка Git
1. Проверка установки Git:
   ```bash
   git --version
   ```
   Если Git не установлен, используйте команду для установки:
   ```bash
   xcode-select --install
   ```

## Настройка Git
1. Установить имя пользователя для коммитов:
   ```bash
   git config --global user.name "Ваше Имя"
   ```

2. Установить email для коммитов:
   ```bash
   git config --global user.email "ваш_email@example.com"
   ```

3. Проверить текущие настройки Git:
   ```bash
   git config --list
   ```

## Основные команды Git

### Инициализация репозитория
1. Инициализировать новый локальный репозиторий:
   ```bash
   git init
   ```

2. Клонировать удалённый репозиторий:
   ```bash
   git clone https://github.com/имя_пользователя/имя_репозитория.git
   ```

### Работа с изменениями
1. Добавить файл в зону индексации (staging area):
   ```bash
   git add <имя_файла>
   ```

2. Добавить все файлы:
   ```bash
   git add .
   ```

3. Сделать коммит с сообщением:
   ```bash
   git commit -m "Сообщение коммита"
   ```

### Проверка статуса и истории
1. Проверить статус репозитория:
   ```bash
   git status
   ```

2. Просмотреть историю коммитов:
   ```bash
   git log
   ```

## Работа с удалённым репозиторием

### Добавление удалённого репозитория
1. Добавить удалённый репозиторий:
   ```bash
   git remote add origin https://github.com/имя_пользователя/имя_репозитория.git
   ```

2. Проверить, что удалённый репозиторий добавлен:
   ```bash
   git remote -v
   ```

### Отправка изменений в удалённый репозиторий
1. Отправить изменения в ветку `main`:
   ```bash
   git push origin main
   ```

2. Если ветка не была создана, выполните команду:
   ```bash
   git push -u origin main
   ```

### Получение изменений из удалённого репозитория
1. Получить изменения с удалённого репозитория:
   ```bash
   git pull origin main
   ```

## Ветвление

### Создание и управление ветками
1. Создать новую ветку:
   ```bash
   git branch имя_ветки
   ```

2. Переключиться на новую ветку:
   ```bash
   git checkout имя_ветки
   ```

3. Создать и сразу переключиться на новую ветку:
   ```bash
   git checkout -b имя_ветки
   ```

### Слияние веток
1. Выполнить слияние одной ветки с другой:
   ```bash
   git merge имя_ветки
   ```

## Игнорирование файлов
1. Создать файл `.gitignore` в корне проекта и добавить в него файлы или директории, которые нужно игнорировать:
   ```bash
   *.log
   node_modules/
   ```


## C August 13, 2021. Запрещено использование логина и пароля для работы с github

Создайте персональный токен доступа (PAT):

Перейдите на GitHub и авторизуйтесь.

Зайдите в Настройки (Settings).

В меню слева выберите Настройки разработчика (Developer Settings).

Далее выберите Персональные токены доступа (Personal Access Tokens).

Нажмите на кнопку Сгенерировать новый токен (Generate new token).

Укажите права для токена (например, выберите repo для доступа к репозиториям).

Сгенерируйте токен и скопируйте его.

Настройте удалённый репозиторий с использованием токена: Теперь нужно выполнить push, используя этот токен.

В терминале выполните команду push, указав ваш репозиторий:

   ```bash
   git push https://github.com/username/repo.git
   ```

Когда появится запрос на ввод имени пользователя и пароля:

Введите ваше имя пользователя GitHub.

В качестве пароля введите созданный персональный токен доступа (PAT).

Сохранение токена для последующих команд: Чтобы не вводить токен каждый раз при git push или git pull, вы можете сохранить его с помощью следующей команды:

```bash
git config --global credential.helper store
```
После этого Git запомнит ваш токен и будет использовать его автоматически при следующих аутентификациях.

## Полезные команды

1. Отмена изменений в файле до индексации (staging):
   ```bash
   git checkout -- имя_файла
   ```

2. Отмена последнего коммита (с сохранением изменений):
   ```bash
   git reset --soft HEAD~
   ```

3. Удаление файла из индексации, не удаляя его из рабочей директории:
   ```bash
   git reset имя_файла
   ```

4. Сравнение изменений с предыдущим коммитом:
   ```bash
   git diff
   ```