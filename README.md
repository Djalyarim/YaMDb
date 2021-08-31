![Yamdb_final_workflow Actions Status](https://github.com/djalyarim/yamdb_final/workflows/yamdb_final_workflow/badge.svg)](https://github.com/djalyarim/yamdb_final/actions)
# REST API Yamdb
База отзывов пользователей о произведениях.
## Описание
Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен администратором.
Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
В каждой категории есть произведения: книги, фильмы или музыка.
Произведению может быть присвоен жанр (Genre) из списка предустановленных. Новые жанры может создавать только администратор.
Пользователи оставляют к произведениям текстовые отзывы (Review) и ставят произведению оценку в диапазоне от одного до десяти; из пользовательских оценок формируется усреднённая оценка произведения — рейтинг. На одно произведение пользователь может оставить только один отзыв.

## Ресурсы API YaMDb:
* AUTH: аутентификация.
* USERS: пользователи.
* TITLES: произведения, к которым можно написать отзыв.
* CATEGORIES: категории (типы) произведений («Фильмы», «Книги», «Музыка»).
* GENRES: жанры произведений.
* REVIEWS: отзывы на произведения.
* COMMENTS: комментарии к отзывам.

## Технологии
Python 3, Django 3, Django REST Framework, PostgreSQL, Docker, Simple-JWT.

## Запуск проекта
Для работы приложения требуется установка на ваш компьютер Python, PostgreSQL, Docker.

Склонируйте репозиторий на локальную машину:
```shell
git clone https://github.com/Djalyarim/infra_sp2.git
```
Установите и активируйте виртуальное окружение.

Сделайте 2 файла: .env и db_postgres.env (инструкции в файле .env.template).

Запустите docker-compose:
```shell
docker-compose up -d --build   
```
Применените миграции базы данных:
```shell
docker-compose exec web python manage.py makemigrations 
docker-compose exec web python manage.py migrate
```

Обновите статику:
```shell
docker-compose exec web python manage.py collectstatic
```

Создайте суперпользователя:
```shell
docker-compose exec web python manage.py createsuperuser
```
Заполнените базы тестовыми данными:
```shell
docker-compose exec web python manage.py loaddata fixtures.json
```

> Для остановки docker-compose:
```shell
docker-compose down
```
API доступен по адресу http://127.0.0.1/api/v1/.

## Документация
http://localhost/redoc/.

## Автор
Проект разработал Djalyarim.