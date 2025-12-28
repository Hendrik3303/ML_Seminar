# Projekt TODOs

## Architektur & Training
- [x] Decoder mehr lightweight machen (1/4 Kanäle)
- [ ] ResNet50 mit anderen Gewichten testen
- [ ] Encoder teilweise einfrieren
- [ ] AttentionResnet Module implementieren

## Loss & Metriken
- [x] FocalLoss implementieren und mit CrossEntropy vergleichen
- [ ] Bewertungsformel der Challenge auf Test-Ergebnisse anwenden

## Data
- [ ] Mehr Data-Augmentation
- [ ] Transponieren statt nur Flip/Rotate

## Recherche
- [ ] self.normalize = transforms.Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225]) laut ki standart werte für resnet modelle bitte einmal prüfen
- [ ] Sonstige ideen gerne hier einfach reinschreiben