# Публикация расширения

## 1. Получить токены

| Токен          | Где получить                                                                                                                 |
|----------------|------------------------------------------------------------------------------------------------------------------------------|
| **VSCE_PAT**   | [dev.azure.com](https://dev.azure.com/) → User Settings → Personal Access Tokens → New Token (scope: `Marketplace → Manage`) |
| **OVSX_TOKEN** | [open-vsx.org](https://open-vsx.org/) → Account → Access Tokens                                                              |

## 2. Добавить секреты в GitHub

Путь: Settings → Secrets and variables → Actions → New repository secret

- `VSCE_PAT` — токен для VS Marketplace
- `OVSX_TOKEN` — токен для Open VSX

## 3. Запустить workflow

1. Перейти в раздел **Actions** в репозитории GitHub
2. Выбрать workflow **Release**
3. Нажать **Run workflow**
4. Указать версию релиза (например, `1.0.3` или `v1.0.3`)
5. При необходимости настроить опции:
   - Создать GitHub Release (по умолчанию включено)
   - Опубликовать в Open VSX (по умолчанию включено)
   - Опубликовать в VS Marketplace (по умолчанию включено)
6. Нажать **Run workflow**

## 4. Результат

Pipeline автоматически:

- Обновит версию в `package.json`
- Соберёт `.vsix`
- Создаст GitHub Release (если включено)
- Опубликует в VS Marketplace и Open VSX (если включено)
