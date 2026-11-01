# Learn Claude Code -- Harness Engineering für echte Agenten

[English](./README.md) | [中文](./README-zh.md) | [日本語](./README-ja.md) | [Deutsch](./README-de.md)

## Das Modell IST der Agent

Bevor wir über Code sprechen, klären wir eine Sache ganz unmissverständlich.

**Ein Agent ist ein Modell. Kein Framework. Keine Prompt-Kette. Kein Drag-and-Drop-Workflow.**

### Was ein Agent IST

Ein Agent ist ein neuronales Netz -- ein Transformer, ein RNN, eine gelernte Funktion --, das durch Milliarden von Gradienten-Updates auf Daten aus Handlungssequenzen darauf trainiert wurde, eine Umgebung wahrzunehmen, über Ziele nachzudenken und zu handeln, um sie zu erreichen. Das Wort „Agent“ hat in der KI immer genau das bedeutet. Immer.

Ein Mensch ist ein Agent. Ein biologisches neuronales Netz, geformt durch Millionen Jahre evolutionäres Training, das die Welt über Sinne wahrnimmt, mit einem Gehirn schlussfolgert und mit einem Körper handelt. Wenn DeepMind, OpenAI oder Anthropic „Agent“ sagen, meinen sie dasselbe wie das Fachgebiet seit seiner Entstehung: **ein Modell, das gelernt hat zu handeln.**

Der Beweis steht in der Geschichte:

