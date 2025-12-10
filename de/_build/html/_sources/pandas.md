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
  <a href="../../de/{{path-to-page}}" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../../en/{{path-to-page}}">🇬🇧 English</a>
</div>

# 4. pandas und matplotlib

Erinnerst du dich an die Bibliothek, die wir im letzten Kapitel installiert haben? Diese Bibliothek heißt **pandas** und ist vermutlich die am häufigsten verwendete Bibliothek in Python. Sie erlaubt es uns, beliebige Daten in eine Tabelle zu verwandeln, die wir anschließend analysieren und visualisieren können.

Schauen wir sie uns in Aktion an:

```{code-cell}
import pandas as pd
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
hobby = ["Python-Tutorials abschließen", "Sport", "Python-Tutorials abschließen"]
data = {"Name": names, "Alter": ages, "Hobby": hobby}
df = pd.DataFrame(data)
print(df)
```

Wie du siehst, erlaubt es uns pandas, unsere Daten sauber in Tabellenform zu organisieren.

Wir können jetzt die `groupby`-Funktion von pandas verwenden, um unsere Daten nach einer bestimmten Spalte zu gruppieren und dann eine Funktion auf jede Gruppe anzuwenden. In diesem Fall gruppieren wir nach der Spalte "Hobby" und zählen, wie viele Personen dasselbe Hobby haben:

```{code-cell}
df_grouped = df.groupby("Hobby").size()
print(df_grouped)
```

Nehmen wir nun an, wir haben eine CSV-Datei namens "prices.csv", die wir normalerweise mit Microsoft Excel öffnen würden und die Daten enthält, die wir analysieren möchten. pandas erlaubt es uns, Excel- bzw. CSV-Dateien mit nur einer Zeile in ein DataFrame einzulesen:

```{code-cell}
price_data = pd.read_csv("prices.csv")
print(price_data)
```

Diese Datei enthält Zeitstempel und die Kursveränderungen einer Aktie zwischen den jeweiligen Zeitpunkten. Wenn wir nur die Daten für einen bestimmten Zeitraum sehen wollen, können wir das DataFrame mit der Funktion `loc` filtern. In diesem Fall wollen wir die Daten vom 01.02.2022 bis zum 01.09.2023 anzeigen:

```{code-cell}
start_date = "2022-02-01"
end_date = "2023-09-01"
filtered_data = price_data.loc[(price_data["timestamp"] >= start_date) & (price_data["timestamp"] <= end_date)]
print(filtered_data)
```

Um diese zeitabhängigen Daten zu visualisieren, nutzen wir die Bibliothek matplotlib. Mit dem Befehl to_datetime (aus pandas) können wir zunächst die Spalte mit den Zeitstempeln in ein Datumsformat umwandeln und dann mit plot, angewandt auf price_data ein Diagramm erstellen, das durch show() aus matplotlib angezeigt wird.
```{code-cell}
import matplotlib.pyplot as plt
price_data["timestamp"] = pd.to_datetime(price_data["timestamp"])
price_data.plot(x="timestamp", y="difference")
plt.show()
```
