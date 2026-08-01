Ich würde das Projekt wie ein echtes Produkt entwickeln und nicht wie ein Lernprojekt. Das spart später viel Umbauarbeit.

Ein möglicher Projektname wäre beispielsweise:

NutriSync
SmartKitchen
MealFlow
CookLedger
PantryPilot
KitchenHub
FoodWise
NutriHome

Ich würde außerdem einige Grundprinzipien von Anfang an festlegen:

Offline-First: Alles Wichtige funktioniert auch ohne Internet.
Mobile-First: Die App ist primär für Smartphone und Tablet optimiert.
Gemeinsamer Haushalt: Mehrere Benutzer können zusammenarbeiten.
Strukturierte Daten: Keine unstrukturierten Freitextlisten.
Automatische Berechnungen: Nährwerte, Kosten und Portionsgrößen werden stets aus den Zutaten berechnet.
Erweiterbarkeit: Neue Module lassen sich ergänzen, ohne bestehende Funktionen umzubauen.
Mögliche Roadmap

Version 0.1

Anmeldung
Haushalte
Zutaten
Rezepte
Nährwertberechnung

Version 0.2

Einkaufslisten
Preisverwaltung
Wochenplan

Version 0.3

Vorrat
Ablaufdaten
Barcode-Scanner

Version 0.4

KI-Rezeptvorschläge
Rezeptimport von Webseiten
Rezeptvorschläge anhand des Vorrats

Version 1.0

Vollständige Haushalts- und Ernährungsverwaltung
Synchronisation zwischen allen Geräten
PWA mit Installationsfunktion
Export und Backup

Ich würde zusätzlich eine klare Trennung zwischen Lebensmitteln, Produkten und Rezepten einführen:

Lebensmittel: z. B. „Haferflocken“ (mit allgemeinen Nährwerten).
Produkte: z. B. „Kölln Haferflocken 500 g“ oder „Gut & Günstig Haferflocken 1 kg“ (mit Hersteller, Preis und ggf. abweichenden Nährwerten).
Rezepte: Verweisen auf Lebensmittel oder Produkte und berechnen daraus Kosten und Nährwerte.

Das macht Preisvergleiche, Herstellerwechsel und spätere Barcode-Unterstützung deutlich einfacher.

Aus meiner Sicht ist das ein Projekt, das sich hervorragend als langfristige Eigenentwicklung eignet und gleichzeitig viele Technologien vereint: Angular, Django, PostgreSQL, Docker, PWA, Offline-Synchronisation und später eventuell KI-Unterstützung. Es wäre damit nicht nur im Alltag nützlich, sondern auch ein starkes Referenzprojekt für dein Portfolio.

Ok hört sich interessant an

Ich glaube, das Projekt hat vor allem deshalb Potenzial, weil es ein echtes Alltagsproblem löst. Viele Apps können entweder Rezepte oder Einkaufslisten oder Kalorien zählen – aber nur wenige verbinden alles sinnvoll.

Ich würde den Fokus nicht auf "Kalorien zählen" legen, sondern auf gesunde Ernährung einfach organisieren.

Ein mögliches Leitbild wäre:

"Plane, koche und kaufe gesund – gemeinsam in einer App."

Ein paar Funktionen, die ich persönlich als besonders wertvoll ansehen würde:

🍽️ "Was koche ich heute?" – Vorschläge basierend auf Vorrat, Budget und Ernährungsziel.
🛒 Intelligente Einkaufsliste – Erkennt, dass 300 g Möhren für zwei Rezepte insgesamt 600 g ergeben und fasst sie zusammen.
🥗 Portionsrechner – Ein Rezept von 2 auf 5 Personen umrechnen.
📊 Nährwert-Dashboard – Tages-, Wochen- und Monatsübersicht.
💰 Preisvergleich – Was kostet dieses Rezept aktuell und wo kaufe ich die Zutaten am günstigsten?
📦 Vorrat – Zeigt an, was vorhanden ist und was bald verbraucht werden sollte.
📅 Wochenplanung – Einmal planen, Einkaufsliste automatisch erstellen.
Eine Idee, die ich spannend finde

Ihr könntet euch beim Einkaufen Arbeit sparen, indem die App erkennt:

"Für den Wochenplan fehlen noch 8 Zutaten. Drei davon sind bereits im Vorrat."

Oder:

