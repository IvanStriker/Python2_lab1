# Портфолио лабораторных работ

Репозиторий содержит исходники статического сайта-портфолио, созданного с помощью MkDocs и опубликованного через GitHub Pages.

## Сайт

**[https://ivanvinogradov.github.io](https://ivanvinogradov.github.io)**

## Структура репозитория

```
├── source/          # Исходники MkDocs (Markdown + конфигурация)
│   ├── mkdocs.yml   # Конфигурация сайта
│   └── docs/        # Markdown-страницы
├── docs/            # Собранный сайт (публикуется через GitHub Pages)
├── venv/            # Виртуальное окружение Python (не в git)
└── README.md
```

## Тема оформления

Используется тема **[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)**.

**Обоснование выбора:** Material — наиболее популярная и зрелая тема для MkDocs. Она предоставляет современный дизайн в стиле Google Material Design, встроенный поиск, поддержку тёмного режима, адаптивную вёрстку и богатые возможности кастомизации. Для портфолио важна профессиональная подача, которую Material обеспечивает «из коробки».

## Локальный запуск

```bash
# Создать и активировать виртуальное окружение
python3 -m venv venv
source venv/bin/activate

# Установить зависимости
pip install mkdocs mkdocs-material

# Запустить локальный сервер
cd source
mkdocs serve

# Собрать сайт
mkdocs build -d ../docs
```

## Публикация

GitHub Pages настроен на публикацию из папки `/docs` ветки `main`. После выполнения `git push` сайт автоматически обновляется.
