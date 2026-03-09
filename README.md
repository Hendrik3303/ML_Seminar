# MoNuSAC Challenge – Lösungsansatz (Gruppe 2)

Dieses Repository enthält den Lösungsansatz von **Gruppe 2** für die MoNuSAC Challenge im Rahmen des Seminars **Maschinelles Lernen**. 

Im Fokus dieses Projekts steht die Segmentierung und Klassifikation von Zellkernen. Unser finales und bestes Modell ist das **Feature-Pyramid-Net (FPN)**. Ein alternativer Ansatz basierend auf einem **U-Net** steht ebenfalls in diesem Repository zur Verfügung und funktioniert nach dem gleichen Prinzip.

---

## Projektstruktur

- `Binary_mask_generation.ipynb`: Skript zur Extraktion von Masken für jedes Bild im Datensatz (erstellt von Ruchika Verma).
- `Pyramid-Net.ipynb`: Unser finaler und stärkster Ansatz (Feature Pyramid Network) zur Segmentierung.
- `U-Net.ipynb`: Alternativer Segmentierungs-Ansatz basierend auf der U-Net Architektur.
- `PQ_metric_new.ipynb`: Notebook zur Berechnung der Panoptic Quality (PQ) Metrik, um die Performance unserer Vorhersagen zu evaluieren.
- `output_graphs/`: Beinhaltet die generierten Graphen und Visualisierungen der Modell-Evaluation.
- `TODO.md`: Offene Punkte und zukünftige Meilensteine.

---

## Voraussetzungen und Installation

Um den Code lokal auszuführen, wird **Python 3.8+** sowie **Jupyter Notebook** (oder JupyterLab) benötigt.

### 1. Repository klonen
Öffne dein Terminal und klone das Repository:

```bash
git clone [https://github.com/Hendrik3303/ML_Seminar.git](https://github.com/Hendrik3303/ML_Seminar.git)
cd ML_Seminar
```

### 2. Abhängigkeiten installieren
Stelle sicher, dass alle benötigten Bibliotheken installiert sind. Die grundlegenden Data-Science- und Deep-Learning-Pakete kannst du wie folgt über dein Terminal installieren:

```bash
pip install jupyterlab numpy matplotlib pandas opencv-python scikit-learn
pip install torch torchvision
```

---

## Nutzung (Ausführungs-Pipeline)

Bitte führe die Schritte zwingend in der folgenden Reihenfolge aus:

### Schritt 1: Datensatz herunterladen
Lade dir den offiziellen **MoNuSAC Datensatz** von der Challenge-Website herunter und entpacke ihn lokal auf deinem Rechner.

### Schritt 2: Binäre Masken generieren
Öffne das Notebook `Binary_mask_generation.ipynb` und führe es aus. 
- Achte darauf, dass die Datei-Pfade im Code auf deinen heruntergeladenen MoNuSAC-Datensatz zeigen.
- Dieses Notebook extrahiert die Ground-Truth-Masken für jedes Bild, welche für das Training benötigt werden.

### Schritt 3: Modell trainieren / ausführen
Öffne `Pyramid-Net.ipynb` (oder `U-Net.ipynb`).
- Passe auch hier die Pfade (`Paths`) im Notebook an, sodass sie auf die in Schritt 2 generierten Masken und die Originalbilder zeigen (im normal Fall sollte diese aber schon richtig gesetzt sein). Genauere Details dazu sind als Kommentare im FPN-Notebook hinterlegt.
- Führe das Notebook aus, um das Modell zu trainieren und Vorhersagen zu generieren.

### Schritt 4: Metriken evaluieren
Um zu überprüfen, wie gut das Modell performt, öffne `PQ_metric_new.ipynb`. 
- Führe das Notebook aus, um die **Panoptic Quality (PQ) Metrik** für die Vorhersagen deines Modells zu berechnen.