"Du hast noch Blumenkohl, Skyr und Möhren. Daraus kannst du heute zwei passende Rezepte kochen."

Das ist genau die Art von Funktion, die im Alltag wirklich Zeit spart.

Mein Vorschlag für den nächsten Schritt

Bevor eine einzige Zeile Code geschrieben wird, würde ich gemeinsam ein kleines Pflichtenheft erstellen. Darin halten wir fest:

Ziele der App
Zielgruppe
Funktionsumfang des MVP
Datenmodell
Benutzeroberflächen (Wireframes)
API-Konzept
Datenbankschema
Entwicklungsplan mit Meilensteinen

Das sorgt dafür, dass ihr während der Entwicklung nicht ständig die Richtung ändert und bildet eine solide Grundlage für das gesamte Projekt.

Ok mach das

Hier ist ein erster Entwurf als solide Projektgrundlage.

Pflichtenheft – PWA für gesunde Ernährung, Rezepte und Einkäufe
1. Projektübersicht
   1.1 Arbeitstitel

NutriHome

Der Projektname ist vorläufig und kann später geändert werden.

1.2 Projektidee

NutriHome ist eine mobile, installierbare Progressive Web App für die gemeinsame Organisation von gesunder Ernährung.

Die Anwendung verbindet:

Rezeptverwaltung
Nährwertberechnung
Preisverwaltung
Einkaufslisten
Wochenplanung
Vorratsverwaltung

Die App wird zunächst für einen gemeinsamen Haushalt mit zwei Personen entwickelt. Die Architektur soll eine spätere Nutzung durch weitere Haushalte und Benutzer ermöglichen.

2. Ausgangssituation

Rezepte, Einkaufslisten, Lebensmittelpreise und Ernährungsinformationen werden häufig in unterschiedlichen Apps oder als Notizen verwaltet.

Dadurch entstehen mehrere Probleme:

Rezepte sind auf verschiedene Quellen verteilt.
Nährwerte müssen manuell berechnet werden.
Einkaufsmengen werden nicht automatisch zusammengeführt.
vorhandene Lebensmittel werden beim Einkauf vergessen.
Kosten pro Rezept sind nicht transparent.
eine gemeinsame Bearbeitung ist nur eingeschränkt möglich.

Die Anwendung soll diese Bereiche in einem gemeinsamen System zusammenführen.

3. Projektziele

Die Anwendung soll es ermöglichen:

eigene Rezepte zu erfassen und zu speichern
Zutaten strukturiert zu verwalten
Nährwerte automatisch zu berechnen
Preise von Produkten zu speichern
Rezeptkosten und Portionskosten zu berechnen
gemeinsame Einkaufslisten zu erstellen
Mahlzeiten für mehrere Tage zu planen
vorhandene Lebensmittel zu berücksichtigen
die wichtigsten Funktionen offline zu verwenden
Daten zwischen zwei Benutzern zu synchronisieren
4. Zielgruppe
   4.1 Primäre Zielgruppe

Die erste Version wird für einen privaten Zwei-Personen-Haushalt entwickelt.

4.2 Mögliche spätere Zielgruppen
Paare
Familien
Wohngemeinschaften
ernährungsbewusste Einzelpersonen
Nutzer mit Meal-Prep-Planung
Nutzer mit festem Lebensmittelbudget
5. Produktgrundsätze

Die Anwendung wird nach folgenden Grundsätzen entwickelt:

Mobile First

Die Hauptnutzung erfolgt auf Smartphones. Die Bedienung muss auch beim Kochen und Einkaufen einfach möglich sein.

Offline First

Bereits geladene Rezepte und Einkaufslisten sollen ohne Internetverbindung verfügbar sein.

Gemeinsamer Haushalt

Mehrere Benutzer können auf gemeinsame Rezepte, Einkaufslisten, Preise und Vorräte zugreifen.

Strukturierte Daten

Zutaten, Produkte, Preise und Nährwerte werden als eigene Datensätze gespeichert und nicht ausschließlich als Freitext.

Nachvollziehbare Berechnungen

Nährwerte und Kosten müssen aus den gespeicherten Zutatenmengen berechnet werden.

Erweiterbarkeit

Die Anwendung soll später um Barcode-Scanner, Rezeptimport, Angebote und intelligente Rezeptvorschläge erweitert werden können.

6. Begriffsdefinitionen
   6.1 Lebensmittel

