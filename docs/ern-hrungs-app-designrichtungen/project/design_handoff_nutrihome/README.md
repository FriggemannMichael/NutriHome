# Handoff: NutriHome PWA – UI-Design & Prototyp

## Überblick
NutriHome ist eine mobile-first, installierbare PWA für die gemeinsame Organisation gesunder Ernährung in einem Haushalt (2 Personen, später mehr). Dieses Paket enthält die **Design-Referenzen** für den ersten Entwicklungsumfang: Auth/Onboarding, Startseite, Rezepte (Liste + Detail mit Portionsberechnung), Kochmodus, Wochenplan, Einkaufsliste und Vorrat.

Fachliche Grundlage ist das Pflichtenheft (MVP-Umfang, Abschnitte 8, 14, 16). Der Produkt-Kern ist die **live rechnende Portions-/Nährwert-/Kostenberechnung**.

## Über die Design-Dateien
Die HTML-Dateien in diesem Bundle sind **Design-Referenzen**, erstellt als interaktive Prototypen — sie zeigen Aussehen und Verhalten, **sind aber kein Produktionscode zum Kopieren**. Aufgabe ist es, diese Designs im **Ziel-Stack nachzubauen**:

- **Frontend:** Angular + TypeScript, SCSS, Angular Service Worker (PWA), IndexedDB (Offline), optional Angular Material oder eigene Komponenten.
- **Backend:** Django + Django REST Framework + PostgreSQL (siehe Pflichtenheft 10.2 / API-Konzept 13).

Die HTML-Prototypen wurden mit einem React-artigen Template-Runtime gebaut — **diese Runtime nicht übernehmen**. Nur Layout, Tokens, Copy und Interaktionslogik als Vorlage nutzen und in idiomatischem Angular (Standalone-Components oder Feature-Module, Reactive Forms, Services, Signals/RxJS) umsetzen.

## Fidelity
**High-Fidelity.** Farben, Typografie, Abstände, Radien und Interaktionen sind final und folgen dem NutriHome Design System (siehe `NutriHome Style Guide.dc.html`). Die UI sollte pixelnah mit Angular-Komponenten nachgebaut werden; Werte unten sind verbindlich.

Die Datei `NutriHome Wireframes.dc.html` ist dagegen **Low-Fidelity** (frühe Struktur-Exploration) und dient nur als Kontext für alternative Layouts — nicht als Styling-Vorlage.

---

## Design Tokens

### Farben
| Rolle | Name | Hex |
|---|---|---|
| Dominant / Text / dunkle Flächen | Space Cadet | `#332D56` |
| Sekundär / Primär-Button / aktiv | Verdigris | `#71C0BB` |
| Interaktiv / Progress / Links | Verdigris Deep | `#3E8C87` |
| Gedämpfter Text / Fett-Makro | Cadet Soft | `#8B83B0` |
| Akzent / Budget / Sekundär-Button | Cream | `#E3EEB2` |
| App-Hintergrund | Cream Wash | `#F4F7EA` |
| Kartenrahmen | Border | `#E3E6D2` |
| Trennlinie (innen) | Divider | `#F0F2E3` |
| Track (Progress-Hintergrund) | Track | `#EEF1DF` |
| Erfolg / gut gefüllt | Success | `#5FA85B` |
| Warnung / Carbs-Makro | Warn | `#E0A94B` (Text-Variante `#C08A2E`) |
| Fehler / MHD kritisch | Danger | `#B14A28` |
| Platzhaltertext | Muted | `#B0AAC6` |

Makro-Farbcodierung (durchgängig): **Protein** `#3E8C87`, **Kohlenhydrate** `#E0A94B`/`#C08A2E`, **Fett** `#8B83B0`, **Ballaststoffe** `#5FA85B`.

Store-/Laden-Chips: Rewe `#B14A28`, Aldi `#2A6BB0`, Lidl `#C08A2E`, dm `#A0447A` (jeweils Text auf 10–16 % getöntem Hintergrund).

### Typografie
- **Bricolage Grotesque** (600/700/800) – Headlines, Screen-Titel, Karten-Überschriften. Titel: `letter-spacing:-.02em`.
- **Manrope** (400–800) – Fließtext, Labels, Buttons (Buttons 800).
- **Space Mono** (400/700) – **alle Zahlen**: kcal, €, Mengen, Uhrzeit, Codes, Prozentwerte, Mono-Labels (`letter-spacing:.08em`, uppercase für Labels).

