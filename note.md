# Notizen

## allgemeines zur oberfläche

- "abbrechen" und "rückgängig" bzw "wiederholen" einfügen

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

### Upscaler & Enhancer

- Enhancer kann nicht gestartet werden oder schlaegt fehl.
- Upscaler zeigt offenbar keine sichtbare Wirkung oder tut nichts.
- TensorFlow.js wird jetzt explizit vor dem Enhancer geladen.
- Modellpfade wurden auf offizielle UpscalerJS-Pakete umgestellt.
- Upscaler fordert jetzt explizit ein neues `src`-Bild als Ergebnis an.
- Sichtbares Fehlerbanner fuer Modell-/CDN-Ladefehler wurde eingebaut.

### Hintergrundentferner

- Bei vielen Bildern bleibt in der Mitte des Objekts noch eine Hintergrund-Zone stehen.
- Die Freistellung wirkt bei manchen Motiven instabil oder unvollstaendig.
- Neuer Modus `Schnell` eingebaut, der die teure Masken-Nachbearbeitung ueberspringt.
- Nachbearbeitung der Alpha-Maske wurde eingebaut: kleine Loecher innerhalb des Objekts sollen nun besser geschlossen werden.
- Groesste zusammenhaengende Vordergrund-Komponente wird jetzt bevorzugt behalten, damit Geisterflaechen ausserhalb des Hauptobjekts eher verschwinden.
- Neuer Freistellmodus `Streng fuer Logos & Buchstaben` hinzugefuegt.
- Muss noch mit problematischen Beispielbildern gegengeprueft werden.
- Neues Beispiel: Metallbuchstabe `D` zeigt nach der Freistellung noch einen grossen rechteckigen Restbereich und verstreute graue Artefakte um das Objekt.
- Vergleichsbild `O` wirkt deutlich sauberer. Das Problem tritt also motivabhaengig auf, besonders bei stark strukturierten, dunklen oder halbtransparent wirkenden Randbereichen.

### Bildqualitaet

- Manche Bilder sehen nach der Verarbeitung sichtbar komisch oder fehlerhaft aus.
- Beispielbild soll noch als Referenz hinzugefuegt werden.

### Fortschritt / UX

- Die Fortschrittsanzeige bleibt offenbar auf `1` stehen oder aktualisiert sich nicht korrekt.
- Fortschrittslogik wurde auf Gesamtfortschritt pro Batch umgestellt.
- Bildkarten zeigen waehrend Freistellen und Enhance jetzt einen direkten Bearbeitungsstatus.

### Naechste Debug-Schritte

- Auf Artefakte pruefen und beheben.

- Pruefen, ob fuer schwierige Motive noch staerkere Masken-Nachbearbeitung noetig ist.
- Gegenpruefen, wie gut der neue strenge Modus bei Buchstaben, Logos und Symbolen funktioniert.
- Speziell Buchstaben, Logos und freistehende Symbole mit harten Kanten als eigene Testgruppe behandeln.
- Enhancer-/Upscaler-Import und Laufzeitfehler gezielt pruefen.
- Sichtbar machen, ob der Upscaler wirklich ein neues Ergebnisbild erzeugt.
- Gegenpruefen, ob die neue Initialisierung die bisherigen Startfehler beseitigt.

## Verbesserungen

- Freistellen beschleunigen oder einen schnelleren Modus anbieten.
- Erledigt: `Schnell`-Freistellmodus hinzugefuegt.
