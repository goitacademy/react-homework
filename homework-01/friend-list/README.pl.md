**Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Lista znajomych

Należy utworzyć komponent `<FriendList>`, przy pomocy którego możemy wyświetlać informację o znajomych użytkownika. Informacja o znajomych przechowywana jest w pliku [friends.json](./friends.json).

![Preview komponentu FriendList](./preview.jpg)

## Opis komponentu `<FriendList>`

Komponent powinien przyjmować jeden props `friends` - tablica obiektów znajomych.

Komponent powinien tworzyć DOM następującej struktury.

```html
<ul class="friend-list">
  <!-- Dowolna ilość FriendListItem -->
</ul>
```

## Opis komponentu `<FriendListItem>`

Komponent powinien przyjmować kilka propsów:

- `avatar` - odnośnik do awatara
- `name` - imię znajomego
- `isOnline` - wartość boolowska sygnalizująca status znajomego – jest lub nie ma go w sieci.

W zależności od propsu `isOnline`, powinien zmieniać się kolor tła `span.status`. Można to zrobić poprzez różne klasy CSS lub Styled Components.

Komponent powinien tworzyć DOM o następującej strukturze.

```html
<li class="item">
  <span class="status"></span>
  <img class="avatar" src="" alt="User avatar" width="48" />
  <p class="name"></p>
</li>
```

## Przykład wykorzystania

```js
import friends from 'trasa/do/friends.json';

<FriendList friends={friends} />,
```
