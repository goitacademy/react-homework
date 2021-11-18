**Czytaj w innych językach: [rosyjski](README.md), [ukraiński](README.ua.md).**

# Historia transakcji

Należy utworzyć komponent historii transakcji na koncie osobistym banku internetowego.

![Preview komponentu TransactionHistory](./preview.jpg)

Dane do listy dostępne w formacie JSON w pliku [transactions.json](./transactions.json). To tablica obiektów, każdy obiekt opisuje jedną transakcję z następującymi właściwościami:

- `id` — indywidualny identyfikator transakcji
- `type` — typ transakcji
- `amount` - kwota transakcji
- `currency` - typ waluty

## Opis komponentu `<TransactionHistory>`

Należy utworzyć komponent `<TransactionHistory>` przyjmujący jeden props `items` - tablicę obiektów transakcji z `transactions.json`. Komponent tworzy układ tablicy. W przykładzie widać układ dwóch transakcji.

```html
<table class="transaction-history">
  <thead>
    <tr>
      <th>Type</th>
      <th>Amount</th>
      <th>Currency</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>Invoice</td>
      <td>125</td>
      <td>USD</td>
    </tr>
    <tr>
      <td>Withdrawal</td>
      <td>85</td>
      <td>USD</td>
    </tr>
  </tbody>
</table>
```

## Przykład wykorzystania

```js
import transactions from 'droga/do/transactions.json';

<TransactionHistory items={transactions} />;
```