Ein Lebensmittel beschreibt eine allgemeine Zutat.

Beispiele:

Haferflocken
Kartoffeln
Möhren
Skyr

Ein Lebensmittel kann allgemeine Nährwerte und eine Standardeinheit besitzen.

6.2 Produkt

Ein Produkt ist eine konkrete Handelsware.

Beispiele:

Kölln Haferflocken 500 g
Aldi Haferflocken 500 g
Skyr Natur 500 g einer bestimmten Marke

Ein Produkt besitzt unter anderem:

Marke
Packungsgröße
Barcode
konkrete Nährwerte
Preise
6.3 Rezept

Ein Rezept besteht aus:

allgemeinen Informationen
Portionen
Zutatenmengen
Zubereitungsschritten
Nährwerten
Kosten
6.4 Haushalt

Ein Haushalt ist ein gemeinsamer Datenbereich mehrerer Benutzer.

Zum Haushalt gehören beispielsweise:

Rezepte
Einkaufslisten
Wochenpläne
Vorräte
Preise
7. Rollen und Berechtigungen
   7.1 Haushaltsadministrator

Der Administrator kann:

Mitglieder einladen
Mitglieder entfernen
Haushaltsdaten bearbeiten
Rezepte verwalten
Einkaufslisten verwalten
Preise und Vorräte verwalten
7.2 Haushaltsmitglied

Ein Mitglied kann:

Rezepte erstellen und bearbeiten
Einkaufslisten bearbeiten
Artikel abhaken
Preise erfassen
Wochenpläne erstellen
Vorräte aktualisieren

Für die erste Version können Administrator und Mitglied nahezu dieselben fachlichen Rechte besitzen.

8. Funktionsumfang des MVP

Der MVP ist die erste vollständig nutzbare Version.

8.1 Benutzerverwaltung

Die Anwendung muss folgende Funktionen bereitstellen:

Registrierung
Anmeldung
Abmeldung
Passwortänderung
Passwort-zurücksetzen-Funktion
Anzeige des eigenen Profils
8.2 Haushaltsverwaltung

Benutzer müssen:

einen Haushalt erstellen können
einem Haushalt beitreten können
Mitglieder anzeigen können
gemeinsame Daten verwenden können

In der ersten Version gehört ein Benutzer maximal einem Haushalt an.

8.3 Zutatenverwaltung

Benutzer müssen Zutaten:

erstellen
anzeigen
bearbeiten
suchen
deaktivieren
Kategorien zuordnen

Eine Zutat enthält mindestens:

Name
Kategorie
Standardeinheit
Kalorien
Eiweiß
Kohlenhydrate
Fett
Ballaststoffe
Zucker
Salz

Die Nährwerte werden standardmäßig je 100 Gramm oder 100 Milliliter gespeichert.

8.4 Rezeptverwaltung

Benutzer müssen Rezepte:

erstellen
anzeigen
bearbeiten
löschen oder archivieren
als Favorit markieren
suchen
filtern

Ein Rezept enthält mindestens:

Name
Beschreibung
Portionen
Zubereitungszeit
Zutaten
Mengen
Einheiten
Zubereitungsschritte
Kategorie
Tags
optionales Bild
8.5 Portionsberechnung

Die Portionszahl eines Rezeptes muss geändert werden können.

Die Anwendung passt anschließend automatisch an:

Zutatenmengen
Nährwerte
Kosten

Beispiel:

Ein Rezept für zwei Portionen enthält 400 Gramm Kartoffeln.

Bei vier Portionen werden 800 Gramm Kartoffeln angezeigt.

8.6 Nährwertberechnung

Die Anwendung muss die Nährwerte eines Rezeptes automatisch berechnen.

Berechnet werden mindestens:

Kalorien
Eiweiß
Kohlenhydrate
Fett
Ballaststoffe
Zucker
Salz

Die Anzeige erfolgt:

für das gesamte Rezept
pro Portion
optional je 100 Gramm, sofern ein Gesamtgewicht berechnet werden kann
Berechnungsbeispiel

Besitzt ein Lebensmittel 370 Kilokalorien je 100 Gramm und werden 80 Gramm verwendet:

80 / 100 × 370 = 296 Kilokalorien

Die Werte aller Zutaten werden anschließend addiert.

8.7 Produktverwaltung

Zu einem Lebensmittel können konkrete Produkte hinterlegt werden.

