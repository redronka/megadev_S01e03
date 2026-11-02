# megadev_C03

Analiza zgłoszenia #4471 z kursu MEGA.dev. Źródło: eksport bazy wiedzy z 2026-10-04.

## Wynik

Nowa strona: `src/routes/kb/incidents/4471-review/+page.svx`.
Wyrenderowana wersja: `build/kb/incidents/4471-review/index.html`.
Oryginalne strony i komponenty zachowano. Nowa strona używa ich logiki do obliczania tabel i wykresu. Akceptowanej decyzji 0001 nie zmieniono.

## Uruchomienie

Wymagane Node.js i npm. Dokładne wersje zależności zapisuje `package-lock.json`.

```sh
npm ci
npm run build
npm run preview
```

Otwórz `/kb/incidents/4471-review/` na adresie lokalnym pokazanym przez serwer.
Strony HTML zawierają wynik renderowania na serwerze. Zasoby w `build/_app/` zapewniają style i interakcję po otwarciu przez serwer HTTP. Nie wymaga to GitHub Pages.

Reguły eksportu: `EXPORT-README.md`.
