# Домашнее задание к занятию "`GITLAB`" - `Senkov Artem`

### Задание 1

**Что нужно сделать:**

1. Разверните GitLab локально, используя Vagrantfile и инструкцию, описанные в [этом репозитории](https://github.com/netology-code/sdvps-materials/tree/main/gitlab).   
2. Создайте новый проект и пустой репозиторий в нём.
3. Зарегистрируйте gitlab-runner для этого проекта и запустите его в режиме Docker. Раннер можно регистрировать и запускать на той же виртуальной машине, на которой запущен GitLab.

В качестве ответа в репозиторий шаблона с решением добавьте скриншоты с настройками раннера в проекте.
```
```

![screen 1](https://github.com/artem-senkov/8-03-hw/blob/main/img/project1.png)
![screen 2](https://github.com/artem-senkov/8-03-hw/blob/main/img/runner%20installed.png)
![screen 3](https://github.com/artem-senkov/8-03-hw/blob/main/img/runner%20connected.png)

---

### Задание 2

**Что нужно сделать:**

1. Запушьте [репозиторий](https://github.com/netology-code/sdvps-materials/tree/main/gitlab) на GitLab, изменив origin. Это изучалось на занятии по Git.
2. Создайте .gitlab-ci.yml, описав в нём все необходимые, на ваш взгляд, этапы.

В качестве ответа в шаблон с решением добавьте: 
   
 * файл gitlab-ci.yml для своего проекта или вставьте код в соответствующее поле в шаблоне; 
 * скриншоты с успешно собранными сборками.

![screen 1](https://github.com/artem-senkov/8-03-hw/blob/main/img/gitpush.png)
![screen 2](https://github.com/artem-senkov/8-03-hw/blob/main/img/push%20pipeline.png)
![screen 3](https://github.com/artem-senkov/8-03-hw/blob/main/img/jobs%20executing.png)
![screen 4](https://github.com/artem-senkov/8-03-hw/blob/main/img/jobsresult.png)
```yaml
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script:
   - go test .

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
```
---

### Задание 3*

Измените CI так, чтобы:

 - этап сборки запускался сразу, не дожидаясь результатов тестов;
 - тесты запускались только при изменении файлов с расширением *.go.

В качестве ответа добавьте в шаблон с решением файл gitlab-ci.yml своего проекта или вставьте код в соответсвующее поле в шаблоне.
```yaml
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script:
   - go test .
   - echo "This job only runs for branches when go files is changed"
  only:
    changes:
      - '*.go'

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
```
![screen 1](https://github.com/artem-senkov/8-03-hw/blob/main/img/go_filerule.png)
---