Ein Produkt enthält:

Produktname
Marke
Lebensmittelzuordnung
Packungsgröße
Packungseinheit
optionale eigene Nährwerte
optionalen Barcode
8.8 Preisverwaltung

Zu einem Produkt können Preise erfasst werden.

Ein Preiseintrag enthält:

Produkt
Geschäft
Preis
Packungsgröße
Erfassungsdatum
optionales Angebotsende

Die Anwendung berechnet automatisch:

Preis je Kilogramm
Preis je 100 Gramm
Preis je Liter
anteilige Kosten einer Rezeptmenge
8.9 Rezeptkosten

Die Anwendung muss anzeigen:

Gesamtkosten des Rezeptes
Kosten pro Portion
Kosten je Zutat

Falls mehrere Preise vorhanden sind, kann zunächst der zuletzt erfasste Preis verwendet werden.

Später kann zwischen dem günstigsten, letzten oder bevorzugten Preis gewählt werden.

8.10 Einkaufslisten

Benutzer müssen Einkaufslisten:

erstellen
umbenennen
bearbeiten
abschließen
löschen oder archivieren können

Artikel können:

manuell hinzugefügt
aus Rezepten übernommen
abgehakt
wieder aktiviert
nach Kategorien gruppiert werden
8.11 Einkaufsliste aus Rezepten

Aus einem oder mehreren Rezepten muss eine Einkaufsliste erstellt werden können.

Gleiche Zutaten werden zusammengeführt.

Beispiel:

Rezept A benötigt 300 Gramm Möhren.
Rezept B benötigt 400 Gramm Möhren.
Die Einkaufsliste enthält 700 Gramm Möhren.
8.12 Wochenplan

Benutzer können Rezepte einem Datum und einer Mahlzeit zuordnen.

Mahlzeitentypen:

Frühstück
Mittagessen
Abendessen
Snack

Aus dem Wochenplan kann eine Einkaufsliste erstellt werden.

8.13 Vorratsverwaltung

Benutzer können vorhandene Lebensmittel speichern.

Ein Vorratseintrag enthält:

Lebensmittel oder Produkt
vorhandene Menge
Einheit
Lagerort
optionales Mindesthaltbarkeitsdatum
optionalen Öffnungsstatus

Mögliche Lagerorte:

Kühlschrank
Gefrierschrank
Vorratsschrank
Keller
sonstiger Lagerort
8.14 Vorräte von Einkaufslisten abziehen

Bei der Erstellung einer Einkaufsliste kann der vorhandene Vorrat berücksichtigt werden.

Beispiel:

Benötigt werden 1.000 Gramm Kartoffeln.

Im Vorrat befinden sich 400 Gramm.

Die Einkaufsliste enthält 600 Gramm Kartoffeln.

Der Vorrat wird dabei nicht sofort automatisch reduziert. Eine tatsächliche Reduzierung erfolgt erst nach Bestätigung oder beim Kochen.

8.15 Suche und Filter

Rezepte müssen mindestens nach folgenden Kriterien gefiltert werden können:

Name
Kategorie
Favorit
Zubereitungszeit
maximale Kalorien
minimale Proteinmenge
vegetarisch
vegan
9. Nicht-funktionale Anforderungen
   9.1 Bedienbarkeit
   Die Anwendung muss für Smartphones optimiert sein.
   Wichtige Aktionen müssen mit wenigen Eingaben erreichbar sein.
   Schaltflächen müssen ausreichend groß sein.
   Formulare müssen verständliche Fehlermeldungen anzeigen.
   Einkaufslisten müssen mit einer Hand bedienbar sein.
   9.2 Leistung
   Die Startansicht sollte bei normaler Verbindung innerhalb weniger Sekunden geladen werden.
   Suchergebnisse sollen ohne wahrnehmbare Verzögerung erscheinen.
   Lange Rezeptlisten müssen paginiert oder schrittweise geladen werden.
   9.3 Offline-Fähigkeit

Offline verfügbar sein müssen mindestens:

aktuelle Einkaufslisten
zuletzt geladene Rezepte
gespeicherter Wochenplan
häufig genutzte Zutaten

Offline vorgenommene Änderungen werden lokal gespeichert und später synchronisiert.

