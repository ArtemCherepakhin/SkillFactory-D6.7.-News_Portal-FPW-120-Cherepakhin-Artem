1. Добавлены подписки на рассылки о новых материалах в категориях:
   
-страница должна быть доступна по адресу https://127.0.0.1:8000/news/subscriptions/;
-была создана модель Subscriber для хранения подписок пользователей;
-при публикации новости все подписчики получили сообщение на почту со ссылкой на страницу 
для прочтения новости (использовался для этого сигнал m2m_changed).

2. Реализована отправка списка статей на почту подписчиков категорий каждую неделю на основе той же модели Subscriber:

-подключино приложение django_apscheduler;
-добавлена команда запуска периодических задач;
-настроена периодическая задача отправки списка статей каждую пятницу в 18:00;
-составлено сообщение со ссылками на статьи;
-сообщение содержит только статьи, которые появились с момента предыдущей рассылки.
-При разработке лучше всего использовать вывод отправляемых писем в консоль ('django.core.mail.backends.console.EmailBackend').
