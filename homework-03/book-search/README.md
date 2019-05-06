# Поиск книг

Необходимо написать приложение поиска книг по названию и жанру. Для
HTTP-запросов используется
[Google Books API](https://developers.google.com/books/docs/v1/using#WorkingVolumes).

Например, если пользователь хочет найти книги с заголовком `sun` и жанром
`drama`, то адрес GET-запроса будет выглядеть следующим образом.

```bash
https://www.googleapis.com/books/v1/volumes?q=sun+subject:drama
```

## Описание компонента SearchForm

Форма поиска, состоит из инпута и селекта жанра. Принимает пропы:

- `onSearch(query, genre)` - функция поиска книг для вызова при сабмите
- `genres` - массив жанров для `select`

Список жанров лежит в файле [genres.json](./genres.json).

## Описание компонентов BookList и BookListItem

Компоненты списка книг и одной книги соответственно.