Skala (Mobil): Screen-Titel 26–27px/800 Bricolage · Karten-Titel 16px/700 Bricolage · Body 14–15px/600 Manrope · Meta/Labels 10–12px · Zahlen 13–21px Space Mono.

### Radius
Klein (Buttons/Inputs) `12–14px` · Standard (innere Karten) `18px` · Karte `22px` · Pill/Tag/Progress `999px` · Telefon-Screen `35px`.

### Abstände
Screen-Padding horizontal `18px` (Auth `26px`). Vertikaler Gap zwischen Karten `14–15px`. Karten-Innenpadding `16–20px`. Icon-Tap-Ziele ≥ `40px` (Pflichtenheft 9.1).

### Schatten
Sehr dezent. Karten meist nur `1px solid #E3E6D2` ohne Schatten. Telefon-Rahmen `0 24px 60px rgba(51,45,86,.32)`. Toast `0 6px 20px rgba(51,45,86,.3)`.

---

## Screens / Views

Bildschirmgröße im Prototyp: 368×772 (Content-Bereich innerhalb des Telefonrahmens). Layout ist mobile-first, eine Spalte, feste Bottom-Nav.

### 1. Login (`/login`)
- **Zweck:** Anmeldung im Haushalt (Pflichtenheft 8.1).
- **Layout:** Zentriertes Logo (60px, Radius 20px, Verdigris-Fläche, Blatt-Icon Space Cadet), Titel „Willkommen zurück" (30/800 Bricolage), Untertitel Cadet Soft. Darunter Formular-Gruppe (E-Mail, Passwort) mit Mono-Labels über weißen Input-Feldern (Border `#E3E6D2`, Radius 14, Icon links). „Passwort vergessen?" rechtsbündig, Verdigris Deep. Primär-Button „Anmelden" (Verdigris, Text Space Cadet, 800). Fußzeile „Noch kein Konto? Registrieren".
- **Validierung:** E-Mail-Format, Passwort erforderlich. Fehlermeldungen inline, verständlich (9.1).

### 2. Registrieren (`/register`)
- **Zweck:** Konto anlegen (8.1). Zurück-Chevron zu Login.
- **Felder:** Vorname + Name (zwei Spalten), E-Mail, Passwort (Hinweis „Mindestens 8 Zeichen" → `Validators.minLength(8)`). Button „Weiter" → Onboarding. Rechtstext zu Nutzungsbedingungen/Datenschutz.

### 3. Haushalt-Onboarding (`/onboarding`)
- **Zweck:** Haushalt erstellen oder beitreten (8.2). In V1 gehört ein User genau einem Haushalt an.
- **Layout:** Dunkle Space-Cadet-Karte „Neuen Haushalt erstellen" (Name-Input + Button „Haushalt erstellen", User wird Admin). ODER-Trenner. Weiße Karte „Einem Haushalt beitreten" (Einladungscode-Input + Button „Beitreten", Cream). Beide führen in die App.

### 4. Startseite / Übersicht (`/` – Tab „Start")
- **Zweck:** Tagesüberblick (Pflichtenheft 14.2).
- **Inhalt:** Begrüßung mit Datum (Mono-Label) + Haushalts-Avatare oben rechts (Tap = Abmelden). Karte „Heute essen" (3 Mahlzeiten mit farbigem Punkt + kcal). Zwei Kacheln: „Einkauf offen" (X/Y + Progress) und „Wochenbudget" (Cream, €/Budget). Karte „Bald ablaufend" (Vorräte mit Warn-Pills). „Favoriten" als 3 Mini-Rezeptkarten.

### 5. Rezepte (`/recipes` – Tab „Rezepte")
- **Zweck:** Übersicht, Suche, Filter (8.4, 8.15, 14.3).
- **Inhalt:** Titel, Suchfeld (Icon + Input), Filter-Pills (Vegan aktiv = Verdigris; High Protein, Schnell). Rezeptkarten (Radius 22): Farbverlauf-Thumbnail mit Blatt-Icon, Tag-Pill oben links, Favoriten-Herz oben rechts (Toggle, gefüllt = Danger `#B14A28`), Titel, Meta (Zeit/kcal Mono), 3 Makro-Chips (Protein/Carbs/Fett, getönte Hintergründe), Fußzeile „pro Portion" + Preis.

