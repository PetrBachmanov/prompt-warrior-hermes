# Prompt Warrior (Hermes Edition) — AGENTS.md

## Концепция проекта

Проект **Prompt Warrior (Hermes Edition)** — это адаптированная версия оригинального инструмента prompt-warrior для работы с логами Hermes Agent. Инструмент читает локальную SQLite базу данных (`state.db`) и превращает логи сессий в RPG-лист персонажа с метриками, титулами, ачивками и рекомендациями.

## Структура проекта

```
prompt-warrior-hermes/
├── scripts/
│   ├── analyze.py      # Анализатор логов (Hermes SQLite)
│   ├── avatar.py       # Генератор аватара (robohash)
│   ├── render.py       # Рендерер HTML-карточки
│   └── icons.py        # Генератор SVG-икон
├── references/         # Справочные материалы
│   ├── scale.md        # Формулы и пороги
│   ├── rpg.md          # Звания, ачивки
│   ├── recommendations.md  # Рекомендации
│   ├── sources.md      # База источников
│   ├── widget.md       # Спецификация карточки
│   └── harnesses.md    # Поддержка разных харнессов
├── assets/             # Изображения и иконки
├── docs/               # Документация
└── LICENSE             # MIT
```

## Технологии и стек

- **Язык:** Python 3 (stdlib только)
- **База данных:** SQLite (Hermes Agent `state.db`)
- **Генерация аватара:** `robohash` (опционально, локально)
- **Формат карточки:** HTML/CSS (автономный файл)
- **Генерация контента:** LLM (Hermes Agent)

## Ключевые функции

1. **Анализ логов** — чтение `state.db`, подсчёт метрик
2. **Генерация аватара** — детерминированный монстр из титула
3. **Написание хроники** — 2-4 абзаца в гримуарном стиле
4. **Рендеринг карточки** — HTML с визуализацией метрик
5. **Рекомендации** — на основе доказательной базы

## Выполненные работы

### 4 июля 2026

- ✅ Адаптирован инструмент `prompt-warrior` под Hermes Agent
- ✅ Написан коннектор к SQLite базе данных `state.db`
- ✅ Интегрирован источник `hermes` в `scripts/analyze.py`
- ✅ Обновлены `README.md`, `README_RU.md`, `SKILL.md`
- ✅ Обновлены все справочные материалы
- ✅ Инициализирован Git-репозиторий
- ✅ Force-push в `PetrBachmanov/prompt-warrior-hermes`
- ✅ Создан локальный навык `prompt-warrior` в Hermes
- ✅ Протестирован полный цикл работы скилла

### 11 июля 2026

- ✅ Обновлена документация: все упоминания Claude Code заменены на Hermes Agent
- ✅ Исправлен флаг `--source hermes-agent` → `--source hermes`
- ✅ Обновлены словари переводов в `render.py`
- ✅ Обновлён `SKILL.md` с актуальными инструкциями
- ✅ Завершён force-push изменений в GitHub

## Известные проблемы и решения

### Проблема: Avatar generation fails (robohash not in correct venv)
**Решение:** Установить `robohash` в окружение Hermes Agent:
```bash
"C:\Users\pbach\AppData\Local\hermes\hermes-agent\venv\Scripts\python.exe" -m pip install robohash
```

### Проблема: Opening HTML in browser on Windows (MSYS/Git Bash)
**Решение:** Использовать `cmd.exe /c start "" "path/to/file.html"` вместо `start`.

### Проблема: Git push rejected
**Решение:** Выполнить `git pull origin main` перед push.

## Статус проекта

- **Активен:** Да
- **Версия:** 1.5 (SCALE)
- **GitHub:** https://github.com/PetrBachmanov/prompt-warrior-hermes
- **Локальный навык:** `prompt-warrior` (devops)
- **Последнее обновление:** 11 июля 2026

## Дальнейшие планы

- [ ] Добавить поддержку других харнессов (OpenCode, Codex, Copilot)
- [ ] Оптимизировать рендеринг для мобильных устройств
- [ ] Добавить экспорт карточки в PDF
- [ ] Создать веб-интерфейс для просмотра карточек

---

*AGENTS.md создан автоматически. Последнее обновление: 11 июля 2026.*
