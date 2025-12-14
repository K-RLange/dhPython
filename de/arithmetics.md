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
  <a href="../../../de/arithmetics.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../../../en/arithmetics.html">🇬🇧 English</a>
</div>

# 1. Arithmetik und Variablen

## Arithmetik
In seiner einfachsten Form kann Python wie ein Taschenrechner verwendet werden. Du kannst damit unter anderem Zahlen addieren, subtrahieren, multiplizieren und dividieren.

Die folgende Zelle zeigt dir, wie man zwei Zahlen in Python addiert:
```{code-cell}
print(2 + 3)
```
Um ein Objekt in der Konsole auszugeben, kannst du den Befehl print(...) verwenden, wobei du „...“ durch das Objekt ersetzt, das du anzeigen möchtest. In diesem Fall ist es das Ergebnis von 2 + 3.

Weitere mathematische Operationen können wie folgt durchgeführt werden:
```{code-cell}
print(3 * 4)  # Multiplikation
print(3 - 2)  # Subtraktion
print(10 / 2)  # Division
print(10 ** 2)  # Potenzierung
print(10 % 3)  # Modulo
```

Das Symbol # wird verwendet, um Code zu kommentieren. Das bedeutet, dass der Code hinter dem #-Symbol nicht ausgeführt wird. Kommentare sind hilfreich, um zu erklären, was der Code macht.

## Variablen
````{margin}
```{note}
Beim Benennen von Variablen solltest du darauf achten, keine bereits verwendeten Namen zu überschreiben. Du solltest zum Beispiel keine Variable „print“ nennen, da dies die Funktion `print` überschreiben würde. Das würde später zu einem Fehler führen, wenn du versuchst, die `print`-Funktion zu verwenden.
```
````

In Python kannst du Werte in Variablen speichern. Das ist nützlich, wenn du einen Wert mehrfach im Code verwenden möchtest. Eine Zuweisung erfolgt über den = Operator.
Variablen können beliebige Namen haben. In einer praktischen Analyse empfiehlt es sich jedoch, aussagekräftige Namen zu verwenden. So wird der Code verständlicher – für dich und für andere.

Die folgende Zelle zeigt, wie man einer Variable (hier mit dem Namen x) einen Wert zuweist und diesen dann ausgibt:

```{code-cell}
x = 5
print(x)
```

Wenn du eine Variable verändern möchtest, kannst du das ebenfalls mit dem = Operator tun:

```{code-cell}
x = 5
print(x)
x = x + 5
print(x)
```

Du kannst Variablen also als Platzhalter für Objekte verwenden. In diesem Fall wird x eine ganze Zahl (Integer) zugewiesen. Wenn wir eine weitere Variable y definieren, können wir Berechnungen mit diesen Variablen durchführen:

```{code-cell}
x = 5
x = x + 2
y = 10
z = x + y
print(z)
```

### Übung

Jetzt bist du dran! Löse die folgende Übung und klicke auf die versteckte Code-Zelle darunter, um die Lösung zu sehen.
`````{margin}
```{attention}
Um den Python-Code in diesem Kurs zu bearbeiten und auszuführen, findest du dieses Symbol ![live code symbol](code_symbol.PNG) oben auf jeder Seite, die Python-Code enthält. Du kannst darauf klicken und dann „Live code“ auswählen, um den Code selbst zu bearbeiten und auszuführen. Probiere ruhig verschiedene Dinge aus und experimentiere mit dem Code. Du kannst hier nichts kaputt machen, und niemand (auch wir nicht) kann deinen Code sehen – also fühl dich frei, zu experimentieren.
```
`````

#### Übung 1

Berechne die Summe von 5 und 7 und speichere das Ergebnis in einer Variablen namens „var1“. Multipliziere dann diese Variable mit sich selbst und speichere das Ergebnis in einer Variablen namens „var2“. Gib zum Schluss das Ergebnis von „var2“ aus.
```{code-cell}
# Dein Code hier
```

```{code-cell}
:tags: ["hide-cell"]
var1 = 5 + 7
var2 = var1 * var1
print(var2)
```

