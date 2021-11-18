**Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Widget odpowiedzi

Jak większość spółek, kawiarnia Expresso zbiera informacje zwrotne od swoich klientów. Twoim zadaniem jest utworzenie aplikacji dla zbierania statystyk. Istnieją tylko trzy warianty odpowiedzi: dobra, neutralna i zła.

## Krok 1

Aplikacja powinna wyświetlać ilość zebranych odpowiedzi dla każdej kategorii. Aplikacja nie powinna zapisywać statystyk odpowiedzi między różnymi sesjami (aktualizacja strony).

Stan aplikacji powinien wyglądać następująco, nie należy dodawać nowych właściwości.

```bash
state = {
  good: 0,
  neutral: 0,
  bad: 0
}
```

Interfejs może wyglądać tak.

![preview](./mockup/step-1.png)

## Krok 2

Rozszerz funkcjonalność aplikacji tak, by w interfejsie wyświetlało się więcej statystyk z zebranych odpowiedzi. Dodaj wyświetlanie ogólnej ilości zebranych odpowiedzi ze wszystkich kategorii i procent pozytywnych odpowiedzi. W tym celu stwórz metody wspomgające `countTotalFeedback()` i `countPositiveFeedbackPercentage()`, podliczające te wartości, bazując na danych w stanie (wyliczane dane).

![preview](./mockup/step-2.png)

## Krok 3

Przeprowadź refaktor aplikacji. Stan aplikacji powinien pozostawać w głównym komponencie `<App>`.

- Przenieś wyświetlanie statystyki do oddzielnego komponentu
  `<Statistics good={} neutral={} bad={} total={} positivePercentage={}>`.
- Przenieś blok przycisków do komponentu
  `<FeedbackOptions options={} onLeaveFeedback={}>`.
- Utwórz komponent `<Section title="">`, który renderuje sekcję z nagłówkami i dzieci (children). Obróć każdy z `<Statistics>` i `<FeedbackOptions>` w utworzony komponent sekcji.

## Krok 4

Rozszerz funkcjonalność aplikacji tak, by blok statystyki renderował się tylko po nadejściu przynajmniej jednej odpowiedzi. Wiadomość o braku statystyk przenieś do komponentu `<Notification message="There is no feedback">`.

![preview](./mockup/preview.gif)
