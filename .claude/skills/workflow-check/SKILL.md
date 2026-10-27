---
name: workflow-check
description: Проверка файлов GitHub Actions. Используй, когда пользователь просит проверить workflow из .github/workflows/ перед коммитом.
---

# workflow-check

Для каждого указанного файла проверь:

- есть `permissions:` (у workflow или у каждого задания);
- нет `write-all` и `read-all`;
- права на запись — только у задания, которому они нужны;
- секреты не выводятся в журнал (`echo` с `secrets.` или токеном);
- действия `actions/*` — мажоры курса: checkout v7, setup-node v7, upload-pages-artifact v5, deploy-pages v5.

Ответ: «принято» или «отказ: причина» по каждому файлу. Сам файлы не меняй.
