**Читать на других языках Czytaj w innych językach: [rosyjski](README.md), [ukraiński](README.ua.md).**

# Секция статистики Sekcja statystyki

Создать компонет `<Statistics>`, который бы отображал статистику по переданным
пропам. Например, загрузки в облако по типу файлов, посещение веб-страницы
пользователями разных стран, финансовые траты и т. п. Данные о статистике лежат
в файле [data.json](./data.json).

Należy utworzyć komponent `<Statistics>`, który będzie wyświetlał statystyki zgodnie z przekazanymi popsami. Na przykład ładowanie w chmurze po typie pliku, odwiedziny strony internetowej przez użytkowników z różnych krajów, wydatki finansowe itp. Dane o statystykach leżą w pliku [data.json](./data.json).

![Превью компонента Prewiev komponentu Statistics](./preview.jpg)

## Описание компонента Opis komponentu

Компонент должен принимать два пропа `title` и `stats`, в которых указывается
заголовок и объект статистики.

Komponent powinien przyjmowac dwa propsy `title` i `stats`, w których wyświetla się ngłówek i obiekt statystyk.

- `title` - не обязателен, и если он не передан, не должна рендериться разметка
  заголовка `<h2>`.
  nie jest obowiązkowy i jeśli nie został przekazany, układ nagłówka nie powinien się renderować `<h2>`. 
- `stats` - массив объектов содержащих информацию о элементе статистики. Может
  иметь произвольное кол-во элементов.
  tablica obiektów zawierających informcję o elemencie statystyki. Może mieć dowolną ilość elementów.
- Цвет фона элемента статистики в оформлении можно пропустить, либо создать
  функцию для генерации случайного цвета.
  Kolor tła elementu statystyki można opuścić lub utworzyć funkcje do generowania losowego koloru.

Компонент должен создавать DOM элемент следующей структуры.
Komponent powinien tworzyć element DOM o następującej strukturze.

```html
<section class="statistics">
  <h2 class="title">Upload stats</h2>

  <ul class="stat-list">
    <li class="item">
      <span class="label">.docx</span>
      <span class="percentage">4%</span>
    </li>
    <li class="item">
      <span class="label">.mp3</span>
      <span class="percentage">14%</span>
    </li>
    <li class="item">
      <span class="label">.pdf</span>
      <span class="percentage">41%</span>
    </li>
    <li class="item">
      <span class="label">.mp4</span>
      <span class="percentage">12%</span>
    </li>
  </ul>
</section>
```

## Пример использования Przykład wykorzystania

```js
import data from '/путь/к/data.json';

<Statistics title="Upload stats" stats={data} />;
<Statistics stats={data} />;
```
