# ich-bin

`index.html` – Mikrofon-Auswahl im Browser. Es wird ausschließlich Audio angefordert
(`getUserMedia({ audio, video: false })`) und nur Geräte vom Typ `audioinput` werden
aufgelistet – keine Kamera, keine Lautsprecher.

Öffnen über HTTPS oder `localhost`, z. B.:

```sh
python3 -m http.server 8000
# dann http://localhost:8000 öffnen
```
