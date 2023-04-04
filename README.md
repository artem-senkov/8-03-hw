# Домашнее задание к занятию "`GIT`" - `Senkov Artem`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

`Вношу изменения в README.md`
[First commit link](https://github.com/artem-senkov/githomework/commit/f4447682f2c73dbaab0956f3e37c6674ecaffb8a)
```
git clone https://github.com/artem-senkov/githomework
nano README.md
git diff
git diff --staged
git add README.md
git commit -m 'First commit'
git push origin main
```

![screen 1](https://github.com/artem-senkov/8-03-hw/blob/main/img/screenshot20h43m44s_010_.png)
![screen 2](https://github.com/artem-senkov/8-03-hw/blob/main/img/screenshot20h44m00s_011_.png)
![screen 3](https://github.com/artem-senkov/8-03-hw/blob/main/img/screenshot20h44m14s_012_.png)



---

### Задание 2

`Добавил gitignore`
[Ссылка на commit](https://github.com/artem-senkov/githomework/commit/8b9d8dbd716437708bb75a5c43be314a964e34dc)

```
nano .gitignore
git add .gitignore
git commit -m 'gitignore add commit'
git push origin main
```

---

### Задание 3

`Создал ветку dev сделал в ней несколько commitov и произвел слияние с main`

[Network graph link](https://github.com/artem-senkov/githomework/network)
```
git checkout -b dev
nano test.sh
git add test.sh
git commit -m 'dev 1.0  commit'
nano test.sh
git add test.sh
git commit -m 'dev 1.1  commit'
git push origin dev
git checkout main
git merge dev
git push origin main
```
---
## Дополнительные задания (со звездочкой*)

`Сделал ветку conflict, внес изменения в файл, слил ее с main с приоритетом из ветки  conflict`

[Network graph link](https://github.com/artem-senkov/githomework/network)
```
git checkout -b conflict
nano test.sh
git add test.sh
git commit -m 'conflict 1.0  commit'
nano test.sh
git add test.sh
git commit -m 'conflict 1.1  commit'
git push origin conflict
git checkout main
nano test.sh
git commit -m 'main  commit'
git push origin main
git merge conflict
git merge --abort
git merge -Xours conflict 
git commit -m 'main  commit aftermerge'
git push origin main

