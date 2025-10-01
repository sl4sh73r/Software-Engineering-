# Окружение для разработки системы (Developer Environment)

Эта страница содержит подробную информацию о настройке рабочего окружения для разработки в рамках проекта "Программная инженерия".

## Системные требования

### Минимальные требования

- **Операционная система**:
  - Windows 10/11 (64-bit)
  - macOS 11.0 (Big Sur) или новее
  - Linux (Ubuntu 20.04 LTS, Fedora 35+, или эквивалент)

- **Процессор**: Intel Core i3 / AMD Ryzen 3 или лучше
- **Оперативная память**: минимум 4 ГБ (рекомендуется 8 ГБ+)
- **Свободное место на диске**: минимум 5 ГБ
- **Интернет-соединение**: стабильное подключение для работы с GitHub

### Рекомендуемые требования

- **Процессор**: Intel Core i5 / AMD Ryzen 5 или лучше
- **Оперативная память**: 16 ГБ или больше
- **SSD диск**: для быстрой работы с Git и IDE
- **Монитор**: разрешение Full HD (1920x1080) или выше

## Установка обязательного ПО

### 1. Git

#### Windows

Скачайте установщик с официального сайта:
```
https://git-scm.com/download/win
```

При установке рекомендуемые настройки:
- Используйте Git из командной строки и сторонних приложений
- Используйте OpenSSH
- Используйте OpenSSL библиотеку
- Checkout Windows-style, commit Unix-style line endings

Проверка установки:
```bash
git --version
# Должна вывести: git version 2.x.x
```

#### macOS

Установка через Homebrew (рекомендуется):
```bash
# Установите Homebrew, если его нет
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Установите Git
brew install git
```

Или скачайте установщик:
```
https://git-scm.com/download/mac
```

#### Linux

Ubuntu/Debian:
```bash
sudo apt update
sudo apt install git
```

Fedora:
```bash
sudo dnf install git
```

Arch Linux:
```bash
sudo pacman -S git
```

### 2. Редактор кода / IDE

#### Visual Studio Code (рекомендуется)

**Преимущества**: бесплатный, легкий, множество расширений, интеграция с Git

Скачать: https://code.visualstudio.com/

**Рекомендуемые расширения для VS Code**:

1. **Git Graph** - визуализация истории Git
2. **GitLens** - расширенная интеграция с Git
3. **Markdown All in One** - поддержка Markdown
4. **YAML** - поддержка YAML файлов для CI/CD
5. **EditorConfig** - единообразное форматирование
6. **Prettier** - форматирование кода
7. **GitHub Pull Requests and Issues** - работа с GitHub из IDE

Установка расширений:
```bash
code --install-extension mhutchie.git-graph
code --install-extension eamodio.gitlens
code --install-extension yzhang.markdown-all-in-one
code --install-extension redhat.vscode-yaml
code --install-extension editorconfig.editorconfig
code --install-extension esbenp.prettier-vscode
code --install-extension github.vscode-pull-request-github
```

#### Другие IDE

- **JetBrains IDE** (IntelliJ IDEA, PyCharm, WebStorm)
  - Мощные инструменты для разработки
  - Отличная интеграция с Git
  - Платная (есть бесплатные версии для студентов)
  - Скачать: https://www.jetbrains.com/

- **Sublime Text**
  - Быстрый и легкий редактор
  - Скачать: https://www.sublimetext.com/

- **Atom**
  - Открытый исходный код, разработан GitHub
  - Скачать: https://atom.io/

## Настройка Git

### Базовая конфигурация

```bash
# Установите ваше имя
git config --global user.name "Ваше Имя"

# Установите ваш email (используйте тот же, что на GitHub)
git config --global user.email "your.email@example.com"

# Установите основную ветку по умолчанию
git config --global init.defaultBranch main

# Включите автоматическую подсветку вывода
git config --global color.ui auto

# Установите редактор по умолчанию (например, VS Code)
git config --global core.editor "code --wait"
```

### Настройка SSH ключей для GitHub

Использование SSH ключей рекомендуется для безопасной работы с GitHub без ввода пароля.

#### Генерация SSH ключа

```bash
# Генерация нового SSH ключа
ssh-keygen -t ed25519 -C "your.email@example.com"

# Если ваша система не поддерживает ed25519, используйте:
# ssh-keygen -t rsa -b 4096 -C "your.email@example.com"

# Нажмите Enter для сохранения по умолчанию (~/.ssh/id_ed25519)
# Введите passphrase (опционально, но рекомендуется)
```

#### Добавление ключа в ssh-agent

**Linux/macOS**:
```bash
# Запустите ssh-agent в фоне
eval "$(ssh-agent -s)"

# Добавьте ключ
ssh-add ~/.ssh/id_ed25519
```

