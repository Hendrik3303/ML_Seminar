# Projekt TODOs

## Architektur & Training
- [x] Decoder mehr lightweight machen (1/4 Kanäle)
- [x] ResNet50 mit anderen Gewichten testen (currently IMAGENET1K_V2)
- [x] Encoder teilweise einfrieren
- [ ] AttentionResnet Module implementieren

## Loss & Metriken
- [x] FocalLoss implementieren und mit CrossEntropy vergleichen
- [ ] Bewertungsformel der Challenge auf Test-Ergebnisse anwenden

## Data
- [x] Mehr Data-Augmentation (aktuelle Elastic Deformations)
- [x] Transponieren statt nur Flip/Rotate

## Recherche
- [ ] Datensatz analysieren
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
- [x] Foliensatz für Abschluss-Präsi vorbereiten
- [ ] Projektokumentation schreiben
    - Vorgehen
    - erzielte Ergebnisse
    - Vergleich mit bestehenden Lösungen
