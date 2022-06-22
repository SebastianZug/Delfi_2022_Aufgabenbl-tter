# SoftwareentwicklungSoSe2021 Aufgabe 09

## Bearbeitungzeit

SWE: 12. Juli - 16. Juli 2021 (Mm, BWM, ROB, BAI, BGIP, BBWL, BBL, MGIN)

## Idee der Übung

Mit dem Aufgabenblatt sollen Ihre Fähigkeiten beim objektorientierten Entwurf auf der Basis der Delegate- und dem Event-Konzepte weiter verbessert werden.

Lösen Sie die Aufgaben wie üblich in Teamarbeit. Verwenden Sie zur Organisation der Zusammenarbeit die GitHub-Features.

## 1. Delegaten
Das E-Orakel von Freiberg soll für ein Fußballspiel folgende Voraussagen treffen können:

+	das Spielergebnis
+ ob die Verlängerung (bzw. zwei Verlängerungen) stattfinden werden
+ die Anzahl der roten Karten für jede Mannschaft

Aus organisatorischen Gründen werden die Anfragen erst nur eingereicht, die Aussagen liefert das Orakel dann zum späteren Zeitpunkt flott nacheinander.

Erstellen Sie eine Klasse, die für die drei Arten von Voraussagen je eine `static`-Methode definiert. Alle Methoden sollen als Parameter einen String des folgenden Formats bekommen: “Mannschaft1 – Mannschaft2“. Die Methoden haben keinen Rückgabewert, die Voraussagen bzw. Meldungen, dass die Voraussage wegen eines falschen Formats nicht möglich ist, werden innerhalb der jeweiligen Methode auf der Konsole ausgegeben.

Erstellen Sie zufällige Voraussagen. Benutzen Sie dazu z.B. die `Random`-Klasse und die `GetHashCode()`-Methode der Mannschaftsbezeichnungen um den Bezug zu der jeweiligen Mannschaften herzustellen.

Erstellen Sie für die Methoden einen geeigneten `delegate`-Typ.

In der `Main`-Methode sind die drei oben beschriebenen Methoden dem Delegaten hinzuzufügen und mit verschieden Argumenten auszuführen.


## 2. Events
In der digitalisierten Welt funktioniert die Müllentsorgung wie folgt:

Sobald die Mülltonne nicht mehr die zu übernehmende Müllmenge fassen kann, wird ein Event ausgelöst, das das Abtransportieren des Mülls mit einem Müllfahrzeug zufolge hat. Die Tonne wird geleert (der Füllstand der Tonne auf 0 gesetzt) und der Müll wird aus der Tonne in das Fahrzeug übertragen.

Erstellen Sie ein Programm, das u. a. die Klassen `Mülltonne` und `Müllfahrzeug` beinhaltet. Die Klasse `Mülltonne` soll ein Event enthalten, die Klasse `Müllfahrzeug` die Methode (bzw. Property), die infolge des Event-Auslösens ausgeführt wird.

 Um den Vorgang entsprechend dem Standard Event Pattern darstellen zu können, wird außerdem eine von der Klasse `EventArgs` abgeleitete Klasse (z.B. `TransportEventArgs`) benötigt. Die Klasse soll über

+ ein Müllmenge-Property und
+ einen passenden Konstruktor verfügen.

Die Klasse Mülltonne enthält

+ die Datenfelder (und evtl. Properties) mit Angaben zu Tonnen-ID, Volumen und Füllstand,
+ die Methode zum Müllaufnehmen (bzw. ein Property), wo die Überprüfung der Müllmenge und das evtl. Auslösen des Events stattfindet, sowie
+ das Event (z.B. `Abtransport`).

Verwenden Sie zum Definieren des Events den vorhandenen generischen `EventHandler`-Delegattypen, z.B.

```C#
public event EventHandler<TransportEventArgs> Transport;
```

Definieren Sie in der Klasse Mülltonne einen passenden Konstruktor und die `ToString`-Methode.

Die Klasse `Müllfahrzeug` soll:

+	die Angabe zur Müllmenge im Fahrzeug und
+	die Methode zum Abtransportieren (z.B. `OnTransport`) enthalten.

Die Methode zum Abtransportieren soll entsprechend dem Standard Event Pattern folgende Signatur aufweisen, wobei die Bezeichner natürlich frei wählbar sind:

```C#
public void OnTransport(object tonne, TransportEventArgs args)
{
  //TODO
}
```

Definieren Sie in der Klasse ebenfalls einen passenden Konstruktor und die `ToString`-Methode.

In der `Main`-Methode einer anderen Klasse sollen in mehrere Mülltonnen (z.B. `List` oder `Array`) wiederholt verschiedene Müllmengen eingefüllt werden (diese können z.B. zufällig erzeugt werden), sodass dabei in regelmäßigen Abständen ein Event ausgelöst wird. Geben Sie die Füllstände der Tonnen und Fahrzeuges nach jedem Füllen und Leeren aus.
