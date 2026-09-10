# AI Studio — Vorlagen-Foliensatz: Hinweise für Claude Code und Codex

In diesem Ordner liegt ein **Vorlagen-Foliensatz** für die Veranstaltung «AI Studio and the
Future of Work» der Executive School der Universität St.Gallen. Er ist eine einzelne,
eigenständige reveal.js-Datei im Comicstil «Golden Age».

Wer hier arbeitet, will meistens **eigene Folien bauen**, nicht die Vorlage umbauen. Die Regeln
unten sind das Ergebnis mehrerer Runden am Layout; halte dich an sie, statt sie neu zu erfinden.

## Die eine wichtige Regel

**`AI Studio — Vorlagen-Foliensatz v1.html` ist die Quelle der Wahrheit.** Es gibt keinen Build,
keinen Generator, keine Abhängigkeiten. Alles — reveal.js 5.2.0, die drei Schriften, das
HSG-Logo — steckt eingebettet in der Datei. Sie läuft offline in jedem Browser.

Für einen eigenen Foliensatz: **Datei kopieren**, neu benennen (z. B. `AI Studio — Tag 2.html`),
in der Kopie arbeiten. Die Vorlage selbst bleibt unverändert, damit die nächste Person wieder
sauber starten kann.

## So entsteht eine neue Folie

1. In der Datei die passende Vorlage suchen. Jede beginnt mit einem Kommentar
   `<!-- ===== 06 · Vorlage: Inhalt ... ===== -->` und ist ein `<section data-id="…">`-Block
   bis zum schliessenden `</section>`.
2. Den **ganzen Block** kopieren und an die gewünschte Stelle in `<div class="slides">` einfügen.
3. `data-id` auf einen eigenen, sprechenden Namen setzen (`data-id="S12Agenten"`). Der Name ist
   frei, muss aber eindeutig sein.
4. **Nur die Texte ersetzen.** Positionen, Grössen, Farben und Abstände stehen als
   `style="…"`-Attribute direkt am Element und bleiben stehen.
5. Fusszeile anpassen: Folientyp und Nummer im rechten Teil (`Inhalt · 08 / 27`).
6. Sprechernotizen im `<aside class="notes">` ausfüllen (Gerüst: ZEIT / SAGEN / ÜBERLEITUNG / NICHT).

Passt der Text nicht ins Layout: **Folie teilen, nicht Schrift verkleinern.** Das ist die
häufigste Verschlechterung und sie fällt im Raum sofort auf.

## Das Raster

Alle Folien sind absolut positioniert in einem Rahmen von **1280 × 720 px**. Die Zahlen sind
verbindlich, damit die Folien im Durchlauf nicht springen:

| Zone | Position |
|---|---|
| Rand links und rechts | `left: 64px`, Breite `1152px` |
| Kopfzeile | `top: 40px` — Eyebrow links, **HSG-Logo rechts** |
| Titel (h2) | `top: 104px`, einzeilig |
| Untertitel | direkt darunter, einzeilig |
| Inhalt | **`top: 232px` bis `616px`** — nichts beginnt zwischen 105 und 231 px |
| Quellenzeile | `top: 626px` (bei vollflächigen Folien 652–656 px) |
| Fusszeile | `top: 684px` — Vortragstitel links, Folientyp und Nummer rechts |

Das HSG-Logo steht **immer oben rechts** und wird weder verschoben noch skaliert. Auf der
Titelfolie ist es Teil derselben Kopfzeile.

## Farben und Schriften

```
Papier      #F6EBD0   Grund aller Folien (helles Gelb-Ocker, nie Weiss)
Tusche      #111111   Konturen, Text, Schlagschatten
Rot         #D62828   Akzent, Kapitelnummern, Titel-3D, Warnung
Blau        #2456C7   zweiter Akzent, Zahlen, Zwischentitel
Gelb        #F9D949   Caption-Kästen, Bursts
Mint        #3DBE8B / #9FE3C4   ausschliesslich für die Beispielfirma
Panel       #FFFBEF   Füllung der Kästen
Braun       #4A3D24 / #6B5B3A / #8A7A55   Fliesstext, Quellen, Kleingedrucktes
Nachtblau   #1B1F3B   Hintergrund von Code- und Video-Panels
```

```
Bangers          Klasse .display   Titel, Zahlen, Kapitelnummern (nur Versalien!)
Barlow           Fliesstext, Panels, Captions (400 / 600 / 700)
JetBrains Mono   Klasse .mono      Code, Dateinamen, URLs
```

