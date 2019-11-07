# Кинопоиск

Создай базовую маршрутизацию для приложения поиска и хранения фильмов, используя
[themoviedb.org API](https://www.themoviedb.org/).

## themoviedb.org

Для работы с API необходимо зарегистриваться (можно ввести произвольные данные)
и получить API-ключ. В этой работе будут использоваться следующие ендпоинты.

- [https://developers.themoviedb.org/3/trending/get-trending](https://developers.themoviedb.org/3/trending/get-trending) -
  список самых популярных фильмов на сегодня. Используется для создания
  коллекции на главной странице.
- [https://developers.themoviedb.org/3/search/search-movies](https://developers.themoviedb.org/3/search/search-movies) -
  поиск кинофильма по ключевому слову. Используется на странице поиска фильмов.
- [https://developers.themoviedb.org/3/movies/get-movie-details](https://developers.themoviedb.org/3/movies/get-movie-details) -
  запрос полной информации о фильме. Используется на странице кинофильма.
- [https://developers.themoviedb.org/3/movies/get-movie-credits](https://developers.themoviedb.org/3/movies/get-movie-credits) -
  запрос информации о актреском составе. Используется на странице кинофильма.
- [https://developers.themoviedb.org/3/movies/get-movie-reviews](https://developers.themoviedb.org/3/movies/get-movie-reviews) -
  запрос обзоров кинофильма. Используется на странице кинофильма.

[Ссылка на документацию](https://developers.themoviedb.org/3/getting-started/introduction)

## Маршруты

В приложении должны быть следующие маршруты. Если пользователь зашел по
несуществующему маршруту, его необходимо перенаправлять на домашнюю страницу.

- `'/'` - компонент `<HomePage>`, домашняя страница со списком популярных
  кинофильмов.
- `'/movies'` - компонент `<MoviesPage>`, страница поиска фильмов по ключевому
  слову.
- `'/movies/:movieId'` - компонент `<MovieDetailsPage>`, страница с детальной
  информацией о кинофильме.
- `/movies/:movieId/cast` - компонент `<Cast>`, информация о актерском составе.
  Рендерится на странице `<MovieDetailsPage>`.
- `/movies/:movieId/reviews` - компонент `<Reviews>`, информация об обзорах.
  Рендерится на странице `<MovieDetailsPage>`.
