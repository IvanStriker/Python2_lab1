# Лабораторная работа 1

**Тема:** Создание и развертывание статического сайта на базе MkDocs с публикацией на GitHub Pages

## Цель работы

- Освоить процесс создания статического сайта с использованием генератора документации MkDocs.
- Научиться организовывать структуру документации проекта (портфолио лабораторных работ).
- Изучить базовые принципы работы с системой контроля версий Git и платформой GitHub.
- Развернуть статический сайт с использованием механизма GitHub Pages на домене вида `username.github.io`.
- Освоить базовую настройку темы оформления и конфигурационного файла `mkdocs.yml`.

## Задание

### Основная часть

1. Создать публичный репозиторий на GitHub для размещения сайта-портфолио.
2. Настроить GitHub Pages с публикацией из каталога `/docs` ветки `main`.
3. Клонировать репозиторий на локальный компьютер.
4. Создать и активировать виртуальное окружение Python, установить MkDocs.
5. Настроить `.gitignore`.
6. Создать новый сайт командой `mkdocs new source`.
7. Запустить локальный сервер и убедиться в корректности сборки.
8. Собрать сайт в каталог `/docs` и опубликовать.

### Самостоятельная часть

1. Подключить тему оформления **Material for MkDocs**.
2. Настроить `mkdocs.yml`: название сайта, тема, навигация через `nav`.
3. Создать структуру страниц: главная, «Об авторе», раздел «Лабораторные работы» с отдельной страницей для каждой работы.
4. Обеспечить корректную навигацию по сайту.
5. Выполнить повторную сборку и публикацию.

## Ход выполнения

### 1. Создание репозитория и настройка GitHub Pages

Создан публичный репозиторий `ivanvinogradov.github.io` на GitHub.
В настройках репозитория (Settings → Pages) указан источник публикации:
ветка `main`, каталог `/docs`.

### 2. Локальная настройка проекта

```bash
# Клонирование репозитория
git clone https://github.com/ivanvinogradov/ivanvinogradov.github.io.git
cd ivanvinogradov.github.io

# Создание и активация виртуального окружения
python3 -m venv venv
source venv/bin/activate

# Установка MkDocs и темы
pip install mkdocs mkdocs-material
```

### 3. Создание структуры сайта

```bash
# Создание нового сайта в каталоге source
mkdocs new source
cd source
```

Структура каталога `source/docs/` после создания страниц:

```
source/
├── mkdocs.yml
└── docs/
    ├── index.md          # Главная страница
    ├── about.md          # Страница «Об авторе»
    └── labs/
        ├── index.md      # Обзор лабораторных работ
        ├── lab1.md       # Отчёт по лаб. работе 1
        ├── lab2.md       # Отчёт по лаб. работе 2
        ├── lab3.md       # Отчёт по лаб. работе 3
        ├── lab4.md       # Отчёт по лаб. работе 4
        └── lab5.md       # Отчёт по лаб. работе 5
```

### 4. Настройка mkdocs.yml

```yaml
site_name: Портфолио лабораторных работ
site_url: https://ivanvinogradov.github.io/
site_author: Иван Виноградов
site_description: Портфолио лабораторных работ по курсу Python

theme:
  name: material
  language: ru
  palette:
    - scheme: slate
      primary: teal
      accent: cyan
      toggle:
        icon: material/brightness-4
        name: Переключить на светлую тему
    - scheme: default
      primary: teal
      accent: cyan
      toggle:
        icon: material/brightness-7
        name: Переключить на тёмную тему
  features:
    - navigation.tabs
    - navigation.sections
    - navigation.top
    - search.highlight
    - content.code.copy

nav:
  - Главная: index.md
  - Об авторе: about.md
  - Лабораторные работы:
    - Обзор: labs/index.md
    - Лабораторная работа 1: labs/lab1.md
    - Лабораторная работа 2: labs/lab2.md
    - Лабораторная работа 3: labs/lab3.md
    - Лабораторная работа 4: labs/lab4.md
    - Лабораторная работа 5: labs/lab5.md
```

### 5. Локальное тестирование и сборка

```bash
# Запуск локального сервера для предпросмотра
cd source
mkdocs serve
# Сайт доступен по адресу http://127.0.0.1:8000/

# Сборка в каталог /docs корня репозитория
mkdocs build -d ../docs
```

### 6. Публикация

```bash
git add source/ docs/
git commit -m "Add MkDocs site: source files and built docs"
git push origin main
```

После отправки изменений сайт автоматически обновился по адресу
[https://ivanvinogradov.github.io](https://ivanvinogradov.github.io).

## Выводы

В ходе выполнения лабораторной работы был создан и опубликован статический сайт-портфолио с использованием MkDocs и GitHub Pages.

Были освоены:

- принцип работы генератора статических сайтов MkDocs и его конфигурирование через `mkdocs.yml`;
- организация иерархической структуры документации из Markdown-файлов;
- настройка темы оформления Material for MkDocs с поддержкой тёмного/светлого режима и встроенной навигацией;
- базовый рабочий процесс Git: клонирование, коммиты, отправка изменений на GitHub;
- публикация статического сайта через GitHub Pages без использования серверной части.

Результат: сайт доступен по адресу [https://ivanvinogradov.github.io](https://ivanvinogradov.github.io).
