**Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Książka telefoniczna

Napisz aplikację do przechowywania kontaktów w książce telefonicznej.

## Krok 1

Aplikacja powinna składać się z formularza i listy kontaktów. W tym kroku zrealizuj dodanie nazwy kontaktu i wyświetlanie listy kontaktów. Aplikacja nie powinna zapisywać kontaktów między różnymi sesjami (aktualizacja strony).

Wykorzystaj układ input z wmontowaną walidacją nazwy kontaktu.


```html
<input
  type="text"
  name="name"
  pattern="^[a-zA-Zа-яА-Я]+(([' -][a-zA-Zа-яА-Я ])?[a-zA-Zа-яА-Я]*)*$"
  title="Name may contain only letters, apostrophe, dash and spaces. For example Adrian, Jacob Mercer, Charles de Batz de Castelmore d'Artagnan"
  required
/>
```
Stan przechowywany w komponencie rodzicu `<App>` powinien wyglądać następująco, nie należy dodawać nowych właściwości.

```bash
state = {
  contacts: [],
  name: ''
}
```

Każdy kontakt powinien być obiektem z właściwościami `name` i `id`. Do generowania identyfikatorów wykorzystaj dowolną pasującą paczkę, na przykład [nanoid](https://www.npmjs.com/package/nanoid). Po tym kroku aplikacja powinna wyglądać mniej więcej tak.

![preview](./mockup/step-1.png)

## Krok 2

Rozszerz funkcjonalność aplikacji, pozwalając użytkownikom dodawać numery telefonów. W tym celu dodaj do formularza `<input type="tel">` oraz właściwość dla przechowywania jego wartości w stanie.

```bash
state = {
  contacts: [],
  name: '',
  number: ''
}
```

Wykorzystaj układ input z wmontowaną walidacją numeru kontaktu.

```html
<input
  type="tel"
  name="number"
  pattern="\+?\d{1,4}?[-.\s]?\(?\d{1,3}?\)?[-.\s]?\d{1,4}[-.\s]?\d{1,4}[-.\s]?\d{1,9}"
  title="Phone number must be digits and can contain spaces, dashes, parentheses and can start with +"
  required
/>
```

Po tym kroku aplikacja powinna działać mniej więcej tak.

![preview](./mockup/step-2.png)

## Krok 3

Dodaj pole wyszukiwania, które można wykorzystać do filtrowania listy kontaktów po nazwie.

- Pole wyszukiwania to input bez formularza, którego wartość zapisuje się w stanie (kontrolowany element).
- Logika filtrowania powinna być niewrażliwa na wielkość liter.

```bash
state = {
  contacts: [],
  filter: '',
  name: '',
  number: ''
}
```

![preview](./mockup/step-3.gif)

Gdy pracujemy nad nową funkcjonalnością, wygodne może być twarde zakodowanie niektórych danych w stanie. Sprawi to, że nie będziemy musieli ręcznie wprowadzać danych do interfejsu, aby przetestować pracę nowej funkcjonalności. Można na przykład wykorzystać taki stan początkowy.

```bash
state = {
  contacts: [
    {id: 'id-1', name: 'Rosie Simpson', number: '459-12-56'},
    {id: 'id-2', name: 'Hermione Kline', number: '443-89-12'},
    {id: 'id-3', name: 'Eden Clements', number: '645-17-79'},
    {id: 'id-4', name: 'Annie Copeland', number: '227-91-26'},
  ],
  filter: '',
  name: '',
  number: ''
}
```

## Krok 4

Jeżeli twoja aplikacja jest realizowana w jednym komponencie `<App>`, wykonaj refaktor, rozdzielając pasujące części do oddzielnych komponentów. W stanie głównego komponentu `<App>` zostaną tylko właściwości `contacts` i `filter`.

```bash
state = {
  contacts: [],
  filter: ''
}
```
Wystarczy wydzielić cztery komponenty: formularz dodania kontaktów, listę kontaktów, element listy kontaktów i filtr wyszukiwania.

Po refaktorze źródłowy komponent aplikacji będzie wyglądał tak.

```jsx
<div>
  <h1>Phonebook</h1>
  <ContactForm ... />

  <h2>Contacts</h2>
  <Filter ... />
  <ContactList ... />
</div>
```

## Krok 5

Wyłącz użytkownikowi możliwość dodawania kontaktów, których nazwy są już w książce telefonicznej. W razie próby wykonania takiego działania, pokaż `alert` z ostrzeżeniem.

![preview](./mockup/step-5.png)

## Krok 6

Rozszerz funkcjonalność aplikacji, pozwalając użytkownikowi usuwać wcześniej zapisane kontakty.

![preview](./mockup/step-6.gif)
