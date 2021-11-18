**Читать на других языках: Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Критерии приема Kryteria zaliczenia

- Создан репозиторий Stworzone repozytorium `goit-react-hw-06-phonebook`
- При сдаче домашней работы есть ссылки: на исходные файлы и рабочую страницу
  проекта на `GitHub Pages` или `Netlify`
  Przy oddawaniu zadania domowego znajdują się w nim odnośniki do: oryginalnych plików i roboczej strony projektu na `GitHub Pages` lub `Netlify`.
- В Redux-состоянии хранится минимально необходимый набор данных
- W stanie Redux przechowywany jest minimalny wymagany zestaw danych.
- При запуске кода задания, в консоли нету ошибок и предупреждений
- Po włączeniu kodu zadania, na konsoli nie ma błędów i ostrzeżeń.
- Для каждого компонента есть отдельная папка с файлом React-компонента и файлом
  стилей
   DLa każdego komponentu stworzony został folder z plikiem komponenta React i plikiem stylów.
- Для компонентов описаны `propTypes`
- Dla komponentu opisane są `propTypes`.
- Использована библиотека `Redux Toolkit`
- Wykorzystywana jest biblioteka `Redux Toolkit`.

## Телефонная книга Książka telefoniczna

Выполни рефакторинг кода приложения «Телефонная книга» добавив управление
состоянием при помощи библиотеки [Redux Toolkit](https://redux-toolkit.js.org/).

Przeprowadź refaktor kodu aplikacji "Książka telefoniczna", dodając zarządzanie stanem przy pomocy biblioteki [Redux Toolkit](https://redux-toolkit.js.org/).

Пусть Redux-состояние выглядит следующим образом.
Niech stan Redux wygląda następująco.

```bash
{
  contacts: {
    items: [],
    filter: ''
  }
}
```

- Создай хранилище с `configureStore()`
- Stwórz magazyn z `configureStore()`.
- Создай действия сохранения и удаления контакта, а также обновления фильтра.
  Используй функцию `createAction()`.
  Stwórz działanie zapisywania i usuwania kontaktu oraz odświeżenia filtru. Wykorzystaj funkcję `createAction()`.
- Создай редюсеры контактов и фильтра. Используй функцию `createReducer()` или
  `createSlice()`.
  Stwórz reduktory kontaktów i filtru. Wykorzystaj funkcję `createReducer()` lub
  `createSlice()`.
- Свяжи React-компоненты с Redux-логикой при помощи хуков бибилиотеки
- Powiąż komponent React i logikę Redux przy pomocy hooków biblioteki
  [react-redux](https://react-redux.js.org/).
