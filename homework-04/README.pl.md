**Czytaj w innych językach: [rosyjski](README.md), [ukraiński](README.ua.md).**

Użyj tego
[szablonu projektu React](https://github.com/goitacademy/react-homework-template#readme)
jako punktu wyjścia dla swojej aplikacji.

# Kryteria zaliczenia

- Stworzone repozytorium `goit-react-hw-05-movies`.
- W oddawanym zadaniu domowym są odnośniki: do oryginalnych plików i strony
  roboczej każdego projektu na `Netlify`.
- W stanie komponentów przechowywany jest minimalny niezbędny zestaw danych,
  pozostałe są obliczane.
- Po włączeniu kodu zadania, na konsoli nie ma błędów i ostrzeżeń.
- Dla każdego komponentu stworzony został folder z plikiem komponentu React i
  plikiem stylów.
- Dla komponentu opisane są `propTypes`.
- Wszystko, czego komponent żąda w postaci propsów, przekazuje się do niego przy
  wywołaniu.
- Nazwy komponentów są zrozumiałe, opisowe.
- Kod JS jest czysty i zrozumiały, wykorzystuje się `Prettier`.
- Stylizacja wykonania `CSS-modułami` lub `Styled Components`.

## Zadanie "Wyszukiwanie filmów"

Stwórz bazowe trasowanie dla aplikacji do wyszukiwania i zapisywania filmów.
Preview roboczej aplikacji
[zobacz link](https://drive.google.com/file/d/1vR0hi3n1236Q5Bg4-se-8JVKD9UKSfId/view?usp=sharing).

## API themoviedb.org

Do backendu wykorzystaj [themoviedb.org API](https://www.themoviedb.org/).
Należy się zarejestrować (można wprowadzić dowolne dane) i pobrać klucz API. W
tym zadaniu będzie się wykorzystywać następujące endpointy.

- [/trending/get-trending](https://developers.themoviedb.org/3/trending/get-trending)
  lista najpopularniejszych filmów dzisiaj w celu utworzenia kolekcji na stronie
  głównej.
- [/search/search-movies](https://developers.themoviedb.org/3/search/search-movies)
  wyszukiwanie filmu po słowie kluczu na stronie filmów.
- [/movies/get-movie-details](https://developers.themoviedb.org/3/movies/get-movie-details)
  zapytanie o pełną informację o filmie dla strony filmu.
- [/movies/get-movie-credits](https://developers.themoviedb.org/3/movies/get-movie-credits)
  zapytanie o informację o zespole aktorskim dla strony filmu.
- [/movies/get-movie-reviews](https://developers.themoviedb.org/3/movies/get-movie-reviews)
  zapytanie o recenzje dla strony filmu.

[Link do dokumentacji](https://developers.themoviedb.org/3/getting-started/introduction)

## Trasy

W aplikacji powinny znaleźć się następujące trasy. Jeśli użytkownik poszedł
nieistniejącą trasą, należy przekierować go na stronę główną.

- `'/'` - komponent `<HomePage>`, strona domowa z listą popularnych filmów.
- `'/movies'` - komponent `<MoviesPage>`, strona wyszukiwania filmów po słowie
  kluczu.
- `'/movies/:movieId'` - komponent `<MovieDetailsPage>`, strona ze szczegółowymi
  informacjami o filmie.
- `/movies/:movieId/cast` - komponent `<Cast>`, informacja o zespole aktorskim.
  Renderuje się na stronie `<MovieDetailsPage>`.
- `/movies/:movieId/reviews` - komponent `<Reviews>`, informacja o recenzjach.
  Renderuje się n stronie `<MovieDetailsPage>`.

## Code Splitting (rozdzielenie kodu)

Dodaj asynchroniczne ładownie kodu JS dla tras aplikacji, wykorzystując
`React.lazy()` i `Suspense`.
