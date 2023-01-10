git push - Это отправка данных на сервер, в удаленный репозиторий, на github. Данные - это коммиты и ветки.

git pull - Это скачивание данных с сервера. Похоже на клонирование репозитория, но с той разницей, что скачиваются не все коммиты, а только новые.

### Зачем пушить на сервер

-   для работы в команде, чтобы делиться своим кодом с коллегами
-   чтобы иметь резервную копию на случай потери данных на своей машине

### master и origin/master

Это ветки: локальная и удаленная (на сервере, в github). По умолчанию мы находимся в ветке master. Подробно работу с ветками мы рассмотрим в следующем уроке, а пока достаточно запомнить, что master - это то, что на нашей машине, а origin/master - в удаленном репозитории, на github.



### Вы сделали новый коммит, пытаетесь запушить его, а git в ответ выдает такое (git push rejected)

    $ git push origin master
    To git@github.com:Webdevkin/site-git.git
     ! [rejected]        master -> master (fetch first)
    error: failed to push some refs to 'git@github.com:Webdevkin/site-git.git'
    hint: Updates were rejected because the remote contains work that you do
    hint: not have locally. This is usually caused by another repository pushing
    hint: to the same ref. You may want to first integrate the remote changes
    hint: (e.g., 'git pull ...') before pushing again.
    hint: See the 'Note about fast-forwards' in 'git push --help' for details.

# Важно

Git устроен так, что локально мы можем коммитить сколько угодно. Но прежде чем отправить свои коммиты на сервер, то есть запушить, нужно подтянуть новые коммиты с сервера. Те самые, которые успели сделать наши коллеги. То есть сделать git pull.

Когда мы делаем git push, git сначала проверяет, а нет ли на сервере новых коммитов. Если они есть, то git выдает то самое сообщение - git push rejected. Значит, нам нужно сначала сделать git pull, а затем снова запушить


In my case, the error was just `fatal: refusing to merge unrelated histories` on every try, especially the first pull request after remotely adding a Git repository.

Using the `--allow-unrelated-histories` flag worked with a pull request in this way:

```
git pull origin branchname --allow-unrelated-histories
```