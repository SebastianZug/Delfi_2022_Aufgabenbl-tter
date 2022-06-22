# Softwareentwicklung SoSe2021 - Aufgabe 05

Das Aufgabenblatt adressiert weiterführende Aspekte der Objektorientierten Programmierung und der spezifischen Semantik unter C#.

**Legen Sie für die Aufgaben 1 und 2 jeweils wechselnd die Rolle des Maintainers (Reviewer) und einen Developers fest und lösen Sie die Aufgaben entsprechend dieser Verteilung. Vermerken Sie die Aufteilung der Rollen in `team.config`** 

Der Einfachheit halber werden die beiden (unabhängigen) Aufgaben in einem Repository bearbeitet. Um die Implementierungen zu separieren sollten diese in den zwei Ordnern `Aufgabe_1` und `Aufgabe_2` erfolgen. Verwenden Sie zur Organisation der Zusammenarbeit die bereits bekannten GitHub - Features (Issues, separate Branches für die Aufgaben, Commits mit Referenzen auf Issues, Pull-Requests mit Reviews).

## Bearbeitungzeit

SWE: 7.6. - 11.6. 2021 (Mm, BWM, ROB, BAI, BGIP, BBWL, BBL, MGIN)

Einführung in SWE: 12.7 - 16.7 2021 (KGB, BENG, VTC, MB)


## 1. Vererbung, Überschreiben von Elementen, dynamische Bindung, Indexer

1. Zu erstellen ist ein C#-Programm, das den Wissenschaftlern ermöglicht, die Merkmale einer infolge der Technoevolution entstandenen Spezies „Helmtiger“ im Vergleich zum bereits bekannten Tiger zu untersuchen. Erstellen Sie dazu die Klasse  `Tiger`, die die Angaben zu

    + Registriernummer,
    + Schädelumfang (reelle Zahl) und
    + Schädelfestigkeit (ganze Zahl) enthält.

   Verwenden Sie dazu automatische Properties, die einen lesenden Zugriff erlauben, und zum Initialisieren der Felder sinnvolle Konstruktoren.

   Des Weiteren soll die Klasse die `ToString`-Methode von `System.Object` überschreiben, um die Ausgabe der Instanzen der Klasse zu erleichtern.

2. Die ebenfalls zu erstellende Klasse `Helm` erhält die Angabe

    + zum inneren Durchmesser und ebenfalls
    + die Festigkeit.
   Ermöglichen Sie in der Klasse den lesenden Zugriff auf die Felder.

3. Die Klasse `Helmtiger` ist von der Klasse Tiger abzuleiten.

   In der Klasse ist ein weiteres Feld vom Typ der Klasse Helm zu definieren.

   Zum Zugriff auf das Feld von außerhalb der Klasse wird ein Property benötigt, das beim Zuweisen des Helms sicherstellt, dass „der Helm dem Tiger passt“, d.h., dass der Helmdurchmesser nicht kleiner als der aus dem Schädelumfang berechnete Wert ist, anderenfalls ist dem Helm-Feld der Wert `null` zuzuweisen.

   Eine weitere `virtual`- Methode der Klassen Tiger und Helmtiger soll die Schädelfestigkeit des „behelmten“ Tigers als die Summe der Festigkeiten des Tigers und des Helms berechnen und zurückgeben.  Beim Tiger ergibt sich die Gesamtfestigkeit nur aus der Schädelfestigkeit.

4. Erstellen Sie weiterhin eine `Verzeichnis`-Klasse, die Instanzen der Klassen Tiger und Helmtiger in einem Array-Datenfeld speichert.

   Definieren Sie zum Zugriff auf die Elemente des Arrays einen Indexer.

   Ein weiteres Property soll einen lesenden Zugriff auf das gesamte Array erlauben.

   Die maximale Anzahl der Elemente des Arrays ist über ein optionales Argument des Konstruktors festzulegen.

   Ergänzen Sie die `Verzeichnis`-Klasse um eine Methode zum Suchen von Instanzen mit einer als Parameter übergebenen Registriernummer.

   Testen Sie die Methoden und Properties der Klassen, indem Sie eine Instanz der Verzeichnis-Klasse anlegen, die Array-Elemente mit den Instanzen der Klassen Tiger und Helmtiger initializieren, die Daten aller Instanzen ausgeben bzw. einige suchen und ausgeben.

## 2. Überladene Operatoren, Klasse Object

Die Anwohner einer kleinen und kaum bekannten Insel haben ein eigenes Rechensystem mit folgenden Regeln entwickelt:

+ Jede Zahl wird durch eine entsprechende Anzahl von Stöckchen dargestellt.
+ Es gibt nur natürliche Zahlen (ganze Zahlen, die größer oder gleich Null sind).
+ Als Operationen beherrschen die Insulaner Addition, Subtraktion, Multiplikation und Division und die Vergleichsoperatoren kleiner, größer, gleich und ungleich.

Erstellen Sie eine Klasse, die eine Zahl dieses Rechensystems repräsentiert.

Intern soll die Zahl als eine ganze Zahl gespeichert werden, nach außen wird sie als ein String aus mehreren I-Buchstaben sichtbar. Beim Zuweisen des Strings ist zu überprüfen, ob die Zechenkette tatsächlich nur I-Zeichen enthält, anderenfalls ist eine `FormatException` zu werfen.

Definieren Sie in der Klasse die Operatoren `+`, `-`, `*` und `/`. Beachten Sie beim
Minusoperator, dass es keine negativen Zahlen gibt, und beim Divisionsoperator, dass
es keine gebrochenen Zahlen gibt.

Definieren Sie die Vergleichsoperatoren `<`, `>`, `==` und `!=`.

Ergänzen Sie die Klasse um die von der Klasse `Object` vererbten, überschriebenen Methoden `ToString`, `Equals` und `GetHashCode`.

Testen Sie die überladenen Operatoren und Methoden in der Main-Methode.
