# Простенький чат-бот для чистки чатов
Данный чат бот выполняют функцию или тотальной очистки чата в VK, или делает проверку на членство в группе, и если
пользователь не состоит в группе, то он будет удален из чата.

## Как это запустить
Во-первых, активируем виртуальное окружение:
```bash
$ source venv/bin/activate
```

Во-вторых, устанавливаем все зависимости:
```bash
$ pip install -r requirements.txt
```

Обязательно нужно настроить переменные окружения.

Делается это так. Создаете в дериктории проекта файл .env, в котором прописываете следующие данные без < >:
```
CONFIRMATION_TOKEN=<Строка, которую должен вернуть сервер, находится в настройках API группы>

OPEN_GROUP_TOKEN=<токен открытой группы>
CLOSED_GROUP_TOKEN=<токен закрытой группы, или группы, где делается проверка на членство>

SERVICE_TOKEN=<токен вашего приложения, нужен, чтобы грабать общедоступную инфу по пользователю>

ADMIN_ID=<ваш id, ведь вы будее запускать команды бота>
GROUP_ID=<id группы, в которой нужно делать проверки на членство>
```
Дальше вам необходимо будет провести ряд настроек уже в самом VK.
Детально процесс описан в документации [по вот этой ссылке](https://dev.vk.com/api/bots/getting-started#%D0%A1%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D1%81%D1%82%D0%B2%D0%BE).

Данный бот работает через Callback API.

Все, что осталось сделать, это запустить бота.

Выполняем команду:
```bash
$ uvicorn main:app --host HOST --port PORT --reload
```

В HOST прописываете необходимый хост, ну а в PORT(внезапно) прописываете порт.

Все!