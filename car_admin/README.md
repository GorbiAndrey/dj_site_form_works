# Админка сайта обзора автомобилей

## Задание

Каждому динамическому сайту пользователи просят сделать админку.
Удобно редактировать модели, добавлять новые с помощью графического интерфейса.
Это позволяет не залезать в базу данных и не писать вручную sql-запросы.
Действия с объектами всегда одинаковые: создать, изменить, удалить.

Одна из сильных сторон Django - админка из коробки.
Её можно легко кастомизировать, просто отнаследовавшись от стандартной формы.

Есть две модели в БД: автомобиль (марка, модель), обзорная статья (автомобиль, заголовок статьи, текст обзора).
Нужно сделать админку:

1) С выводом в таблицу списка объектов.
2) Добавить поиск по названиям и заголовкам и фильтры по основным полям.
3) Для модели автомобиля добавить кастомное поля, в котором выводить количество статей про данный автомобиль.
4) Русифицировать отображение название моделей в админке (`car` -> `машина`).
5) Поменять порядок вывода объектов в списке (например от элемента с большим id к элементу с меньшим).
Тогда новые записи будут наверху.

![](./docs/admin_car.png)

![](./docs/admin_review.png)

## Реализация

В качестве виджета для редактирования текста в админке стоит CKEditor.
Для его установки требуется установить пакет для python `django-ckeditor`.
Затем требуется загрузить нужные js и прочие файлы командой:
```
python manage.py collectstatic
```

Для задания готов небольшой список данных для тестов.
Их можно загрузить коммандой: 
```
python manage.py loaddata app.json
```
