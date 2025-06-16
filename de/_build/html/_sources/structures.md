---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
<div style="float: right;">
  <a href="../de/structures.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/structures.html">🇬🇧 English</a>
</div>


# 2. Datentypen

Im letzten Kapitel haben wir gelernt, dass Variablen eine ganze Zahl zugewiesen werden kann, was zu einer Integer-Variable führt.
In Python gibt es verschiedene Arten von Daten, die in Variablen gespeichert werden können. Ein Integer ist nur eine von vielen Formen, die eine Variable annehmen kann.
In diesem Kapitel stellen wir dir die gängigsten Datentypen in Python vor.

## Variablentypen

### Numerische Datentypen

In Python gibt es zwei wichtige numerische Datentypen: Ganzzahlen ("int") und Fließkommazahlen ("float").
Ganzzahlen sind ganze Zahlen, während Fließkommazahlen Zahlen mit einem Dezimalpunkt sind.

```{note}
Python ist eine dynamisch typisierte Sprache. Das bedeutet, dass du den Datentyp einer Variablen beim Erstellen nicht explizit angeben musst. Python erkennt automatisch den Datentyp der Variablen basierend auf dem zugewiesenen Wert. Das gilt für alle Datentypen in Python, nicht nur für Zahlen.
```

```{code-cell}
x = 5
y = 5.5
print(type(x))
print(type(y))
```

```{margin} Achtung!
Python versucht immer, den seiner Meinung nach passenden Datentyp zu erkennen. Dies kann zu Problemen führen, wenn du einen bestimmten Datentyp verwenden willst, Python aber deine Variable in einen anderen Typ umwandelt.

Angenommen, wir möchten bei einer Division nur Ganzzahlen verwenden. Aber bei einer Division wandelt Python Zahlen immer in Fließkommazahlen um. Um diesen Fehler zu korrigieren, können wir das Ergebnis zurück in einen Integer casten:
```

```{code-cell}
:tags: [margin]
x = 10
y = 2
z = x / y
print(z, type(z))
z = int(z)
print(z, type(z))
```

```{margin}
Wir sehen, dass sich der Wert nicht ändert, sondern nur der Dezimalpunkt verschwindet. Type-Casting ist eine fortgeschrittene Technik und sollte nur verwendet werden, wenn du einen bestimmten Datentyp benötigst.
Mehr dazu findest du [hier](https://www.geeksforgeeks.org/type-conversion-python/). 
```

Du kannst mit beiden Zahlentypen Rechenoperationen durchführen.
Python konvertiert das Ergebnis automatisch in den Datentyp, den es für am geeignetsten hält:

```{code-cell}
x = 5
y = 5.5
print(type(x + x))
print(type(x + y))
print(type(y + y))
```

### Strings

Strings sind Zeichenfolgen (Buchstaben, Symbole etc.). Sie können erstellt werden, indem man Zeichen in einfache oder doppelte Anführungszeichen einschließt. Für mehrzeilige Strings kann man auch dreifache Anführungszeichen verwenden.
Alle drei Varianten ergeben denselben Datentyp:

```{code-cell}
x = "Hello, World!"
y = 'Hello, World!'
z = """Hello,
World!"""
print(x, type(x))
print(y, type(y))
print(z, type(z))
```

### Booleans

Booleans sind ein Datentyp, der nur zwei Werte annehmen kann: `True` oder `False`. Sie repräsentieren den Wahrheitswert einer Aussage. Du kannst den Datentyp eines Booleans mit der Funktion `type()` überprüfen:

```{code-cell}
x = True
y = False
print(type(x))
print(type(y))
```

Wir können auch einen Boolean relativ zu einer anderen Variablen definieren. Im folgenden Codeblock überprüfen wir, ob x größer als 3 ist:

```{code-cell}
x = 5
y = x > 3
print(y)
```

Du kannst den Wert von x ändern, um zu sehen, wie sich der Boolean-Wert ändert.

Booleans werden häufig in Bedingungsanweisungen verwendet, die wir in einem späteren Kapitel behandeln.

## Collections für Variablen

Um nicht nur einzelne Werte in Variablen zu speichern, bietet Python die Möglichkeit, mehrere Werte in einer einzigen Variable zu speichern. Diese nennt man Collections. Die gängigsten Collection-Typen in Python sind Listen, Tupel, Sets und Dictionaries.

### Listen

Listen sind die flexibelste Art, mehrere Variablen zu speichern. Du kannst eine Liste erstellen, indem du Elemente in eckige Klammern setzt und mit Kommas trennst:

```{code-cell}
x = [1, 2, 3, 4, 5]
print(x)
```

Auf Elemente in einer Liste kann über den Index zugegriffen werden.

```{attention}
Ungewöhnlich ist, dass die Indexierung in Python bei 0 beginnt. Das heißt, das erste Element hat den Index 0, das zweite den Index 1 usw.
```