9.4 Sicherheit
Passwörter dürfen nicht im Klartext gespeichert werden.
Die Datenübertragung erfolgt ausschließlich über HTTPS.
API-Endpunkte müssen authentifiziert sein.
Benutzer dürfen nur auf Daten ihres Haushalts zugreifen.
Eingaben müssen serverseitig validiert werden.
Datei-Uploads müssen auf Typ und Größe geprüft werden.
sicherheitsrelevante Aktionen müssen protokolliert werden.
9.5 Datenschutz
Es werden nur notwendige personenbezogene Daten gespeichert.
Benutzer müssen ihre Daten exportieren können.
Benutzerkonten müssen gelöscht werden können.
Haushaltsdaten dürfen nicht öffentlich erreichbar sein.
Ernährungs- und Körperdaten werden im MVP nicht zwingend benötigt.
9.6 Wartbarkeit
Frontend und Backend werden klar getrennt.
Fachbereiche werden modular aufgebaut.
Geschäftslogik wird nicht ausschließlich im Frontend implementiert.
Berechnungen werden durch automatisierte Tests abgesichert.
API-Schnittstellen werden dokumentiert.
10. Systemarchitektur
    10.1 Frontend

Empfohlene Technologien:

Angular
TypeScript
Angular Service Worker
IndexedDB
SCSS
optional Angular Material oder eigene UI-Komponenten

Aufgaben des Frontends:

Darstellung der Benutzeroberfläche
lokale Datenspeicherung
Offline-Nutzung
Formulare
Synchronisation mit dem Backend
Installation als PWA
10.2 Backend

Empfohlene Technologien:

Python
Django
Django REST Framework
PostgreSQL
Docker

Aufgaben des Backends:

Authentifizierung
Berechtigungsprüfung
Haushaltsverwaltung
Datenspeicherung
Nährwertberechnung
Kostenberechnung
Synchronisation
API-Bereitstellung
10.3 Infrastruktur

Möglicher Aufbau:

Angular PWA
|
| HTTPS / REST API
|
Django REST Framework
|
PostgreSQL

Produktiver Betrieb:

Nginx
Angular Frontend
Django Backend
PostgreSQL
Docker Compose
11. Fachliche Module

Die Anwendung wird in folgende Fachbereiche gegliedert:

Accounts
Households
Ingredients
Products
Nutrition
Recipes
Pricing
Shopping
Meal Planning
Pantry
Synchronization

Die Module sollen fachlich getrennt bleiben, dürfen aber über definierte Services miteinander kommunizieren.

12. Datenmodell
    12.1 User
    id
    email
    password
    first_name
    last_name
    is_active
    created_at
    updated_at
    12.2 Household
    id
    name
    created_by
    created_at
    updated_at
    12.3 HouseholdMember
    id
    household_id
    user_id
    role
    joined_at
    12.4 IngredientCategory
    id
    name
    icon
    sort_order
    12.5 Ingredient
    id
    name
    category_id
    default_unit
    nutrition_reference_amount
    calories
    protein
    carbohydrates
    fat
    fiber
    sugar
    salt
    created_by
    is_active
    created_at
    updated_at
    12.6 Product
    id
    household_id
    ingredient_id
    name
    brand
    barcode
    package_amount
    package_unit
    calories
    protein
    carbohydrates
    fat
    fiber
    sugar
    salt
    created_at
    updated_at
    12.7 Store
    id
    household_id
    name
    location
    is_active
    12.8 ProductPrice
    id
    product_id
    store_id
    price
    currency
    package_amount
    package_unit
    valid_from
    valid_until
    recorded_at
    12.9 Recipe
    id
    household_id
    name
    description
    servings
    preparation_time
    cooking_time
    category
    image
    created_by
    is_favorite
    is_archived
    created_at
    updated_at
    12.10 RecipeIngredient
    id
    recipe_id
    ingredient_id
    product_id
    amount
    unit
    position
    note

Die Produktzuordnung ist optional. Ein Rezept kann nur auf das allgemeine Lebensmittel verweisen.

