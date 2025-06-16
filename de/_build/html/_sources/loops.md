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
  <a href="../de/loops.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/loops.html">🇬🇧 English</a>
</div>


# 6. Bedingungen und Schleifen

In der Programmierung hört es meist nicht bei der Erstellung von Variablen auf. Häufig möchtest du bestimmte Aktionen nur unter bestimmten Bedingungen ausführen oder Aktionen mehrmals wiederholen. Hier kommen Bedingungen und Schleifen ins Spiel.

## Bedingungen

Bedingungen werden genutzt, um zu prüfen, ob eine Aussage wahr oder falsch ist.
Wenn die Aussage wahr ist, wird eine bestimmte Aktion ausgeführt. Wenn die Aussage falsch ist,
wird eine andere Aktion ausgeführt. Solche Bedingungen sind immer binär und können daher als Boolean (True oder False) dargestellt werden.

````{margin}
```{note} Codeblöcke
In Python zeigt der Doppelpunkt ":" den Anfang eines Codeblocks an. Alle Zeilen, die zu diesem Block gehören, werden dann um vier Leerzeichen eingerückt (normalerweise ein Tab). Nur so erkennt Python, welche Zeilen zusammengehören.

Diese Struktur – ein Doppelpunkt gefolgt von eingerückten Zeilen – wird immer verwendet, wenn du Bedingungen, Schleifen, Funktionen oder Klassen erstellst.
```
````

Wir prüfen Bedingungen mit dem Schlüsselwort `if`. Der zugehörige eingerückte Codeblock wird nur dann ausgeführt, wenn die Bedingung erfüllt ist.

```{code-cell}
boolean = True
if boolean:
    print("The boolean is true")
```

Mit `else` kannst du definieren, was passiert, wenn die Bedingung **nicht** erfüllt ist:

```{code-cell}
number = 4
if number > 5:
    print("The number is larger than 5")
else:
    print("The number is not larger than 5")
```

Mit `elif` (else if) kannst du mehrere Bedingungen prüfen:

```{code-cell}
number = 6
if number > 10:
    print("The number is larger than 10")
elif number > 5:
    print("The number is larger than 5 but smaller or equal to 10")
elif number > 0:
    print("The number is larger than 0 but smaller than 5")
else:
    print("The number is smaller or equal to 0")
```

#### Übung 1

Schreibe ein Programm, das nach dem Alter fragt und sagt, ob die Person volljährig ist (ab 18 Jahren).

```{code-cell}
age = 19
if age >= 18:
    print("You are an adult.")
else:
    print("You are not adult.")
```

## Schleifen

```{note} Copy-Pasting
Mehrfaches Kopieren von Code ist ineffizient und führt zu Fehlern, die an mehreren Stellen korrigiert werden müssten. Verwende stattdessen Schleifen.
```

Wenn du eine Aktion mehrfach wiederholen willst, verwende Schleifen.
Es gibt zwei Hauptarten von Schleifen in Python: `while`-Schleife und `for`-Schleife.

### while-Schleife

Eine `while`-Schleife wiederholt ihren Codeblock, solange eine Bedingung erfüllt ist:

```{code-cell}
number = 0
while number < 10:
    number += 1
    print(number)
print("Loop has ended")
```

Wenn die Bedingung zu Beginn **nicht** erfüllt ist, wird der Codeblock gar nicht ausgeführt:

```{code-cell}
number = 11
while number < 10:
    number += 1
    print(number)
print("Loop has not been executed")
```

Man kann `while True:` verwenden und mit `break` gezielt abbrechen:

```{code-cell}
number = 0
while True:
    if number >= 10:
        break
    number += 1
    print(number)
print("Loop has ended")
```

Kombination mit Bedingungen:

```{code-cell}
number = 0
limit = 8
while number < 10:
    number += 1
    if number == limit:
        break
    print(number)
print("Loop has ended")
```

#### Übung 2

Verwende eine `while`-Schleife, um von 1 bis 20 zu zählen, aber gib nur gerade Zahlen aus:

```{code-cell}
number = 1
while number <= 20:
    if number % 2 == 0:
        print(number)
    number += 1
```

#### Übung 3

Verwende `while True:` und `break`, um einen Zähler bis 3 zu zählen:

```{code-cell}
counter = 0
while True:
    if counter == 3:
        break
    print(counter)
    counter += 1
```

### for-Schleife

Wenn du über eine Liste oder ein iterierbares Objekt gehen willst, nutze die `for`-Schleife:

```{code-cell}
numbers = range(0, 10)
for number in numbers:
    print(number)
print("Loop has ended")
```

Mit `enumerate` kannst du gleichzeitig über Index und Wert iterieren:

```{code-cell}
numbers = range(0, 10)
larger_numbers = range(10, 20)

for index, number in enumerate(numbers):
    print(larger_numbers[index] + number)
print("Loop has ended")
```

Auch in einer `for`-Schleife kannst du mit `break` abbrechen:

```{code-cell}
for number in range(0, 10):
    if number > 7:
        break
    print(number)
print("Loop has ended")
```

#### Übung 4

Berechne die Summe einer Liste von Zahlen mit einer `for`-Schleife:

```{code-cell}
numbers = [3, 5, 7, 9, 11]
sum = 0
for i in numbers:
    sum += i
print(sum)
```

### List Comprehension

Mit einer **List Comprehension** kannst du Listen mit Schleifen in einer einzigen Zeile erzeugen:

```{code-cell}
numbers = range(0, 10)
larger_numbers = range(10,20)
even_larger_numbers = [number + larger_numbers[index] for index, number in enumerate(numbers)]
print(even_larger_numbers)
```

````{margin}
```{note}
Sei vorsichtig mit Bedingungen in List Comprehensions. Die resultierende Liste sollte die gleiche Länge behalten, sonst kann es zu Fehlern kommen.
```
````

Du kannst Bedingungen innerhalb einer List Comprehension verwenden:

```{code-cell}
[number if number % 2 == 1 else number / 2 for number in range(0, 10)]
```

#### Übung 5

Nutze eine List Comprehension, um eine Liste zu erstellen, die die Quadrate der **geraden** Zahlen von 1 bis 20 enthält und **0** für ungerade Zahlen:

```{code-cell}
new_list = [i ** 2 if i % 2 == 0 else 0 for i in range(1, 20)]
print(new_list)
```
