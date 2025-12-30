# Practica-IAA

Aquest projecte aborda un dels principals reptes en psiquiatria clínica: la **predicció precoç de l’esquizofrènia resistent al tractament (TRS)**, una condició que afecta aproximadament entre el 20–30% dels pacients amb esquizofrènia i que comporta una resposta inadequada als antipsicòtics convencionals.
L’objectiu és desenvolupar i comparar diferents **models de classificació supervisada** per predir si un pacient desenvoluparà o no TRS, utilitzant dades demogràfiques, clíniques i genètiques.

---

## 📊 Dataset

- **Conjunt d’entrenament**: `trs_train`
- **Observacions**: 9.000 pacients
- **Característiques**: 27 variables
- **Variable objectiu**: `TRS` (0 = No TRS, 1 = TRS)
- **Conjunt de test**: 1.000 observacions

---

## 🧪 Metodologia

El treball s’estructura en **tres fases principals**:

### 1. Anàlisi Exploratori de Dades (EDA)
- Estudi de distribucions i asimetries
- Identificació de valors mancants i outliers
- Anàlisi de correlacions
- Avaluació de la necessitat de reducció de dimensionalitat (PCA)
- Estudi del desbalanceig de la variable objectiu

### 2. Preprocessament
- Eliminació de variables redundants i no informatives
- Codificació de variables categòriques (One-Hot Encoding)
- Imputació de valors mancants:
  - Numèriques → mediana
  - Categòriques → moda
- Normalització (StandardScaler) quan és necessari
- Ponderació de classes per tractar el desbalanceig
- Split del dataset: 80% entrenament / 20% validació

### 3. Modelització i Avaluació
S’han entrenat i comparat tres models predictius:
- **Support Vector Machine (SVM)**
- **XGBoost**
- **Regressió Logística (implementació pròpia)**

La mètrica principal d’optimització és **F1-macro**, per garantir un rendiment equilibrat entre classes.

---

## 🤖 Models implementats

### 🔹 Support Vector Machine (SVM)
- Kernel: lineal i RBF
- Cerca d’hiperparàmetres amb Grid Search (5-fold CV)
- Normalització obligatòria
- Rendiment estable però capacitat discriminativa limitada

### 🔹 XGBoost
- Model basat en arbres i boosting
- Regularització intensiva per evitar overfitting
- No requereix escalat
- Bona generalització, però rendiment modest en la detecció de TRS

### 🔹 Regressió Logística 
- Implementació pròpia amb:
  - Descens de gradient mini-batch
  - Regularització L2 (Ridge)
  - Ponderació de classes
- Preprocessament equivalent al SVM
- Cerca d’hiperparàmetres manual amb validació creuada

---

## 📈 Resultats

Cap dels models aconsegueix una capacitat predictiva elevada:
- **ROC-AUC ≈ 0.62–0.63**
- **Recall TRS ≈ 0.5**
- Dificultat inherent del problema i fort desbalanceig de classes

Els models **generalitzen correctament**, però la detecció de pacients TRS continua sent un repte clínic important.

---


## ✍️ Autoria

Treball acadèmic – 2025  
(Carlos Palazón Domingo / Introducció a l'aprenentatge automàtic / Universitat Politècnica de Catalunya)