12.11 RecipeStep
id
recipe_id
position
instruction
duration
12.12 RecipeTag
id
name
12.13 RecipeTagAssignment
id
recipe_id
tag_id
12.14 ShoppingList
id
household_id
name
status
created_by
created_at
updated_at
completed_at
12.15 ShoppingListItem
id
shopping_list_id
ingredient_id
product_id
amount
unit
is_checked
estimated_price
note
created_at
updated_at
12.16 MealPlanEntry
id
household_id
date
meal_type
recipe_id
servings
note
created_by
12.17 PantryItem
id
household_id
ingredient_id
product_id
amount
unit
storage_location
best_before_date
opened_at
created_at
updated_at
13. API-Konzept
    13.1 Authentifizierung
    POST /api/auth/register/
    POST /api/auth/login/
    POST /api/auth/logout/
    POST /api/auth/token/refresh/
    POST /api/auth/password-reset/
    GET  /api/auth/profile/
    13.2 Haushalte
    GET    /api/households/
    POST   /api/households/
    GET    /api/households/{id}/
    PATCH  /api/households/{id}/
    GET    /api/households/{id}/members/
    POST   /api/households/{id}/invite/
    DELETE /api/households/{id}/members/{memberId}/
    13.3 Zutaten
    GET    /api/ingredients/
    POST   /api/ingredients/
    GET    /api/ingredients/{id}/
    PATCH  /api/ingredients/{id}/
    DELETE /api/ingredients/{id}/
    13.4 Produkte und Preise
    GET   /api/products/
    POST  /api/products/
    GET   /api/products/{id}/
    PATCH /api/products/{id}/

GET   /api/products/{id}/prices/
POST  /api/products/{id}/prices/
PATCH /api/prices/{id}/
13.5 Rezepte
GET    /api/recipes/
POST   /api/recipes/
GET    /api/recipes/{id}/
PATCH  /api/recipes/{id}/
DELETE /api/recipes/{id}/
POST   /api/recipes/{id}/favorite/
GET    /api/recipes/{id}/nutrition/
GET    /api/recipes/{id}/costs/
13.6 Einkaufslisten
GET    /api/shopping-lists/
POST   /api/shopping-lists/
GET    /api/shopping-lists/{id}/
PATCH  /api/shopping-lists/{id}/
DELETE /api/shopping-lists/{id}/

POST /api/shopping-lists/from-recipes/
POST /api/shopping-lists/from-meal-plan/
POST /api/shopping-lists/{id}/items/
PATCH /api/shopping-list-items/{id}/
13.7 Wochenplan
GET    /api/meal-plan/
POST   /api/meal-plan/
PATCH  /api/meal-plan/{id}/
DELETE /api/meal-plan/{id}/
13.8 Vorräte
GET    /api/pantry/
POST   /api/pantry/
PATCH  /api/pantry/{id}/
DELETE /api/pantry/{id}/
14. Benutzeroberfläche
    14.1 Hauptnavigation

Die mobile Hauptnavigation enthält:

Start
Rezepte
Plan
Einkaufen
Vorrat

Weitere Funktionen befinden sich in einem zusätzlichen Menü.

14.2 Startseite

Die Startseite zeigt:

heutige Mahlzeiten
offene Einkaufsliste
zuletzt verwendete Rezepte
Favoriten
bald ablaufende Vorräte
geschätzte Wochenkosten
14.3 Rezeptübersicht

Die Rezeptübersicht enthält:

Suchfeld
Kategorien
Filter
Rezeptkarten
Favoritenkennzeichnung
Schaltfläche zum Erstellen eines Rezeptes
14.4 Rezeptdetailseite

Die Rezeptdetailseite zeigt:

Rezeptbild
Name
Portionen
Zubereitungszeit
Kosten pro Portion
Nährwerte pro Portion
Zutatenliste
Zubereitungsschritte
Schaltfläche zum Hinzufügen zur Einkaufsliste
Schaltfläche zum Einplanen
14.5 Einkaufsansicht

Die Einkaufsansicht enthält:

große Kontrollfelder
Gruppierung nach Kategorie
Mengen und Einheiten
geschätzte Preise
Fortschrittsanzeige
Offline-Verfügbarkeit
15. Offline- und Synchronisationskonzept
    15.1 Lokale Speicherung

Für lokale Daten wird IndexedDB verwendet.

Lokal gespeichert werden:

Benutzersitzung
aktuelle Einkaufslisten
zuletzt geladene Rezepte
Wochenplan
häufig verwendete Zutaten
noch nicht synchronisierte Änderungen
15.2 Synchronisationswarteschlange

Offline vorgenommene Änderungen werden als Aktionen gespeichert.

Beispiel:

