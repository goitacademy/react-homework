# Фильтр фильмов

Необходимо создать компоненты отображения и фильтра для страницы фильмов. Список
фильмов хранится в файле [movies.json](./movies.json).

Необходимо создать компоненты `MoviePage`, `MovieGrid`, `MovieGridItem` и
`SearchBar` с необходимыми пропами и состоянием.

При вводе текста в инпуте компонента `SearchBar`, должны быть отфильтрованы и
отображены только те фильмы, заголовок которых содержит введенный текст. Если ни
один фильм не подходит, отображается строка `'No matching results!'`.

[Ссылка на видео](https://take.ms/Abnv1)

![reader preview](./mockup/preview.png)

## Описание компонента MoviePage

Родительский компонент, контейнер для строки поиска и списка фильмов.

```html
<div class="container">
  <!-- Остальные компоненты -->
</div>
```

## Описание компонента MovieGrid

Компонент должен иметь один проп `items` - массив объектов фильмов.

Компонент должен создавать DOM-элемент следующей структуры.

```html
<div class="movie-grid">
  <!-- Набор карточек фильмов -->
</div>
```

## Описание компонента MovieGridItem

Компонент должен принимать пропы с именами ключей объекта фильма, и должен
создавать DOM-элемент следующей структуры.

```html
<div class="movie-card">
  <img src="" alt="" />
  <div class="content">
    <h2></h2>
    <p></p>
  </div>
</div>
```

## Описание компонента SearchBar

Компонент должен принимать два пропа: `value` и `onChange`, и должен создавать
DOM-элемент следующей структуры.

```html
<input type="text" class="input" />
```

## Стили

Возьми готовые стили и подкорректируй их под `CSS-модули` или
`Styled Components`.

```css
.container {
  max-width: 1200px;
  min-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.input {
  color: #171718;
  font-size: 16px;
  min-height: 38px;
  padding: 4px 8px;
  border-radius: 4px;
  border: 1px solid rgb(179, 179, 179);
  width: 100%;
  outline: 0;
  transition: border-color 200ms ease-in-out;
}

.input:focus {
  border-width: 2px;
  border-color: rgb(38, 132, 255);
}

.movie-grid {
  display: flex;
  flex-wrap: wrap;
  margin-left: -8px;
  margin-right: -8px;
}

.movie-card {
  box-shadow: 0px 1px 3px 0px rgba(0, 0, 0, 0.2), 0px 1px 1px 0px rgba(0, 0, 0, 0.14),
    0px 2px 1px -1px rgba(0, 0, 0, 0.12);
  border-radius: 4px;
  background-color: #fff;
  flex: 0 0 calc(25% - 16px);
  margin-left: 8px;
  margin-right: 8px;
  margin-top: 16px;
  overflow: hidden;
}

.movie-card .content {
  padding: 8px;
}

.movie-card img {
  display: block;
  max-width: 100%;
}

.movie-card h2 {
  margin-top: 0;
  margin-bottom: 0;
  font-weight: 500;
}

.movie-card p {
  margin-bottom: 0;
  line-height: 1.5;
}
```
