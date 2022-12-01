# TestProject
Пример работы с github.

## Заметки по работе с git/github

### Разовая первичная настройка

Указать username и email, которые будут использоваться по умолчанию для указания информации об авторе изменений
`git config --global user.name 'your name'`
`git config --global user.email "your@mail"`

### Создать/получить репозиторий

Создать локально
1. Создать директорию для нового репозирория и перейти в неё(для linux можно использовать `mkdir` и `cd`)
2. Выполнить инициализацию репозитория `git init`

Создать и получить с github
1. Авторизоваться на github
2. Находясь на главной странице или в списке собственных репозиториев нажать "New"
3. Следовать инструкции создания репозитория
	1. установить необходимые параметры для видимости репозитория и наличия предсозданных файлов (readme/license)
4. Находясь внутри созданного репозитория скопировать ссылку для клонирования находящуюся за кнопкой "Code"
5. Открыть терминал, перейти в директорию для хранения проектов/репозиториев
6. Выполнить `git clone {ссылка, скопированна из П.4}`

Для получения имеющегося на Github репозитория проследовать П.4 и далее.

### Опциональные действия после клонирования репозитория:

1. `git init`
2. Задать для репозитория собственные имя и email
	* Необходимо делать, если для данного репозитория необходимо работать от пользователя, отличного от умолчания.
	* `git config user.name 'your name'`
	* `git config user.email "your@mail"`
3. Настроить общение с github через [ssh ключ](https://htmlacademy.ru/blog/git/git-console) или [access token](https://linuxpip.org/git-error-fatal-authentication-failed/)
	* Для использования отдельного ssh ключа для каждого репозитория можно [указать его явно](https://stackoverflow.com/questions/4565700/how-to-specify-the-private-ssh-key-to-use-when-executing-shell-command-on-git) в опциях git выполнив `git config core.sshCommand 'ssh -i private_key_file'`

### Работа с репозиторием

1. Непосредственно изменение файлов
	* Не требует каких либо действий в git
2. Добавление файла к репозиторию `git add {file}`
	* Необходимо для начала отслеживания изменений в файле.
	* Выполняется каждый раз как файл был добавлен/изменён/удалён
	* Можно указать как путь к файлу или нескольким файлам, так и "`.`" знак точки вместо файла для добавления всех изменённых файлов
4. Закрепление изменения в репозитории `git commit -m "some commentary"`
	* Необходимо вместо "some commentary" описывать актуальные изменения для наглядности
	* Можно не указывать `-m "some commentary"`, тогда git запустит вешний редактор для запроса комментария у пользователя.
5. Просмотр изменеий в отслеживаемых файлах `git diff`
	* Покажит изменения выполненные в файлах относительно пооследнего commit
	* Можно указать конкретный файл, если таких несколько
6. Отправление изменений на внешний сервер `git push`
	* Можно опустить, если репозиторий сущеструет только на локальном ПК
7. Лог действий `git log`
	* Выведет историю `commit` действий с указанием времени и автора
	* Можно добавить ключ `-c`, что также покажет изменения в файлах
8. Текущий статус репозитория `git status`
	* Покажет наличие и состояние файлов в репозитории исходя из их статуса "отслеживается"/"новый"/"удалён"
	* Также сообщит о наличии неотправленных `commit`, если таковые есть и репозиторий находится на внешнем сервере

## Возможные примеры работы комманд и вопросы

> push не работает с ошибкой на фото
> ![[images/push_auth_error.png]]

Не настроена аутентификация. Необходимо использовать стороннее ПО вроде Visual studio или рассмотреть настройку авторизации исходя П.3 описанного в "Опциональные действия после клонирования репозитория"

---

