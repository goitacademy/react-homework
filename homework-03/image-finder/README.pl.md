**Читать на других языках: Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Поиск изображений Wyszukiwanie obrazów

Напиши приложение поиска изображений по ключевому слову. Превью рабочего
приложения
Napisz aplikację wyszukiwania obrazów po słowu kluczu. Preview roboczej aplikacji
[смотри по ссылке zobacz link](https://drive.google.com/file/d/1oXCGyiq4uKwW0zzraZLKk4lh3voBlBzZ/view?usp=sharing).

Создай компоненты `<Searchbar>`, `<ImageGallery>`, `<ImageGalleryItem>`,
`<Loader>`, `<Button>` и `<Modal>`. Готовые стили компонентов можно взять в
файле [styles.css](./styles.css) и подправить под себя, если необходимо.

Stwórz komponenty `<Searchbar>`, `<ImageGallery>`, `<ImageGalleryItem>`,
`<Loader>`, `<Button>` i `<Modal>`. Gotowe style komponentów można znaleźć w pliku [styles.css](./styles.css) i dostosować do siebie, jeśli jest to potrzebne.

![preview](./mockup/preview.jpg)

## Инструкция Instrukcja Pixabay API

Для HTTP-запросов используй публичный сервис поиска изображений
[Pixabay](https://pixabay.com/api/docs/). Зарегистрируйся и получи приватный
ключ доступа.

Dla zapytań HTTP wykorzystujących serwis wyszukiwania obrazów [Pixabay](https://pixabay.com/api/docs/). Zarejestruj się i otzymaj prywatny kod dostępu.

URL-строка HTTP-запроса. Łańcuch URL zapytania HTTP.

```bash
https://pixabay.com/api/?q=cat&page=1&key=your_key&image_type=photo&orientation=horizontal&per_page=12
```

Pixabay API поддерживает пагинацию, по умолчанию параметр `page` равен `1`.
Пусть в ответе приходит по 12 объектов, установлено в параметре `per_page`. Не
забудь что при поиске по новому ключевому слову, необходимо сбрасывать значение
`page` в `1`.

Pixabay API wspiera paginację, domyślnie parametr `page` równa się `1`. Niech w odpowiedzi przychodzi po 12 obiektów, umieszczonych w parametrze `per_page`. Nie zapomnij, że podczas wyszukiwania po nowym słowie kluczu należy odrzucać wartość `page` w `1`.

В ответе от апи приходит массив объектов, в которых тебе интересны только
следущие свойства.

W odpowiedzi od api przychodzi tablica obiektów, wśród których interesują cię wyłącznie następujące właściwości.

- `id` - уникальный идентификатор unikalny identyfikator
- `webformatURL` - ссылка на маленькое изображение для списка карточек 
- odnośnik do małego przedstawienia listy kart
- `largeImageURL` - ссылка на большое изображение для модального окна
- odnośnik do dużego przedstawienia okna modalnego

## Описание компонента Opis komponentu `<Searchbar>` 

Компонент принимает один проп `onSubmit` - функцию для передачи значения инпута
при сабмите формы. Создает DOM-элемент следующей структуры.

Komponent przyjmuje jeden props `onSubmit` – funkcję do przekazywania wartości inputu przy submicie formulrza. Tworzy element DOM o następującej strukturze.

```html
<header class="searchbar">
  <form class="form">
    <button type="submit" class="button">
      <span class="button-label">Search</span>
    </button>

    <input
      class="input"
      type="text"
      autocomplete="off"
      autofocus
      placeholder="Search images and photos"
    />
  </form>
</header>
```

## Описание компонента Opis komponentu `<ImageGallery>`

Список карточек изображений. Создает DOM-элемент следующей структуры.

Lista kart obrazków. Tworzy element DOM o następującej strukturze.

```html
<ul class="gallery">
  <!-- Набор <li> с изображениями -->
</ul>
```

## Описание компонента Opis komponentu `<ImageGalleryItem>`

Компонент элемента списка с изображением. Создает DOM-элемент следующей
структуры.

Komponent elementu listy z obrazem. Tworzy element DOM o następującej strukturze.

```html
<li class="gallery-item">
  <img src="" alt="" />
</li>
```

## Описание компонента Opis komponentu `<Button>`

При нажатии на кнопку `Load more` должна догружаться следующая порция
изображений и рендериться вместе с предыдущими. Кнопка должна рендерится только
тогда, когда есть какие-то загруженные изобаржения. Если массив изображений
пуст, кнопка не рендерится.

Po naciśnięciu przycisku `Load more` powinna ładować się następna porcja obrazów i renderować się razem z poprzednimi. Przycisk powinien renderować się tylko wtedy, gdy są jakieś załadowane obrazy. Jeśli tablica obrazów jest pusta, przycisk nie renderuje się.

## Описание компонента Opis komponentu `<Loader>`

Компонент спинера, отображется пока идет загрузка изобаржений. Используй любой
готовый компонент, например
Komponent spinnera, pokaże się w trakcie ładowania obrazów. Wykorzystaj dowolny gotowy komponent, na przykład
[react-loader-spinner](https://github.com/mhnpd/react-loader-spinner) или любой
другой.

## Описание компонента Opis komponentu `<Modal>`

При клике по элементу галереи должно открываться модальное окно с темным
оверлеем и отображаться большая версия изображения. Модальное окно должно
закрываться по нажатию клавиши `ESC` или по клику на оверлее.

Po kliknięciu na element galerii powinno otwierać się okno modalne z ciemnym overlay i wyświetlać się duża wersja obrazu. Okno modalne powinno zamykać się po naciśnięsiu klawisza `ESC` lub po kliknięciu na overlay.

Внешний вид похож на функционал этого
Wygląd podobny jest do tej funkcjonalności
[VanillaJS-плагина](https://basiclightbox.electerious.com/), только вместо
белого модального окна рендерится изображение (в примере нажми `Run`). Анимацию
делать не нужно!
tylko zamiast białego okna modalnego renderuje się obraz (na przykład kliknij `Run`). Nie trzeba tworzyć animacji!

```html
<div class="overlay">
  <div class="modal">
    <img src="" alt="" />
  </div>
</div>
```
