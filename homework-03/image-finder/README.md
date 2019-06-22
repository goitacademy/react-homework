# Поиск изображений

Напиши приложение поиска и просмотра изображений по ключевому слову. Создай
компоненты `SearchForm`, `Gallery`, `PhotoCard` и `Modal`. Стили компонентов
можно взять в файле [styles.css](./styles.css).

![preview](./mockup/preview.jpg)

## Инструкции Pixabay API

Для HTTP-запросов используй публичный
[RESTful API Pixabay](https://pixabay.com/api/docs/). Зарегистрируйся и получи
ключ.

URL-строка HTTP-запроса:

```bash
https://pixabay.com/api/?image_type=photo&orientation=horizontal&q=что_искать&page=номер_страницы&per_page=12&key=твой_ключ
```

Pixabay API поддерживает пагинацию, пусть в ответе приходит по 12 объектов,
установлено в параметре `per_page`. По умолчанию параметр `page` равен `1`.

> Не забудь, при поиске по новому ключевому слову необходимо сбрасывать значение
> страницы в `1`.

При нажатии на кнопку `Load more` должна догружаться следующая порция
изображений и рендериться вместе с предыдущими. Страница должна автоматически
плавно проскроливаться после рендера изображений. Можно использовать
[window.scrollTo()](https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollTo).

Каждое изобаржение описывается объектом.

```json
{
  "comments": 78,
  "downloads": 63296,
  "favorites": 558,
  "id": 1508613,
  "imageHeight": 2135,
  "imageSize": 1630104,
  "imageWidth": 2894,
  "largeImageURL": "https://pixabay.com/get/57e5d54b4c53af14f6da8c7dda793376173cd8e7524c704c702873dc9f44c551_1280.jpg",
  "likes": 575,
  "pageURL": "https://pixabay.com/photos/cat-animal-cat-portrait-cat-s-eyes-1508613/",
  "previewHeight": 110,
  "previewURL": "https://cdn.pixabay.com/photo/2016/07/10/21/47/cat-1508613_150.jpg",
  "previewWidth": 150,
  "tags": "cat, animal, cat portrait",
  "type": "photo",
  "user": "cocoparisienne",
  "userImageURL": "https://cdn.pixabay.com/user/2018/11/26/11-06-29-714_250x250.jpg",
  "user_id": 127419,
  "views": 127450,
  "webformatHeight": 472,
  "webformatURL": "https://pixabay.com/get/57e5d54b4c53af14f6da8c7dda793376173cd8e7524c704c702873dc9f44c551_640.jpg",
  "webformatWidth": 640
}
```

Нам интересны следующие свойства:

- `id` - уникальный идентификатор
- `webformatURL` - ссылка на маленькое изображение для списка карточек
- `largeImageURL` - ссылка на большое изображение для модального окна
- `likes` - количество лайков
- `views` - количество просмотров
- `comments` - количество комментариев
- `downloads` - количество загрузок

## Описание компонента SearchForm

Компонент принимает один проп `onSubmit` - функцию для передачи значения инпута
при сабмите. Создает DOM-элемент следующей структуры.

```html
<form class="search-form">
  <input type="text" autocomplete="off" placeholder="Search images..." />
</form>
```

## Описание компонента Gallery

Список карточек изображений. Создает DOM-элемент следующей структуры.

```html
<ul class="gallery">
  <!-- Список <li> с карточками изображений <PhotoCard> -->
</ul>
```

## Описание компонента PhotoCard

Компонент карточки с изображением и статистикой. Создает DOM-элемент следующей
структуры.

```html
<div class="photo-card">
  <img src="" alt="" />

  <div class="stats">
    <p class="stats-item">
      <i class="material-icons">thumb_up</i>
      1108
    </p>
    <p class="stats-item">
      <i class="material-icons">visibility</i>
      320321
    </p>
    <p class="stats-item">
      <i class="material-icons">comment</i>
      129
    </p>
    <p class="stats-item">
      <i class="material-icons">cloud_download</i>
      176019
    </p>
  </div>

  <!-- Кнопка для открытия модалки с большим изображением, появляется при наведении -->
  <button type="button" class="fullscreen-button">
    <i class="material-icons">zoom_out_map</i>
  </button>
</div>
```

Для иконок используются
[Material icons](https://google.github.io/material-design-icons/). Для их
корректной работы достаточно в HTML-файле добавить ссылку на веб-шрифт.

```html
<link
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
  rel="stylesheet"
/>
```

## Описание компонента Modal

При клике на кнопку `fullscreen-button` в карточке галлереи, должно открываться
модальное окно с темным оверлеем и отображаться большая версия изображения.
Модальное окно должно закрываться по `ESC`, или клику по оверлею.

Внешний вид похож на функционал этого
[VanillaJS-плагина](https://basiclightbox.electerious.com/), только вместо
белого модального окна рендерится изображение (в примере нажми `Run`). Анимации
делать не нужно!

```html
<div class="overlay">
  <div class="modal">
    <img src="" alt="" />
  </div>
</div>
```
