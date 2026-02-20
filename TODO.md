# Projekt TODOs

## Architektur & Training
- [x] Decoder mehr lightweight machen (1/4 Kanäle)
- [x] ResNet50 mit anderen Gewichten testen (currently IMAGENET1K_V2)
- [x] Encoder teilweise einfrieren
- [ ] (AttentionResnet Module implementieren)
- [x] Maybe scheduler cos annealing (oder so)
- [x] dice score
- [x] mean IOU

## Loss & Metriken
- [x] FocalLoss implementieren und mit CrossEntropy vergleichen
- [x] Bewertungsformel der Challenge auf Test-Ergebnisse anwenden

## Data
- [x] Mehr Data-Augmentation (aktuelle Elastic Deformations)
- [x] Transponieren statt nur Flip/Rotate
- [x] Elastic Difformation (aber selten -> 20%)

## Recherche
- [x] Datensatz analysieren
    - Wie sehen die Daten genau aus? (visuelle Inspektion)
    - Welche Strukturen sind zu erkennen und was bedeuten sie?
    - Was repräsentieren die Daten?
    - Wie groß ist die Varianz der Daten?
    - Könnenn die Daten mathematisch beschrieben und visualisiert werden (t-SNE)?
    - Wie sind die Daten gelabelt / annotiert?
- [ ] Eingereichte Verfahren und erzielte Ergebnisse analysieren
    - Literaturrecherche
    - zentrale algorithmische verfahren
    - grafische Veranschaulichung?
- [ ] ---
- [ ] Sonstige ideen gerne hier einfach reinschreiben
## Generell
- [X] Foliensatz für Abschluss-Präsi vorbereiten
- [ ] Projektokumentation schreiben
    - Vorgehen
    - erzielte Ergebnisse
    - Vergleich mit bestehenden Lösungen

## Notes 1
### Elastische Difformierung:
- [X]
- Im Moment haben wir 20% Elastic Difformation eingebaut (sind aber hyperlokal)
- Elastic wird jedes Mal neu initialisiert (muss nur einmal, danach zufällig anwenden)
- Testweise ein paar Bilder nehmen (alpha = magnitude of displacement, sigma = of displacement)
- Die Bilder sollen beim Elastic Difformation so verändert sein, dass wir keinen Unterschied sehen, es aber unterschiedliche Bilder sind
- self.elastic
### Transponieren anstelle von Rotieren
- Er macht sich nochmal Gedanken und schreibt ob alles in einer Operation geht
- 90° Verteilung und Flips sollen gleichermaßen vorkommen
### Reduzierung der Layer auf 1/4
- Forward Block musste angepasst werden (Layer reduce)
- Ausgaben der Up-Layer können kleiner sein 
- unter Vorbehalt: Ausgabe auf 1/4 verringern HILFE ICH HABE ES KAPUTT GEMACHT
- reduce kann entfernt werden
- statt layer 3 reduce -> layer 3 --> Zeile 89/90
### Freezing Layers
- adam neu initialisieren könnte problematisch sein
- model.train aktiviert die batchnorm 
    - lieber eigene Methode einbauen: def train(self) (Batchnorm aus den Up-Blöcken)
- Test mit 100 Epochen eingefroren
### Vergleich ohne Training
- resnet mit "gewicht = none" anstelle von default etc
### Weiteres
- Input bei 3 Kanälen lassen? Könnte bei 16 problematisch werden