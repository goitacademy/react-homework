**Читать на других языках: [Русский](README.md), [Українська](README.ua.md).**

# Критерії прийому

- Створено репозиторії `goit-react-hw-04-movies`
- При здачі домашньої роботи є посилання: на вихідні файли і робочу сторінку
  проектів на `Netlify`
- У стані компонентів зберігається мінімально необхідний набір даних, інше
  обчислюється
- При запуску коду завдання, в консолі немає помилок і попереджень
- Для кожного компонента є окрема папка з файлом React-компонента і файлом
  стилів
- Для компонентів описані `propTypes`, і де необхідно, `defaultProps`
- Все що компонент очікує у вигляді пропів, передається йому при виклику
- Імена компонентів зрозумілі, описові
- JS-код чистий і зрозумілий, використовується `Prettier`
- Стилізація робиться тільки `SASS`, `CSS-модулями` або `Styled Components`.
  Можна використовувати бібліотеки компонентів.

## Завдання «Кінопошук»

Створи базову маршрутизацію для програми пошуку і зберігання фільмів. Прев'ю
робочого додатку
[дивись за посиланням](https://drive.google.com/file/d/1vR0hi3n1236Q5Bg4-se-8JVKD9UKSfId/view?usp=sharing).

## API themoviedb.org

Для бекенда використовуй [themoviedb.org API](https://www.themoviedb.org/).
Необхідно зареєструватися (можна ввести довільні дані) і отримати API-ключ. У
цій роботі будуть використовуватися такі ендпоінти.

- [https://developers.themoviedb.org/3/trending/get-trending](https://developers.themoviedb.org/3/trending/get-trending) -
  список найпопулярніших фільмів на сьогодні для створення колекції на головній
  сторінці.
- [https://developers.themoviedb.org/3/search/search-movies](https://developers.themoviedb.org/3/search/search-movies) -
  пошук фільму по ключовому слову на сторінці фільмів.
- [https://developers.themoviedb.org/3/movies/get-movie-details](https://developers.themoviedb.org/3/movies/get-movie-details) -
  запит повної інформації про фільм для сторінки кінофільму.
- [https://developers.themoviedb.org/3/movies/get-movie-credits](https://developers.themoviedb.org/3/movies/get-movie-credits) -
  запит інформації про акторський склад для сторінки кінофільму.
- [https://developers.themoviedb.org/3/movies/get-movie-reviews](https://developers.themoviedb.org/3/movies/get-movie-reviews) -
  запит оглядів для сторінки кінофільму.

[Посилання на документацію](https://developers.themoviedb.org/3/getting-started/introduction)

## Маршрути

У додатку повинні бути наступні маршрути. Якщо користувач зайшов по неіснуючому
маршруту, його необхідно перенаправляти на домашню сторінку.

- `'/'` - компонент `<HomePage>`, домашня сторінка зі списком популярних
  кінофільмів.
- `'/movies'` - компонент `<MoviesPage>`, сторінка пошуку фільмів по ключовому
  слову.
- `'/movies/:movieId'` - компонент `<MovieDetailsPage>`, сторінка з детальною
  інформацією про кінофільми.
- `/movies/:movieId/cast` - компонент `<Cast>`, інформація про акторський склад.
  Рендериться на сторінці `<MovieDetailsPage>`.
- `/movies/:movieId/reviews` - компонент `<Reviews>`, інформація про огляди.
  Рендериться на сторінці `<MovieDetailsPage>`.

## Code Splitting (розщеплення коду)

Додай асинхронне завантаження JS-коду для маршрутів додатки використовуючи
`React.lazy()` і `Suspense`.