- **2013 -- DeepMind DQN spielt Atari.** Ein einziges neuronales Netz, das nur rohe Pixel und Spielstände erhielt, lernte 7 Atari-2600-Spiele zu spielen -- und übertraf alle früheren Algorithmen; bei 3 Spielen schlug es sogar menschliche Experten. Bis 2015 skalierte dieselbe Architektur auf [49 Spiele und erreichte das Niveau professioneller menschlicher Tester](https://www.nature.com/articles/nature14236), veröffentlicht in *Nature*. Keine spielspezifischen Regeln. Keine Entscheidungsbäume. Ein Modell, das aus Erfahrung lernt. Dieses Modell war der Agent.

- **2019 -- OpenAI Five erobert Dota 2.** Fünf neuronale Netze, die in 10 Monaten [45.000 Jahre Dota 2](https://openai.com/index/openai-five-defeats-dota-2-world-champions/) gegen sich selbst gespielt hatten, besiegten bei einem Livestream in San Francisco **OG** -- den amtierenden TI8-Weltmeister -- mit 2:0. In einer anschließenden öffentlichen Arena gewann die KI 99,4 % von 42.729 Spielen gegen alle Herausforderer. Keine geskripteten Strategien. Keine fest einprogrammierte Teamkoordination. Teamarbeit, Taktik und Anpassung in Echtzeit haben die Modelle allein durch Selbstspiel gelernt.

- **2019 -- DeepMind AlphaStar meistert StarCraft II.** AlphaStar [schlug in einem Match hinter verschlossenen Türen Profispieler mit 10:1](https://deepmind.google/blog/alphastar-mastering-the-real-time-strategy-game-starcraft-ii/) und erreichte später auf europäischen Servern den [Grandmaster-Status](https://www.nature.com/articles/d41586-019-03298-6) -- die obersten 0,15 % von 90.000 Spielern. Ein Spiel mit unvollständiger Information, Entscheidungen in Echtzeit und einem kombinatorischen Aktionsraum, der Schach und Go in den Schatten stellt. Der Agent? Ein Modell. Trainiert. Nicht geskriptet.

- **2019 -- Tencents Jueyu dominiert Honor of Kings.** Jueyu von Tencent AI Lab [besiegte KPL-Profis](https://www.jiemian.com/article/3371171.html) in einem vollständigen 5-gegen-5-Match beim World Champion Cup. Im 1-gegen-1-Modus gewannen Profis nur [1 von 15 Spielen und überlebten nie länger als 8 Minuten](https://developer.aliyun.com/article/851058). Trainingsintensität: ein Tag entsprach 440 Menschenjahren. Bis 2021 übertraf Jueyu die KPL-Profis über den gesamten Heldenpool hinweg. Keine handgebauten Matchup-Tabellen. Keine geskripteten Aufstellungen. Ein Modell, das das gesamte Spiel von Grund auf durch Selbstspiel gelernt hat.

- **2024-2025 -- LLM-Agenten verändern die Softwareentwicklung.** Claude, GPT, Gemini -- große Sprachmodelle, trainiert auf der Gesamtheit menschlichen Codes und Denkens -- werden als Coding-Agenten eingesetzt. Sie lesen Codebasen, schreiben Implementierungen, debuggen Fehler und koordinieren sich in Teams. Die Architektur ist dieselbe wie bei jedem Agenten vor ihnen: ein trainiertes Modell, in eine Umgebung gesetzt und mit Werkzeugen zum Wahrnehmen und Handeln ausgestattet. Der einzige Unterschied liegt im Umfang dessen, was sie gelernt haben, und in der Allgemeinheit der Aufgaben, die sie lösen.

Jeder dieser Meilensteine zeigt dieselbe Wahrheit: **Der „Agent“ ist nie der Code drumherum. Der Agent ist immer das Modell.**

### Was ein Agent NICHT ist

Das Wort „Agent“ wurde von einer ganzen Branche der Prompt-Klempnerei (Prompt Plumbing) gekapert.

Drag-and-Drop-Workflow-Builder. No-Code-Plattformen für „KI-Agenten“. Bibliotheken zur Orchestrierung von Prompt-Ketten. Sie alle teilen denselben Wahn: dass das Zusammenstecken von LLM-API-Aufrufen mit if-else-Verzweigungen, Knotengraphen und fest verdrahteter Routing-Logik bedeute, „einen Agenten zu bauen“.

Tut es nicht. Was sie bauen, ist eine Rube-Goldberg-Maschine -- eine überkonstruierte, fragile Pipeline aus prozeduralen Regeln, in die ein LLM als aufgeblasener Textvervollständigungs-Knoten eingeklemmt ist. Das ist kein Agent. Das ist ein Shell-Skript mit Größenwahn.

**Prompt-Plumbing-„Agenten“ sind die Fantasie von Programmierern, die keine Modelle trainieren.** Sie versuchen, Intelligenz mit Brute Force zu erzwingen, indem sie prozedurale Logik aufstapeln -- riesige Regelbäume, Knotengraphen, Wasserfälle aus Prompt-Ketten -- und beten, dass genug Klebecode irgendwie von selbst autonomes Verhalten hervorbringt. Das tut er nicht. Handlungsfähigkeit lässt sich nicht herbeiengineeren. Agency wird gelernt, nicht programmiert.

Diese Systeme sind von Anfang an tot: fragil, nicht skalierbar und grundsätzlich unfähig zur Verallgemeinerung. Sie sind die moderne Wiederauferstehung von GOFAI (Good Old-Fashioned AI) -- jener symbolischen Regelsysteme, die das Fachgebiet vor Jahrzehnten aufgegeben hat, nun mit einer LLM-Fassade übertüncht. Andere Verpackung, dieselbe Sackgasse.

### Der Perspektivwechsel: Vom „Agenten entwickeln“ zum Harness entwickeln

Wenn jemand sagt „Ich entwickle einen Agenten“, kann er nur eines von zwei Dingen meinen:

**1. Das Modell trainieren.** Gewichte per Reinforcement Learning, Fine-Tuning, RLHF oder andere gradientenbasierte Verfahren anpassen. Daten aus Aufgabenverläufen sammeln -- die tatsächlichen Abfolgen aus Wahrnehmung, Schlussfolgerung und Handlung in realen Domänen -- und damit das Verhalten des Modells formen. Das tun DeepMind, OpenAI, Tencent AI Lab und Anthropic. Das ist Agentenentwicklung im eigentlichen Sinn.

**2. Das Harness bauen.** Den Code schreiben, der dem Modell eine Umgebung gibt, in der es arbeiten kann. Das tun die meisten von uns, und darauf konzentriert sich dieses Repository.

Ein Harness ist alles, was der Agent braucht, um in einer bestimmten Domäne zu funktionieren:

```
Harness = Tools + Knowledge + Observation + Action Interfaces + Permissions

    Tools:          Datei-I/O, Shell, Netzwerk, Datenbank, Browser
    Knowledge:      Produktdokumentation, Domänenreferenzen, API-Spezifikationen, Styleguides
    Observation:    git diff, Fehlerlogs, Browserzustand, Sensordaten
    Action:         CLI-Befehle, API-Aufrufe, UI-Interaktionen
    Permissions:    Sandboxing, Freigabe-Workflows, Vertrauensgrenzen
```

Das Modell entscheidet. Das Harness führt aus. Das Modell denkt. Das Harness liefert Kontext. Das Modell ist der Fahrer. Das Harness ist das Fahrzeug.

**Das Harness eines Coding-Agenten sind seine IDE, sein Terminal und sein Dateisystemzugriff.** Das Harness eines Landwirtschafts-Agenten sind seine Sensorik, seine Bewässerungssteuerung und seine Wetterdatenfeeds. Das Harness eines Hotel-Agenten sind sein Buchungssystem, seine Kommunikationskanäle zu den Gästen und seine Schnittstellen zur Gebäudeverwaltung. Der Agent -- die Intelligenz, der Entscheider -- ist immer das Modell. Das Harness ändert sich je nach Domäne. Der Agent verallgemeinert über alle hinweg.

Dieses Repository bringt dir bei, Fahrzeuge zu bauen. Fahrzeuge für das Programmieren. Aber die Entwurfsmuster lassen sich auf jede Domäne übertragen: Landwirtschaft, Hotelbetrieb, Fertigung, Logistik, Gesundheitswesen, Bildung, wissenschaftliche Forschung. Überall dort, wo eine Aufgabe wahrgenommen, durchdacht und umgesetzt werden muss, braucht ein Agent ein Harness.

### Was Harness Engineers wirklich tun

Wenn du dieses Repository liest, bist du wahrscheinlich ein Harness Engineer -- und das ist etwas Mächtiges. Das ist deine eigentliche Aufgabe:

- **Werkzeuge implementieren.** Gib dem Agenten Hände. Dateien lesen und schreiben, Shell-Ausführung, API-Aufrufe, Browsersteuerung, Datenbankabfragen. Jedes Werkzeug ist eine Aktion, die der Agent in seiner Umgebung ausführen kann. Entwirf sie atomar, kombinierbar und gut beschrieben.

- **Wissen kuratieren.** Gib dem Agenten Fachwissen. Produktdokumentation, Architekturentscheidungen, Styleguides, regulatorische Anforderungen. Lade sie bei Bedarf (s05) und nicht im Voraus. Der Agent soll wissen, was verfügbar ist, und sich holen, was er braucht.

- **Kontext verwalten.** Gib dem Agenten ein sauberes Gedächtnis. Die Isolation von Subagenten (s04) verhindert, dass Rauschen durchsickert. Kontextkomprimierung (s06) verhindert, dass die Historie alles erdrückt. Aufgabensysteme (s07) halten Ziele über einzelne Unterhaltungen hinaus fest.

- **Berechtigungen steuern.** Gib dem Agenten Grenzen. Dateizugriff in einer Sandbox. Freigabe für destruktive Operationen verlangen. Vertrauensgrenzen zwischen Agent und externen Systemen durchsetzen. Hier trifft Sicherheitstechnik auf Harness Engineering.

- **Daten aus Aufgabenverläufen sammeln.** Jede Handlungssequenz, die der Agent in deinem Harness ausführt, ist ein Trainingssignal. Die Wahrnehmungs-, Schlussfolgerungs- und Handlungsspuren aus realen Einsätzen sind der Rohstoff für das Fine-Tuning der nächsten Generation von Agentenmodellen. Dein Harness dient dem Agenten nicht nur -- es kann helfen, ihn zu verbessern.

Du schreibst nicht die Intelligenz. Du baust die Welt, in der die Intelligenz lebt. Die Qualität dieser Welt -- wie klar der Agent wahrnehmen kann, wie präzise er handeln kann, wie reichhaltig sein verfügbares Wissen ist -- bestimmt unmittelbar, wie wirksam sich die Intelligenz entfalten kann.

**Baue großartige Harnesses. Den Rest erledigt der Agent.**

### Warum Claude Code -- eine Meisterklasse in Harness Engineering

Warum nimmt dieses Repository ausgerechnet Claude Code auseinander?

Weil Claude Code das eleganteste und am vollständigsten umgesetzte Agenten-Harness ist, das wir kennen. Nicht wegen eines einzelnen cleveren Tricks, sondern wegen dessen, was es *nicht* tut: Es versucht nicht, der Agent zu sein. Es erzwingt keine starren Workflows. Es zweifelt das Modell nicht mit aufwendigen Entscheidungsbäumen an. Es gibt dem Modell Werkzeuge, Wissen, Kontextverwaltung und Berechtigungsgrenzen -- und geht dann aus dem Weg.

Schau dir an, was Claude Code im Kern wirklich ist:

```
Claude Code = one agent loop
            + tools (bash, read, write, edit, glob, grep, browser...)
            + on-demand skill loading
            + context compression
            + subagent spawning
            + task system with dependency graph
            + team coordination with async mailboxes
            + worktree isolation for parallel execution
            + permission governance
```

Das war's. Das ist die gesamte Architektur. Jede Komponente ist ein Harness-Mechanismus -- ein Stück der Welt, die für den Agenten gebaut wurde. Der Agent selbst? Das ist Claude. Ein Modell. Von Anthropic auf der gesamten Breite menschlichen Denkens und Codes trainiert. Das Harness macht Claude nicht klug. Claude ist schon klug. Das Harness gibt Claude Hände, Augen und einen Arbeitsplatz.

Deshalb ist Claude Code das ideale Lehrbeispiel: **Es zeigt, was passiert, wenn du dem Modell vertraust und deine Ingenieursarbeit auf das Harness konzentrierst.** Jede Lektion in diesem Repository (s01-s12) entschlüsselt per Reverse Engineering einen Harness-Mechanismus aus der Architektur von Claude Code. Am Ende verstehst du nicht nur, wie Claude Code funktioniert, sondern auch die universellen Prinzipien des Harness Engineering, die für jeden Agenten in jeder Domäne gelten.

Die Lehre ist nicht „kopiere Claude Code“. Die Lehre ist: **Die besten Agentenprodukte werden von Ingenieuren gebaut, die verstehen, dass ihre Aufgabe das Harness ist und nicht die Intelligenz.**

---

## Die Vision: Das Universum mit echten Agenten füllen

Hier geht es nicht nur um Coding-Agenten.

Jede Domäne, in der Menschen komplexe, mehrstufige, urteilsintensive Arbeit leisten, ist eine Domäne, in der Agenten arbeiten können -- mit dem richtigen Harness. Die Muster in diesem Repository sind universell:

```
Estate management agent    = model + property sensors + maintenance tools + tenant comms
Agricultural agent         = model + soil/weather data + irrigation controls + crop knowledge
Hotel operations agent     = model + booking system + guest channels + facility APIs
Medical research agent     = model + literature search + lab instruments + protocol docs
Manufacturing agent        = model + production line sensors + quality controls + logistics
Education agent            = model + curriculum knowledge + student progress + assessment tools
```

Die Schleife ist immer dieselbe. Die Werkzeuge ändern sich. Das Wissen ändert sich. Die Berechtigungen ändern sich. Der Agent -- das Modell -- verallgemeinert.

Jeder Harness Engineer, der dieses Repository liest, lernt Muster, die weit über die Softwareentwicklung hinaus gelten. Du lernst, die Infrastruktur für eine intelligente, automatisierte Zukunft zu bauen. Jedes gut entworfene Harness, das in einer realen Domäne eingesetzt wird, ist ein weiterer Ort, an dem ein Agent wahrnehmen, schlussfolgern und handeln kann.

Zuerst füllen wir die Werkstätten. Dann die Farmen, die Krankenhäuser, die Fabriken. Dann die Städte. Dann den Planeten.

**Bash genügt. Echte Agenten sind alles, was das Universum braucht.**

---

```
                    THE AGENT PATTERN
                    =================

    User --> messages[] --> LLM --> response
                                      |
                            stop_reason == "tool_use"?
                           /                          \
                         yes                           no
                          |                             |
                    execute tools                    return text
                    append results
                    loop back -----------------> messages[]


    Das ist die minimale Schleife. Jeder KI-Agent braucht diese Schleife.
    Das MODELL entscheidet, wann es Werkzeuge aufruft und wann es aufhört.
    Der CODE führt nur aus, was das Modell verlangt.
    Dieses Repository bringt dir bei, alles zu bauen, was diese Schleife umgibt --
    das Harness, das den Agenten in einer bestimmten Domäne wirksam macht.
```

**12 aufeinander aufbauende Lektionen, von der einfachen Schleife bis zur isolierten autonomen Ausführung.**
**Jede Lektion fügt einen Harness-Mechanismus hinzu. Jeder Mechanismus hat ein Motto.**

> **s01** &nbsp; *„Eine Schleife und Bash reichen völlig aus“* &mdash; ein Werkzeug + eine Schleife = ein Agent
>
> **s02** &nbsp; *„Ein Werkzeug hinzuzufügen heißt, einen Handler hinzuzufügen“* &mdash; die Schleife bleibt gleich; neue Werkzeuge werden in der Dispatch-Map registriert
>
> **s03** &nbsp; *„Ein Agent ohne Plan verliert die Richtung“* &mdash; erst die Schritte auflisten, dann ausführen; die Erfolgsquote verdoppelt sich
>
> **s04** &nbsp; *„Große Aufgaben zerlegen; jede Teilaufgabe bekommt einen sauberen Kontext“* &mdash; Subagenten nutzen eigene messages[] und halten die Hauptunterhaltung sauber
>
> **s05** &nbsp; *„Wissen laden, wenn man es braucht, nicht im Voraus“* &mdash; per tool_result einspeisen, nicht über den System-Prompt
>
> **s06** &nbsp; *„Der Kontext füllt sich; man braucht eine Möglichkeit, Platz zu schaffen“* &mdash; dreischichtige Komprimierungsstrategie für unendlich lange Sitzungen
>
> **s07** &nbsp; *„Große Ziele in kleine Aufgaben zerlegen, ordnen, auf der Festplatte speichern“* &mdash; ein dateibasierter Aufgabengraph mit Abhängigkeiten, die Grundlage für die Zusammenarbeit mehrerer Agenten
>
> **s08** &nbsp; *„Langsame Operationen im Hintergrund ausführen; der Agent denkt weiter“* &mdash; Daemon-Threads führen Befehle aus und melden den Abschluss per Benachrichtigung
>
> **s09** &nbsp; *„Ist die Aufgabe für einen allein zu groß, an Teammitglieder delegieren“* &mdash; dauerhafte Teammitglieder + asynchrone Mailboxen
>
> **s10** &nbsp; *„Teammitglieder brauchen gemeinsame Kommunikationsregeln“* &mdash; ein einziges Anfrage-Antwort-Muster steuert alle Abstimmungen
>
> **s11** &nbsp; *„Teammitglieder prüfen das Board und übernehmen Aufgaben selbst“* &mdash; der Lead muss nicht jede einzeln zuweisen
>
> **s12** &nbsp; *„Jeder arbeitet in seinem eigenen Verzeichnis, ohne Störungen“* &mdash; Aufgaben verwalten Ziele, Worktrees verwalten Verzeichnisse, verbunden über die ID

---

## Das Kernmuster

```python
def agent_loop(messages):
    while True:
        response = client.messages.create(
            model=MODEL, system=SYSTEM,
            messages=messages, tools=TOOLS,
        )
        messages.append({"role": "assistant",
                         "content": response.content})

        if response.stop_reason != "tool_use":
            return

        results = []
        for block in response.content:
            if block.type == "tool_use":
                output = TOOL_HANDLERS[block.name](**block.input)
                results.append({
                    "type": "tool_result",
                    "tool_use_id": block.id,
                    "content": output,
                })
        messages.append({"role": "user", "content": results})
```

Jede Lektion legt einen Harness-Mechanismus auf diese Schleife -- ohne die Schleife selbst zu verändern. Die Schleife gehört dem Agenten. Die Mechanismen gehören dem Harness.

## Umfang (wichtig)

Dieses Repository ist ein 0->1-Lernprojekt für Harness Engineering -- also dafür, die Umgebung zu bauen, die ein Agentenmodell umgibt.
Es vereinfacht oder lässt absichtlich mehrere Produktionsmechanismen weg:

- Vollständige Event-/Hook-Busse (zum Beispiel PreToolUse, SessionStart/End, ConfigChange).
  s12 enthält nur einen minimalen, rein anhängenden Lebenszyklus-Event-Stream zu Lehrzwecken.
- Regelbasierte Berechtigungssteuerung und Vertrauens-Workflows
- Steuerung des Sitzungslebenszyklus (Fortsetzen/Verzweigen) und erweiterte Steuerung des Worktree-Lebenszyklus
- Vollständige MCP-Laufzeitdetails (Transport/OAuth/Ressourcen-Abonnement/Polling)

Das JSONL-Mailbox-Protokoll für Teams in diesem Repository ist eine Lehrimplementierung und keine Aussage über die Interna eines bestimmten Produktivsystems.

## Schnellstart

```sh
git clone https://github.com/shareAI-lab/learn-claude-code
cd learn-claude-code
pip install -r requirements.txt
cp .env.example .env   # .env bearbeiten und ANTHROPIC_API_KEY eintragen

python agents/s01_agent_loop.py       # Hier anfangen
python agents/s12_worktree_task_isolation.py  # Endpunkt der gesamten Abfolge
python agents/s_full.py               # Abschluss: alle Mechanismen kombiniert
```

### Web-Plattform

Interaktive Visualisierungen, Schritt-für-Schritt-Diagramme, Quellcode-Viewer und Dokumentation.

```sh
cd web && npm install && npm run dev   # http://localhost:3000
```

## Lernpfad

```
Phase 1: THE LOOP                    Phase 2: PLANNING & KNOWLEDGE
==================                   ==============================
s01  The Agent Loop          [1]     s03  TodoWrite               [5]
     while + stop_reason                  TodoManager + nag reminder
     |                                    |
     +-> s02  Tool Use            [4]     s04  Subagents            [5]
              dispatch map: name->handler     fresh messages[] per child
                                              |
                                         s05  Skills               [5]
                                              SKILL.md via tool_result
                                              |
                                         s06  Context Compact      [5]
                                              3-layer compression

Phase 3: PERSISTENCE                 Phase 4: TEAMS
==================                   =====================
s07  Tasks                   [8]     s09  Agent Teams             [9]
     file-based CRUD + deps graph         teammates + JSONL mailboxes
     |                                    |
s08  Background Tasks        [6]     s10  Team Protocols          [12]
     daemon threads + notify queue        shutdown + plan approval FSM
                                          |
                                     s11  Autonomous Agents       [14]
                                          idle cycle + auto-claim
                                     |
                                     s12  Worktree Isolation      [16]
                                          task coordination + optional isolated execution lanes

                                     [N] = Anzahl der Werkzeuge
```

## Architektur

```
learn-claude-code/
|
|-- agents/                        # Python-Referenzimplementierungen (s01-s12 + s_full als Abschluss)
|-- docs/{en,zh,ja}/               # Dokumentation mit Mental-Model-Fokus (3 Sprachen)
|-- web/                           # Interaktive Lernplattform (Next.js)
|-- skills/                        # Skill-Dateien für s05
+-- .github/workflows/ci.yml      # CI: Typprüfung + Build
```

## Dokumentation

Mental Model zuerst: Problem, Lösung, ASCII-Diagramm, minimaler Code.
Die Lektionsdokumentation ist auf [English](./docs/en/) | [中文](./docs/zh/) | [日本語](./docs/ja/) verfügbar.
Die folgenden Links führen zu den englischen Lektionen; eine deutsche Übersetzung der Lektionen ist noch nicht enthalten.

| Lektion | Thema | Motto |
|---------|-------|-------|
| [s01](./docs/en/s01-the-agent-loop.md) | Die Agent-Schleife | *Eine Schleife und Bash reichen völlig aus* |
| [s02](./docs/en/s02-tool-use.md) | Tool Use | *Ein Werkzeug hinzuzufügen heißt, einen Handler hinzuzufügen* |
| [s03](./docs/en/s03-todo-write.md) | TodoWrite | *Ein Agent ohne Plan verliert die Richtung* |
| [s04](./docs/en/s04-subagent.md) | Subagenten | *Große Aufgaben zerlegen; jede Teilaufgabe bekommt einen sauberen Kontext* |
| [s05](./docs/en/s05-skill-loading.md) | Skills | *Wissen laden, wenn man es braucht, nicht im Voraus* |
| [s06](./docs/en/s06-context-compact.md) | Context Compact | *Der Kontext füllt sich; man braucht eine Möglichkeit, Platz zu schaffen* |
| [s07](./docs/en/s07-task-system.md) | Aufgaben | *Große Ziele in kleine Aufgaben zerlegen, ordnen, auf der Festplatte speichern* |
| [s08](./docs/en/s08-background-tasks.md) | Hintergrundaufgaben | *Langsame Operationen im Hintergrund ausführen; der Agent denkt weiter* |
| [s09](./docs/en/s09-agent-teams.md) | Agententeams | *Ist die Aufgabe für einen allein zu groß, an Teammitglieder delegieren* |
| [s10](./docs/en/s10-team-protocols.md) | Teamprotokolle | *Teammitglieder brauchen gemeinsame Kommunikationsregeln* |
| [s11](./docs/en/s11-autonomous-agents.md) | Autonome Agenten | *Teammitglieder prüfen das Board und übernehmen Aufgaben selbst* |
| [s12](./docs/en/s12-worktree-task-isolation.md) | Worktree + Aufgabenisolation | *Jeder arbeitet in seinem eigenen Verzeichnis, ohne Störungen* |

## Wie es weitergeht -- vom Verstehen zum Ausliefern

Nach den 12 Lektionen verstehst du, wie Harness Engineering von innen funktioniert. Es gibt zwei Wege, dieses Wissen einzusetzen:

### Kode Agent CLI -- Open-Source-CLI für Coding-Agenten

> `npm i -g @shareai-lab/kode`

Unterstützt Skills und LSP, ist Windows-tauglich und lässt sich mit GLM / MiniMax / DeepSeek und anderen offenen Modellen verbinden. Installieren und loslegen.

GitHub: **[shareAI-lab/Kode-cli](https://github.com/shareAI-lab/Kode-cli)**

### Kode Agent SDK -- Agentenfähigkeiten in die eigene App einbetten

Das offizielle Claude Code Agent SDK kommuniziert im Hintergrund mit einem vollständigen CLI-Prozess -- jeder gleichzeitige Nutzer bedeutet einen eigenen Terminalprozess. Das Kode SDK ist eine eigenständige Bibliothek ohne Prozess-Overhead pro Nutzer und lässt sich in Backends, Browser-Erweiterungen, eingebettete Geräte oder jede andere Laufzeit einbetten.

GitHub: **[shareAI-lab/Kode-agent-sdk](https://github.com/shareAI-lab/Kode-agent-sdk)**

---

## Schwester-Repo: von *Sitzungen auf Abruf* zum *Always-on-Assistenten*

Das Harness, das dieses Repository lehrt, ist **Benutzen und Wegwerfen** -- Terminal öffnen, dem Agenten eine Aufgabe geben, nach getaner Arbeit schließen, die nächste Sitzung beginnt leer. Das ist das Claude-Code-Modell.

[OpenClaw](https://github.com/openclaw/openclaw) hat eine andere Möglichkeit bewiesen: Auf demselben Agentenkern machen zwei Harness-Mechanismen aus einem Agenten, den man anstoßen muss, damit er sich bewegt, einen, der alle 30 Sekunden von selbst aufwacht und nach Arbeit sucht:

- **Heartbeat** -- alle 30 Sekunden schickt das Harness dem Agenten eine Nachricht, ob etwas zu tun ist. Nichts? Weiterschlafen. Etwas? Sofort handeln.
- **Cron** -- der Agent kann seine eigenen künftigen Aufgaben planen, die zum jeweiligen Zeitpunkt automatisch ausgeführt werden.

Kommen noch Multi-Channel-IM-Routing (WhatsApp / Telegram / Slack / Discord, über 13 Plattformen), persistentes Kontextgedächtnis und ein Soul-Persönlichkeitssystem hinzu, wird der Agent vom Wegwerfwerkzeug zum dauerhaft verfügbaren persönlichen KI-Assistenten.

**[claw0](https://github.com/shareAI-lab/claw0)** ist unser begleitendes Lehr-Repository, das diese Harness-Mechanismen von Grund auf zerlegt:

```
claw agent = agent core + heartbeat + cron + IM chat + memory + soul
```

```
learn-claude-code                   claw0
(agent harness core:                (proactive always-on harness:
 loop, tools, planning,              heartbeat, cron, IM channels,
 teams, worktree isolation)          memory, soul personality)
```

## Über uns
<img width="260" src="https://github.com/user-attachments/assets/fe8b852b-97da-4061-a467-9694906b5edf" alt="WeChat-QR-Code von shareAI-Lab" /><br>

Scanne den Code mit WeChat, um uns zu folgen,
oder folge uns auf X: [shareAI-Lab](https://x.com/baicai003)

## Lizenz

MIT

---

**Das Modell ist der Agent. Der Code ist das Harness. Baue großartige Harnesses. Den Rest erledigt der Agent.**

**Bash genügt. Echte Agenten sind alles, was das Universum braucht.**
