# Softwareentwicklung SoSe2021 Aufgabe 06

## Bearbeitungzeit

SWE: 14. Juni - 18. Juni 2021 (Mm, BWM, ROB, BAI, BGIP, BBWL, BBL, MGIN)

## Idee der Übung

Mit dem Aufgabenblatt sollen Ihre Fähigkeiten beim objektorientierten Entwurf und der entsprechenden Implementierung weiter trainiert werden. Angespochen werden speziell Vererbung, abstracte Klassen, Interfaces und die virtuellen Methoden.

Gehen Sie dabei wie folgt vor:

+ Der Projekt Maintainer entwirft zunächst ausgehend aus der vorhandenen Aufgabenstellung eine Klassenstruktur in UML mit PlantUML.
+ Halten Sie den Entwurf in einem Issue fest damit der Developer diese Klassenstruktur (zuerst nur die Struktur) in Csharp umsetzen kann. Die Klassen sollen dabei in einzelnen Dateien gespeichert werden. Vergleichen Sie das Fragment und das Modell in einer in einer gemeinsamen Videokonferenz. Wo ist der Entwickler warum abgewichen? Welche Änderungen schlägt sie/er vor?
+ Ordnen Sie über Issues die Zuständigkeiten bei der weiteren Implementierung, teilen Sie dabei die Teilaufgaben gleichmäßig unter Projektteilnehmern auf. Legen Sie Branches an, in denen Sie die Teilaufgaben realisieren und schließen Sie Issues nach dem Erledigen der Aufgabe. Denken Sie daran, die finale Version mit einem Release-Tag zu versehen.
+ Generieren Sie abschließend ein UML Diagramm, das die Lösung mit allen Feldern und Methoden dokumentiert und veröffentlichen Sie Ihr Diagramm im Wiki.

Tragen Sie bitte wiederum die Aufteilung Ihrer Rollen in die `team.config` ein.

## Aufgabe

Schreiben Sie ein Programm, das in der Lage ist, eine Haustierverwaltung zu realisieren.

+ Erstellen Sie bitte zunächst eine abstrakte Klasse `Pet`, die als Basis der Klassenhierarchie dienen soll. Jedes Haustier hat einen Namen ( `get` -/ `set` -Property) und will gepflegt werden (abstrakte Methode `Attend()`).

Die Haustiere werden in Säugetiere (Klasse `Mammal`) und Fische (Klasse `Fish`) unterteilt.

+ Legen Sie bitte die entsprechenden Klassen an.
+ Säugetiere verfügen über eine Methode zur Fortbewegung ( `Move()` ), Fische analog über eine Methode zum Schwimmen ( `Swim()` ). Beide Methoden sind abstrakt.
+ Für alle Fische ist die Pflege einheitlich: Das Wasser muss gewechselt werden. Bitte implementieren Sie die Methode `Attend()` entsprechend (Konsolenausgabe).

Goldfische und Guppys sind spezielle Fische.

+ Legen Sie bitte die entsprechenden Klassen an.
+ Goldfische schwimmen bekanntermaßen immer im Kreis, Guppys nur vor und zurück. Bitte implementieren Sie passende `Swim()` -Methoden.

Katzen und Kaninchen sind spezielle Säugetiere.

+ Legen Sie bitte die entsprechenden Klassen an.
+ Zur Pflege von Katzen bürstet man ihr Fell. Kaninchen pflegt man durch Ausmisten ihres Stalls. Bitte implementieren Sie passende `Attend()` -Methoden.
+ Katzen bewegen sich fort, indem sie schleichen, während Kaninchen bevorzugt hoppeln. Bitte implementieren Sie passende `Move()` -Methoden.

Haustiere können einen Besitzer haben.

