# Practica-IAA

Aquest projecte aborda un dels principals reptes en psiquiatria clínica: la **predicció precoç de l’esquizofrènia resistent al tractament (TRS)**, una condició que afecta aproximadament entre el 20–30% dels pacients amb esquizofrènia i que comporta una resposta inadequada als antipsicòtics convencionals.
L’objectiu és desenvolupar i comparar diferents **models de classificació supervisada** per predir si un pacient desenvoluparà o no TRS, utilitzant dades demogràfiques, clíniques i genètiques.

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
- Codificació de variables categòriques 
- Imputació de valors mancants:
- Normalització
- Ponderació de classes per tractar el desbalanceig
- Split del dataset

### 3. Modelització i Avaluació
S’han entrenat i comparat tres models predictius:
- **Support Vector Machine (SVM)**
- **XGBoost**
- **Regressió Logística (implementació pròpia)**

---


## ✍️ Autoria

Treball acadèmic – 2025  
(Carlos Palazón Domingo / Introducció a l'aprenentatge automàtic / Universitat Politècnica de Catalunya)