**Windows** (в Git Bash):
```bash
# Запустите ssh-agent
eval $(ssh-agent -s)

# Добавьте ключ
ssh-add ~/.ssh/id_ed25519
```

#### Добавление SSH ключа в GitHub

1. Скопируйте публичный ключ:
   ```bash
   # Linux/macOS
   cat ~/.ssh/id_ed25519.pub | pbcopy  # macOS
   cat ~/.ssh/id_ed25519.pub | xclip   # Linux
   
   # Windows (Git Bash)
   cat ~/.ssh/id_ed25519.pub | clip
   
   # Или просто выведите и скопируйте вручную
   cat ~/.ssh/id_ed25519.pub
   ```

2. Откройте GitHub → Settings → SSH and GPG keys
3. Нажмите "New SSH key"
4. Вставьте ключ и сохраните

5. Проверьте подключение:
   ```bash
   ssh -T git@github.com
   # Должно вывести: Hi username! You've successfully authenticated...
   ```

## Дополнительные инструменты

### GitHub CLI

Инструмент командной строки для работы с GitHub.

**Установка**:

Windows (через Chocolatey):
```bash
choco install gh
```

macOS:
```bash
brew install gh
```

Linux:
- См. инструкции: https://github.com/cli/cli/blob/trunk/docs/install_linux.md

**Аутентификация**:
```bash
gh auth login
```

### GitHub Desktop

Графический интерфейс для работы с Git и GitHub.

Скачать: https://desktop.github.com/

**Преимущества**:
- Визуальный интерфейс для коммитов и веток
- Простое создание Pull Requests
- Интеграция с GitHub
- Отлично подходит для начинающих

### Дополнительные утилиты

1. **tig** - текстовый интерфейс для Git
   ```bash
   # Linux
   sudo apt install tig
   
   # macOS
   brew install tig
   ```

2. **diff tools** - визуальное сравнение изменений
   - Meld (Linux/Windows)
   - DiffMerge (все платформы)
   - Beyond Compare (платная)

## Настройка рабочего пространства

### Структура локальных директорий

Рекомендуемая организация:

```
~/Projects/
├── Software-Engineering/       # Основной репозиторий
│   ├── .github/
│   ├── docs/
│   ├── Wiki/
│   └── ...
└── Software-Engineering.wiki/  # Wiki репозиторий (опционально)
```

### Клонирование репозиториев

```bash
# Создайте директорию для проектов
mkdir -p ~/Projects
cd ~/Projects

# Клонируйте основной репозиторий
git clone git@github.com:sl4sh73r/Software-Engineering-.git

# Опционально: клонируйте Wiki
git clone git@github.com:sl4sh73r/Software-Engineering-.wiki.git
```

## Проверка окружения

Проверьте, что всё установлено правильно:

```bash
# Проверка Git
git --version

# Проверка GitHub CLI (если установлен)
gh --version

# Проверка SSH подключения к GitHub
ssh -T git@github.com

# Проверка конфигурации Git
git config --list --global
```

## Следующие шаги

После настройки окружения:

1. Вернитесь к странице **[Getting Started](Getting-Started)** для начала работы
2. Изучите **[CONTRIBUTING.md](https://github.com/sl4sh73r/Software-Engineering-/blob/main/CONTRIBUTING.md)** для понимания процесса работы
3. Выберите задачу из **[Issues](https://github.com/sl4sh73r/Software-Engineering-/issues)** и начните работу!

## Troubleshooting

### Проблемы с SSH

Если не работает SSH подключение к GitHub:
```bash
# Проверьте, запущен ли ssh-agent
eval "$(ssh-agent -s)"

# Добавьте ключ заново
ssh-add ~/.ssh/id_ed25519

# Проверьте права доступа к ключам
chmod 600 ~/.ssh/id_ed25519
chmod 644 ~/.ssh/id_ed25519.pub
```

### Проблемы с line endings

Если возникают проблемы с окончаниями строк (особенно на Windows):
```bash
# Настройте автоматическое преобразование
git config --global core.autocrlf true  # Windows
git config --global core.autocrlf input  # Linux/macOS
```

### Проблемы с кодировкой

```bash
# Установите UTF-8 по умолчанию
git config --global core.quotepath false
git config --global i18n.commitencoding utf-8
git config --global i18n.logoutputencoding utf-8
```

## Полезные ресурсы

- [GitHub Skills](https://skills.github.com/) - интерактивные курсы по Git и GitHub
- [Pro Git Book](https://git-scm.com/book/en/v2) - полная книга по Git
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf) - шпаргалка по Git
- [Oh My Git!](https://ohmygit.org/) - игра для изучения Git

---

Окружение настроено? Отлично! Вернитесь к **[Getting Started](Getting-Started)** для продолжения работы.