+ Fügen Sie der `Pet`-Klasse eine entsprechende String-Property (oder alternativ ein `public readonly` -Feld) hinzu.
+ Der Wert wird einmalig bei der Instanziierung festgelegt (bzw. auf `null` gesetzt) und kann anschließend nicht mehr geändert werden. Erstellen Sie einen passenden Konstruktor.
+ Fügen Sie den abgeleiteten Klassen ebenfalls Konstruktoren hinzu. Bitte beachten Sie dabei, dass
Katzen grundsätzlich keinen Besitzer haben ( `null` ).

Einige Haustiere lassen sich streicheln.

+ Erstellen Sie bitte zunächst ein Interface (z. B. `IStrokeable` ), mit dem sich streichelbare Haustiere auszeichnen lassen. Fügen Sie eine passende Methodendeklaration ( `Stroke()` ) hinzu.
+ Alle Säugetiere sowie Goldfische können gestreichelt werden.
+ Wenn man Katzen streichelt, schnurren sie. Leider beißen sie in einem von fünf Fällen anschließend grundlos zu. Bitte implementieren Sie dieses Verhalten.
+ Goldfische, die keinen Besitzer haben, schwimmen weg, wenn man sie streichelt.

Haustiere sollten auf einfache Weise mithilfe der Konsole ausgegeben werden können.

+ Überschreiben Sie die `ToString` -Methode in den vier nicht-abstrakten Tierklassen und geben Sie jeweils Art, Name und Besitzer (nicht bei Katzen) in einer formatierten Zeichenkette zurück.

Testen Sie Ihre Tierklassen in der Main -Methode.

+ Legen Sie einen Garten (Liste mit Säugetieren) und ein Aquarium (Liste mit Fischen) an. Füllen Sie sie mit Katzen, Kaninchen, Goldfischen und Guppys.
+ Geben Sie Ihre Haustiere auf der Konsole aus und lassen Sie sie schwimmen bzw. sich bewegen.
+ Kombinieren Sie Garten und Aquarium in einer `Pet` -Liste namens `Zoo`. Pflegen Sie den gesamten Zoo.
+ Streicheln Sie diejenigen Haustiere im Zoo, die das IStrokeable -Interface implementieren (Tipp: `as` -Operator nutzen).
+ Welches objektorientierte Konzept ermöglicht es, dass beim Zugriff über den Basisklassen-Typ die korrekten Methodenimplementierungen aus den Unterklassen aufgerufen werden?

## Hinweise zur Nutzung von PlantUML

Zum Erstellen von Diagrammen mit plantUML können Sie direkt den PlantUML-Online-Server ([https://plantuml.com](https://plantuml.com)) oder Visual Studio Code Extensions nutzen.

Bei der Nutzung von Visual Studio Code ist Ihre Installation um die folgenden Extensions zu ergänzen:

+ PlantUML und
+ CSharp to PlantUML

Zum Erstellen und Anzeigen von Diagrammen mit PlantUML benötigen Sie außerdem **plantuml.jar** (s. [https://plantuml.com/de/download](https://plantuml.com/de/download)).

Zum Generieren einer URL wäre die Extension-Setting-Veränderung im Visual Studion Code für "UML diagrams on-the-fly" auf "https://www.plantuml.com/plant.uml" notwendig.

1. Zum Erstellen eines PlantUML-Diagramms erzeugen Sie eine Datei mit der Namenserweiterung .plantuml (.puml, .pu bzw. weitere möglich). Über das Kontextmenü können Sie u.a.:

+ Ihr Diagramm in Preview-Ansicht anzeigen,
+ Ihr Diagramm in eine .png-Datei (und weitere Formate) exportieren,
+ URL zum Verwenden, z.B. in einem GitHub-Repository, generieren.

2. Das Erzeugen des PlantUML Codes aus den C#-Code ist durch die Ausführung des Kommandos   `csarp2plantuml.classDiagram` in Command Palette möglich. Überprüfen Sie zuvor die Input- und Output-Verzeichnisse (siehe Preferences/Settings).

