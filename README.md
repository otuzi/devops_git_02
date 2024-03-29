------

## Задание 1. Знакомимся с GitLab и Bitbucket 

Из-за сложности доступа к Bitbucket в работе достаточно использовать два репозитория: GitHub и GitLab.

Иногда при работе с Git-репозиториями надо настроить свой локальный репозиторий так, чтобы можно было 
отправлять и принимать изменения из нескольких удалённых репозиториев. 

Это может понадобиться при работе над проектом с открытым исходным кодом, если автор проекта не даёт права на запись в основной репозиторий.

Также некоторые распределённые команды используют такой принцип работы, когда каждый разработчик имеет свой репозиторий, а в основной репозиторий пушатся только конечные результаты 
работы над задачами. 

### GitLab

Создадим аккаунт в GitLab, если у вас его ещё нет:

1. GitLab. Для [регистрации](https://gitlab.com/users/sign_up)  можно использовать аккаунт Google, GitHub и другие. 
2. После регистрации или авторизации в GitLab создайте новый проект, нажав на ссылку `Create a projet`. 
Желательно назвать также, как и в GitHub — `devops-netology` и `visibility level`, выбрать `Public`.
3. Галочку `Initialize repository with a README` лучше не ставить, чтобы не пришлось разрешать конфликты.
4. Если вы зарегистрировались при помощи аккаунта в другой системе и не указали пароль, то увидите сообщение:
`You won't be able to pull or push project code via HTTPS until you set a password on your account`. 
Тогда перейдите [по ссылке](https://gitlab.com/profile/password/edit) из этого сообщения и задайте пароль. 
Если вы уже умеете пользоваться SSH-ключами, то воспользуйтесь этой возможностью (подробнее про SSH мы поговорим в следующем учебном блоке).
5. Перейдите на страницу созданного вами репозитория, URL будет примерно такой:
https://gitlab.com/YOUR_LOGIN/devops-netology. Изучите предлагаемые варианты для начала работы в репозитории в секции
`Command line instructions`. 
6. Запомните вывод команды `git remote -v`.
   
   <img width="506" alt="Screenshot 2024-02-11 at 09 33 45" src="https://github.com/otuzi/devops_git_02/assets/61628386/896312c6-afea-4a5e-972a-bb583b1a4a5c">

8. Из-за того, что это будет наш дополнительный репозиторий, ни один вариант из перечисленных в инструкции (на странице 
вновь созданного репозитория) нам не подходит. Поэтому добавляем этот репозиторий, как дополнительный `remote`, к созданному
репозиторию в рамках предыдущего домашнего задания:
`git remote add gitlab https://gitlab.com/YOUR_LOGIN/devops-netology.git`.
9. Отправьте изменения в новый удалённый репозиторий `git push -u gitlab main`.
10. Обратите внимание, как изменился результат работы команды `git remote -v`.
   <img width="656" alt="Screenshot 2024-02-11 at 09 53 11" src="https://github.com/otuzi/devops_git_02/assets/61628386/480a7d1a-70a6-482e-bcb1-f6721d31611e">


#### Как изменить видимость репозитория в  GitLab — сделать его публичным 

* На верхней панели выберите «Меню» -> «Проекты» и найдите свой проект.
* На левой боковой панели выберите «Настройки» -> «Основные».
* Разверните раздел «Видимость» -> «Функции проекта» -> «Разрешения».
* Измените видимость проекта на Public.
* Нажмите «Сохранить изменения».

  <img width="1456" alt="Screenshot 2024-02-11 at 09 57 15" src="https://github.com/otuzi/devops_git_02/assets/61628386/9055304f-1b4a-4f2d-b6e6-ef9614d4e30b">


## Задание 2. Теги

Представьте ситуацию, когда в коде была обнаружена ошибка — надо вернуться на предыдущую версию кода,
исправить её и выложить исправленный код в продакшн. Мы никуда не будем выкладывать код, но пометим некоторые коммиты тегами и создадим от них ветки. 

1. Создайте легковестный тег `v0.0` на HEAD-коммите и запуште его во все три добавленных на предыдущем этапе `upstream`.
2. Аналогично создайте аннотированный тег `v0.1`.

   <img width="723" alt="Screenshot 2024-02-11 at 10 10 02" src="https://github.com/otuzi/devops_git_02/assets/61628386/d1e563d0-31da-43a3-93ff-d4685e812008">

   <img width="671" alt="Screenshot 2024-02-11 at 10 10 12" src="https://github.com/otuzi/devops_git_02/assets/61628386/81e9336c-026b-4db1-bc56-6cafb9eeb78f">

   <img width="986" alt="Screenshot 2024-02-11 at 10 10 55" src="https://github.com/otuzi/devops_git_02/assets/61628386/493c1d4d-4556-4402-8429-ee0b3650e818">

   <img width="590" alt="Screenshot 2024-02-11 at 10 13 59" src="https://github.com/otuzi/devops_git_02/assets/61628386/7f52ffd9-6f05-481c-9ffd-e523a7d3b489">


3. Перейдите на страницу просмотра тегов в GitHab (и в других репозиториях) и посмотрите, чем отличаются созданные теги. 
    * в GitHub — https://github.com/YOUR_ACCOUNT/devops-netology/releases;
    * в GitLab — https://gitlab.com/YOUR_ACCOUNT/devops-netology/-/tags;

<img width="1339" alt="Screenshot 2024-02-11 at 10 14 15" src="https://github.com/otuzi/devops_git_02/assets/61628386/294fe99a-3d3d-428d-8177-146c0012c43c">

<img width="1387" alt="Screenshot 2024-02-11 at 10 14 47" src="https://github.com/otuzi/devops_git_02/assets/61628386/de62894d-ec9a-4b4c-808c-2eaf288aa666">

## Задание 3. Ветки 

Давайте посмотрим, как будет выглядеть история коммитов при создании веток. 

1. Переключитесь обратно на ветку `main`, которая должна быть связана с веткой `main` репозитория на `github`.
2. Посмотрите лог коммитов и найдите хеш коммита с названием `Prepare to delete and move`, который был создан в пределах предыдущего домашнего задания. 
3. Выполните `git checkout` по хешу найденного коммита. 
4. Создайте новую ветку `fix`, базируясь на этом коммите `git switch -c fix`.
5. Отправьте новую ветку в репозиторий на GitHub `git push -u origin fix`.
6. Посмотрите, как визуально выглядит ваша схема коммитов: https://github.com/YOUR_ACCOUNT/devops-netology/network.

   <img width="943" alt="Screenshot 2024-02-11 at 10 40 59" src="https://github.com/otuzi/devops_git_02/assets/61628386/f3868338-e932-4d59-8ff5-1d8ae951ec0f">
   
   <img width="1393" alt="Screenshot 2024-02-11 at 10 41 28" src="https://github.com/otuzi/devops_git_02/assets/61628386/72f7e978-1f18-43c4-9fe9-449487648748">


8. Теперь измените содержание файла `README.md`, добавив новую строчку.
9. Отправьте изменения в репозиторий и посмотрите, как изменится схема на странице https://github.com/YOUR_ACCOUNT/devops-netology/network 
и как изменится вывод команды `git log`.

<img width="1368" alt="Screenshot 2024-02-11 at 10 44 23" src="https://github.com/otuzi/devops_git_02/assets/61628386/2d6f79df-db07-4bcc-ae3b-e10607ef3c72">

<img width="703" alt="Screenshot 2024-02-11 at 10 44 45" src="https://github.com/otuzi/devops_git_02/assets/61628386/8949c1b4-3c9c-439b-a465-57eaad79d809">




## Задание 4. Упрощаем себе жизнь

Попробуем поработь с Git при помощи визуального редактора. 

1. В используемой IDE PyCharm откройте визуальный редактор работы с Git, находящийся в меню View -> Tool Windows -> Git.
2. Измените какой-нибудь файл, и он сразу появится на вкладке `Local Changes`, отсюда можно выполнить коммит, нажав на кнопку внизу этого диалога. 
3. Элементы управления для работы с Git будут выглядеть примерно так:

  <img width="1368" alt="Screenshot 2024-02-11 at 11 02 25" src="https://github.com/otuzi/devops_git_02/assets/61628386/7500fb84-545b-4030-ad6d-a0c4c120ac9d">

 
----
