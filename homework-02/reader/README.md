# Читатель публикаций

Создай читатель публикаций для просмотра контента с возможностью перейти к
следующей либо предыдущей публикации, а так же отображением прогресса.

![reader preview](./mockup/preview.gif)

Необходимо создать компоненты `<Reader>`, `<Controls>`, `<Progress>` и
`<Publication>` c пропсами и состоянием.

## Описание компонента Reader

Корневой родительский компонент, хранит состояние приложения - индекс текущей
публикации. Должен принимать один проп `items` - массив объектов публикаций.
Публикации хранятся в файле [publications.json](./publications.json).

Приложение должено создавать DOM-элемент следующей структуры.

```html
<!-- Разметка компонента <Reader> -->
<div class="reader">
  <!-- Разметка компонента <Controls> -->
  <section>
    <button type="button">Назад</button>
    <button type="button">Вперед</button>
  </section>

  <!-- Разметка компонента <Progress> -->
  <p>3/10</p>

  <!-- Разметка компонента <Publication> -->
  <article>
    <h2>Lorem ipsum dolor sit amet</h2>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus,
      molestiae dolore ipsa sed similique necessitatibus. Aut qui porro
      quibusdam esse libero est eius, repellendus unde nihil, sequi voluptate
      eaque officiis aliquam impedit laborum adipisci cumque sit.
    </p>
  </article>
</div>
```

## Пример использования

```js
import publications from 'path/to/publications.json';

ReactDOM.render(
  <Reader items={publications} />,
  document.getElementById('root'),
);
```
