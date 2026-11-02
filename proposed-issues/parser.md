# Parser zamienia dzień z miesiącem — 379 raportów z #4471

## Problem
Wspólny parser odczytuje daty w kolejności miesiąc/dzień. Dla klientów używających kolejności dzień/miesiąc zmienia to datę rezerwacji.

## Zakres
379 unikalnych raportów od 11 klientów. Pierwszy raport: 2026-04-01. Ostatni: 2026-10-04. Źródło: eksport z 2026-10-04, `reports-4471.json`, po `uniqueById` i filtrze `mergedInto === 4471`; klasyfikacja przez `groupByCause` i katalog klientów.

## Przykład
R-41200: harbour.dental, kanał app. Przypomnienie na 7 kwietnia wysłano na 4 lipca. Raport R-41201 opisuje odwrotną zamianę. Zachować dzień i miesiąc zgodne z formatem klienta.

## Klasyfikacja
Używać locale klienta i kanału, zgodnie z `src/lib/kb/causes.ts`. Nie grupować po temacie ani `meta.intakeTag`. Etykiety wejściowe tej grupy: parser 356, hint 23.

Pięć raportów wskazanych przez `desk-notes.json` opisano jako przesunięcie o jeden dzień. Funkcja `readAs` pokazuje je jako przypis w grupie parser. Nie liczyć ich ponownie ani jako potwierdzonej trzeciej przyczyny.

## Kryteria naprawy
Daty klienta z kolejnością dzień/miesiąc zachowują dzień i miesiąc. Wspólny parser ma jawny format wejściowy. Osobno sprawdzić błąd podpowiedzi formularza booking-v3.
