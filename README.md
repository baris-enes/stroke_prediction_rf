#  Stroke Prediction mit Machine Learning

##  Projektüberblick

Ziel dieses Projekts ist die Entwicklung eines Vorhersagemodells zur Einschätzung des Schlaganfallrisikos auf Basis medizinischer und demografischer Patientendaten. Der zugrunde liegende Datensatz umfasst über 5.000 Einträge mit Merkmalen wie Alter, Blutzucker, BMI, Beruf und Rauchverhalten.

Da Schlaganfälle nur bei etwa 5 % der Fälle auftreten, besteht ein starkes Klassenungleichgewicht. Deshalb liegt der Schwerpunkt auf dem F1-Score der positiven Klasse (stroke = 1), um Sensitivität und Präzision gleichermaßen zu bewerten.

Im Rahmen dieses Projekts wurden verschiedene Machine-Learning-Algorithmen untersucht – darunter SVM, Logistische Regression, KNN und Naive Bayes.
Der Fokus dieses GitHub-Repositories liegt auf dem `Random Forest Classifier`, da dieser in meiner Analyse das beste Gleichgewicht zwischen Recall und Präzision erreicht hat.

##  Datensatz

- **Beobachtungen:** 5.110 Patientendaten
- **Features:** Alter, Geschlecht, Hypertonie, Herzkrankheiten, Familienstand, Beruf, Wohnort, Glukose, BMI, Raucherstatus
- **Ziel:** Binäre Variable `stroke` (0 = kein Schlaganfall, 1 = Schlaganfall)


##  Modellübersicht & Performancevergleich

| Modell                  | Accuracy | F1-Score (Positiv) | Besonderheiten |
|------------------------|----------|--------------------|----------------|
| 🔵 Random Forest        | 88 %     | **0.29**           | Bestes Modell (mit Gewichtung), gute Balance |
| 🟠 Support Vector Classifier (SVC) | 85 %     | 0.26               | Polynom-Kernel, Recall hoch |
| 🟢 Decision Tree        | 86 %     | 0.19               | Inkl. SMOTE, aber viele False Positives |
| 🔴 K-Nearest Neighbors  | 83 %     | 0.13               | Hoher Bias, Recall schlecht |
| ⚪ Naive Bayes          | 82 %     | 0.14               | Extrem hoher Recall, kaum Präzision |
| 🟡 Logistische Regression | 84 %   | 0.22 – 0.25        | Gute Basis, stabil auch mit wenigen Features |


##  Bewertungskriterien

- **F1-Score Klasse 1** als wichtigste Metrik  
- Train/Test-Split: 80/20 (stratifiziert)  
- Kreuzvalidierung: 5-fach  
- Klassengewichtungen vs. SMOTE getestet


##  Lessons Learned

- Gewichtung der Klassen stabiler als SMOTE
- GridSearch verbessert Recall signifikant
- Dropping von Daten (z. B. Junge Patienten) kann Recall senken
- F1-Score bietet bessere Aussagekraft als Accuracy bei Imbalance


##  Projektstruktur

```
.
├── healthcare_dataset_random_forest_.ipynb
├── healthcare-dataset-stroke-data.csv
├── df_final.csv
├── requirements.txt
```


##  Ausführung

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Dann im Notebook starten:
```bash
jupyter notebook
```
→ Öffne `healthcare_dataset_random_forest_.ipynb`


##  Hinweis

Die Daten stammen aus einem öffentlich zugänglichen Kaggle-Datensatz. Das Modell dient **ausschließlich zu Lernzwecken**.

