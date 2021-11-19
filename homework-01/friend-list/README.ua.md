**Читати іншими мовами: [Русский](README.md), [Українська](README.ua.md).**

# Список друзів

Необхідно створити компонент `<FriendList>`, за допомогою якого ми могли б відображати інформацію про друзів користувача. Інформація про друзів зберігається у файлі [friends.json](./friends.json).

![Прев'ю компонента FriendList](./preview.jpg)

## Опис компонента `<FriendList>`

Компонент повинен приймати один проп `friends` – масив об'єктів друзів.

Компонент повинен створювати DOM наступної структури.

```html
<ul class="friend-list">
  <!-- Довільна кіл-сть FriendListItem -->
</ul>
```

## Опис компонента `<FriendListItem>`

Компонент повинен приймати кілька пропів:

- `avatar` – посилання на аватар
- `name` – ім'я друга
- `isOnline` – буль, що сигналізує про стан друга: в мережі або ні.

Залежно від пропа `isOnline`, повинен змінюватися колір фону `span.status`. Це можна зробити за допомогою різних CSS-класів або Styled Components.

Компонент повинен створювати DOM наступної структури.

```html
<li class="item">
  <span class="status"></span>
  <img class="avatar" src="" alt="User avatar" width="48" />
  <p class="name"></p>
</li>
```

## Приклад використання

```js
import friends from 'путь/к/friends.json';

<FriendList friends={friends} />,
```
