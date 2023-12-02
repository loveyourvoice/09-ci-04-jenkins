### Задание 1 (Подготовка)

Созданы две ВМ и применен ansible playbook на них.
Выполнена первоначальная настройка, добавлен агент, выключена сборка на мастере.
На агенте пришлось использовать CentOS 8, чтобы плейбук отработал нормально и доработать, чтобы ставилась правильная версия питона и молекула установилась.
Так же был дополнительно прокинут ключ от мастера в агента.
![1](https://i.imgur.com/d1f4uJN.png)


### Задание 2 (Основная часть)

`Сделать Freestyle Job, который будет запускать molecule test из любого вашего репозитория с ролью.`
![2](https://i.imgur.com/WZmxLeB.png)

`Сделать Declarative Pipeline Job, который будет запускать molecule test из любого вашего репозитория с ролью.`
В отличии от фристайла, тут была обязательна авторизация через секрет токен github.
![3](https://i.imgur.com/ejAPhvx.png)

`Перенести Declarative Pipeline в репозиторий в файл Jenkinsfile.`
[08-ansible-05-testing](https://github.com/loveyourvoice/08-ansible-05-testing/blob/master/Jenkinsfile)

`Создать Multibranch Pipeline на запуск Jenkinsfile из репозитория.`
![4](https://i.imgur.com/J4zH67j.png)

`Создать Scripted Pipeline, наполнить его скриптом из pipeline.
Внести необходимые изменения, чтобы Pipeline запускал ansible-playbook без флагов --check --diff, если не установлен параметр при запуске джобы (prod_run = True). По умолчанию параметр имеет значение False и запускает прогон с флагами --check --diff.
Проверить работоспособность, исправить ошибки, исправленный Pipeline вложить в репозиторий в файл ScriptedJenkinsfile`
![5](https://i.imgur.com/Q20AW3K.png)

`Отправить ссылку на репозиторий с ролью и Declarative Pipeline и Scripted Pipeline.`
[Declarative](https://github.com/loveyourvoice/08-ansible-05-testing/blob/master/Jenkinsfile)
[Script](https://github.com/loveyourvoice/09-ci-04-jenkins/blob/master/pipeline/JenkinsfileScripted)