Bangers kennt **keine Kleinbuchstaben** — Titel werden immer als Ruf gelesen. Wer einen ruhigen
Titel braucht, nimmt Barlow 700.

## Bausteine

Diese Klassen sind definiert und decken fast alles ab. Neue Klassen nur anlegen, wenn wirklich
keine passt.

| Klasse | Was sie ist |
|---|---|
| `.display` | Bangers. Für Titel, grosse Zahlen, Kartentitel |
| `.mono` | JetBrains Mono. Für Code im Fliesstext, Dateinamen |
| `.caption` | Gelber Kasten mit schwarzem Rand und Schlagschatten — der Eyebrow oben links |
| `.panel` | Weisser Kasten, 4 px Rand, 8 px Schlagschatten — der Standard-Container |
| `.bubble` | Sprechblase mit Zipfel unten links — für Fragen ans Publikum und Prompts |
| `.code` | Nachtblaues Code-Panel; darin `.k` Schlüsselwort, `.s` String, `.c` Kommentar, `.n` Zahl |
| `.num` | Rote Ziffer im Kreis — für nummerierte Schritte |
| `.tag` | Kleiner Rahmen-Tag; Hintergrundfarbe setzt die Bedeutung |
| `.mint` | Modifier: färbt `.caption` oder `.tag` mint — **nur für die Beispielfirma** |
| `.pf-strip` | Mintgestreifter Balken am linken Rand — markiert Fallstudien-Folien |
| `.dots` | Ben-Day-Punktraster als Overlay, immer mit `mask-image` weich auslaufend |
| `.title3d` | Roter Titel mit blauem und schwarzem Versatz — nur für die Titelfolie |
| `.foot` | Fusszeile |

**Bildmarken statt Icons:** keine Emoji, keine Icon-Fonts. Formen werden als Inline-SVG
gezeichnet (siehe Burst auf der Titelfolie, Play-Stern auf der Video-Folie).

## Die dreizehn Vorlagen

| # | `data-id` | Wofür |
|---|---|---|
| 01 | `Main` | Titelfolie: 3D-Titel, Edition-Balken, Burst mit der Kernzahl |
| 02 | `AgendaDrei` | Programm über mehrere Tage, drei Panels |
| 03 | `AgendaTag` | Run-of-Show eines Tages, zwei Spalten mit Zeit und Format-Tag |
| 04 | `Kapitel` | Kapiteltrenner: grosse Ziffer in Ben-Day-Punkten, Aussage rechts |
| 05 | `Statement` | Ein Satz, ganzseitiger Burst, sonst nichts |
| 06 | `Inhalt` | **Der Standard.** Kopf-Trio, drei Panels, Frage in der Sprechblase |
| 07 | `Code` | Quelltext links, drei nummerierte Callouts rechts |
| 08 | `Screenshot` | Bild über die volle Breite (1152 × 522 px), Caption als Overlay |
| 09 | `Video` | Video-Panel 16:9 links, Beobachtungsfragen rechts |
| 10 | `Prompting` | Prompt-Muster in der Sprechblase, Hinweise rechts |
| 11 | `PfefferminziaFall` | Kontext zur Beispielfirma, Mint-Streifen links |
| 12 | `PfefferminziaDrill` | Aufgabenblatt: Rolle und Ergebnis links, Prompts als Blasen rechts |
| 13 | `Schluss` | Zum Mitnehmen, Ausblick, Kontakt |

Fehlt eine Vorlage: aus `Inhalt` ableiten. Kopf-Trio behalten, den Bereich ab 232 px neu füllen.

## Screenshot einsetzen

In der Vorlage `Screenshot` steht ein gezeichneter SVG-Platzhalter. Ersetze das ganze `<svg>…</svg>`
im Panel durch:

```html
<img src="assets/screenshot-cockpit.png" alt="[Was zu sehen ist]"
     style="width: 1152px; height: 522px; object-fit: cover; display: block;">
```

Das Bild vorher auf **1152 × 522 px** zuschneiden, sonst verzerrt es. Soll die Datei weitergegeben
werden und alleine lauffähig bleiben, das Bild als `data:`-URI einbetten statt zu verlinken.
Der passende Kommentar steht an Ort und Stelle im Quelltext.

## Video einbetten

In der Vorlage `Video` steht das fertige `<iframe>`-Markup als Kommentar direkt über dem Panel.
Kommentar auflösen, Panel löschen, `VIDEO_ID` und `start=` setzen. Wichtig:

- `youtube-nocookie.com` statt `youtube.com` verwenden.
- Ohne Netz spielt das Video nicht. Für den Notfall bleibt der gezeichnete Platzhalter mit der
  URL eine gültige Rückfallebene — dann wird das Video eben beschrieben statt gezeigt.

## Inhaltliche Regeln

Diese Regeln stammen aus dem Foliensatz, aus dem die Vorlage abgeleitet ist. Sie sind der Grund,
warum der Satz funktioniert:

1. **Action-Titel.** Der Titel ist die **Aussage** der Folie, nicht ihr Thema. Ein ganzer Satz.
   Liest man alle Titel nacheinander, versteht man den ganzen Vortrag. Ausnahmen: Titelfolie,
   Agenda, Kapiteltrenner, Schluss.
2. **Titel und Untertitel bleiben einzeilig.** Titel etwa 49 Zeichen, Untertitel etwa 105 Zeichen.
   Was nicht passt, wandert in den Untertitel oder auf eine zweite Folie.
3. **Eine Aussage pro Folie.** Ein Satz, den man laut sagen kann. Elemente, die ihn nicht tragen,
   fliegen raus. Keine Kachelwände, keine Logowände.
4. **Keine Dreier-Automatik.** Mal zwei, mal vier Punkte, ungleiche Tiefe. So wie die Sache es hergibt.
5. **Zahlen brechen nie um.** Geschützte Leerzeichen bei `3 198`, `71 %`, `n = 3 198`, `CHF 1'950`.
6. **Kartentitel sind ein bis zwei Wörter** («Schaden», «Police», «Urteil»), der Satz steht daneben.
7. **Quellen sind Dritte oder eigene Publikationen**, nie interne Notizen. Fehlt eine Angabe, bleibt
   ein sichtbarer Platzhalter `[Quelle prüfen]` stehen — nichts erfinden.
8. **Schriftgrössen:** Fliesstext nicht unter 19 px, nichts auf der Folie unter 15 px.

## Die Beispielfirma

Der Kurs arbeitet mit **Pfefferminzia**, einem frei erfundenen Versicherer (Datensatz:
`github.com/falkue/Pfefferminzia`, Zweig `teilnehmer`). Folien über sie sind an drei Dingen
erkennbar: Mint-Streifen am linken Rand (`.pf-strip`), mintfarbener Eyebrow (`.caption.mint`)
und dem Logo-Platzhalter daneben.

**Pfefferminzia hat noch kein Logo und kein Branding.** In der Vorlage steht ein gestrichelter
Kasten `[Logo Pfefferminzia · folgt]`. Er bleibt stehen, bis eines existiert — nicht durch ein
selbstgebautes Logo ersetzen, das wird separat entschieden.

Beim Erfinden von Beispielen aus diesem Universum: Alle Personen, Firmen und Zahlen sind
synthetisch. Der Hinweis darauf gehört auf die Fallstudien-Folie.

## Präsentieren und exportieren

| | |
|---|---|
| Weiter / zurück | Pfeiltasten, Leertaste |
| Referentenansicht mit Notizen | **S** |
| Vollbild | **F** |
| Übersicht aller Folien | **ESC** |
| PDF-Export | `?print-pdf` an die URL hängen, dann im Browser drucken, «Hintergrundgrafiken» anhaken |

Schrittweises Aufdecken: einem Element `class="fragment"` geben, die Reihenfolge über
`data-fragment-index="0"`, `"1"` … steuern.

## Was du nicht tun solltest

- Den Skin im `<style>`-Block umbauen, um eine einzelne Folie zu retten. Lieber die Folie ändern.
- Schriftgrössen unter die Grenzen drücken, damit mehr Text passt.
- Das HSG-Logo verschieben, verkleinern oder einfärben.
- Weisse Folienhintergründe einführen. Das Papier ist `#F6EBD0`, das ist der halbe Charakter.
- Emoji als Icons verwenden.
- Mint für irgendetwas anderes als die Beispielfirma verwenden.
- Die Datei neu erzeugen wollen. Es gibt keinen Generator mehr; hier wird direkt editiert.

## Herkunft und Rechte

Struktur (Raster, Folientypen, Kopf-Trio, Fusszeile) stammt aus dem Foliensatz «Synthetic
Personas» für den FHNW E-Commerce Day 2026, das Aussehen ist für das AI Studio neu entworfen.
Schriften: Bangers, Barlow, JetBrains Mono, alle SIL Open Font License 1.1, eingebettet.
reveal.js 5.2.0, MIT. Das HSG-Logo ist Marke der Universität St.Gallen und nur im Rahmen von
Veranstaltungen der Universität zu verwenden.