### 6. Rezeptdetail (Overlay über Rezepte)
- **Zweck:** Kern-Screen mit Portionsberechnung (8.5, 8.6, 8.9, 14.4).
- **Layout:** Farbverlauf-Header (196px) mit Tag-Pill, Zurück (‹) und Favoriten-Button. Titel (25/800 Bricolage).
- **Portions-Hero (Space-Cadet-Karte):** Label „PORTIONEN" + Stepper (−/Zahl/+, Verdigris-Rahmen). Darunter 3 Werte-Kacheln: kcal/Portion (Verdigris), €/Portion (Cream), Eiweiß/Portion. Hinweistext „Mengen · Nährwerte · Kosten passen sich automatisch an".
- **Nährwert-Ring:** Conic-Gradient-Donut (Protein/Carbs/Fett-Anteile), Mitte kcal. Rechts Legende mit Gramm-Werten.
- **Zutatenliste:** weiße Karte, Name links, Menge (Mono) + Kosten rechts, „für N Portionen".
- **Aktionen (sticky):** „Kochen starten" (Verdigris, Play-Icon) → Kochmodus; darunter „Einplanen" (Ghost) + „+ Einkaufsliste" (Cream).

### 7. Kochmodus (Vollbild-Overlay, Space Cadet)
- **Zweck:** Schritt-für-Schritt-Kochen, küchentauglich.
- **Layout:** Header mit Rezeptname (Verdigris) + Schließen. Fortschritt „SCHRITT X / N" + Balken. Großer Schritttext (28px Bricolage, `text-wrap:pretty`). Bei Kochzeit: Timer-Chip (Uhr-Icon + „15 Min · Timer starten"). Unten „Zutaten im Blick" als Chips (in gewählter Portionsmenge skaliert). Footer: ‹ zurück + „Weiter" / „Fertig".

### 8. Wochenplan (`/plan` – Tab „Plan")
- **Zweck:** Mahlzeiten planen, Einkaufsliste aus Plan (8.12, 14).
- **Inhalt:** Wochennavigation (‹ Datum ›), zwei Kennzahl-Kacheln (Ø kcal/Tag, Woche €). Tageskarten mit Mahlzeiten-Slots (Früh/Mittag/Abend), gefüllte Slots als Verdigris-getönte Chips, leere als gestrichelter „+ Hinzufügen". Button „Einkaufsliste aus Plan erstellen".

### 9. Einkaufsliste (`/shopping` – Tab „Einkauf")
- **Zweck:** Einkaufen, abhaken (8.10, 14.5).
- **Inhalt:** Titel, Fortschrittskarte (X von Y erledigt + Summe + Balken). Gruppen nach Kategorie (Mono-Label), Items als Zeilen: 22px-Checkbox (checked = Verdigris Deep + weißes Häkchen), Name (durchgestrichen + Muted wenn erledigt), Menge (Mono), Preis rechts. „+ Artikel hinzufügen".

### 10. Vorrat (`/pantry` – Tab „Vorrat")
- **Zweck:** Bestände nach Lagerort (8.13).
- **Inhalt:** Titel, Lagerort-Tabs (Kühlschr./Gefrier/Schrank/Keller; aktiv = Space-Cadet-Fläche). Item-Karten mit farbigem linken Rand (Warn = Danger), Name + Menge (Mono) + Ablauf-Pill. Hinweis „Beim Einkauf wird der Vorrat abgezogen".

### Bottom-Navigation (global)
Weiße Leiste, `1px solid #E3E6D2` oben, 5 Tabs (Start/Rezepte/Plan/Einkauf/Vorrat) mit Icon + Label. Aktiv: Icon+Label Verdigris Deep, Icon in `rgba(113,192,187,.2)`-Pill (40×26). Inaktiv: Cadet Soft.

---

