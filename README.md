# Pixel-Aquarium

Ein Aquarium in Pixel-Art: Fische kaufen und benennen, Deko, Pflanzen, Hintergründe, Effekte,
Album, Erfolge – und ein **Multiplayer**, bei dem mehrere Leute dasselbe Becken sehen und bearbeiten.

Alles steckt in einer einzigen Datei (`index.html`), ohne Build-Schritt und ohne eigenen Server.

## Multiplayer

Der Multiplayer läuft **direkt zwischen den Browsern** (WebRTC über [PeerJS](https://peerjs.com)).
Du brauchst dafür keinen eigenen Server und keine Zugangsdaten.

- **Hosten:** *Multiplayer → Raum hosten* erzeugt einen 6-stelligen Code. Dein aktuelles Aquarium
  wird zum gemeinsamen Becken.
- **Beitreten:** Code eingeben und *Beitreten* drücken, oder den Link öffnen, den *Link kopieren*
  erzeugt (`…/#raum=CODE`). Das eigene Becken des Gastes bleibt unberührt und ist nach *Verlassen*
  wieder da.
- **Synchronisiert** wird: Fische samt Position, Namen und Zubehör, Deko inklusive Größe und
  Position, Hintergrund, Boden, Rahmen, Effekt, Kulisse und das Futter im Wasser.
- **Pro Spieler** bleiben Münzen, Erfolge, Album und Goldene Blasen.
- Alle können kaufen, verkaufen, umbenennen, verschieben und füttern. Wer das Futter ins Wasser
  wirft, bekommt die Münzen, wenn es gefressen wird.

### Gut zu wissen

- Der **Host** berechnet die Fischbewegung. Sein Tab muss **offen und sichtbar** bleiben, sonst
  pausiert der Browser die Animation und die Fische bleiben bei allen stehen.
- Geht der Host weg, bekommen die Gäste die Meldung „Der Host hat den Raum verlassen“ und spielen
  lokal weiter. Ihr eigenes gespeichertes Becken wird dabei nicht überschrieben.
- Ändern zwei Leute im selben Moment etwas, gilt die zuletzt gesendete Änderung.
- Die Verbindung wird über den kostenlosen öffentlichen PeerJS-Server vermittelt. In sehr
  strengen Firmen- oder Schulnetzen kann sie scheitern.
- Bei WebRTC sehen die Mitspieler technisch die IP-Adressen der anderen. Gib den Code nur an Leute,
  denen du vertraust.

## Technik

- Reines HTML, CSS und JavaScript, gezeichnet auf einem 320×180-Canvas.
- Alle Grafiken sind als Text-Sprites im Code definiert und werden zur Laufzeit gerendert.
- Gespeichert wird im `localStorage` des Browsers (nicht im Multiplayer).
- Externe Abhängigkeiten: PeerJS 1.5.4 (über jsDelivr) und die Schrift „Press Start 2P“ (Google Fonts).

Bibliothek: PeerJS, MIT-Lizenz.
