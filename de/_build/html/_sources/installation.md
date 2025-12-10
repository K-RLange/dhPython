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
  <a href="../de/installation.html" style="margin-left: 10px;">🇩🇪 Deutsch</a>
  <a href="../en/installation.html">🇬🇧 English</a>
</div>


# 8. Installation von Python, einer IDE und Paketen

## Installation von Python

Um Python auf deinem lokalen Rechner zu installieren, kannst du entweder das Installationsprogramm von der offiziellen Website herunterladen oder conda installieren, einen Versionsmanager für Python und andere Programmiersprachen (wie R). Wir empfehlen dir, conda zu verwenden, da es dir eine simple Möglichkeit bietet, verschiedene Python-Versionen und Pakete zu verwalten.

````{margin}
#### Installation mit dem offiziellen Installer (nicht empfohlen)

Um Python direkt zu installieren, besuche die [offizielle Python-Website](https://www.python.org/downloads/) und lade die gewünschte Version herunter.
Beachte jedoch, dass die Verwendung von conda empfohlen wird, da es dir die Verwaltung von Versionen und Paketen erleichtert.
````


### Installation mit conda (empfohlen)

Um conda herunterzuladen, besuche bitte die [offizielle conda Website](https://conda.io/projects/conda/en/latest/user-guide/install/index.html).
Du kannst entweder Miniconda oder die Anaconda-Distribution installieren (empfohlen). Miniconda ist eine Minimalinstallation, während Anaconda zusätzliche vorinstallierte Funktionen bietet, die für dich nützlich sein könnten. Unter anderem wird Anaconda Navigator mitgeliefert: eine visuelle Oberfläche für conda, welche dir die Verwaltung von Umgebungen und Paketen erleichtert.

Folge den Anweisungen auf der Website und installiere die gewünschte Version von conda. Falls du dabei nicht weiterwissen solltest, kannst du dir in diesem ![YouTube Video](https://youtu.be/WUeBzT43JyY?t=52) zwischen 0:53 und 3:53 ein kurzes Tutorial ansehen, das dir bei der Installation hilft. Falls trotzdem Probleme auftreten, zögere bitte nicht, uns eine Mail zu schreiben.  

````{margin}
```{note}
Nach der Installation kannst du jederzeit eine neue Programmierumgebung für Python erstellen. Falls du mehrere Projekte mit unterschiedlichen Paketversionen hast, kannst du für jedes eine eigene Umgebung anlegen, um Versionskonflikte zu vermeiden.
```
````

#### Erstellen einer neuen Python-Umgebung

Um die Aufgaben im DaLi-Thema 3 zu bearbeiten, kannst du dir mit conda eine Programmierumgebung für Python erstellen.

Um eine Python-Umgebung zu erstellen, kannst du im Anaconda Navigator den Tab "Environments" auswählen. Wenn du diesen aufgerufen hast, kannst du unten auf den "Create"-Knopf drücken, worauf hin du gefragt wirst, ob du eine Python- oder R-Umgebung erstellen möchtest und welche Version du installieren willst. Wähle hier einfach Python und die gewünschte Version aus (z.B. 3.9).

## Installation von Paketen

Um Python verwenden zu können, wirst du früher oder später Pakete benötigen. Python bietet zwei wichtige Paketmanager: conda und pip. Die Installation von conda haben wir weiter oben beschrieben und pip ist automatisch bei jeder Python-Installation dabei. 

````{margin}
```{note}
Diese beiden Manager sind nicht immer miteinander kompatibel. Falls du beide nutzen musst, installiere zuerst möglichst viele Pakete über conda und danach den Rest mit pip. Die Reihenfolge der Paketinstallation ist in diesem Fall relevant. 
```
````

Es Pakete gibt, die entweder nur mit conda oder mit pip installiert werden können, daher kann es hilfreich sein, mit beiden umgehen zu können. Solltest du dich aber zunächst auf einen von beiden konzentrieren wollen, dann empfehlen wir pip. pip sollte etwa 95% der Anwendungsfälle abdecken.

Um Pakete mit einem der beiden Paketmanager zu installieren, musst du zunächst ein Terminal öffnen. Dafür kannst du in Anaconda Navigator unter dem Tab "Environments" auf deine gerade eben erstellte Python-Umgebung klicken und dann auf den grünen Pfeil direkt rechts daneben klicken und in dem sich dann öffnenden Fenster "Open Terminal" klicken. Dadurch sollte sich ein Terminal öffnen, in das du hineintippen kannst.

### 1) Mit pip

Um ein Paket mit pip zu installieren, öffne ein Terminal, tippe den folgenden Befehl und drücke Enter:

```bash
pip install paketname
```

Beispiel für das Paket `numpy`:

```bash
pip install numpy
```

Wenn die Installation erfolgreich war, sollte das Terminal eine Nachricht anzeigen, die so ähnlich aussieht:

```bash
Successfully installed numpy-1.21.0
```


### 2) Mit conda

Um ein Paket mit conda zu installieren, öffne ein Terminal, tippe den folgenden Befehl und drücke Enter:

```bash
conda install paketname
```

Beispiel für das Paket `numpy`:

```bash
conda install numpy
```

## Installation einer IDE

Eine IDE (integrierte Entwicklungsumgebung) ist eine Software mit grafischer Oberfläche zum Schreiben und Ausführen von Code. Für Python empfehlen wir Jupyter Notebook oder PyCharm.

Diese IDEs können entweder manuell installiert werden oder mit dem Anaconda Navigator, der mit der Anaconda-Distribution (nicht Miniconda) mitgeliefert wird. Nach dem Start des Navigators werden dir verschiedene Programme zur Installation angeboten.

Falls du den Navigator nicht nutzt, folge diesen Schritten:

### 1) Jupyter Notebook (für Dali-Thema 3 empfohlen)

Jupyter Notebook ist für interaktive Notebooks konzipiert. Es besteht aus einzelnen Code-Blöcken, die nacheinander ausgeführt werden können. Es ist ideal für Lehre und Demos, wie auch dieses Projekt, aber eher ungeeignet für größere Projekte mit mehreren Dateien.

Wenn du Anaconda installiert hast, kannst du Jupyter im Terminal starten mit:

```bash
jupyter notebook
```

Alternativ kannst du auch im Anaconda Navigator unter dem Tab "Home" Jupyter Notebook starten, indem du auf "Launch" klickst.

### 2) PyCharm (für größere Projekte empfohlen)

PyCharm ist eine professionelle IDE für große Projekte, ähnlich wie RStudio für R. Sie bietet viele Funktionen: mehrere Dateien, integrierten Debugger, grafische Verwaltung von conda-Umgebungen und viele mehr. Ihr großer Umfang kann jedoch zu Überforderung bei Anfänger*innen führen.

Wenn du Anaconda Navigator nutzt, kannst du PyCharm dort unter dem Tab "Home" installieren, indem du auf "Install" neben PyCharm Community oder Professional klickst. Die Community Edition ist kostenlos und die Professional Edition ist kostenpflichtig. Falls du ein Hochschul-Login hast, kannst du die Professional Edition kostenlos nutzen, wenn du dein Konto bei JetBrains, dem Herrsteller von PyCharm, mit deiner Uni-E-Mail verknüpfst.

````{margin}
```{note}
Alternativ kannst du Pycharm über die die [offizielle PyCharm-Website](https://www.jetbrains.com/pycharm/download/) installieren.
```
````

Ein Tutorial, um dich mit PyCharm vertraut zu machen findest du auf der [offiziellen PyCharm-Hilfeseite](https://www.jetbrains.com/help/pycharm/quick-start-guide.html).