CREATE_RECIPE
UPDATE_SHOPPING_ITEM
CHECK_SHOPPING_ITEM
UPDATE_PANTRY_ITEM

Sobald eine Verbindung verfügbar ist, werden die Aktionen an das Backend übertragen.

15.3 Konfliktbehandlung

Für den MVP gilt grundsätzlich:

Die zuletzt gespeicherte Änderung gewinnt.
Zeitstempel werden serverseitig gespeichert.
Gelöschte Datensätze werden zunächst logisch gelöscht.
Konflikte werden protokolliert.

Für gemeinsam verwendete Einkaufslisten kann später eine feinere Echtzeit-Synchronisation ergänzt werden.

16. Validierungsregeln
    16.1 Zutaten
    Name ist erforderlich.
    Nährwerte dürfen nicht negativ sein.
    Referenzmenge muss größer als null sein.
    Einheiten müssen unterstützt werden.
    16.2 Rezepte
    Name ist erforderlich.
    Ein Rezept muss mindestens eine Portion besitzen.
    Ein Rezept muss mindestens eine Zutat besitzen.
    Zutatenmengen dürfen nicht negativ sein.
    Die Reihenfolge der Arbeitsschritte muss eindeutig sein.
    16.3 Preise
    Preis muss größer oder gleich null sein.
    Packungsgröße muss größer als null sein.
    Währung ist standardmäßig Euro.
    Das Angebotsende darf nicht vor dem Angebotsbeginn liegen.
    16.4 Einkaufslisten
    Mengen dürfen nicht negativ sein.
    Abgehakte Artikel bleiben bis zum Abschluss der Liste sichtbar.
    Gleiche Zutaten können zusammengeführt werden.
17. Einheiten und Umrechnungen

Unterstützte Gewichtseinheiten:

Milligramm
Gramm
Kilogramm

Unterstützte Volumeneinheiten:

Milliliter
Liter

Weitere Einheiten:

Stück
Packung
Esslöffel
Teelöffel
Prise
Bund
Dose

Für verlässliche Nährwertberechnungen müssen nicht standardisierte Einheiten bei Bedarf in Gramm oder Milliliter umgerechnet werden.

Beispiel:

1 Esslöffel Olivenöl = ungefähr 13,5 Gramm

Solche Umrechnungen können lebensmittelspezifisch gespeichert werden.

18. Testanforderungen
    18.1 Backendtests

Automatisiert getestet werden mindestens:

Berechnung der Nährwerte
Berechnung der Rezeptkosten
Portionsumrechnung
Zusammenführung gleicher Einkaufsartikel
Abzug vorhandener Vorräte
Haushaltsberechtigungen
Zugriffsschutz der API
18.2 Frontendtests

Getestet werden mindestens:

Formularvalidierung
Portionsänderung
Einkaufslisteninteraktion
Offline-Speicherung
Synchronisationsanzeige
Fehlerzustände
18.3 End-to-End-Tests

Wichtige Benutzerabläufe:

Benutzer meldet sich an.
Benutzer erstellt eine Zutat.
Benutzer erstellt ein Rezept.
Nährwerte werden berechnet.
Benutzer plant das Rezept ein.
Benutzer erzeugt eine Einkaufsliste.
Benutzer hakt Artikel offline ab.
Änderungen werden später synchronisiert.
19. Entwicklungsphasen
    Phase 1 – Projektgrundlage
    Repositories erstellen
    Angular-Projekt einrichten
    Django-Projekt einrichten
    PostgreSQL anbinden
    Docker Compose erstellen
    Umgebungsvariablen definieren
    CI-Pipeline einrichten
    Grundlegende Authentifizierung umsetzen
    Phase 2 – Haushalte und Zutaten
    Haushaltsmodell
    Mitgliedschaften
    Zutatenkategorien
    Zutatenverwaltung
    Nährwertfelder
    Suchfunktion
    Phase 3 – Rezepte
    Rezeptmodell
    Rezeptzutaten
    Arbeitsschritte
    Rezepteditor
    Rezeptübersicht
    Favoriten
    Portionsumrechnung
    Phase 4 – Nährwerte und Preise
    Nährwertservice
    Produktverwaltung
    Geschäfte
    Preise
    Rezeptkosten
    Kosten pro Portion
    Phase 5 – Einkaufslisten
    Listenverwaltung
    Artikel
    Rezeptübernahme
    Mengen zusammenführen
    Preise schätzen
    Artikel abhaken
    Phase 6 – Wochenplan
    Kalenderansicht
    Mahlzeitentypen
    Rezeptzuordnung
    Einkaufsliste aus Wochenplan
    Nährwertübersicht
    Phase 7 – Vorräte
    Vorratsverwaltung
    Lagerorte
    Ablaufdaten
    Vorratsabzug
    Verbrauchsbuchungen
    Phase 8 – PWA und Offline
    Installierbarkeit
    Service Worker
    IndexedDB
    Offline-Einkaufslisten
    Synchronisationswarteschlange
    Konfliktbehandlung
    Phase 9 – Qualität und Veröffentlichung
    Tests vervollständigen
    Sicherheitsprüfung
    Performanceoptimierung
    Backup-Konzept
    Deployment
    technische Dokumentation
    Benutzeranleitung
