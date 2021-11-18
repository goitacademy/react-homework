**Czytaj w innych językach: [rosyjski](README.md), [ukraiński](README.ua.md).**

# Sekcja statystyki

Należy utworzyć komponent `<Statistics>`, który będzie wyświetlał statystyki zgodnie z przekazanymi propsami. Na przykład ładowanie w chmurze po typie pliku, odwiedziny strony internetowej przez użytkowników z różnych krajów, wydatki finansowe itp. Dane o statystykach znajdują się w pliku [data.json](./data.json).

![Preview komponentu Statistics](./preview.jpg)

## Opis komponentu

Komponent powinien przyjmować dwa propsy `title` i `stats`, w których wyświetla się nagłówek i obiekt statystyk.

- `title` - nie jest obowiązkowy i jeśli nie został przekazany, układ nagłówka nie powinien się renderować `<h2>`. 
- `stats` - tablica obiektów zawierających informację o elemencie statystyki. Może mieć dowolną ilość elementów.
- Kolor tła elementu statystyki można opuścić lub utworzyć funkcję do generowania losowego koloru.

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

## Przykład wykorzystania

```js
import data from '/droga/do/data.json';

<Statistics title="Upload stats" stats={data} />;
<Statistics stats={data} />;
```
