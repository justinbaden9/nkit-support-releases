# NK IT Support - Veroeffentlichungen

Dieses Repository enthaelt **keinen Quellcode**. Es dient ausschliesslich dazu,
die jeweils aktuelle Fassung von **NK IT Support** bereitzustellen.

Die Anwendung sieht beim Start in `update.json` nach, ob eine neuere Fassung
vorliegt, laedt sie gegebenenfalls im Hintergrund und uebernimmt sie beim
naechsten Start.

## Warum ein eigenes, oeffentliches Repository

Waere die Beschreibungsdatei in einem privaten Repository hinterlegt, muesste
in jeder ausgelieferten EXE ein Zugangsschluessel stecken - und der liesse sich
dort auslesen. Damit haette jeder Kunde Lesezugriff auf den Quellcode. Deshalb
liegen hier nur die fertigen Dateien; die Entwicklung bleibt privat.

## Aufbau von update.json

```json
{
  "version": "3.1.0",
  "url": "https://github.com/justinbaden9/nkit-support-releases/releases/download/v3.1.0/NK-IT-Support.exe",
  "sha256": "GROSSBUCHSTABEN-HEX",
  "size": 70422101,
  "notes": "Kurzer Hinweis, was neu ist."
}
```

Die Anwendung uebernimmt eine Datei nur, wenn

- die Adresse mit `https` beginnt,
- die Pruefsumme exakt stimmt und
- die Versionsnummer hoeher ist als die laufende Fassung.

Stimmt etwas nicht, bleibt die vorhandene Fassung unveraendert in Betrieb.

## Eine neue Fassung veroeffentlichen

1. Im Entwicklungsprojekt die Version in `NKITSupport.csproj` erhoehen und
   `build.ps1` ausfuehren.
2. Ein Release mit dem Kennzeichen `vX.Y.Z` anlegen und die EXE als
   `NK-IT-Support.exe` anhaengen.
3. `update.json` in diesem Zweig auf die neue Version, Adresse und Pruefsumme
   setzen.

Erst Schritt 3 macht die Fassung fuer die Kunden sichtbar. Bis dahin passiert
nichts - damit laesst sich eine Veroeffentlichung in Ruhe vorbereiten.

(c) NK IT Service
