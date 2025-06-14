# Stroke Prediction mit Random Forest

Dieses Projekt demonstriert einen vollständigen ML-Workflow zur Vorhersage von Schlaganfallrisiken anhand von Patientendaten. Ziel ist es, ein zuverlässiges Klassifikationsmodell zu erstellen, das potenzielle Schlaganfälle frühzeitig identifiziert – als Entscheidungsunterstützung für Prävention und Diagnostik.

---

##  Projekthighlights

-  Klassifikation medizinischer Risikodaten
-  Modell: Random Forest mit F1-Optimierung
-  Fokus auf Klassenausgleich & medizinische Fairness
-  Evaluation: Konfusionsmatrix, Klassifikationsbericht, ROC-AUC

---

##  Datengrundlage

Der Datensatz stammt aus Kaggle und enthält anonymisierte Patienteninformationen:

- **Geschlecht**
- **Alter**
- **Hypertonie (Bluthochdruck)**
- **Herzerkrankung**
- **Raucherstatus**
- **BMI**
- **Glukoselevel**
- **Beruf & Familienstand**
- **Ziel:** `stroke` (0 = kein Schlaganfall, 1 = Schlaganfall)

---

##  Verwendete Tools

- **Python 3.8+**
- **pandas**, **NumPy** – Datenaufbereitung
- **scikit-learn** – Modellierung & Metriken
  - `RandomForestClassifier`
  - `train_test_split`, `GridSearchCV`
  - `classification_report`, `confusion_matrix`, `roc_auc_score`
- **matplotlib**, **seaborn** – Visualisierung

---

##  Methodik

1. **Datenbereinigung**
   - Entfernung leerer Einträge & Ausreißer
   - Umwandlung kategorialer Variablen (z. B. `smoking_status` → One-Hot)

2. **Explorative Analyse**
   - Korrelationen & Risikomuster sichtbar gemacht
   - Verteilung von Schlaganfällen nach Alter, Glukose, BMI

3. **Modelltraining mit Random Forest**
   - Optimierung via GridSearchCV (F1-Score als Ziel)
   - Feature-Importances extrahiert

4. **Evaluation**
   - Konfusionsmatrix mit Recall & Precision pro Klasse
   - ROC-AUC zur Schwellenanalyse
   - Optional: SHAP zur Interpretierbarkeit

---

##  Besonderheiten & Herausforderungen

- **Ungleichgewicht der Klassen** (wenige Schlaganfall-Fälle)
  - Umgang durch: `class_weight='balanced'`, Stratified Sampling
- **Klinische Validität vs. Modellkomplexität**
  - Bewusst Entscheidung gegen Blackbox-Modelle (z. B. XGBoost, NN)
  - Fokus auf nachvollziehbare Bäume

---

##  Lessons Learned

-  Feature-Auswahl entscheidend: Alter, Hypertonie und Glukoselevel sind starke Prädiktoren
-  Klassische ML-Methoden wie Random Forest liefern robuste Basis ohne Overfitting
-  Falsche Negative sind medizinisch kritisch: Recall ist wichtiger als Accuracy

---

##  Nächste Schritte

- Einbindung echter Zeitverlaufsdaten (z. B. Verlauf von Blutwerten)
- Vergleich mit XGBoost / LightGBM-Modellen
- Deployment als Screening-Tool für Ärzte mit UI (Streamlit, Dash)
- Erweiterung um Patientenhistorien (z. B. Anzahl Klinikaufenthalte)

---

*Projekt von Enes Baris, 2025*

