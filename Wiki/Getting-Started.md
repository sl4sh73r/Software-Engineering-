# Начало работы (Getting Started)

Добро пожаловать в проект "Программная инженерия"! Эта страница поможет вам начать работу с проектом и настроить всё необходимое для эффективной работы.

## Предварительные требования

Перед началом работы убедитесь, что у вас установлены следующие инструменты:

### Обязательное ПО

1. **Git** (версия 2.30+)
   - Скачать: https://git-scm.com/downloads
   - Проверка установки: `git --version`

2. **Текстовый редактор или IDE**
   - Visual Studio Code (рекомендуется)
   - JetBrains IDE (IntelliJ IDEA, PyCharm, WebStorm)
   - Sublime Text, Atom или другой редактор по выбору

3. **Аккаунт на GitHub**
   - Зарегистрироваться: https://github.com/signup
   - Настроить SSH ключи (рекомендуется)

### Опциональное ПО

- **GitHub Desktop** - графический интерфейс для работы с Git
- **GitHub CLI** (`gh`) - инструмент командной строки для работы с GitHub

## Шаг 1: Клонирование репозитория

### Через HTTPS

```bash
git clone https://github.com/sl4sh73r/Software-Engineering-.git
cd Software-Engineering-
```

### Через SSH (рекомендуется)

```bash
git clone git@github.com:sl4sh73r/Software-Engineering-.git
cd Software-Engineering-
```

## Шаг 2: Изучение структуры проекта

После клонирования ознакомьтесь со структурой проекта:

```bash
# Просмотр структуры
ls -la

# Основные файлы и директории:
# - README.md          # Основная информация о проекте
# - CONTRIBUTING.md    # Руководство по внесению изменений
# - .github/workflows/ # CI/CD конфигурации
# - docs/              # Дополнительная документация
# - Wiki/              # Локальные файлы Wiki
```

## Шаг 3: Настройка Git конфигурации

Настройте свои данные для коммитов:

```bash
# Установите имя пользователя
git config user.name "Ваше Имя"

# Установите email
git config user.email "your.email@example.com"

# Проверьте настройки
git config --list
```

## Шаг 4: Создание рабочей ветки

Для работы над задачами создавайте отдельные ветки:

```bash
# Создайте новую ветку от main
git checkout -b feature/your-feature-name

# Или создайте ветку от develop (если используется git-flow)
git checkout -b feature/your-feature-name develop
```

## Шаг 5: Работа с задачами (Issues)

1. Перейдите во вкладку [Issues](https://github.com/sl4sh73r/Software-Engineering-/issues)
2. Найдите задачу, над которой хотите работать
3. Назначьте её на себя (Assignees)
4. Добавьте комментарий о начале работы

## Шаг 6: Внесение изменений

1. Внесите необходимые изменения в файлы
2. Проверьте статус изменений: `git status`
3. Добавьте изменения: `git add .`
4. Создайте коммит: `git commit -m "feat: описание изменений"`
5. Отправьте изменения: `git push origin your-branch-name`

## Шаг 7: Создание Pull Request

1. Перейдите на страницу репозитория на GitHub
2. Нажмите кнопку **"Compare & pull request"**
3. Заполните описание PR:
   - Опишите внесённые изменения
   - Укажите номер связанного Issue (например, "Closes #123")
   - Добавьте скриншоты, если это применимо
4. Запросите ревью у коллег
5. Дождитесь прохождения CI/CD проверок

## Шаг 8: Code Review и слияние

1. Ответьте на комментарии ревьюеров
2. Внесите необходимые правки
3. После получения одобрения (Approve) PR будет готов к слиянию
4. Мерж выполняет maintainer или вы сами (в зависимости от настроек проекта)

## Полезные команды Git

### Просмотр истории

```bash
# Просмотр логов
git log --oneline --graph --all

# Просмотр изменений
git diff

# Просмотр статуса
git status
```

### Синхронизация с основной веткой

```bash
# Получить последние изменения
git fetch origin

# Обновить текущую ветку
git pull origin main

# Перебазировать вашу ветку (если нужно)
git rebase origin/main
```

### Отмена изменений

```bash
# Отменить изменения в файле
git checkout -- filename

# Отменить последний коммит (сохранив изменения)
git reset --soft HEAD~1

# Отменить добавление в staging
git reset HEAD filename
```

## Следующие шаги

После настройки базового окружения переходите к:

1. **[Настройка окружения для разработки](Developer-Environment)** - детальная настройка инструментов
2. **[CONTRIBUTING.md](https://github.com/sl4sh73r/Software-Engineering-/blob/main/CONTRIBUTING.md)** - правила работы с проектом
3. **[Issues](https://github.com/sl4sh73r/Software-Engineering-/issues)** - текущие задачи проекта

## Получение помощи

Если у вас возникли вопросы:

- Проверьте существующие [Issues](https://github.com/sl4sh73r/Software-Engineering-/issues)
- Создайте новый Issue с меткой "question"
- Обратитесь к преподавателю или координатору курса

## Полезные ресурсы

- [GitHub Docs](https://docs.github.com) - официальная документация GitHub
- [Git Book](https://git-scm.com/book/en/v2) - полное руководство по Git
- [Markdown Guide](https://www.markdownguide.org/) - справочник по Markdown
- [GitHub Actions](https://docs.github.com/en/actions) - документация по CI/CD

---

Готовы начать? Переходите к следующему разделу: **[Developer Environment](Developer-Environment)**
