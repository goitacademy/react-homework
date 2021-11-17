**Читать на других языках: Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Список друзей Lista znajomych

Необходимо создать компонент `<FriendList>`, с помощью которого мы могли бы
отображать информацию о друзьях пользователя. Информация о друзьях хранится в
файле [friends.json](./friends.json).

Należy utworzyć komponent `<FriendList>`, przy pomocy którego możemy wyświetlać informację o znajomych użytkownika. Informacha o znajomych przechowywana jest w pliku [friends.json](./friends.json).

![Превью компонента Prewiev komponentu FriendList](./preview.jpg)

## Описание компонента Opis komponentu `<FriendList>`

Компонент должен принимать один проп `friends` - массив объектов друзей.
Komponent powinien przyjmować jeden props `friends` - tablica obiektów znajomych.

Компонент должен создавать DOM следующей структуры.
Komponent powinien tworzyć DOM następującej struktury.

```html
<ul class="friend-list">
  <!-- Произвольное кол-во Dowolna ilość FriendListItem -->
</ul>
```

## Описание компонента Opis komponentu `<FriendListItem>`

Компонент должен принимать несколько пропов:
Komponent powinien przyjmować kilka propsów:

- `avatar` - ссылка на аватар odnośnik do awatara
- `name` - имя друга imię znajomego
- `isOnline` - буль сигнализирующий о состоянии друга, в сети или нет. wartość boolowska sygnalizująca status znajomego – jest lub nie ma go w sieci.

В зависимости от пропа `isOnline`, должен меняться цвет фона `span.status`. Это
можно сделать через разный CSS-класс или Styled Components.

W zależności od propsa `isOnline`, powinien zmieniać się kolor tła `span.status`. Można to zrobić poprze różne klasy CSS lub Styled Components.

Компонент должен создавать DOM следующей структуры.

Komponent powinien tworzyć DOM o następującej strukturze.

```html
<li class="item">
  <span class="status"></span>
  <img class="avatar" src="" alt="User avatar" width="48" />
  <p class="name"></p>
</li>
```

## Пример использования Przykład wykorzystania

```js
import friends from 'путь/к/friends.json';

<FriendList friends={friends} />,
```
