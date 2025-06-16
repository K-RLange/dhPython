---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
    class: no-execute
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---
<div style="float: right;">
  <a href="../de/modules.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/modules.html">🇬🇧 English</a>
</div>


# 3. Module

Grundsätzlich kann in Python alles von Grund auf neu programmiert werden. Es ist jedoch klüger, zuerst zu überprüfen, ob jemand anderes bereits das umgesetzt hat, was du tun möchtest. Das spart Zeit und Aufwand — und hoffentlich wurde die Umsetzung von jemandem vorgenommen, der kompetent genug war, seinen Code online zu veröffentlichen.

Um Funktionen, Klassen und anderen Code zu verwenden, der online veröffentlicht wurde, musst du die entsprechenden Module importieren.

Module sind Code-Dateien. Sie sind in Bibliotheken (auch Pakete genannt) organisiert, also Sammlungen von Modulen in strukturierter Form.

## Bibliotheken installieren

Python bringt eine kleine Anzahl vorinstallierter Module und Bibliotheken mit. Es gibt jedoch viele weitere, die du erst installieren musst.

Die Veröffentlichungen von Python-Bibliotheken erscheinen in der Regel auf dem [Python Package Index (PyPi)](https://pypi.org/).

Um Bibliotheken von PyPi zu installieren, kannst du **pip** verwenden, das seit Python 3.0 bei jeder Installation automatisch mitgeliefert wird.

Du kannst pip direkt aus Python heraus aufrufen, üblicher ist es aber, pip über das Terminal zu verwenden.

Angenommen, wir wollen das beliebte Paket "pandas" installieren. Direkt aus Python heraus könntest du dazu die Funktion "main" aus dem pip-Modul aufrufen. Diese Funktion nimmt eine Liste als Eingabe, deren erstes Element der String "install" ist (was anzeigt, dass du etwas installieren willst), und das zweite der Name des Pakets:

```python
import pip
pip.main(["install", "pandas"])
```

In einem Terminal (was die empfohlene Methode ist) lautet der Befehl so:

```bash
pip install pandas
```

## Module importieren

Um ein Modul oder eine Bibliothek zu importieren, verwendest du den Befehl `import modul_oder_bibliothek_name` in deiner Python-Konsole.

Wenn du ein Modul importierst, kannst du dessen Funktionen mit `modulname.funktion()` aufrufen. Wenn du z. B. den Mittelwert einer Liste berechnen willst, musst du das Modul `statistics` importieren:

```{code-block}
import statistics
print(statistics.mean([1, 2, 3]))
```

Alternativ kannst du auch nur bestimmte Funktionen aus einem Modul importieren. Das machst du mit `from modulname import funktion`:

```{code-block}
from statistics import mean
print(mean([1, 2, 3]))
```

Wenn du eine gesamte Bibliothek importieren, aber den vollen Namen nicht jedes Mal ausschreiben willst (oder wenn du bereits eine Variable mit demselben Namen hast), kannst du dem Modul beim Importieren einen Spitznamen geben. Das geht mit dem Schlüsselwort `as`. Hier ein Beispiel für die Bibliothek pandas:

```{code-block}
import pandas as pd
```

### Lokale Module importieren

Du kannst lokale Python-Dateien genauso importieren wie externe Module. Wenn du z. B. eine Datei mit dem Namen `modul.py` erstellt hast, kannst du sie so importieren:

```{code-block}
import modul
```

Wenn sich das Modul in einem anderen Verzeichnis befindet, kannst du es dennoch importieren. Befindet es sich zwei Verzeichnisse oberhalb des aktuellen, fügst du zwei Punkte vor dem Modulnamen hinzu:

```{code-block}
import ..modul
```

Wenn du ein Modul in einem Unterverzeichnis importieren willst, geht das so:

```{code-block}
import unterverzeichnis.modul
```
