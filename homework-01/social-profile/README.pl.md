**Czytaj w innych językach: [rosyjski](README.md), [ukraiński](README.ua.md).**

# Profil w sieci społecznościowej

Należy stworzyć komponent `<Profile>`, przy pomocy którego możemy wyświetlać informacje o użytkowniku sieci społecznościowej. Dane o użytkowniku znajdują się w pliku [user.json](./user.json).

![Preview komponentu Profile](./preview.png)

## Opis komponentu `<Profile>`

Komponent powinien przyjmować kilka propsów z informacją o użytkowniku:

- `username` — nazwa użytkownika
- `tag` — tag w sieci społecznościowej bez `@`
- `location` — miasto i państwo 
- `avatar` — odnośnik do zdjęcia
- `stats` — obiekt z informacją o aktywności

Komponent powinien tworzyć element DOM o następującej strukturze.

```html
<div class="profile">
  <div class="description">
    <img
      src="https://cdn-icons-png.flaticon.com/512/1077/1077012.png"
      alt="User avatar"
      class="avatar"
    />
    <p class="name">Petra Marica</p>
    <p class="tag">@pmarica</p>
    <p class="location">Salvador, Brasil</p>
  </div>

  <ul class="stats">
    <li>
      <span class="label">Followers</span>
      <span class="quantity">1000</span>
    </li>
    <li>
      <span class="label">Views</span>
      <span class="quantity">2000</span>
    </li>
    <li>
      <span class="label">Likes</span>
      <span class="quantity">3000</span>
    </li>
  </ul>
</div>
```

## Przykład wykorzystania

```js
import user from 'droga/do/user.json;

<Profile
  username={user.username}
  tag={user.tag}
  location={user.location}
  avatar={user.avatar}
  stats={user.stats}
/>
```
