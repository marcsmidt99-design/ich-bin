# Ich bin

Die App ist die eine Datei `index.html`. Sie läuft über GitHub Pages unter
https://marcsmidt99-design.github.io/ich-bin/.

## Regeln für die Arbeit an der App

- **Nur hier bauen.** Änderungen an der App gehören in `index.html` in diesem Repo. Baue keine
  zweite Fassung als Claude-Artifact oder Vorschau-Seite.
- **Mikrofon.** Die direkte Aufnahme übers Mikrofon ist die Hauptfunktion und darf bei keiner
  Änderung wegfallen. „Datei wählen“ ist nur der Rückfall.
- **Testlink.** Das Mikrofon geht nur unter der Pages-Adresse (HTTPS). In Claude-Artifacts und
  eingebetteten Vorschauen ist es immer gesperrt. Gib zum Testen deshalb immer die Pages-Adresse
  weiter, nie einen Vorschau-Link.
- **Ablauf.** Der Besitzer arbeitet am Handy. Arbeite auf einem Branch `claude/…`, öffne einen
  Pull Request und erkläre in einfachen Worten, was sich ändert. Live ist eine Änderung erst nach
  dem Merge.
- **Version.** Erhöhe bei jeder Änderung `VERSION` in `index.html`. Die Zahl steht in der
  Zielauswahl und in der Rückmeldung, damit sichtbar ist, ob die neue Fassung angekommen ist.
- **Aufnahme und Wiedergabe.** Dieser Teil ist auf dem iPhone heikel und lässt sich hier nicht auf
  einem echten Gerät testen. Ändere ihn nur, wenn es nötig ist, und sag dazu, dass ein Test am
  Handy aussteht.
- **Keine Heilversprechen.** Die Kategorie „Raus aus dem Stimmungstief“ ist aus dem Start
  genommen und kommt erst nach einer Rechtsprüfung zurück.

## Aufbau

- Jeder Satz hat einen Schlüssel aus Ziel, Fassung und Platz im Bogen, zum Beispiel `wert.s.4`
  (`k` kraftvoll, `s` sanft, `x` eigenes Set). Unter diesem Schlüssel liegt die Aufnahme in
  IndexedDB (`ichbin` / `rec`).
- Ausnahme: Die zehn Sätze der ersten Fassung behalten die Schlüssel `0` bis `9` (`LEGACY`), damit
  alte Aufnahmen erhalten bleiben und `v6.html` sie weiter findet.
- Ein Ziel hat 30 Sätze in drei Teilen zu je zehn. Teil 1 (`first`) ist eine Auswahl über den
  ganzen Bogen, die Session spielt alle aufgenommenen Sätze in der Reihenfolge des Bogens.
- `PLUS_OPEN = true` gibt in der Testphase alles frei. Mit `false` bleibt nur Teil 1 von
  „Positive Gedanken“ in der kraftvollen Fassung offen, alles andere führt zur Plus-Seite.
- Die App hat keinen Server. Einstellungen und Zähler liegen in `localStorage` unter `ichbin.*`.

## Stand und nächster Schritt

Version 7 (2. Oktober 2026): fünf Ziele mit je 30 Sätzen, kraftvolle und sanfte Fassung, eigenes
Set mit Link zum Teilen, Frequenzwahl, Pausenlänge, gemischte Reihenfolge, Stimmung vor und nach
der Session, einzelne Aufnahme löschen, Aufnahmen als ZIP sichern, „Rückmeldung senden“.

Der Besitzer hat entschieden, die App auszubauen, bevor der Test mit 20 Personen gelaufen ist. Der
Test bleibt der nächste Schritt: Mindestens die Hälfte soll an 4 von 7 Tagen hören. Gemessen wird
über „Rückmeldung senden“ in der Zielauswahl, die Testpersonen schicken den Text selbst.

`v6.html` ist die vorige Fassung als Rückfall. Sie kann weg, sobald Version 7 am iPhone geprüft ist.

Offen, weil es Konten oder Angaben des Besitzers braucht: Bezahlen, Impressum und
Datenschutzerklärung, Fassung für die App-Stores. Offen, weil es sich hier nicht anhören lässt:
Klangteppiche wie Regen oder Meer, vorgelesenes Intro. Tägliche Erinnerungen gehen in einer
Web-App nicht verlässlich.