## Interaktionen & Verhalten
- **Navigation:** Bottom-Tabs wechseln den Haupt-View. In Angular = Router-Outlet + `routerLinkActive`.
- **Overlays:** Rezeptdetail, Kochmodus und Auth liegen über der App (eigene Routen bzw. Route mit Overlay-Layout). Öffnen/Schließen mit kurzer Fade-Animation (`nhfade`, 0.25–0.3s ease, translateY 6px).
- **Portionsberechnung (Kern):** Stepper ändert `servings`. Faktor `f = servings / recipe.base`. Zutatenmenge = `menge * f`; Kosten = `kosten * f`; Nährwerte je Portion bleiben konstant (Basiswerte / base). Gesamtwerte = Summe der Zutaten × f. Rundung: Gewichte ganzzahlig, Stück eine Nachkommastelle, € zwei Nachkommastellen mit Komma. Grenzen: 1–12 Portionen.
- **Nährwertberechnung:** je Zutat `menge/100 × referenzwert`, dann summieren (Pflichtenheft 8.6). Ring-Anteile aus Gramm Protein/Carbs/Fett.
- **Favoriten:** Herz toggelt `is_favorite` (`POST /api/recipes/{id}/favorite/`); Klick auf Karte darf nicht das Detail öffnen (`stopPropagation`).
- **Suche/Filter:** clientseitig auf Name + vegan im Prototyp; serverseitig via Query-Params (8.15) in Produktion.
- **Einkaufsliste zusammenführen:** gleiche Zutat (Name+Einheit, nicht abgehakt) wird addiert statt doppelt angelegt (8.11). Nach „+ Einkaufsliste" Wechsel zu Einkauf + Bestätigungs-Toast.
- **Abhaken:** Item-Klick toggelt `is_checked`; Fortschritt & offene Summe aktualisieren sich; abgehakte bleiben sichtbar bis Listenabschluss (16.4).
- **Kochmodus:** Weiter/zurück durch Schritte; „Fertig" schließt mit Toast. Zutaten-Chips in aktueller Portionsmenge.
- **Toast:** unten mittig, Space Cadet, Pill, 2.4s sichtbar, `toastin`-Animation.
- **Abmelden:** Avatar-Tap auf Start → zurück zu Login.

## State Management
Empfehlung Angular: pro Feature ein Service mit Signals oder RxJS-Store; Auth-State global.
- **Auth:** `authed`, aktueller User, Token (access/refresh in Memory/Storage). Guards: `AuthGuard` (App), `OnboardingGuard` (erzwingt Haushalt, falls keiner).
- **Auth-Flow-Schritt:** login | register | household.
- **Rezepte:** Liste, aktives Detail-Rezept, `servings`-Override je Rezept, Favoriten-Set, Query/Filter.
- **Kochen:** aktives Rezept + Schrittindex.
- **Einkaufsliste:** Items (id, name, amount, unit, cat, cost, checked); abgeleitet: erledigt-Anzahl, offene Summe, Gruppierung nach Kategorie.
- **Vorrat:** Items je Lagerort; aktiver Lagerort-Tab.
- **Datenbeschaffung:** REST-Endpunkte aus Pflichtenheft 13. Offline: IndexedDB-Cache + Sync-Queue (Pflichtenheft 15) — nicht im Prototyp abgebildet, aber Screens (Einkauf/Rezepte/Plan) müssen offline lesbar sein.

## Assets
- **Icons:** durchgängig Inline-SVG im Lucide-Stil (stroke `currentColor`, `stroke-width` 1.6–2), 13–32px. In Angular am besten als Icon-Set (z. B. `lucide-angular`) nachziehen. Verwendete Icons: Blatt (Logo), Buch (Rezepte), Kalender (Plan), Einkaufswagen (Einkauf), Box (Vorrat), Home, Uhr, Lupe, Play, Timer, Häkchen, Chevron, Mail, Schloss.
- **Rezeptbilder:** im Prototyp Farbverlauf-Platzhalter (`linear-gradient(135deg, …)` aus Verdigris/Cadet/Success) + Blatt-Icon. In Produktion echte Bild-Uploads (`recipe.image`), Platzhalter als Fallback beibehalten.
- **Fonts:** Google Fonts – Bricolage Grotesque, Manrope, Space Mono. In Angular via self-hosted `@font-face` oder Fontsource einbinden.

## Dateien
- `NutriHome Prototype.dc.html` — **Haupt-Referenz**: alle App-Screens + Auth, voll interaktiv (Portionsrechnung, Favoriten, Einkauf abhaken, Kochmodus).
- `NutriHome Style Guide.dc.html` — Design System: Farben, Typografie, Komponenten, Radien.
- `NutriHome Design System.dc.html` — zusätzliche Komponenten-Mocks (Desktop-Dashboard-Variante) als Referenz für Statistik-/Preis-Screens.
- `NutriHome Wireframes.dc.html` — Low-Fi-Struktur-Exploration (nur Kontext).

Zum Ansehen im Browser öffnen. Der Auth-Flow lässt sich über den Tweak `startAuth` bzw. den Avatar-Tap („Abmelden") starten.
