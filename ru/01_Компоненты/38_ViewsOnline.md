## Сниппет ViewsOnline

[![](https://file.modx.pro/files/8/f/b/8fbfa1707d51a469803adaad32ef40d1s.jpg)](https://file.modx.pro/files/8/f/b/8fbfa1707d51a469803adaad32ef40d1.jpg)

Cниппет выводит статистику пользователей онлайн для любой страницы сайта и работает на базе таблицы просмотров от Tickets.
Может использоваться например для форума в виде:
> Читают тему 17 пользователей: гостей 15, пользователей 2 (user1, user5)

Для работы скрипту нужны:

1. установленный **pdoTools**
2. включённый **Fenom** в настройках pdoTools
3. установленный **Tickets**
4. разрешён в настройках Tickets **подсчёт просмотров гостей**

Эти дополнения бесплатны и на их базе работает сниппет **ViewsOnline**.

## Параметры сниппета

* **tpl** — чанк для вывода информации, активно используются возможности Fenom. Плейсхолдеры чанка: **total**, **guests**, **users** и **userlist**.
* **tplUserlist** — чанк для вывода списка пользователей, принимает 2 плейсхолдера: **separator** и **user**.
* **tplUserlistOuter** - чанк для обёртки списка пользователей, принимает плейсхолдер: **wrapper**.</li>
* **separator** — разделитель для списка пользователей.
* **pid** — id страницы для вывода статистики. По умолчанию текущая.
* **parents** - id разделов через запятую для подсчёта значений всех страниц, исключает параметр **pid**
* **min** — количество минут, в течении которых пользователь считается онлайн. По умолчанию: 15

Все параметры есть у сниппета и их можно увидеть перетаскиванием сниппета на поле с кодом.

## Примеры

Вызываем сниппет некэшируемым на нужной нам странице:

```{'!ViewsOnline'|snippet}```

Пример вызова статистики для какой-то другой страницы:

```php
{'!ViewsOnline'|snippet: [
    'pid' => 1,
]}
```

Пример вызова статистики для всего раздела, например **форума** на сайте:

```php
{'!ViewsOnline'|snippet: [
    'parents' => 10,
]}
```

Пример вызова статистики для двух разделов, например раздела **Вакансии (35)** и раздела **Резюме (48)**, если нужно объединить их в группу **Работа**:

```php
{'!ViewsOnline'|snippet: [
    'parents' => '35,48',
]}
```

* [Статья в сообществе =>][0]
* [Демо-сайт =>][1]
* [Скачать транспортный пакет =>][2]
* [Пакет в ModStore.pro =>][3]

[0]: https://modx.pro/solutions/9778-output-users-online-for-a-specific-page/
[1]: https://demo.bazstudio.com
[2]: https://demo.bazstudio.com/assets/files/viewsonline-1.0.1-beta1.transport.zip
[3]: https://modstore.pro/packages/users/viewsonline
