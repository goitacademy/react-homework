**Читать на других языках: Czytaj w innych językach [rosyjski](README.md), [ukraiński](README.ua.md).**

# Виджет отзывов Widget odpowiedzi

Как и большинство компаний, кафе Expresso собирает отзывы от своих клиентов.
Твоя задача - создать приложение для сбора статистики. Есть всего три варианта
обратной связи: хорошо, нейтрально и плохо.

Jak większość spółek, kawiarnia Expresso zbiera informacje zwrotne od swoich klientów. Twoim zadaniem jest utworzenie aplikacji dla zbierania statystyk. Istnieją tylko trzy warianty odpowiedzi: dobry, neutralny i zły.

## Шаг 1 Krok 1

Приложение должно отображать количество собранных отзывов для каждой категории.
Приложение не должно сохранять статистику отзывов между разными сессиями
(обновление страницы).

Aplikacja powinna wyświetlać ilość zebranych odpowiedzi dla każdej kategorii. Aplikacja nie powinna zapisywać statystyk odpowiedzi między różnymi sesjami (aktualizacja strony).

Состояние приложения обязательно должно быть следующего вида, добавлять новые
свойства нельзя.

Stan aplikacji powinien wyglądać następująco, nie powinno się dodawać nowych właściwości.

```bash
state = {
  good: 0,
  neutral: 0,
  bad: 0
}
```

Интерфейс может выглядеть так. Interfejs może wyglądać tak.

![preview](./mockup/step-1.png)

## Шаг 2 Krok 2

Расширь функционал приложения так, чтобы в интерфейсе отображалось больше
статистики о собранных отзывах. Добавь отображение общего количества собранных
отзывов из всех категорий и процент положительных отзывов. Для этого создай
вспомогательные методы `countTotalFeedback()` и
`countPositiveFeedbackPercentage()`, подсчитывающие эти значения основываясь на
данных в состоянии (вычисляемые данные).

Rozszerz funkcjonalność aplikacji tak, by w interfejsie wyświetlało się więcej statystyk z zebranych odpowiedzi. Dodaj wyświetlanie ogólnej ilości zebranych odpowiedzi ze wszystkich kategorii w procent pozytywnych odpowiedzi. W tym celu stwórz metody wspomgające `countTotalFeedback()` i `countPositiveFeedbackPercentage()`, podliczające te wartości, bazując na danych w stanie (wyliczane dane).

![preview](./mockup/step-2.png)

## Шаг 3 Krok 3

Выполни рефакторинг приложения. Состояние приложения должно оставаться в
корневом компоненте `<App>`.

Przeprowadź refaktor aplikacji. Stan aplikacji powinien pozostawać w głównym komponencie `<App>`.

- Вынеси отображение статистики в отдельный компонент
Przenieś wyświetlanie statystyki do oddzielnego komponentu
  `<Statistics good={} neutral={} bad={} total={} positivePercentage={}>`.
- Вынеси блок кнопок в компонент Przenieś blok przycisków do komponentu
  `<FeedbackOptions options={} onLeaveFeedback={}>`.
- Создай компонент `<Section title="">`, который рендерит секцию с заголовком и
  детей (children). Оберни каждый из `<Statistics>` и `<FeedbackOptions>` в
  созданный компонент секции.
  Utwórz komponent `<Section title="">`, który renderuje sekcję z nagłówkami i dzieci (children). Obróć każdy z `<Statistics>` i `<FeedbackOptions>` w utworzony komponent sekcji.

## Шаг 4 Krok 4

Расширь функционал приложения так, чтобы блок статистики рендерился только после
того, как был собран хотя бы один отзыв. Сообщение об отсутствиии статистики
вынеси в компонент `<Notification message="There is no feedback">`.

Rozszerz funkcjonalnośc aplikacji tak, by blok statystyki renderował się tylko po tym, jak nadeszła przynajmniej jedn odpowiedź. Wiadomość o braku statystyk przenieś do komponentu `<Notification message="There is no feedback">`.

![preview](./mockup/preview.gif)
