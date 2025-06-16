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
  <a href="../../../de/functions.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../../../en/functions.html">🇬🇧 English</a>
</div>

# 7. Funktionen und Klassen

Funktionen und Klassen sind Pythons primäre Möglichkeit, Codeblöcke für wiederholte Ausführungen zu speichern.

## Funktionen

```{margin} Namensräume
Wenn du eine Funktion erstellst, entsteht eine neue Umgebung, in der Variablen unterschiedlich benannt sein können. Das nennt man einen Namensraum.

Das bedeutet, dass Variablen, die innerhalb einer Funktion definiert werden, außerhalb dieser Funktion nicht zugänglich sind. Das ist wichtig zu beachten, da du sonst beim Zugriff auf solche Variablen einen Fehler bekommst.
```

Funktionen sind eine Möglichkeit, einem bestimmten Codeblock einen Namen zu geben, sodass er wiederholt mit unterschiedlichen Startwerten (Inputs) ausgeführt werden kann.

Jede Funktion beginnt mit einer Kopfzeile, die das Schlüsselwort "def" enthält, gefolgt vom Namen der Funktion. Danach müssen runde Klammern folgen, in denen die benötigten Eingaben stehen. Ein Doppelpunkt folgt danach, und der dazugehörige Funktions-Codeblock wird eingerückt, genauso wie bei Schleifen und Bedingungen. Der Codeblock endet normalerweise mit einem "return"-Statement, das angibt, was die Funktion zurückgibt. Die Funktion kann dann mit ihrem Namen und den gewünschten Eingabewerten in Klammern aufgerufen werden.

Beispiel: Wenn wir eine Funktion erstellen wollen, die den Wert von x^2 + 2 zurückgibt, wobei x unser Input ist:

```{code-cell}
def example_function(x):
    result = x ** 2 + 2
    return result

function_result = example_function(2)
print(function_result)
```

Man kann einer Funktion auch mehrere Eingabewerte geben. Wenn wir z. B. x^k + 2 berechnen wollen:

```{code-cell}
def example_function(x, k):
    result = x ** k + 2
    return result

function_result = example_function(2, 3)
print(function_result)
```

Wir können auch Standardwerte für Eingaben im Funktionskopf festlegen. Hier ein Beispiel mit k=2 als Standardwert:

```{code-cell}
def example_function(x, k=2):
    result = x ** k + 2
    return result

# Standardwert
function_result = example_function(2) # k muss nicht angegeben werden
print(function_result)

# Anderer Wert als der Standard:
function_result = example_function(2, 3) # k wird angegeben
print(function_result)
```

Wenn Funktionen viele Eingabevariablen haben, möchte man manchmal nur eine bestimmte davon ändern. Das geht, indem man die entsprechende Variable beim Funktionsaufruf explizit angibt:

```{code-cell}
def example_function(x, a=1, b=1, c=1, d=1, e=1, f=1, k=2):
    result = x ** k + 2
    return result

function_result = example_function(2, k=3) # Nur k wird geändert
print(function_result)
```

Wenn man seine Funktionen beschreiben möchte (hilfreich für andere Nutzer), kann man Docstrings verwenden. Diese werden direkt nach dem Funktionskopf mit drei Anführungszeichen erstellt:

```{code-cell}
def example_function(x, k=2):
    """Dies ist eine Beispiel-Funktion. Sie berechnet x^k + 2
    Args:
        x: Die Zahl, für die der Ausdruck berechnet wird.
        k: Der Exponent
    Returns:
        x^k + 2
    """
    result = x ** k + 2
    return result

print(help(example_function))
```

#### Übung 1

Schreibe eine Funktion namens `add_five`, die eine Zahl als Eingabe nimmt und diese Zahl plus fünf zurückgibt. Führe sie mit einer beliebigen Zahl aus, um zu testen, ob sie funktioniert.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
def add_five(x):
    return x + 5

print(add_five(10))
```

---

#### Übung 2

Schreibe eine Funktion namens `power_plus_two`, die zwei Eingaben `x` und `k` nimmt und `x` hoch `k` plus 2 zurückgibt.
Rufe die Funktion mit den Werten `x = 3`, `k = 2` auf.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
def power_plus_two(x, k):
    return x ** k + 2

print(power_plus_two(3, 2))
```

## Klassen

```{note}
Die Namen von Klassen werden normalerweise großgeschrieben, während Funktions- und Variablennamen klein geschrieben werden.
```

Klassen sind größere Strukturen, die mehrere Funktionen und Variablen speichern können. Dies dient oft dazu, ein zusammenhängendes Objekt zu erstellen, das komplexe Operationen mit mehreren Funktionen durchführen kann.

Klassen werden mit einer Kopfzeile wie "class Klassen\_Name" erstellt. Jede Klasse muss eine Initialisierungsfunktion "**init**(self, ...)" enthalten.

* Die Unterstriche deuten darauf hin, dass diese Funktion nicht direkt vom Nutzer verändert werden soll.
* Der Parameter "self" wird in (fast) jeder Funktion einer Klasse verwendet. Damit kann man innerhalb der Klasse auf andere Funktionen und Variablen zugreifen.

Beispiel: Wir erstellen eine Klasse, die bei der Initialisierung eine Variable x als Input nimmt. Dann definieren wir zwei Funktionen: Eine berechnet x^k, die andere x^k+m. Die zweite ruft die erste auf:

```{code-cell}
class Example_Class:
    def __init__(self, x):
        self.x = x  # self setzt eine Klassenvariable

    def exponential(self, k=2):
        result = self.x ** k  # Zugriff auf self.x
        return result

    def exponential_plus_m(self, k=2, m=2):
        exponential_result = self.exponential(k)  # Aufruf interner Funktion
        result = exponential_result + m
        return result

exponential_calculator = Example_Class(x=2)
result1 = exponential_calculator.exponential(k=3)
print(result1)
result2 = exponential_calculator.exponential_plus_m(k=3, m=4)
print(result2)
print(exponential_calculator.x)
```

Wie du siehst, rufen wir Funktionen und Variablen innerhalb der Klasse über einen Punkt-Zugriff auf das Objekt auf.

#### Übung 3

Schreibe eine Klasse namens `Calculator`, die eine Zahl `x` in der Methode `__init__` übernimmt.
Erstelle zwei Methoden:

* `square`: gibt `x` zum Quadrat zurück.
* `add_number`: nimmt ein Argument und gibt die Summe von `x` und diesem Argument zurück.

Erzeuge dann ein Objekt von `Calculator` mit `x = 4` und rufe beide Methoden auf.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
class Calculator:
    def __init__(self, x):
        self.x = x

    def square(self):
        return self.x ** 2

    def add_number(self, y):
        return self.x + y

calc = Calculator(4)
print(calc.square())
print(calc.add_number(6))
```

---

#### Übung 4

Erweitere die `Calculator`-Klasse aus Übung 3 um eine Methode `multiply_and_add`, die `x` mit einer Zahl `m` multipliziert und eine weitere Zahl `a` addiert.
Rufe sie mit `m = 3` und `a = 2` auf.

```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
class Calculator:
    def __init__(self, x):
        self.x = x

    def square(self):
        return self.x ** 2

    def add_number(self, y):
        return self.x + y

    def multiply_and_add(self, m, a):
        return self.x * m + a

calc = Calculator(4)
print(calc.multiply_and_add(3, 2))
```
