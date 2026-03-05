# groupmix
Gruppen zufällig einteilen

**GroupMix** ist ein kleines Web-Tool zum automatischen Erstellen von **durchmischten Kleingruppen** aus einer Liste von Personen.

Die Idee dahinter kommt aus der Praxis von **Jugendfreizeiten, Jugendgruppen und Workshops**: Man möchte Teilnehmende zufällig in neue Gruppen einteilen – zum Beispiel für Bibelarbeiten, Gesprächsrunden oder Spiele – ohne dass immer wieder die gleichen Leute zusammen landen.

GroupMix erstellt solche Gruppen automatisch und versucht dabei gleichzeitig zu vermeiden, dass Personen immer wieder denselben Leuten begegnen.

Typische Einsatzszenarien sind zum Beispiel:

- Bibellese-Gruppen auf einer Freizeit (jeden Tag neue Zusammensetzung)
- Kleingruppen bei Jugendveranstaltungen
- Speed-Dating- oder Kennenlernspiele
- Workshop- oder Diskussionsrunden
- Team-Building-Sessions

Die App läuft komplett im Browser und kann problemlos z.B. über **GitHub Pages** gehostet werden.


## Wie das Tool funktioniert

Zuerst legst du eine **Personenliste** an oder importierst sie. Anschließend definierst du ein paar **Kriterien für die Gruppeneinteilung** (z. B. Gruppengröße oder Altersunterschied). Danach erzeugt ein Klick auf „Mixen“ automatisch neue Gruppen.

Die interne Group-Engine versucht dabei eine möglichst gute Verteilung zu finden. Sie bewertet verschiedene Gruppenkonfigurationen und verbessert sie iterativ, sodass die Kriterien so gut es geht eingehalten werden und Begegnungen möglichst wenig wiederholt werden. Nach jedem Durchlauf wird gespeichert, **welche Personen bereits zusammen in einer Gruppe waren**, damit zukünftige Mischungen abwechslungsreicher bleiben.


## Personenliste

Jede Person besteht aus folgenden Informationen:

- Vorname
- Nachname
- Alter
- Geschlecht (`m` oder `f`)
- Typ (`TN` = Teilnehmer, `MA` = Mitarbeiter)

Beispiel:

Max Mustermann 17 m TN
Anna Beispiel 16 f TN
Sabine Müller 42 f MA

Der **Typ** ist hilfreich, um Mitarbeitende und Teilnehmende unterschiedlich zu behandeln (z. B. gemischt oder getrennt). 

Personen können außerdem **pausiert** werden. Pausierte Personen bleiben in der Liste, werden aber beim Mixen ignoriert – praktisch wenn jemand gerade nicht da ist oder später dazukommt. 


## Import von Personen

Personen lassen sich schnell per Copy-Paste importieren.  
Dazu einfach mehrere Zeilen im Format

Vorname Nachname Alter Geschlecht Typ

einfügen.

Zum Beispiel:

Lukas Weber 14 m TN
Sarah Meyer 15 f TN
Tim Becker 14 m TN
Anna Klein 16 f TN
Jürgen Klopp 45 m MA
Sabine Fischer 42 f MA


## Kriterien für die Gruppeneinteilung

Die Gruppenerstellung kann über mehrere Einstellungen beeinflusst werden.

**Gruppengröße**  
Es kann festgelegt werden, wie viele Personen in einer Gruppe sein sollen (typisch z. B. 3–5).

**Geschlecht**  
Gruppen können entweder gemischt oder nach Geschlecht getrennt erstellt werden. 

**Maximaler Altersunterschied**  
Du kannst festlegen, wie groß der Altersunterschied innerhalb einer Gruppe sein darf (z. B. ±2 Jahre). Das ist ein "weiches" Kriterium, das als erstes Vernachlässigt wird, sollten die Kriterien nicht für alle umsetzbar sein.

**Mitarbeiter / Teilnehmer**  
Teilnehmende (`TN`) und Mitarbeitende (`MA`) können gemeinsam oder getrennt gruppiert werden.


## Verlauf / Begegnungen

GroupMix merkt sich automatisch, **welche Personen bereits zusammen in einer Gruppe waren**.

Wenn du erneut auf „Mixen“ klickst, versucht die Engine Gruppen zu erstellen, bei denen sich möglichst **wenige bekannte Paarungen wiederholen**. Dadurch entstehen über mehrere Runden hinweg abwechslungsreiche Begegnungen.

Der Verlauf kann jederzeit zurückgesetzt werden, falls man komplett neu starten möchte.  


## Titel und Beschreibung

Optional können ein **Titel** und ein **Beschreibungstext** für die aktuelle Gruppenrunde angegeben werden.

Beispiel:

Titel: Lest Matthäus 17
Text: Frage 1, Frage 2, Frage 3

Der Text erscheint oberhalb der generierten Gruppen. Projiziert ihr die Gruppeneinteilung, steht der Text so praktisch oben drüber.


## Datenspeicherung

Alle Daten werden **lokal im Browser gespeichert** (LocalStorage):

- Personenliste
- Kriterien
- Begegnungsverlauf
- Titel und Beschreibung

Es werden **keine Daten an einen Server übertragen**. Absolut DSGVO-konform.


## Hosting

Die App ist eine reine **statische Web-App** und kann deshalb sehr einfach gehostet werden.
Am einfachsten funktioniert das über **GitHub Pages**. Ihr könnt auch einfach diesen Link verwenden: https://dennysdl.github.io/groupmix/

Alternativ kann sie auch lokal gestartet werden.
Terminal: npx serve
