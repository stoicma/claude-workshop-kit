# Claude Workshop Kit

Das Begleitmaterial zum AI-Workshop. Hier liegt alles, was ihr während und nach den Sessions braucht: eine kurze CLI-Einführung, der Terminal-Spickzettel und das Deck-Template, aus dem ihr euren eigenen Folien-Skill baut.

Begleitlektüre zum Nachlesen: [stokic.ai/claude-guide](https://stokic.ai/claude-guide)

Fragen oder etwas klemmt: marko@stokic.ai

## Was ist hier drin

| Ordner / Datei | Was es ist |
|---|---|
| `README.md` | Diese Seite: CLI-Intro, Spickzettel, Anleitung |
| `team-deck-template/` | Der Folien-Skill, den ihr zwischen Session 1 und 2 auf euren Hausstil kalibriert |

## Kurz: Was ist ein Terminal, was ist ein CLI?

Das **Terminal** ist ein Textfenster, über das ihr euren Computer direkt steuert. Ein **CLI-Tool** (Command Line Interface) ist ein Programm ohne Knöpfe und Fenster, das in diesem Textfenster läuft. Claude Code ist so ein CLI-Tool.

Warum das für euch interessant ist: **Claude kann jedes CLI-Tool benutzen, das auf eurem Rechner installiert ist.** Je mehr solcher Tools da sind, desto mehr kann Claude für euch erledigen. Beispiel: Mit der **GitHub CLI** (`gh`, mehr dazu unten) kann Claude Projekte von GitHub holen, dort ablegen und veröffentlichen, wenn ihr es einfach auf Deutsch darum bittet. Ihr müsst die Befehle nicht lernen. Claude kennt sie.

Terminal öffnen:
- **Mac:** `Cmd+Leertaste` (Spotlight), „Terminal" tippen, Enter.
- **Windows:** Startmenü, „PowerShell" tippen, Enter.

## So holt ihr euch dieses Kit

Drei Wege, vom einfachsten zum elegantesten. Alle drei verstecken sich auf der GitHub-Seite hinter dem grünen **Code**-Knopf:

![Der grüne Code-Knopf auf GitHub mit den Optionen HTTPS, GitHub CLI und Download ZIP](assets/github-code-menu.png)

**Weg 1: ZIP herunterladen (kein Git nötig).** Grüner Code-Knopf, dann „Download ZIP", Datei entpacken, fertig. Der Ordner kann z.B. auf den Schreibtisch.

**Weg 2: `git clone` (machen wir in Session 1 gemeinsam).** Im Terminal:

```
git clone https://github.com/stoicma/claude-workshop-kit.git
```

**Weg 3: GitHub CLI.** `gh` ist das offizielle Kommandozeilen-Tool von GitHub, die Variante aus dem Screenshot oben (`gh repo clone ...`). Lohnt sich nicht am Tag eins, aber sobald es installiert und angemeldet ist, kann Claude damit für euch auf GitHub arbeiten: „leg dieses Projekt auf GitHub ab" wird dann ein einziger Satz. Installation und Anmeldung zeigen wir bei Bedarf, oder ihr fragt Claude (Regel Null, siehe unten).

Und falls sich das Kit später mal ändert: sagt Claude einfach „hol die neueste Version dieses Ordners von GitHub". Mehr Git braucht ihr nicht.

## Terminal im richtigen Ordner öffnen

Claude arbeitet immer in dem Ordner, in dem das Terminal gerade steht. Für den Deck-Skill muss das der Kit-Ordner sein. So kommt ihr hin:

**Mac:** Im Finder Rechtsklick auf den Kit-Ordner, dann „Dienste" und „Neues Terminal beim Ordner".

<!-- TODO Screenshot: Finder-Rechtsklick mit Dienste > Neues Terminal beim Ordner -->

**Windows 11:** Im Explorer Rechtsklick auf den Kit-Ordner, dann „Im Terminal öffnen".

<!-- TODO Screenshot: Windows-Explorer-Rechtsklick mit "Im Terminal öffnen" -->

**Falls der Rechtsklick die Option nicht zeigt:** Terminal öffnen, `cd ` tippen (mit Leerzeichen dahinter), dann den Kit-Ordner aus dem Finder bzw. Explorer direkt ins Terminal-Fenster ziehen, Enter.

Danach `claude` tippen, Enter, und es kann losgehen.

## Der Terminal-Spickzettel

Claude Code bedient sich wie ein Chat, nur im Terminal. Diese Handgriffe reichen für den Anfang.

**Vorab einmal:** aktuelle Version sicherstellen mit `claude update`. Die aktuelle Oberfläche könnt ihr mit der Maus bedienen (Befehle anklicken, in Dialogen klicken statt Pfeiltasten). Wer frisch installiert hat, hat sie schon.

| Handgriff | So geht's |
|---|---|
| **Modus wechseln** | `Shift+Tab` schaltet durch: Normal, Auto-Accept (Claude darf Dateien direkt ändern), Plan-Modus (erst denken und planen, nichts anfassen). Für den Anfang: Plan-Modus für alles Größere. |
| **Neue Zeile ohne Absenden** | `Shift+Enter` (funktioniert in Apple Terminal, Windows Terminal und den meisten modernen Terminals). Geht es nicht: `Ctrl+J` geht überall. In VS Code vorher einmal `/terminal-setup` ausführen. |
| **Screenshot einfügen** | Screenshot machen und kopieren, wie ihr es gewohnt seid. Dann im Terminal einfügen mit `Ctrl+V`. Die einzige Stolperfalle, auf dem Mac: `Ctrl+V`, nicht `Cmd+V`. Claude sieht das Bild und kann damit arbeiten. |
| **Claude unterbrechen** | `Esc` stoppt Claude mitten in der Antwort. Bereits Erledigtes bleibt erhalten. |
| **Zurückspulen** | Zweimal `Esc` (bei leerem Eingabefeld) öffnet das Rewind-Menü: zu einem früheren Punkt im Gespräch zurückspringen. |
| **Shell-Befehl direkt** | `!` am Zeilenanfang führt den Befehl direkt aus, ohne dass Claude ihn interpretiert. |
| **Hilfe** | `/help` zeigt alle Befehle. `/` allein öffnet das Befehlsmenü zum Durchklicken. |

**Und Regel Null:** Wenn ihr nicht wisst, wie etwas geht, fragt Claude selbst. „Wie füge ich hier einen Screenshot ein?" funktioniert.

## Die wichtigsten Slash-Befehle

Befehle, die mit `/` beginnen, steuern Claude Code selbst. Diese vier solltet ihr kennen:

| Befehl | Was er tut |
|---|---|
| `/resume` | Eine frühere Session fortsetzen. Jede Terminal-Session ist ein eigenes Gespräch; `/resume` zeigt die Liste der letzten und ihr macht weiter, wo ihr wart. |
| `/model` | Modell wechseln: schneller und günstiger für Alltagsaufgaben, gründlicher für komplexe. |
| `/config` | Einstellungen ansehen und ändern (Theme, Benachrichtigungen, Standardmodell). |
| `/insights` | Ein Bericht über eure eigene Nutzung: was ihr oft tut, wo ihr Zeit verliert, was sich zu automatisieren lohnt. Nach ein paar Wochen Nutzung sehr aufschlussreich. |

Eigene Befehle für eure wiederkehrenden Aufgaben (sogenannte Skills) sind genau das Thema des Workshops. Der erste eigene entsteht mit dem Deck-Template unten; die Konzepte stehen im [Claude Guide](https://stokic.ai/claude-guide).

## Euer erster Skill: der Prozess

So entsteht jeder Build, vom ersten Skill bis zur echten App. Der Prozess ist immer derselbe:

1. **Plan-Modus an** (`Shift+Tab` bis „plan mode"). Claude denkt erst, fasst nichts an.
2. **Schmerz beschreiben.** Euren größten Zeitfresser aus der Checkliste, in normalen Sätzen. Dann: „Interview mich, bis du genug für eine Spec weißt."
3. **Interviewen lassen.** Claude stellt Fragen, ihr antwortet. Das ist der wichtigste Schritt: hier entsteht die Qualität.
4. **Spec lesen und freigeben.** Ein kurzer schriftlicher Plan. Erst wenn er stimmt, geht es weiter.
5. **Bauen lassen** (`Shift+Tab` zu Auto-Accept, dann: „Bau es."). Der Agent arbeitet, ihr trinkt Kaffee oder schaut zu.

**Wessen Nummer 1 Folien oder Reports sind:** In `team-deck-template/` liegt ein fertiger Start. Sagen: „Lies team-deck-template/SKILL.md und führe das Kalibrierungs-Interview mit mir." Er stellt sechs Fragen zu eurem Hausstil und kalibriert sich anhand eurer zwei Referenz-Decks.

**Hausaufgabe bis Session 2 (30. Juni):** Build fertigstellen, mindestens zweimal an echter Arbeit benutzen, nachschärfen. Dann auf euer eigenes GitHub schieben (wie? Claude fragen). Steckenbleiben ist erlaubt, aber schreibt mir vorher: marko@stokic.ai

## Qualität sichern (gegen KI-Schrott)

Die Reviewer-Regel aus dem Workshop: **prüft nie selbst, was eine Maschine vorher hätte ablehnen können.** Eure Aufmerksamkeit ist das Knappste im Prozess. Sie gehört nur dorthin, wo Geschmack und Urteil gefragt sind.

- **Lasst Claude testen, bevor ihr schaut.** Bei allem Gebauten: „Teste das gründlich, zeig mir erst dann das Ergebnis." Bei Texten: „Prüf das gegen unsere Regeln, bevor du es mir gibst."
- **Regeln aufschreiben statt wiederholen.** Wenn ihr dieselbe Korrektur zum dritten Mal gebt (kein Denglisch, keine Floskeln, Zahlenformat), gehört sie in eine Datei, die Claude jedes Mal liest. Auf Wunsch baut Claude euch daraus einen automatischen Prüfer.
- **Fertige Qualitäts-Skills nutzen.** Für Web-Oberflächen lohnt sich z.B. der `frontend-design`-Skill von Anthropic. Es gibt ganze Skill-Pakete gegen generischen KI-Look. Ehrliche Einordnung: die entfernen Schrott, echten Geschmack müsst ihr selbst kalibrieren, mit Beispielen von euch.
