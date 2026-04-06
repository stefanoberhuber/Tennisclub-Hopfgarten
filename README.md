Hier ist die zusammengefasste Bestandsdokumentation (Status Quo) ohne zusätzliche Empfehlungen oder Erweiterungen:

⸻
1. Projektübersicht
Ziel

Webbasierte Anwendung für einen Tennisclub zur Verwaltung von:

	•	Mitgliedern

	•	Kantinen-Entnahmen

	•	Rechnungen

	•	Mitgliedsbeiträgen
Hauptfunktionen
Öffentliche Seite (Mitglieder)

	•	Mitglied auswählen

	•	Produkte/Entnahmen auswählen

	•	Entnahme speichern (wird als offene Position erfasst)
Admin-Bereich

	•	Mitgliederverwaltung (anlegen, bearbeiten)

	•	Mitgliederliste

	•	Mitgliedsbeiträge verwalten

	•	Dashboard für Beiträge

	•	Offene Posten anzeigen

	•	Entnahmen-Übersicht mit Filter

	•	Produktstatistik

	•	Rechnungen anzeigen

	•	Mitglieder-Ranking nach Umsatz
Anwendungsfall

Digitalisierung eines bisher manuellen Systems zur Erfassung von Konsumationen im Tennisclub.

⸻
2. Technologie-Stack
Frontend

	•	HTML

	•	CSS

	•	JavaScript (Vanilla)
Backend

	•	Supabase (PostgreSQL, Zugriff über REST API)
Hosting

	•	GitHub Pages

⸻
3. Architektur & Design
Architekturtyp

	•	Frontend-only Anwendung mit Backend-as-a-Service
Komponenten

	•	Öffentliche Seite für Mitglieder (Tablet)

	•	Admin-Seite für Verwaltung
Datenfluss

Browser → Fetch API → Supabase REST API → Datenbank
API-Nutzung

	•	GET (Daten laden)

	•	POST (Datensätze erstellen)

	•	PATCH (Datensätze aktualisieren)

Authentifizierung über API Key im Header.

⸻
4. Datenbankstruktur
Tabellen
mitglieder

	•	id

	•	name

	•	telefon

	•	email

	•	mitgliedsart_id
mitgliedsarten

	•	id

	•	name

	•	beitrag
produkte

	•	id

	•	name
entnahmen

	•	id

	•	mitglied_id

	•	produkt_id

	•	menge

	•	gesamtpreis

	•	zeitpunkt

	•	rechnung_id (optional)
rechnungen

	•	id

	•	datum

	•	typ (entnahme / mitgliedsbeitrag)

	•	rechnungsnummer

	•	mitglied_id
mitgliedsbeitraege

	•	id

	•	mitglied_id

	•	mitgliedsart_id

	•	jahr

	•	betrag

	•	status

	•	bezahlt_am
Beziehungen

	•	entnahmen verknüpfen mitglieder und produkte

	•	rechnungen bündeln entnahmen

	•	mitgliedsbeitraege gehören zu mitgliedern und mitgliedsarten

⸻
5. Wichtige Codebestandteile
Daten laden

	•	Zentrale Funktion zum Laden aller Tabellen über Supabase API
Globaler Zustand

	•	Arrays für alle Tabellen (members, products, entnahmen, etc.)
Navigation

	•	Button führt fix auf:
https://stefanoberhuber.github.io/Tennisclub-Hopfgarten/
Modal-System

	•	Dynamisches Öffnen/Schließen von Overlays

	•	Button wird bei offenem Modal deaktiviert
UI-Funktionen

	•	Filter für Entnahmen (Datum, Mitglied, Status)

	•	Autocomplete für Mitglieder

	•	Tabellenbasierte Darstellung aller Daten

⸻
6. Aktueller Stand
Implementiert

	•	Mitglieder anlegen und bearbeiten

	•	Mitgliederliste mit Suche

	•	Entnahmen erfassen und anzeigen

	•	Offene Posten berechnen

	•	Rechnungen anzeigen (inkl. Details)

	•	Mitgliedsbeiträge generieren und verwalten

	•	Statistiken (Produkte, Umsatz, Ranking)

	•	Modal-basierte UI

	•	Navigation zwischen Admin- und Hauptseite

	•	UI-Anpassungen (Abstand, Button deaktivieren bei Modal)

⸻
7. Betrieb / Handling
Hardware

	•	Tablet am Kühlschrank installiert

	•	Dauerhaft verfügbar

	•	Für alle Mitglieder zugänglich
Nutzung durch Mitglieder

	•	Kein Login

	•	Auswahl des eigenen Namens

	•	Auswahl von Produkten

	•	Speicherung der Entnahme
Nutzung durch Admin

	•	Separate Admin-Seite

	•	Zugriff über eigenes Gerät

⸻
8. Bekannte Probleme & Einschränkungen

	•	Kein Login-System

	•	API Key im Frontend sichtbar

	•	Keine Zugriffsbeschränkung auf Admin-Funktionen

	•	Keine umfassende Fehlerbehandlung

	•	Keine Datenvalidierung über einfache Checks hinaus

	•	Alle Daten werden vollständig geladen (keine Pagination)

⸻
9. Offene Punkte (faktisch, ohne Bewertung)

	•	Struktur der Admin- und Hauptseite (beide aktuell als index möglich)

	•	Keine expliziten Angaben zu Datenbank-Constraints oder Indizes

	•	Keine Angaben zu Authentifizierung oder Rollenmodell

⸻

Diese Zusammenfassung enthält ausschließlich den aktuellen Stand des Systems ohne zusätzliche Interpretation oder Erweiterung.
 