20. MVP-Abnahmekriterien

Der MVP gilt als abnahmefähig, wenn folgende Abläufe funktionieren:

Zwei Benutzer können denselben Haushalt verwenden.
Zutaten können mit Nährwerten angelegt werden.
Ein Rezept kann aus mehreren Zutaten erstellt werden.
Nährwerte werden automatisch berechnet.
Die Portionszahl kann angepasst werden.
Produkte und Preise können gespeichert werden.
Rezeptkosten werden automatisch berechnet.
Aus Rezepten kann eine Einkaufsliste erstellt werden.
Gleiche Zutaten werden zusammengeführt.
Artikel können offline angezeigt und abgehakt werden.
Änderungen werden nach Wiederherstellung der Verbindung synchronisiert.
Benutzer können ausschließlich auf Daten ihres Haushalts zugreifen.
21. Funktionen nach dem MVP

Folgende Funktionen gehören zunächst nicht zum Pflichtumfang:

Barcode-Scanner
automatische Produktdatenbanken
automatischer Import von Rezeptwebseiten
KI-generierte Rezepte
Bilderkennung
automatische Supermarktangebote
Preisvergleich über externe Anbieter
tägliches Kalorientagebuch
Gewichtsdokumentation
medizinische Ernährungsempfehlungen
Push-Benachrichtigungen
Echtzeitbearbeitung über WebSockets
öffentliche Rezeptprofile
soziale Funktionen
22. Mögliche spätere Erweiterungen
    Barcode-Scanner

Produkte können über die Smartphone-Kamera erkannt werden.

Rezeptimport

Rezepte können von Webseiten übernommen und in strukturierte Daten umgewandelt werden.

Intelligente Rezeptvorschläge

Rezepte werden vorgeschlagen anhand von:

vorhandenen Vorräten
Ernährungszielen
maximalen Kosten
verfügbarer Zeit
bald ablaufenden Lebensmitteln
Preisentwicklung

Historische Produktpreise werden grafisch dargestellt.

Saisonkalender

Obst und Gemüse können nach regionaler Saison gefiltert werden.

Fermentationsbereich

Fermentationsprojekte können mit Rezept, Startdatum, Reifezeit und Erinnerungen verwaltet werden.

Budgetplanung

Die Anwendung kann monatliche und wöchentliche Lebensmittelbudgets auswerten.

23. Offene Entscheidungen

Vor Entwicklungsbeginn sollten folgende Punkte abschließend entschieden werden:

endgültiger Projektname
eigenes Frontend- und Backend-Repository oder Monorepository
JWT oder Cookie-basierte Authentifizierung
UI-Komponentenbibliothek oder eigenes Designsystem
lokale Bildspeicherung oder Objektspeicher
Umgang mit eigenen und globalen Zutaten
verwendete Standarddatenquelle für Nährwerte
genaue Offline-Konfliktstrategie
Umfang der Vorratsabbuchung
Hosting- und Backup-Konzept
24. Empfohlener erster Entwicklungsumfang

Der erste umzusetzende Arbeitsstand sollte nur folgende Bereiche enthalten:

Benutzeranmeldung
gemeinsamer Haushalt
Zutaten
Rezepte
Rezeptzutaten
Nährwertberechnung
einfache responsive Benutzeroberfläche

Preise, Einkaufslisten, Wochenplan und Offline-Synchronisation werden anschließend ergänzt.

Damit entsteht frühzeitig eine funktionsfähige Basis, ohne dass alle Module gleichzeitig entwickelt werden müssen.
