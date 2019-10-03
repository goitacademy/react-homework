# Кабинет интернет банка

Необходимо создать компонент имитирующий операции в личном кабинете интернет
банка.

![reader preview](./mockup/preview.jpg)

Необходимо создать компоненты `<Dashboard>`, `<Controls>`, `<Balance>` и
`<TransactionHistory>` c необходимыми пропами и состоянием.

## Описание компонента Dashboard

Родительский компонент, контейнер. В состоянии компонент хранит историю
транзакций (массив объектов) в `state.transactions` и текущий баланс (число) в
`state.balance`, и пробрасывает необходимые данные своим детям как пропы.

Каждая транзакиця это объект следующего формата:

- `id` - уникальный идентификатор, строка. Для генерации id используй пакет
  [shortid](https://www.npmjs.com/package/shortid) или
  [uuid](https://www.npmjs.com/package/uuid).
- `type` - тип транзакции, один из двух, `deposit` или `withdrawal`, строка.
- `amount` - сумма транзакции, число.
- `date` - дата транзакции, результат метода `Date.prototype.toLocaleString()`,
  строка.

## Описание компонента Controls

В своем состоянии хранит текущее значения инпута (контролируемый компонент).

Должен принимать следующие пропы:

- `onDeposit(amount)` - функция, вызывается при нажатии на кнопку "Deposit",
  принимает сумму транзакции
- `onWithdraw(amount)` - функция, вызывается при нажатии на кнопку "Withdraw",
  принимает сумму транзакции

Если, при операции снятия денег, в инпут введено значение больше чем сейчас есть
на счету, должно появляться оповещение
`'На счету недостаточно средств для проведения операции!'` и операция снятия не
выполняется.

При попытке совершить банковскую операцию когда в инпуте введен `0`, должно
появляться оповещение `'Введите сумму для проведения операции!'` и операция не
выполняется.

Для оповещений используй компоненты
[react-toastify](https://github.com/fkhadra/react-toastify) или
[react-toast-notifications](https://github.com/jossmac/react-toast-notifications).

## Описание компонента Balance

Рендерит текущий баланс и общую сумму расходов и доходов клиента. Эти значения
получает как пропы:

- `balance` - текущий баланс
- `income` - общая сумма доходов
- `expenses` - общая сумма расходов

Для составления значений пропов `income` и `expenses` напиши функцию
высчитывающую общу сумму расходов/доходов из массива транзакций.

## Описание компонента TransactionHistory

Рендерит историю транзакций клиента. Получает один проп `items` - массив
объектов транзакций.

## HTML-разметка

В DOM-дерево должна генериться разметка следующей структуры.

```html
<!-- Разметка компонента <Dashboard> -->
<div class="dashboard">
  <!-- Разметка компонента <Controls> -->
  <section class="controls">
    <input type="number" name="amount" />
    <button type="button">Deposit</button>
    <button type="button">Withdraw</button>
  </section>

  <!-- Разметка компонента <Balance> -->
  <section class="balance">
    <span>⬆️2000$</span>
    <span>⬇️1000$</span>
    <span>Balance: 5000$</span>
  </section>

  <!-- Разметка компонента <TransactionHistory> -->
  <table class="history">
    <thead>
      <tr>
        <th>Transaction</th>
        <th>Amount</th>
        <th>Date</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Deposit</td>
        <td>200$</td>
        <td>4/17/2019, 12:45:17</td>
      </tr>
      <tr>
        <td>Withdrawal</td>
        <td>100$</td>
        <td>4/18/2019, 14:15:23</td>
      </tr>
    </tbody>
  </table>
</div>
```

## Пример использования

```js
ReactDOM.render(<Dashboard />, document.getElementById('root'));
```
