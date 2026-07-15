# 🍷 Wine Quality Classifier — studium przypadku ML

Studium przypadku zrealizowane w ramach przedmiotu **Systemy uczące się** na Politechnice Poznańskiej (Wydział Informatyki i Telekomunikacji, Zakład Uczenia Maszynowego). Projekt obejmuje pełny proces analityczny: od eksploracji danych, przez inżynierię cech, po trenowanie i strojenie kilku modeli klasyfikacyjnych.

**Autor:** Paweł Chumski
**Prowadzący:** dr hab. inż. Maciej Komosiński, prof. PP
**Data:** czerwiec 2023

---

## 📋 O projekcie

Celem projektu jest analiza zbioru danych **Wine Quality Dataset (WineQT)**, opisującego fizykochemiczne właściwości czerwonego wina portugalskiego *Vinho Verde*, oraz zbudowanie modelu przewidującego jego jakość (`quality`, skala 0–10) na podstawie 11 atrybutów warunkowych, m.in.:

- kwasowość stała i lotna (`fixed acidity`, `volatile acidity`)
- kwas cytrynowy, cukier resztkowy, chlorki
- wolny i całkowity dwutlenek siarki
- gęstość, pH, siarczany, zawartość alkoholu

Główne wyzwania analizowanego zbioru to niezbalansowane klasy, niewielka liczba próbek oraz stosunkowo duża liczba cech.

## 🔍 Zakres analizy

1. **Eksploracja danych (EDA)** — statystyki opisowe, rozkłady zmiennych, wykrywanie wartości odstających (histogramy, boxploty).
2. **Analiza korelacji** — macierz korelacji cech oraz ich zależność z atrybutem decyzyjnym `quality`.
3. **Selekcja cech** — `SelectKBest` (ANOVA, chi², mutual information) oraz ranking ważności cech z Random Forest.
4. **Balansowanie klas** — oversampling z użyciem `RandomOverSampler`, `SMOTE`, `ADASYN`, `BorderlineSMOTE`.
5. **Trenowanie modeli** — porównanie klasyfikatorów:
   - Decision Tree
   - Random Forest
   - K-Nearest Neighbors
   - SVC
   - Regresja logistyczna
   - Gradient Boosting
6. **Strojenie hiperparametrów** — `GridSearchCV` z walidacją krzyżową dla każdego modelu.
7. **Porównanie wariantów** — pełny zestaw cech vs. zredukowany zbiór najistotniejszych atrybutów (`volatile acidity`, `citric acid`, `total sulfur dioxide`, `sulphates`, `alcohol`).

## 🏆 Wyniki

Najlepsze rezultaty (mierzone metrykami Accuracy, F1-score, Precision i Recall) osiągnęły modele **Decision Tree** oraz **Random Forest**. Redukcja liczby cech oraz strojenie hiperparametrów przyniosły jedynie nieznaczną poprawę wyników — pełne wnioski i dyskusja znajdują się w raporcie.

## 📁 Struktura repozytorium

```
├── Kod/
│   ├── skrypt.ipynb        # notebook z pełną analizą i modelami
│   ├── WineQT.csv          # zbiór danych
│   └── *.png                # wykresy wygenerowane w toku analizy
├── Raport/
│   └── SUS___projekt.pdf   # pełny raport ze studium przypadku
├── LICENSE
└── README.md
```

## 🛠️ Technologie

- Python, Jupyter Notebook
- `pandas`, `numpy`
- `scikit-learn` (modele, `GridSearchCV`, selekcja cech)
- `imbalanced-learn` (oversampling)
- `matplotlib`, `seaborn`, `plotly` (wizualizacje)

## ▶️ Uruchomienie

```bash
git clone https://github.com/pchumski/Studium-przypadku.git
cd Studium-przypadku/Kod
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn plotly jupyter
jupyter notebook skrypt.ipynb
```

## 📄 Licencja

Projekt udostępniony na licencji [MIT](LICENSE).
