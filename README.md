# Ich bin

`index.html` ist die App „Ich bin“: Du sprichst zehn Sätze in deiner eigenen Stimme ein und
hörst sie als Meditation, unterlegt mit zwei Tönen (links 200 Hz, rechts 210 Hz).

Die ganze App steckt in dieser einen Datei. Aufnahmen bleiben im Browser auf dem Gerät,
nichts wird hochgeladen.

## Mikrofon

- Es wird ausschließlich Audio angefordert (`getUserMedia({ audio, video: false })`), nie die Kamera.
- Sind mehrere Mikrofone angeschlossen, erscheint im Aufnahme-Schritt eine Auswahl mit Pegelanzeige.
  Aufgelistet werden nur Geräte vom Typ `audioinput`.
- Die Wahl wird gemerkt. Fehlt das Gerät später oder wird es abgezogen, nimmt die App das Standardmikrofon.
- Ohne Mikrofonzugriff lassen sich fertige Aufnahmen über „Datei wählen“ laden.

## Öffnen

Der Mikrofonzugriff braucht HTTPS oder `localhost`, z. B.:

```sh
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```

## Rückmeldung im Test

In der Zielauswahl steht „Rückmeldung senden“. Der Knopf baut einen kurzen Text mit den Hörtagen der
ersten Woche, der Zahl der Sessions und Minuten und der Zahl der aufgenommenen Sätze. Die Testperson
verschickt ihn selbst, zum Beispiel per Messenger. Die App sendet nichts von allein.
