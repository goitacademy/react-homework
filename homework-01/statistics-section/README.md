# Секция статистики

Создать компонет `Stats`, который бы отображал статистику по переданным пропам.
К примеру загрузки в облако по типу файлов, посещение веб-страницы
пользователями разных стран, финансовые траты и т. п.

![profile preview](./mockup/preview.jpg)

## Описание компонента

Компонент должен принимать два пропа `title` и `stats`, в которых указывается
заголовок и объект статистики.

- `title` не обязателен, и если он не передан, не должена рендерится разметка
  заголовка.
- `stats` может иметь произвольное кол-во свойств для списка статистики.
- Цвет фона элемента статистики в оформлении можно пропустить, либо создать
  функции для генерации случайного цвета.

Компонент должен создавать DOM элемент следующей структуры.

```html
<section class="stats-section">
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

## Пример использования

```js
const stats = {
  '.docx': 22,
  '.pdf': 4,
  '.mp3': 17,
  '.psd': 47,
  '.pdf': 10,
};

ReactDOM.render(
  <Stats title="Upload stats" stats={stats} />,
  document.getElementById('root'),
);
```