```{code-cell}
x = [1, 2, 3, 4, 5]
print(x[0])
```

Man kann auch negative Indizes verwenden, um Elemente "von hinten" zu erhalten. Mit dem Index -1 bekommst du das letzte Element, mit -2 das vorletzte usw.

```{code-cell}
x = [1, 2, 3, 4, 5]
print(x[-1])
print(x[-2])
```

Listen sind flexibel. Du kannst sie jederzeit verändern, indem du Elemente hinzufügst, entfernst oder änderst. Mit `append()` fügst du Elemente hinzu, mit `remove()` entfernst du sie.

```{code-cell}
x = [1, 2, 3, 4, 5]
x.append(6)
x.remove(2)
print(x)
```

#### Übung 1

Erstelle eine Liste mit den Zahlen 1 bis 10. Entferne dann die Zahl 5 und füge die Zahl 11 hinzu.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
x.remove(5)
x.append(11)
print(x)
```

#### Übung 2

Erstelle eine Liste mit den Zahlen 1 bis 3. Füge dann den String "Four" hinzu. Gib die Liste aus.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
x = [1, 2, 3]
x.append("Four")
print(x)
```

### Tupel

Tupel sind der unflexibelste Datentyp. Einmal erstellt, können ihre Werte nicht geändert werden.
Du solltest Tupel nur verwenden, wenn die Daten garantiert gleich bleiben.

Ein Tupel wird mit runden Klammern und Kommas erstellt:

```{code-cell}
x = (1, 2, 3, 4, 5)
print(x)
```

Ein einzigartiges Merkmal von Tupeln ist das sogenannte Tuple Unpacking, bei dem mehrere Variablen gleichzeitig zugewiesen werden:

```{code-cell}
x = (1, 2, 3)
a, b, c = x
print(a)
print(b)
print(c)
```

### Sets

Sets sind ungeordnet und nicht indexierbar. Du kannst also nicht mit einem Index auf Elemente zugreifen.

Ein Set wird mit geschweiften Klammern und Kommas erstellt:

```{code-cell}
x = {1, 2, 3, 4, 5}
print(x)
```

Alle Elemente in einem Set sind einzigartig. Doppelte Werte werden automatisch entfernt:

```{code-cell}
x = {1, 2, 3, 4, 5, 5}
print(x)
```

Du kannst das auch nutzen, um Duplikate aus einer Liste zu entfernen, indem du sie in ein Set und dann wieder in eine Liste konvertierst:

```{code-cell}
x = [1, 2, 3, 1, 4, 5]
x = set(x)
x = list(x)
print(x)
```

Ein zweiter großer Vorteil von Sets ist die sehr schnelle Suche nach Elementen. Der Unterschied zur Liste wird bei großen Datenmengen deutlich:

```{code-cell}
x = {1, 2, 3, 4, 5}
print(3 in x)
```

#### Übung 3

Erstelle eine Liste, die die Zahlen 1 bis 3 zweimal enthält. Entferne die Duplikate.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
x = [1, 2, 3, 1, 2, 3]
x = set(x)
x = list(x)
print(x)
```

### Dictionaries

Dictionaries erweitern das Konzept von Sets. Während Sets nur Werte enthalten, bestehen Dictionaries aus Schlüssel-Wert-Paaren.
Das bedeutet, dass du jedem Objekt eine eindeutige Kennung geben kannst.

Im folgenden Beispiel speichern wir das Alter einer Person. Wir erstellen ein Dictionary mit dem Namen als Schlüssel und dem Alter als Wert:

```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
print(x["Alice"])
```

Dictionaries sind ähnlich wie Sets: Erstens sind sie ungeordnet. Du kannst also nicht per Index auf sie zugreifen, sondern musst den Schlüssel verwenden. Zweitens nutzen sie, wie Sets, Hashing, womit du blitzschnell auf einen Eintrag zugreifen kannst:

```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
print("Alice" in x)
```

Dictionaries sind sehr flexibel. Du kannst Elemente hinzufügen, ändern oder entfernen. Mit dem Zuweisungsoperator fügst du Werte hinzu, mit der Methode `pop()` entfernst du sie:

```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
x["David"] = 40
x.pop("Bob")
print(x)
```

Du kannst mit `keys()` alle Schlüssel oder mit `values()` alle Werte eines Dictionaries ausgeben:

```{code-cell}
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
print(x.keys())
print(x.values())
```

#### Übung 4

Erstelle ein Dictionary mit den Namen "Alice", "Bob" und "Charlie" als Schlüssel und deren Alter als Werte. Füge dann "David" mit dem gleichen Alter wie "Bob" hinzu. Wandle anschließend die Werte des Dictionaries in eine Liste mit eindeutigen Werten um.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
x = {"Alice": 25, "Bob": 30, "Charlie": 35}
x["David"] = x["Bob"]
y = x.values()
y = list(set(y))
print(y)
```
