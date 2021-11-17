**Читать на других языках Czytaj w innych językach: [rosyjski](README.md), [ukraiński](README.ua.md).**

# Профиль социальной сети Profil w sieci społecznościowej

Необходимо создать компонент `<Profile>`, с помощью которого мы могли бы
отображать информацию о пользователе социальной сети. Данные о пользователе
лежат в файле [user.json](./user.json).

Należy stworzyć komponent `<Profile>`, przy pomocy którego możemy wyświetlać informacje o użytkowniku sieci społecznościowej. Dane o użytkowniku leżą w pliku [user.json](./user.json).

![Превью компонента Prewiev komponntu Profile](./preview.png)

## Описание компонента Opis komponentu `<Profile>`

Компонент должен принимать несколько пропсов с информацией о пользователе:
Komponent powinien przyjmować kilka propsów z informacją o użytkowniku:

- `username` — имя пользователя nazwa użytkownika
- `tag` — тег в социальной сети без `@` tag w sieci społęcznościowej bez `@`
- `location` — город и страна miasti i państwo 
- `avatar` — ссылка на изображение odnośnik do zdjęcia
- `stats` — объект с информацией об активности obiekt z informacją o aktywności

Компонент должен создавать DOM элемент следующей структуры.
Komponent powinen tworzyć element DOM o następującej strukturze.

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

## Пример использования Przykład wykorzystania

```js
import user from 'путь/к/user.json;

<Profile
  username={user.username}
  tag={user.tag}
  location={user.location}
  avatar={user.avatar}
  stats={user.stats}
/>
```
