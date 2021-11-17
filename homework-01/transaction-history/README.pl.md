**Читать на других языках Czytaj w innych językach: [rosyjski](README.md), [ukraiński](README.ua.md).**

# История транзакций Historia transakcji

Необходимо создать компонент истории транзакций в личном кабинете интернет
банка.
Należy utworzyć komponent historii transakcji na koncie osobistym banku internetowego.

![Превью компонента Preview komponentu TransactionHistory](./preview.jpg)

Данные для списка доступны в формате JSON в файле
[transactions.json](./transactions.json). Это массив объектов, каждый объект
описывает одну транзакцию со следующими свойствами:

Dane do listy dostępne w formcie JSON w pliku [transactions.json](./transactions.json). To tablica obiektów, każdy obiekt opisuje jedną transakcję z następującymi właściwościami:

- `id` — уникальный идентификатор транзакции indywidualny identyfikator transakcji
- `type` — тип транзакции typ transakcji
- `amount` - сумма транзакции kwota transakcji
- `currency` - тип валюты typ waluty

## Описание компонента Opis komponentu `<TransactionHistory>`

Необходимо создать компонент `<TransactionHistory>` принимающий один проп
`items` - массив объектов транзакций из `transactions.json`. Компонент создает
разметку таблицы. Каждая транзакция это строка таблицы. В примере приведена
разметка двух транзакций.

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

## Пример использования Przykład wykorzystania

```js
import transactions from 'путь/к/transactions.json';

<TransactionHistory items={transactions} />;
```
