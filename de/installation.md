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

Um Python auf deinem lokalen Rechner zu installieren, kannst du entweder das Installationsprogramm von der offiziellen Website herunterladen oder conda installieren, einen Versionsmanager für Python und andere Programmiersprachen (wie R).

Für dieses Tutorial musst du **kein** Python oder eine integrierte Entwicklungsumgebung (IDE, also eine grafische Benutzeroberfläche) installieren, da der Code direkt im Browser ausgeführt werden kann.
Möchtest du jedoch nach dem Kurs weiterhin mit Python arbeiten, empfehlen wir dir, Python und eine IDE lokal zu installieren.

### 1) Mit conda (empfohlen)

Um conda herunterzuladen, besuche bitte die [offizielle conda Website](https://conda.io/projects/conda/en/latest/user-guide/install/index.html).
Du kannst entweder Miniconda oder die Anaconda-Distribution installieren (empfohlen). Miniconda ist eine Minimalinstallation, während Anaconda zusätzliche vorinstallierte Funktionen bietet, die für dich nützlich sein könnten.

Folge den Anweisungen auf der Website und installiere die gewünschte Version von conda.

Nach der Installation kannst du jederzeit eine neue Programmierumgebung für Python erstellen. Falls du mehrere Projekte mit unterschiedlichen Paketversionen hast, kannst du für jedes eine eigene Umgebung anlegen, um Versionskonflikte zu vermeiden.

Du kannst conda im Terminal aufrufen mit:

```bash
conda
```

Wenn alles korrekt installiert ist, erscheint eine Liste mit verfügbaren Befehlen. Falls du eine Fehlermeldung bekommst und Windows benutzt, musst du eventuell vorher folgenden Befehl ausführen:

```bash
activate
```

oder

```bash
conda activate
```

Zum Erstellen einer neuen Python-Umgebung gibst du im Terminal folgenden Befehl ein:

```bash
conda create --name meineumgebung python=3.11
```

In diesem Fall erstellen wir eine Umgebung namens `meineumgebung` mit Python-Version 3.11. Du kannst Namen und Version nach Belieben anpassen.

Zur Aktivierung deiner Umgebung verwende:

```bash
conda activate meineumgebung
```

Danach kannst du beliebige Pakete installieren.

### 2) Mit dem offiziellen Installer

Um Python direkt zu installieren, besuche die [offizielle Python-Website](https://www.python.org/downloads/) und lade die gewünschte Version herunter.
Beachte jedoch, dass die Verwendung von conda empfohlen wird, da es dir die Verwaltung von Versionen und Paketen erleichtert.

## Installation von Paketen

Python bietet zwei wichtige Paketmanager: conda und pip. Conda kommt mit der Anaconda-Distribution, pip ist bei jeder Python-Installation dabei.

Diese beiden Manager sind nicht immer miteinander kompatibel. Wenn du conda nutzt, installiere Pakete möglichst über conda. Falls du beide nutzen musst, installiere zuerst möglichst viele Pakete über conda und danach den Rest mit pip.

Für die meisten Anwendungsfälle reicht pip aus.

### 1) Mit pip

Um ein Paket mit pip zu installieren, öffne ein Terminal und tippe:

```bash
pip install paketname
```

Beispiel für das Paket `numpy`:

```bash
pip install numpy
```

### 2) Mit conda

Um ein Paket mit conda zu installieren, verwende:

```bash
conda install paketname
```

Beispiel:

```bash
conda install numpy
```

## Installation einer IDE

Eine IDE (integrierte Entwicklungsumgebung) ist eine Software mit grafischer Oberfläche zum Schreiben und Ausführen von Code. Für Python empfehlen wir Jupyter Notebook oder PyCharm.

Diese IDEs können entweder manuell installiert werden oder mit dem Anaconda Navigator, der mit der Anaconda-Distribution (nicht Miniconda) mitgeliefert wird. Nach dem Start des Navigators werden dir verschiedene Programme zur Installation angeboten.

Falls du den Navigator nicht nutzt, folge diesen Schritten:

### 1) Jupyter Notebook

Jupyter Notebook ist für interaktive Notebooks konzipiert. Es besteht aus einzelnen Code-Blöcken, die nacheinander ausgeführt werden können. Ideal für Lehre und Demos, wie auch dieses Projekt.

Nachteil: Für größere Projekte mit mehreren Dateien ungeeignet.

Wenn du Anaconda installiert hast, kannst du Jupyter starten mit:

```bash
jupyter notebook
```

### 2) PyCharm

PyCharm ist eine professionelle IDE für große Projekte, ähnlich wie RStudio für R. Sie bietet viele Funktionen: mehrere Dateien, integrierten Debugger, grafische Verwaltung von conda-Umgebungen u.v.m.

Nachteil: Für Anfänger eventuell überfordernd.

Zur Installation besuche die [offizielle PyCharm-Website](https://www.jetbrains.com/pycharm/download/) und wähle die gewünschte Version. Es gibt eine kostenlose Community Edition und eine kostenpflichtige Professional Edition.

Falls du ein Hochschul-Login hast, kannst du die Professional Edition kostenlos nutzen, wenn du dein JetBrains-Konto mit deiner Uni-E-Mail verknüpfst.

Ein Tutorial zur Nutzung findest du auf der [offiziellen PyCharm-Hilfeseite](https://www.jetbrains.com/help/pycharm/quick-start-guide.html).
