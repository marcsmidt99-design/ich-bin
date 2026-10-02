# Ich bin

`index.html` ist die App „Ich bin“: Du sprichst Sätze in deiner eigenen Stimme ein und hörst sie
als Meditation, unterlegt mit Musik und zwei Tönen (links 200 Hz, rechts je nach Wahl 210, 206
oder 202 Hz).

Es gibt fünf Ziele mit je 30 Sätzen in drei Teilen, jeden Satz in einer kraftvollen („Ich bin …“)
und einer sanften Fassung („Ich erlaube mir …“), dazu ein eigenes Set mit bis zu zehn selbst
geschriebenen Sätzen. Ein eigenes Set lässt sich als Link weitergeben. Der Link enthält nur die
Texte, die andere Person spricht sie selbst ein.

`v6.html` ist die vorige Fassung als Rückfall, falls die neue auf einem Gerät nicht läuft.

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
