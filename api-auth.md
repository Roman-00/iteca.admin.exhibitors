### Апи по страницам
___

#### url запросов

```
/api/auth
```

Будет офигенно если у нас все запросы будут начинать с https://onsite.iteca.kz/api/auth

т.е /api

#### Страница входа

```
Я отправляю POST || GET (метод на твое усмотрение) запрос c данными в виде:
{
    email: ---,
    password: ---( в нашем случаее это код участника )
    lang: ru || en
}
```

```
Что я должен получить в ответ:
{
    token: Токен Авторизации для того чтобы разлогинивать пользователья( когда токен протух должен возвращать стату 401 unautorize )
    В токен обычно вшивается информация о пользователе, (name, email и так далее),
    Если токен не делаем тогда возвращаешь
    user: Тут инфо о пользователь (ps. Лучше если это будет токен);
    isParticipated: true || false,
    В случаее если пользователь участвовал в выставках дополнительно возвращаем список выставок в которых он учасьвовал
    exhibition: Тут возвращаем список выставок в которых он участвовал
    upcoming: Тут возвращаешь список выставок которые должны быить максисум штук 5 || 10
}
```

#### Страница забыли пароль

```
Я отправляю данные в виде POST || GET запрос:
{
    email: Емаил пользователя ты у себя проверяешь если есть такой ты мне просто даешь знать
    lang: ru || en
}

В следующем шаге я отправляю:
{
    email: Email Пользователя,
    password: Новый пароль пользователя
    lang: ru || en
}

После успешной смены ты мне просто отдаешь
{
    message: 'Пароль успешно изменен' (нужно учесть если будт с 2 языков отправляться)
    lang: ru || en
}
```
