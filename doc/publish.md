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

## 3. Создать релиз

```bash
git tag v1.0.3
git push origin master --tags
```

## 4. Результат

Pipeline автоматически:

- Обновит версию в `package.json`
- Соберёт `.vsix`
- Создаст GitHub Release
- Опубликует в VS Marketplace и Open VSX
