# create-repo-auto 🚀

CLI-утилита для автоматического создания и синхронизации репозиториев на **GitHub** и **GitLab**.

## 🌟 Возможности:

- 📁 Автоматическое создание репозиториев из текущей папки
- 🚀 Поддержка GitHub и GitLab
- 📄 Автоматическое создание README и .gitignore
- 🔄 Автоматический коммит и пуш изменений каждую минуту через cron

---

## 📥 Установка (.deb)

Скачай последний релиз [отсюда](https://github.com/YOUR_USERNAME/create-repo/releases):

```bash
sudo dpkg -i create-repo-auto_1.2.0.deb
```

При установке автоматически добавится cron-задание для автосинхронизации.

---

## 🚀 Использование:

Перейди в папку с проектом и выполни:

```bash
create-repo
```

Скрипт задаст вопросы:

- Имя репозитория (по умолчанию название папки)
- Выбор платформы: GitHub или GitLab

---

## 🔑 Настройка авторизации

### GitHub

Авторизуйся через GitHub CLI:

```bash
gh auth login
```

### GitLab

- Создай [Personal Access Token](https://gitlab.com/-/profile/personal_access_tokens)
- Добавь его в переменные окружения:

```bash
export GITLAB_TOKEN=твой_токен
```

Добавь эту строку в `.bashrc` или `.zshrc`, чтобы сохранить настройку.

---

## 🕒 Автоматическое обновление

`update-all.sh` запускается каждую минуту и автоматически делает:

- `git add .`
- `git commit`
- `git pull --rebase`
- `git push`

Логи:

```bash
tail -f /tmp/update-all.log
```

---

## 🖥️ Пример работы

```bash
cd ~/my-project
create-repo
```

Вывод:

```
📁 Текущая папка: my-project
🔤 Введите имя репозитория (по умолчанию: my-project):
🌐 Где создать репозиторий? (github/gitlab, по умолчанию: github): gitlab
📡 Создаём репозиторий на GitLab...
✅ Репозиторий создан: git@gitlab.com:your-username/my-project.git
📝 Папка /home/yourname/my-project добавлена в авто-слежение.
```

---

## Author

Andrey Lesnikov  
Senior DevOps & AI Platform Engineer  
https://orcid.org/0009-0004-7583-4314

---

## ⚖️ Лицензия

MIT © justrunme
