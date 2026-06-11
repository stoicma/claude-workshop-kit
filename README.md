# Claude Workshop Kit

Das Begleitmaterial zum AI-Workshop. Hier liegt alles, was ihr während und nach den Sessions braucht: der Terminal-Spickzettel und das Deck-Template, aus dem ihr euren eigenen Folien-Skill baut.

Begleitlektüre zum Nachlesen: [stokic.ai/claude-guide](https://stokic.ai/claude-guide)

Fragen oder etwas klemmt: marko@stokic.ai

## Was ist hier drin

| Ordner / Datei | Was es ist |
|---|---|
| `README.md` | Diese Seite: Spickzettel + Anleitung |
| `team-deck-template/` | Der Folien-Skill, den ihr zwischen Session 1 und 2 auf euren Hausstil kalibriert |

## Der Terminal-Spickzettel

Claude Code bedient sich wie ein Chat, nur im Terminal. Diese acht Handgriffe reichen für den Anfang.

**Vorab einmal:** aktuelle Version sicherstellen mit `claude update`. Die aktuelle Oberfläche könnt ihr mit der Maus bedienen (Befehle anklicken, in Dialogen klicken statt Pfeiltasten). Wer frisch installiert hat, hat sie schon.

| Handgriff | So geht's |
|---|---|
| **Modus wechseln** | `Shift+Tab` schaltet durch: Normal, Auto-Accept (Claude darf Dateien direkt ändern), Plan-Modus (erst denken und planen, nichts anfassen). Für den Anfang: Plan-Modus für alles Größere. |
| **Neue Zeile ohne Absenden** | `Shift+Enter` (funktioniert in Apple Terminal, Windows Terminal und den meisten modernen Terminals). Geht es nicht: `Ctrl+J` geht überall. In VS Code vorher einmal `/terminal-setup` ausführen. |
| **Screenshot einfügen** | Screenshot in die Zwischenablage (Mac: `Cmd+Ctrl+Shift+4`, Windows: `Win+Shift+S`), dann im Terminal `Ctrl+V`. Achtung Mac: wirklich `Ctrl+V`, nicht `Cmd+V`. Claude sieht das Bild und kann damit arbeiten. |
| **Claude unterbrechen** | `Esc` stoppt Claude mitten in der Antwort. Bereits Erledigtes bleibt erhalten. |
| **Zurückspulen** | Zweimal `Esc` (bei leerem Eingabefeld) öffnet das Rewind-Menü: zu einem früheren Punkt im Gespräch zurückspringen. |
| **Datei erwähnen** | `@` tippen, dann Dateinamen anfangen: Autocomplete schlägt vor. So zeigt ihr Claude gezielt eine Datei. |
| **Shell-Befehl direkt** | `!` am Zeilenanfang führt den Befehl direkt aus, ohne dass Claude ihn interpretiert. |
| **Hilfe** | `/help` zeigt alle Befehle. `/` allein öffnet das Befehlsmenü zum Durchklicken. |

**Und die nullte Regel:** Wenn ihr nicht wisst, wie etwas geht, fragt Claude selbst. „Wie füge ich hier einen Screenshot ein?" funktioniert.

## Git, das Minimum

Ihr müsst kein Git lernen. Zwei Befehle reichen, um mit diesem Kit zu arbeiten:

```
git clone https://github.com/stoicma/claude-workshop-kit.git
```

holt euch das Kit auf den Rechner (machen wir in Session 1 gemeinsam), und

```
git pull
```

im Kit-Ordner holt später Updates. Alles andere übernimmt Claude für euch: sagt einfach „leg das auf GitHub ab" oder „hol die neueste Version", wenn es so weit ist.

## Der Deck-Skill (eure Hausaufgabe nach Session 1)

In `team-deck-template/` liegt ein Skill, der Folien im klassischen Beratungs-Look baut. Er ist absichtlich noch nicht auf euch eingestellt: beim ersten Aufruf stellt er euch sechs Fragen zu eurem Hausstil und kalibriert sich anhand eurer Referenz-Decks (die zwei aus der Checkliste).

So startet ihr nach Session 1:

1. Terminal im Kit-Ordner öffnen, `claude` starten
2. Sagen: „Lies team-deck-template/SKILL.md und führe das Kalibrierungs-Interview mit mir."
3. Den sechs Fragen folgen, eure zwei Referenz-Decks bereithalten
4. Ein erstes Deck zu einem echten Thema aus eurer Arbeit bauen lassen

Das Ergebnis bringt ihr in Session 2 mit. Steckenbleiben ist erlaubt, genau dafür ist die Session da. Aber schreibt mir vorher: marko@stokic.ai
