# CLAUDE.md

Главные правила — в `AGENTS.md`, они действуют полностью. Здесь только то, чего
там нет или что отличается для Claude Code.

@AGENTS.md

## Где что искать

- Требования MVP: `docs/requirements/product-baseline.md`.
- Требования второй очереди (Learning Studio): `docs/requirements/learning-studio-baseline.md`.
- Этапы PH-00…PH-11 и модули MOD-01…MOD-15: `docs/development-plan.md`.
- Регламент (спецификация модуля, тесты, промпты, Git): `docs/development-rules.md`.
- Решения: `docs/architecture/decisions/`, новые ADR — в формате MADR.
- Состояние: `docs/project-status.md`, других документов состояния не заводить.

## Особенности работы Claude

- Ветки `claude/<краткое-имя>`.
- Remote: `galaersh-ai/ask_and_study_box`, публичный. У `aigalaersh` есть push,
  но нет admin. `main` не защищена, поэтому запрет прямой записи держится
  только на дисциплине. PR создавать через `gh`, свой PR не сливать.
- Оболочка — Git Bash, а команды проверок в `AGENTS.md` написаны для PowerShell.
  В bash `$env:UV_CACHE_DIR = ".uv-cache"` заменяется на
  `export UV_CACHE_DIR=.uv-cache`, а `$tracked` — на `$(git ls-files)`.
- Упоминания диалога Codex и концепции v0.3 — внешний контекст. Его в репозитории
  нет, для работы достаточно действующих требований.

## Вторая очередь в работе над MVP

Кода Learning Studio в MVP нет, но обязательства ADR-010 по контрактам ядра
действуют с PH-00: снимок знаний как публичный контракт, события его изменения,
роли автора и ученика, задания для любых модулей. Проектируя эти
контракты, сверяться с таблицей обязательств в ADR-010.
