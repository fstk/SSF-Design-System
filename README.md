# SSF Home · Design System Foundation

Token-basierte Foundation für das SSF-Home-Intranet. Liefert das Schrift-, Farb-, Spacing-, State- und UI-Token-System sowie die zugehörigen Basis-Stile in einer einheitlichen Schicht. Schrift: **Geist**.

---

## Schnellstart

CSS in den `<head>` einbinden — Token-Datei zuerst, weil die Foundation auf ihre Variablen zugreift:

```html
<link rel="stylesheet" href="ssf-tokens.css">
<link rel="stylesheet" href="ssf-foundation.css">
```

Schriften liegen unter `assets/font/` und werden über `@font-face` in `ssf-tokens.css` referenziert. Pfade sind relativ zur Token-Datei.

---

## Datei-Struktur

```
.
├── README.md                       ← dieses Dokument
├── CHANGELOG.md                    ← Versionshistorie
├── LICENSE                         ← Nutzungsbedingungen
├── ssf-tokens.css                  ← Design-Tokens (CSS-Variablen, @font-face)
├── ssf-foundation.css              ← Basis-Stile auf Token-Basis
├── design-system-foundation.html   ← visuelle Dokumentation
└── assets/
    ├── font/                       ← Geist-Schriftdateien (woff2)
    └── logo/                       ← SSF-Logo (SVG)
```

---

## Visuelle Dokumentation

`design-system-foundation.html` zeigt jeden Token im Kontext mit Code-Referenz. Sektionen:

- **Marke** – Logo, Schutzzone, Negativ-Variante
- **Farben** – Primär (Digital), Grün, Orange, Blau Classic, Accent-Lime, Verlauf, Neutral
- **Typografie** – H1 bis H6, Card-Titel, Text-large, Body, Body-small, Caption, Footnote, Blockquote, Inline-Link
- **Abstände** – Spacer-Skala (4 / 8 / 16 / 24 / 32 / 48 / 100), Sektions-Abstände
- **States** – Focus-Ring, Disabled, semantische Banner (Error / Success / Info)
- **UI-Tokens** – Form-Inputs, Tags / Badges, Avatare
- **Buttons** – primärer Link-Button (`.c-btn`)
- **Layout** – Object-Layout (`.o-row` / `.o-col`)

Lokal öffnen oder als GitHub Page bereitstellen.

---

## Naming-Conventions

### CSS-Variablen (`ssf-tokens.css`)

| Präfix | Bedeutung | Beispiel |
|--------|-----------|----------|
| `--primary-font`, `--heading-font` | Schrift-Basis | `--primary-font: "Geist", sans-serif` |
| `--blue-*`, `--green-*`, `--orange-*` | Farb-Familien (inkl. `-hell`, `-alpha-10`) | `--blue-digital-hell: #d1d8ff` |
| `--spacer-N` | Abstands-Skala | `--spacer-24: 2.4rem` (≈ 24 px) |
| `--typo-{level}-{prop}` | Typografische Stufen | `--typo-h5-size: 1.9rem` |
| `--focus-ring-*`, `--state-disabled-opacity` | States | `--focus-ring-color: var(--blue-digital)` |
| `--color-error/success/info/warning` | Semantische Farb-Aliase | `--color-error: var(--orange)` |
| `--input-*` | Form-Felder | `--input-radius: 0.6rem` |
| `--tag-*` | Tag / Badge | `--tag-bg-default: var(--blue-classic-alpha-10)` |
| `--avatar-size-sm/md/lg` | Avatar | `--avatar-size-md: 4rem` |
| `--radius-card`, `--container-*` | Layout-Werte | `--container-padding: 2.4rem` |

### CSS-Klassen (`ssf-foundation.css`)

| Präfix | Zweck | Beispiel |
|--------|-------|----------|
| `.o-*` | **Object** – wiederverwendbare Typografie- / Layout-Bausteine | `.o-h1`, `.o-body-small`, `.o-link`, `.o-row`, `.o-container` |
| `.c-*` | **Component** – konkrete UI-Komponente | `.c-btn` |
| `.ds-*` | **Doku-Hilfsklassen** – ausschließlich im Foundation-HTML verwendet | `.ds-section`, `.ds-swatch`, `.ds-state-card` |
| `.card-title-h5` | Karten-Titel (eigene Größe, kein semantisches H5) | `.card-title-h5` |

Für die Anwendung im Intranet nur `.o-*` und `.c-*` verwenden; `.ds-*` ist Doku-internes Markup.

---

## rem-Logik

In `ssf-foundation.css` ist `html { font-size: 62.5% }` gesetzt — damit gilt **1 rem ≈ 10 px** bei Browser-Standardgröße. Alle `rem`-Werte folgen dieser Konvention; die `px`-Angaben in den Code-Beschreibungen sind Referenzwerte bei dieser Basis. Ändern Nutzer:innen die Browser-Basis, skalieren `rem`-Werte automatisch mit.

---

## Tokens erweitern

Neue Tokens werden so eingepflegt:

1. **Token in `ssf-tokens.css`** im passenden thematischen Block ergänzen. Neue Kategorie → eigener Kommentarblock.
2. **Token in `ssf-foundation.css` referenzieren** (kein direktes Hex / px).
3. **In `design-system-foundation.html` dokumentieren** — Muster + Code-Beschreibung in der grauen Leiste, analog zu den bestehenden Tokens.
4. Diese README ergänzen, wenn es sich um eine neue Kategorie oder Konvention handelt.

---

## Inhalt der Foundation

| Bereich | Enthalten |
|---------|-----------|
| Token-System (Farben, Spacings, Typografie, States, Form, Tag, Avatar) | ✓ |
| Basis-Stile (Typo-Klassen, Buttons, Layout, Logo) | ✓ |
| Visuelle Dokumentation mit On-Page-Navigation | ✓ |
| Schrift-Dateien (Geist, woff2) | ✓ |

---

## Version

Aktuelle Version: **v0.1.0** — siehe [`CHANGELOG.md`](./CHANGELOG.md).

---

## Erstellt von

[ediundsepp GmbH](https://ediundsepp.de) für die SSF Ingenieure AG.
