# piotrpilka-site

Osobista strona CV / portfolio Piotra Piłki. Jeden samowystarczalny plik `index.html`
(zdjęcie, PDF CV, czcionki wpięte inline). Brak kroku budowania.

## Hosting i wdrożenie

- Strona stoi na **GitHub Pages** pod **https://piotrpilka.pl** (własna domena przez plik `CNAME`)
  oraz pod `https://piotrpilka123-ctrl.github.io/piotrpilka-site/`.
- **Wdrożenie jest automatyczne po każdym `git push` do gałęzi `main`.**
  Robi to workflow `.github/workflows/deploy.yml` (Pages `build_type: workflow`).
  Nie ma osobnego kroku „deploy" — push = publikacja.
- HTTPS jest wymuszony. DNS w OVH: rekordy `A` apeksa → adresy GitHub Pages,
  `www` `CNAME` → `piotrpilka123-ctrl.github.io.`

## Zasady pracy w tym repo

- Po **każdej** zmianie w `index.html` (lub innych plikach strony) od razu wykonaj
  `git add` → `git commit` → `git push`. Zmiana ma trafiać na produkcję automatycznie,
  bez pytania o osobne wdrożenie.
- Trzymaj całość w jednym `index.html`. Nie dziel na dodatkowe pliki, nie dodawaj
  bundlera ani frameworka.
- **Nie usuwaj pliku `CNAME`** — jego brak odłącza własną domenę `piotrpilka.pl`.
- Aktualizacja z nową wersją pliku:
  `cp ~/Downloads/index.html . && git add . && git commit -m "aktualizacja" && git push`

## Pliki

- `index.html` — cała strona
- `CNAME` — własna domena (`piotrpilka.pl`)
- `.github/workflows/deploy.yml` — workflow wdrożenia na GitHub Pages
