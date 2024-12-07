# Logikraetsel-CSP

## Beispielrätsel
Auf einer Straße stehen nebeneinander vier Häuser, die von links nach rechts die Hausnummern 2, 4, 6 und 8 haben. Jedes Haus hat eine andere Farbe, und in jedem wohnt eine einzelne Person; alle sind unterschiedlich alt (36, 37, 39 beziehungsweise 42 Jahre). Aus dem Smalltalk der Nachbarschaft entnehmen Sie die folgenden Informationen:
- Die jüngste Person wohnt im gelben Haus.
- Daniel ist kein Nachbar von Ben.
- Das grüne Haus steht nicht neben dem gelben.
- Ben wohnt nicht in einem der äußeren Häuser.
- Die Person im grünen Haus ist 42 Jahre alt.
- Anna wohnt nicht im roten Haus.
- Camilla ist nicht 39 Jahre alt.
- Das gelbe Haus steht ganz rechts.
- Anna oder Daniel wohnt in Hausnummer 4.
- Die 39-jährige Person wohnt ganz links.
- Das rote Haus steht weiter links als das blaue.
- Anna ist älter als Ben, dessen Haus nicht rot ist.
Welches Haus hat welche Farbe, welche Personen wohnen wo, und wie alt sind sie?

## Hintergrund
Die Lösung vieler Probleme und Rätsel besteht darin, mehrere potentiell miteinander in Konflikt geratende Bedingungen zu erfüllen. Beispiele sind etwa Kursblockungen in Schulen und Unis, Dienstpläne, Kreuzworträtsel und Sudokus oder Logik-Zuordnungsrätsel wie das obige. Solche Probleme werden als ''Contraint Satisfaction Problems'' (kurz ''CSP'', zu Deutsch ''Bedingungserfüllungsprobleme'') bezeichnet. Ein CSP hat drei "Zutaten":
- ''Variablen'' (''Variables''): Die Elemente, für die passende, das heißt einen Konflikt vermeidende Werte gesucht werden. Bei einem Sudoku sind die Variablen etwa die 81 Felder, bei dem Zuodnungsrätsel zum Beispiel die Personen, die in den verschiedenen Häusern wohnen.
- ''Domänen'' (''Domains''): Die möglichen Werte, mit denen jede Variable belegt werden kann. Bei einem Sudoku etwa die Zahlen von 1 bis 9 (außer in den bereits in der Aufgabenstellung vorbelegten Feldern, für die der Wert bereits feststeht), beim Zuordnungsrätsel alle denkbaren Tupel (Hausnummer, Hausfarbe, Alter).
- ''Bedingungen'' (''Constraints''): Die Einschränkungen, die für die Wertebelegungen gelten und potentiell Konflikte erzeugen. Beim Sudoku zum Beispiel, dass keine Zahl mehr als einmal in derselben Zeile, derselben Spalte oder demselben 3x3-Unterblock vorkommen darf, beim Zuordnungsrätsel die gegebene Liste der Voraussetzungen.

## Implementierung
In den Unterverzeichnissen ''java'' und ''python'' befinden sich jeweils einfache Implementierungen des CSP-Algorithmus und Lösungen für das Zuordnungsrätsel sowie für ein Sudoku. Die Lösung ist nicht sonderlich optimiert, sondern benutzt einfaches Backtracking – für elegantere Lösungen, die den Suchraum gezielt verkleinern, müsste die Bedingungsprüfungs-Methode so umgeschrieben werden, dass sie die Belegung zweier einzelner Variablen einander gegenüberstellt und auf einen möglichen Konflikt prüft; in der vorliegenden Implementierung wurde dies vereinfacht – es wird jeweils die gesamte bisherige Belegung geprüft. Wenn Sie Sudokus aus Zeitschriften oder Apps übernehmen, die als "schwierig" gekennzeichnet sind, werden Sie daher feststellen, dass die Lösung einige Sekunden dauert.

## Die Beispiele ausführen
### Python
Sie benötigen einen Python-3-Interpreter. Geben Sie dann im Verzeichnis ''python'' einfach ''python3 houses.py'' ein, um die Lösung des Zuordnungsrätsels zu erhalten, oder ''python3 sudoku.py sudoku.txt'' für die Lösung des beiligenden Beispiel-Sudokus. Andere Sudokus können Sie im selben Format als Textdateien speichern und dann mittels ''python3 sudoku.py <Dateiname>'' lösen lassen.
### Java
Die Beispiele müssten mit allen Java-Versionen ab 8 funktionieren. Kompilieren Sie zunächst ''Houses.java'' beziehungsweise ''Sudoku.java'' mit dem Kommandozeilen-Compiler ''javac'' oder in Ihrer IDE, und führen Sie anschließend ''java Houses'' beziehungsweise ''java Sudoku sudoku.txt'' aus.
