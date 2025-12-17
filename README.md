# ExamsFileMetaScrubber

Et lite åpent verktøy (HTML + JS) for å anonymisere metadata i Office/OOXML (`.docx/.xlsx/.pptx` + makrovarianter) og ODF (`.odt/.ods/.odp`) – **uten å endre innholdet**, og **uten opplasting** (klientside, kan kjøres offline).

## Slik bruker du
- Åpne `index.html` i Edge/Chrome.
- Dra og slipp dokumenter i boksen.
- Trykk **Scrub Files** – du får nedlastet «`- ANONYM`» kopier.

## JSZip
Verktøyet trenger [JSZip](https://stuk.github.io/jszip/) for å lese/skrives ZIP (OOXML/ODF er ZIP + XML). Vi laster JSZip slik:
1. **CDN først**: `https://cdn.jsdelivr.net/npm/jszip@3.10.1/dist/jszip.min.js`.
2. **Fallback**: lokal `jszip.min.js` ved siden av `index.html` (for ren offline).

> Hvis du vil ha *fullt offline*, last ned `jszip.min.js` og legg den i samme mappe som `index.html`.

## GitHub-hosting (åpenhet)
- Legg filene i et åpent repo.
- Aktiver **GitHub Pages** (Settings → Pages → Source: `main` → `/(root)`), så kan siden brukes direkte fra repoet.
- Da vil CDN-lastingen fungere automatisk.

## Hva fjernes/blankes
- **OOXML**: `docProps/core.xml` (forfatter, sist endret av, m.m.), tidsstempler (`created/modified`), `revision`; `docProps/app.xml` (`Company`, `Manager`, `HyperlinkBase`, `LastSavedBy`); `docProps/custom.xml` fjernes; kommentarforfattere i Word/Excel/PowerPoint anonymiseres; Excel `xl/persons/person.xml` blankes.
- **ODF**: `meta.xml` (`dc:creator`, `meta:initial-creator`, `meta:keyword`, tittel/subject/description/date, `meta:user-defined`).

## Begrensninger
- Gamle binærformater (`.doc/.xls/.ppt`) må konverteres til OOXML.
- **Track Changes** i Word kan inneholde forfatternavn i revisjoner; verktøyet endrer ikke disse for å unngå risiko. Bruk «Dokumentinspektør» i Office.
- Plattformmetadata (OneDrive/SharePoint) kan vise «Sist endret av» selv om filen er anonym; del lokale kopier.

## Lisens
MIT License – se `LICENSE`.