#### Übung 2
```{raw} html
<style>
  :root {
    --accent: #4f46e5;
    --accent-light: #eef2ff;
    --bg: #ffffff;
    --border: #e5e7eb;
    --text: #111827;
    --gray: #6b7280;
    --success: #16a34a;
    --error: #dc2626;
    --warning: #facc15;
  }

  #quiz-container {
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 2rem;
    max-width: 750px;
    font-family: "Segoe UI", Roboto, sans-serif;
    color: var(--text);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
    transition: box-shadow 0.3s ease;
    margin-bottom: 2rem;
  }

  #quiz-container:hover {
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
  }

  #quiz-container p.question {
    font-size: 1.25rem;
    font-weight: 600;
    margin-bottom: 1.5rem;
  }

  #quiz-form label {
    display: block;
    margin: 0.75rem 0;
    padding: 0.75rem 1rem;
    border-radius: 12px;
    border: 1px solid transparent;
    background-color: var(--accent-light);
    cursor: pointer;
    transition: all 0.25s ease;
  }

  #quiz-form label:hover {
    background-color: #e0e7ff;
    border-color: var(--accent);
  }

  #quiz-form input[type="radio"] {
    margin-right: 0.75rem;
    transform: scale(1.2);
    accent-color: var(--accent);
  }

   #quiz-form pre {
    margin: 0.2rem 0 0;
    background-color: transparent !important;  /* no background */
    border: none !important;                   /* no border */
    display: inline;
    font-size: 0.95rem;
    white-space: pre-wrap;
    padding: 0;                                /* no padding */
    font-family: 'Courier New', Courier, monospace;
  }

  #quiz-form button {
    margin-top: 1.5rem;
    background-color: var(--accent);
    color: white;
    padding: 0.6rem 1.2rem;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  #quiz-form button:hover {
    background-color: #4338ca;
  }

  #quiz-feedback {
    margin-top: 1.25rem;
    padding: 0.75rem 1rem;
    border-radius: 8px;
    font-weight: 500;
    font-size: 1rem;
    display: inline-block;
  }

  .success {
    background-color: #dcfce7;
    color: var(--success);
    border: 1px solid var(--success);
  }

  .error {
    background-color: #fee2e2;
    color: var(--error);
    border: 1px solid var(--error);
  }

  .warning {
    background-color: #fef9c3;
    color: var(--warning);
    border: 1px solid var(--warning);
  }
</style>

<div id="quiz-container">
  <p class="question">🧠 Was ist die korrekte Syntax, um 3 mit 7 zu multiplizieren, das Ergebnis in einer Variable zu speichern, und diese auszugeben? </p>
  <form id="quiz-form">
    <label>
      <input type="radio" name="answer" value="a">
      <pre><code>x = 3 * 7
print(x)</code></pre>
    </label>
    <label>
      <input type="radio" name="answer" value="b">
      <pre><code>3 * 7
print(x)</code></pre>
    </label>
    <label>
      <input type="radio" name="answer" value="c">
      <pre><code>print(3 * 7)</code></pre>
    </label>
    <label>
      <input type="radio" name="answer" value="d">
      <pre><code>print(x = 3 * 7)</code></pre>
    </label>

    <button type="button" onclick="checkAnswer()">Submit Answer</button>
    <p id="quiz-feedback"></p>
  </form>
</div>

<script>
  function checkAnswer() {
    const answers = {
      a: {
        correct: true,
        feedback: "✅ Korrekt!"
      },
      b: {
        correct: false,
        feedback: "❌ x wäre hier nicht definiert, weswegen es nichts zu auszugeben gäbe."
      },
      c: {
        correct: false,
        feedback: "❌ Das gibt das Resultat aus, speichert es aber nicht ab."
      },
      d: {
        correct: false,
        feedback: "❌ Du kannst eine Variable nicht gleichzeitig verwenden und abspeichern."
      }
    };

    const selected = document.querySelector('input[name="answer"]:checked');
    const feedback = document.getElementById("quiz-feedback");

    if (!selected) {
      feedback.textContent = "⚠️ Bitte wähle eine Antwort aus!";
      feedback.className = "warning";
      return;
    }

    const result = answers[selected.value];
    feedback.textContent = result.feedback;
    feedback.className = result.correct ? "success" : "error";
  }
</script>
```



