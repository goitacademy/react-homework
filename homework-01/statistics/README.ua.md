**Читать на других языках: [Русский](README.md), [Українська](README.ua.md).**

# Секція статистики

Створити компонент `<Statistics>`, який би відображав статистику по переданим
пропах. Наприклад завантаження в хмару по типу файлів, відвідування веб-сторінки
користувачами різних країн, фінансові витрати і т. п. Дані про статистику лежать
у файлі [statistical-data.json](./statistical-data.json).

![profile preview](./preview.jpg)

## Опис компонента

Компонент повинен приймати два пропи `title` і `stats`, в яких вказується
заголовок і об'єкт статистики.

- `title` - не обов'язковий, і якщо він не переданий, не повинна рендеритися
  розмітка заголовка `<h2>`.
- `stats` - масив об'єктів, що містять інформацію про елементи статистики. Може
  мати довільну кількість елементів.
- Колір фону елемента статистики в оформленні можна пропустити, або створити
  функцію для генерації випадкового кольору.

Компонент повинен створювати DOM елемент такої структури.

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

## Приклад використання

```js
import statisticalData from '/path/to/statistical-data.json';

ReactDOM.render(
  <Statistics title="Upload stats" stats={statisticalData} />,
  document.getElementById('root'),
);
```
