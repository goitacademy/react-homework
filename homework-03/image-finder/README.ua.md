**Читать на других языках: [Русский](README.md), [Українська](README.ua.md).**

# Пошук зображень

Напиши додаток пошуку зображень за ключовим словом. Прев'ю робочого додатку
[дивись за посиланням](https://drive.google.com/file/d/1oXCGyiq4uKwW0zzraZLKk4lh3voBlBzZ/view?usp=sharing).

Створи компоненти `<Searchbar>`, `<ImageGallery>`, `<ImageGalleryItem>`,
`<Loader>`, `<Button>` і `<Modal>`. Готові стилі компонентів можна взяти в файлі
[styles.css](./styles.css) і підправити під себе, якщо необхідно.

![preview](./mockup/preview.jpg)

## Інструкція Pixabay API

Для HTTP-запитів використовуй публічний сервіс пошуку зображень
[Pixabay](https://pixabay.com/api/docs/). Зареєструйся та отримай приватний ключ
доступу.

URL-рядок HTTP-запиту.

```bash
https://pixabay.com/api/?q=что_искать&page=номер_страницы&key=твой_ключ&image_type=photo&orientation=horizontal&per_page=12
```

Pixabay API підтримує пагінацію, за замовчуванням параметр`page` дорівнює `1`.
Нехай у відповіді приходить по 12 об'єктів, встановлено в параметрі `per_page`.
Не забудь що при пошуку за новим ключовим словом, необхідно скидати значення
`page` в `1`.

У відповіді від апі приходить масив об'єктів, в яких тобі цікаві тільки наступні
властивості.

- `id` - унікальний ідентифікатор
- `webformatURL` - посилання на маленьке зображення для списку карток
- `largeImageURL` - посилання на велике зображення для модального вікна

## Опис компонента Searchbar

Компонент приймає один проп `onSubmit` - функцію для передачі значення інпут при
сабміті форми. Створює DOM-елемент такої структури.

```html
<header className="Searchbar">
  <form className="SearchForm">
    <button type="submit" className="SearchForm-button">
      <span className="SearchForm-button-label">Search</span>
    </button>

    <input
      className="SearchForm-input"
      type="text"
      autocomplete="off"
      autofocus
      placeholder="Search images and photos"
    />
  </form>
</header>
```

## Опис компонента ImageGallery

Список карток зображень. Створює DOM-елемент такої структури.

```html
<ul className="ImageGallery">
  <!-- Набір <li> з зображеннями -->
</ul>
```

## Опис компонента ImageGalleryItem

Компонент елемента списку з зображенням. Створює DOM-елемент наступної
структури.

```html
<li className="ImageGalleryItem">
  <img src="" alt="" className="ImageGalleryItem-image" />
</li>
```

## Опис компонента Button

При натисканні на кнопку `Load more` повинна довантажуватися наступна порція
зображень і рендеритися разом з попередніми. Після завантаження та рендеру нової
партії зображень сторінка повинна плавно скролитися. Для скролу використовуй
наступний код.

```js
window.scrollTo({
  top: document.documentElement.scrollHeight,
  behavior: 'smooth',
});
```

Кнопка повинна рендеритися тільки тоді, коли є якісь завантажені зображення.
Якщо масив зображень порожній, лампочка кнопки не рендериться.

## Опис компонента Loader

Компонент спінера, відображається поки йде завантаження зображень. Використовуй
будь-який готовий компонент, наприклад
[react-loader-spinner](https://github.com/mhnpd/react-loader-spinner) або
будь-який інший.

## Опис компонента Modal

При кліці по елементу галереї має відкриватися модальне вікно з темним оверлеєм
і відображатися велика версія зображення. Модальне вікно повинно закриватися
після натискання клавіші `ESC` чи при натисканні на оверлей.

Зовнішній вигляд схожий на функціонал цього
[VanillaJS-плагина](https://basiclightbox.electerious.com/), тільки замість
білого модального вікна рендериться зображення (в прикладі натисни `Run`).
Анімацію робити не потрібно!

```html
<div className="Overlay">
  <div className="Modal">
    <img src="" alt="" />
  </div>
</div>
```
