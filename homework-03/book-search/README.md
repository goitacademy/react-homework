# Поиск книг

Необходимо написать приложение поиска книг по названию и жанру.

![preview](./mockup/preview.jpg)

Для HTTP-запросов используется
[Google Books API](https://developers.google.com/books/docs/v1/using#WorkingVolumes).

Например, если пользователь хочет найти книги с заголовком `react` и жанром
`computers`, то адрес GET-запроса будет выглядеть следующим образом.

```bash
https://www.googleapis.com/books/v1/volumes?q=react+subject:computers
```

## Описание компонента SearchForm

Форма поиска, состоит из инпута и селекта жанра. Принимает пропы:

- `genres` - массив жанров для `select`
- `onSubmit(query, genre)` - функция поиска книг для вызова при сабмите

Список жанров лежит в файле [genres.json](./genres.json).

## Описание компонентов BookList и BookListItem

Компоненты списка книг и одной книги соответственно.

`BookList` принимает один проп `items` - массив объектов.

`BookListItem` принимает пропы `image` (картинка), `title` (заголовок),
`description` (описание), `author` (автор), `publisher` (издательство) и
`publishedDate` (год издания), `pageCount` (кол-во страниц), `rating` (рейтинг).

## Описание компонента Loader

Спиннер отображающийся во время HTTP-запроса. Оформление произвольное. Можно
использовать готовые компоненты из библиотек
[halogen](https://github.com/yuanyan/halogen) или
[react-spinkit](https://github.com/KyleAMathews/react-spinkit).
