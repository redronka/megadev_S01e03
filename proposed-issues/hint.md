# booking-v3 pokazuje błędny format daty — 33 raporty z #4471

## Problem
Formularz booking-v3 pokazuje MM/DD/YYYY. Użytkownik wpisuje datę według podpowiedzi, lecz formularz odczytuje ją według kolejności dzień/miesiąc klienta. To oddzielny problem od wspólnego parsera.

## Zakres
33 unikalne raporty od 3 klientów: alder.physio, copper.studio, pale.harbour. Pierwszy raport: 2026-04-17. Ostatni: 2026-09-22.

## Źródło i reguła
Eksport z 2026-10-04: `reports-4471.json`, `uniqueById`, filtr `mergedInto === 4471`, katalog klientów i `causeOf` w `src/lib/kb/causes.ts`. Warunki: klient z kolejnością dzień/miesiąc, kanał form i booking-v3. Etykiety wejściowe tej grupy: parser 15, hint 18. Nie klasyfikować według locale przeglądarki ani samego tematu.

## Kryteria naprawy
Podpowiedź, walidacja i odczyt formularza stosują ten sam format daty klienta. Sprawdzić osobno formularz booking-v3 oraz pozostałe kanały tego samego klienta. Naprawa parsera nie zastępuje naprawy podpowiedzi.
