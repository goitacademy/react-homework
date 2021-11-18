**Читать на других языках: Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Критерии приема Kryteria zaliczenia

- Создан репозиторий `goit-react-hw-05-movies`
- Stworzone repozytorium `goit-react-hw-05-movies`.
- При сдаче домашней работы есть ссылки: на исходные файлы и рабочие страницы
  каждого проекта на `Netlify`
  Przy oddawaniu zadania domowego są odnośniki: do oryginalnych plików i strony roboczej każdego projektu na `Netlify`.
- В состоянии компонентов хранится минимально необходимый набор данных,
  остальное вычисляется
  W stanie komponentów przechowywany jest minimalny niezbędny zestaw danych, pozostałe są obliczane.
- При запуске кода задания, в консоли нету ошибок и предупреждений
- Po włączeniu kodu zadania, na konsoli nie ma błędów i ostrzeżeń.
- Для каждого компонента есть отдельная папка с файлом React-компонента и файлом
  стилей
  DLa każdego komponentu stworzony został folder z plikiem komponenta React i plikiem stylów.
- Для компонентов описаны `propTypes`
- Dla komponentu opisane są `propTypes`.
- Все что компонент ожидает в виде пропов, передается ему при вызове
- Wszystko, czego komponent żąda w postaci propsów, przekazuje się do niego przy wywołaniu.
- Имена компонентов понятные, описательные
- Nazwy komponentów są zrozumiałe, opisowe.
- JS-код чистый и понятный, используется `Prettier`
- Kod JS jest czysty i zrozumiały, wykorzystuje się `Prettier`.
- Стилизация выполнена `CSS-модулями` или `Styled Components`.
- Stylizacja wykonania `CSS-modułmi` lub `Styled Components`.

## Задание «Кинопоиск» Zadanie "Wyszukiwanie filmów"

Создай базовую маршрутизацию для приложения поиска и хранения фильмов. Превью
рабочего приложения
Stwórz bazowe trasowanie dla aplikacji do wyszukiwani i zapisywania filmów. Preview roboczej aplikacji
[смотри по ссылке zobacz link](https://drive.google.com/file/d/1vR0hi3n1236Q5Bg4-se-8JVKD9UKSfId/view?usp=sharing).

## API themoviedb.org

Для бекенда используй [themoviedb.org API](https://www.themoviedb.org/).
Необходимо зарегистриваться (можно ввести произвольные данные) и получить
API-ключ. В этой работе будут использоваться следующие ендпоинты.

Do backendu wykorzystaj [themoviedb.org API](https://www.themoviedb.org/). Należy się zarejestrować (można wprowadzić dowolne dane) i otrzymać klucz API. W tym zadaniu będzie się wykorzystywać następujące endpointy.

- [/trending/get-trending](https://developers.themoviedb.org/3/trending/get-trending)
  список самых популярных фильмов на сегодня для создания коллекции на главной
  странице.
  lista najpopularniejszych filmów dzisiaj w celu utworzenia kolekcji n stronie głównej.
- [/search/search-movies](https://developers.themoviedb.org/3/search/search-movies)
  поиск кинофильма по ключевому слову на странице фильмов.
  wyszukiwanie filmu po słwie kluczu na stronie filmów.
- [/movies/get-movie-details](https://developers.themoviedb.org/3/movies/get-movie-details)
  запрос полной информации о фильме для страницы кинофильма.
  zapytanie o pełną informację o filmie dla strony filmu.
- [/movies/get-movie-credits](https://developers.themoviedb.org/3/movies/get-movie-credits)
  запрос информации о актёрском составе для страницы кинофильма.
  zapytanie o informcje o zespole aktorskim dla strony filmu.
- [/movies/get-movie-reviews](https://developers.themoviedb.org/3/movies/get-movie-reviews)
  запрос обзоров для страницы кинофильма.
  zapytanie o recenzje dla strony filmu.

[Ссылка на документацию Link do dokumentacji](https://developers.themoviedb.org/3/getting-started/introduction)

## Маршруты Trasy

В приложении должны быть следующие маршруты. Если пользователь зашел по
несуществующему маршруту, его необходимо перенаправлять на домашнюю страницу.

W aplikacji powinny znaleźć się następujące trasy. Jeśli użytkownik poszedł nieistniejącą trasą, należy przekierować go na stronę główną.

- `'/'` - komponent `<HomePage>`, домашняя страница со списком популярных
  кинофильмов.
  strona domowa z listą popularnych filmów.
- `'/movies'` - komponent `<MoviesPage>`, страница поиска фильмов по ключевому
  слову.
  strona wyszukiwania filmów po słowie kluczu.
- `'/movies/:movieId'` - komponent `<MovieDetailsPage>`, страница с детальной
  информацией о кинофильме.
  strona ze szczegółowymi informacjami o filmie.
- `/movies/:movieId/cast` - komponent `<Cast>`, информация о актерском составе.
  Рендерится на странице `<MovieDetailsPage>`.
  informacja o zespole aktorskim. Renderuje się na stronie `<MovieDetailsPage>`.
- `/movies/:movieId/reviews` - komponent `<Reviews>`, информация об обзорах.
  Рендерится на странице `<MovieDetailsPage>`.
  informacja o recenzjach. Renderuje się n stronie `<MovieDetailsPage>`.

## Code Splitting (разделение кода rozdzielenie kodu)

Добавь асинхронную загрузку JS-кода для маршрутов приложения используя
Dodaj asynchroniczne ładownie kodu JS dla tras aplikacji, wykorzystując
`React.lazy()` i `Suspense`.
