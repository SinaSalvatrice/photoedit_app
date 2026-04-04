# Notizen

## Menu-Reiter "Batch Editing"

- Bestehender Bereich fuer Stapelbearbeitung der Bilder.

## Menu-Reiter "Showcasing"

Zweite Menuseite mit einer Showcase-Funktion:

- Alle geladenen Bilder sollen in ein frei sichtbares Raster gepackt werden.
- Jedes Bild soll innerhalb des Rasters manuell verschiebbar sein.
- Per Tastendruck oder Button soll sich das Raster wieder automatisch sauber ausrichten lassen.
- Das gesamte Raster soll als PNG exportierbar sein.

### Sinnvolle Zusatzpunkte fuer die Umsetzung

- Abstand zwischen den Bildern konfigurierbar machen.
- Anzahl der Spalten oder automatische Rastergroesse einstellbar machen.
- Optional transparenten oder farbigen Hintergrund fuer den PNG-Export anbieten.
- Vor dem Export eine Live-Vorschau des finalen Layouts zeigen.


## Issues

### Hintergrundentferner

- Bei vielen Bildern bleibt in der Mitte des Objekts noch eine Hintergrund-Zone stehen.
- Die Freistellung wirkt bei manchen Motiven instabil oder unvollstaendig.

### Bildqualitaet

- Manche Bilder sehen nach der Verarbeitung sichtbar komisch oder fehlerhaft aus.
- Beispielbild soll noch als Referenz hinzugefuegt werden.

### Fortschritt / UX

- Die Fortschrittsanzeige bleibt offenbar auf `1` stehen oder aktualisiert sich nicht korrekt.

### Naechste Debug-Schritte

- Fortschrittslogik fuer Hintergrundentferner pruefen.
- Problematische Beispielbilder sammeln und vergleichen.
- Optional Nachbearbeitung der Maske einbauen, um Loecher innerhalb des Objekts zu schliessen.

