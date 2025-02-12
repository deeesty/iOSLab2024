# HW_3/4 

## Animations, Core Data, Network Requests

Разработайте iOS-приложение, которое позволяет пользователям просматривать список фильмов и получать детальную информацию о каждом из них, используя публичный API KudaGo. Приложение должно поддерживать анимации, локальное хранение данных и настройку пользовательских предпочтений.
## Дизайн 
Ориентироваться на дизайн, при отсутствии импровизировать.
https://www.figma.com/community/file/1124835379376527920/movies-app 
## Используемые публичные API
API от KudaGo для получения информации о фильмах:

https://docs.kudago.com/api/

**Список фильмов**  
https://kudago.com/public-api/v1.4/movies/  
Позволяет получить список фильмов с базовой информацией.

**Детальная информация о фильме**  
https://kudago.com/public-api/v1.4/movies/{id}/  
Предоставляет подробную информацию о конкретном фильме.

**Список городов**  
https://kudago.com/public-api/v1.2/locations/?lang=ru  
Предоставляет список доступных городов 

## Функциональные требования: 

1) **Загрузка данных через сеть**:
   * Используйте **URLSession** и **async/await** для загрузки списка фильмов и детальной информации по каждому фильму.
   * Используйте **Codable** для парсинга данных.
   * Реализуйте обработку ошибок и добавьте индикатор загрузки (**UIActivityIndicator**).

  
2) **Отображение данных на главном экране**:
   * Отобразите заголовок "Что вы хотите посмотреть?" по дизайну.
   * Отобразите поисковую строку по дизайну.
   * Отобразите рандомно топ 10 фильмов в виде горизонтальной коллекции по дизайну.
   * Отобразите коллекцию городов (вместо того что в дизайне "Now playing", "Upcoming"...). При выборе города снизу отображается соотвествующие данные для города.
   * Отобразите все полученные фильмы в виде вертикальной коллекции-сетки по 3 в ряд по дизайну.

4) **Отображение данных на детальном экране**:
   * При нажатии на фильм открывается экран с детальной информацией, включающей (сверху вниз по порядку):
     * Кнопка для добавления в избранное(сверху в правом углу) 
     * карусель с изображениями (можно свайпать),
     * рейтинг,
     * постер,
     * заголовок фильма,
     * год выпуска,
     * продолжительность,
     * жанр,
     * описание,
     * актеры(stars),
     * трейлер (открывается в SafariController внутри приложения).
    
5) **Отображение данных на экране "Избранные"**:
   * Содержит в себе список добавленных фильмов в соотвествии с дизайном
  
6) **Поиск**:
   * Осуществляет поиск по названию фильмов, которые были подгружены на главном экране.
   * Если фильм с таким названием существует, то сразу открывает детальный экран.
   * Если фильма нет, то выдает Alert с ошибкой. 
  
7) **Хранение данных локально**:
   * Сохраните только 1-ый запрос на фильмы в Core Data.
   * Используйте NSFetchedResultsController для автоматического обновления интерфейса при изменении данных для экрана избранных.
   * Реализуйте возможность добавление/удаление фильмов из списка избранных через детальный экран.
   * Список избранных всегда сохраняется в Core Data.
  
8) **Анимации**:
   * Используйте UIView.animate и Property Animator для любых анимаций в вашем приложении.
   * Варианты для добавления анимации:
       * при выборе ячейки пропорционально уменьшить ее (эффект нажатия);
       * анимационное открытие фильмов
       * анимация добавления в избранное
       * анимация отображения коллекции фильмов

 ### Общие рекомендации 

 * Пишем чистый код, с полными названиями переменных/методов/классов. 
 * Не коммитим закоменченный код. 
 * При работе с UI используем UIStackView где возможно.
 * Используем модификатор доступа final/private.
 * Спрашиваем если есть вопросы.

