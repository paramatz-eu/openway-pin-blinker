# OpenWay PIN-Blinker

Gibt die PIN eines **Itron OpenWay 3.HZ** automatisch mit der Taschenlampe eines Android-Handys ein und setzt danach **Inf On** (erweiterter Datensatz mit Momentanleistung) sowie optional **Pin OFF**.

**App:** https://paramatz-eu.github.io/openway-pin-blinker/

## Benutzung
1. Seite in Chrome auf Android öffnen, PIN und Zählertyp (Einrichtung: 8 Schritte, Zweirichtung: 13 Schritte) wählen.
2. Das Zählerdisplay muss dunkel sein (mindestens 2 Minuten nicht bedient).
3. **Start** tippen, Kamera erlauben, Blitz-LED während des Countdowns vor die optische Taste halten.
4. Nur einmal ausführen. Die langen Impulse schalten um.

Die PIN wird nur lokal im Browser gespeichert. Die Sequenz basiert auf der Itron-Anleitung (langer Impuls ≥ 5 s, Ziffernübernahme nach 3 s) und auf den Angaben von iometer (8 bzw. 13 Schritte bis „Inf“).

## Parameter per Link
`https://paramatz-eu.github.io/openway-pin-blinker/?pin=1234&typ=e`

| Parameter | Werte | Bedeutung |
|---|---|---|
| `pin` | 4 Ziffern | Zähler-PIN |
| `typ` | `e` / `z` | Einrichtungszähler (8 Schritte) / Zweirichtungszähler (13 Schritte) |
| `inf` | `1` / `0` | „Inf On“ setzen (Standard 1) |
| `pinoff` | `1` / `0` | PIN-Schutz ausschalten (Standard 1) |
| `video` | `1` / `0` | Debug-Video aufnehmen |
| `start` | `1` | nach dem Countdown automatisch starten, höchstens einmal pro Tab |
| `on`, `off`, `digit`, `long`, `wake` | ms | Zeiten (Standard 400, 600, 4000, 6500, 2000) |
| `count` | s | Countdown (Standard 5, bei Autostart mindestens 5) |

Unter „Link mit Einstellungen“ erzeugt die Seite den passenden Link aus den aktuellen Einstellungen.

## Debug-Video
Mit `video=1` bzw. der Option „Debug-Video aufnehmen“ filmt die Rückkamera während des Ablaufs. Eingeblendet werden Laufzeit, Schritt, erwartete Zähleranzeige und Lampenzustand. Danach kann das Video gespeichert oder zusammen mit einem Schaltprotokoll (Zeitstempel jeder Flanke inkl. Latenz) geteilt werden.
