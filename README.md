# Тестовое задание для системного инженера

Результаты выполнения тестового задания необходимо опубликовать на GitHub/любой другой открытой платформе.

Тестовое задание состоит из трех задач:

## 1. Подготовка Dockerfile

Необходимо подготовить [Dockerfile](https://docs.docker.com/engine/reference/builder/) для сборки python приложения, 
хранящегося в директории `src/`

В репозитории присутствует файл `requirements.txt`, содержащий в себе зависимости python для запуска приложения, в Dockerfile необходимо добавить шаг для установки данных зависимостей.

## 2. Подготовка docker-compose

   Необходимо подготовить [docker-compose.yml](https://docs.docker.com/compose/compose-file/compose-file-v3/) файл для запуска собранного приложения.

   docker-compose.yml должен содержать следующие директивы:
1. [ ]    [build](https://docs.docker.com/compose/compose-file/compose-file-v3/#build) 
2. [ ]    [ports](https://docs.docker.com/compose/compose-file/compose-file-v3/#ports) (python-приложение слушает по порту 8080)
3. [ ]    [environment](https://docs.docker.com/compose/compose-file/compose-file-v3/#environment). По-умолчанию приложение имеет переменную `HelloMessage='Hello world!'`, необходимо при запуске приложения указать значение данной переменной равным `Hello iac!`

## 3. Ansible
Необходимо настроить сервер с помощью ansible для запуска приложения с помощью ранее написанного docker-compose.

   [ansible-playbook](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_intro.html) должен иметь следующие функции:
- Установка docker, docker-compose
- Передача Dockerfile, docker-compose.yml и исходников приложения на сервер
- Запуск приложения с помощью утилиты docker-compose


Для выполнения данного пункта можно использовать сторонние роли.
Все используемые роли следует указать в файле [requirements.yml](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html#installing-multiple-roles-from-a-file).

## 4. Проверка задания

После запуска приложения, оно будет слушать по указанному в `docker-compose.yml` файле порту.
При выполнении `curl $server_ip:$app_port` приложение должно отдавать указанную в переменной окружения `HelloMessage` строку

В результате ожидаем ссылку на git-репозиторий, хранящий в себе как минимум:
* Исходники приложения.
* Dockerfile.
* docker-compose файл.
* Структура скриптов ansible (playbooks).
* Указание в README используемого дистрибутива Linux.
* Поэтапная инструкция для запуска скриптов.
