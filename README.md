# 🍷 Wine Classifier - Classificação de Vinhos com Aprendizado de Máquina

Este projeto aplica algoritmos de **aprendizado supervisionado** no clássico conjunto de dados **Wine Dataset**, disponível no `sklearn.datasets`. O objetivo é classificar vinhos com base em atributos físico-químicos e avaliar o desempenho dos modelos **Naive Bayes** e **Random Forest**.

---

## 📁 Sobre o Dataset

O **Wine Dataset** contém 178 amostras de vinhos, divididas em três classes (0, 1 e 2), correspondentes a diferentes cultivares da uva.

Cada amostra possui 13 atributos contínuos:

- `alcohol`, `malic_acid`, `ash`, `alcalinity_of_ash`, `magnesium`, `total_phenols`, `flavanoids`, `nonflavanoid_phenols`, `proanthocyanins`, `color_intensity`, `hue`, `od280/od315_of_diluted_wines`, `proline`.

---

## 🧪 Metodologia

### 📊 Pré-processamento

- **Padronização** dos dados com `StandardScaler()`
- Divisão em **conjunto de treino e teste** (80% / 20%)
- Visualização de padrões com **PCA** e **gráficos paralelos**

### 🔍 Modelos Aplicados

#### 🧠 1. Naive Bayes

Algoritmo probabilístico que assume independência entre os atributos.

A predição do Naive Bayes considera a classe com maior probabilidade conjunta:

P(C_k | x) ∝ P(C_k) * Π P(x_i | C_k)

No caso Gaussiano:

P(x_i | C_k) = (1 / sqrt(2πσ²)) * exp( - (x - μ)² / 2σ² )

#### 🌲 2. Random Forest

Ensemble de árvores de decisão que reduz overfitting por meio da aleatoriedade na seleção de atributos e amostras.

Hiperparâmetros otimizados com **GridSearchCV**, testando:
- `max_depth` de 9 a 19
- `min_samples_split` de 2 a 9

---

## 📈 Resultados

### 🔍 Métricas de Avaliação

| Modelo         | Acurácia | F1-score (macro) | Classe 0 | Classe 1 | Classe 2 |
|----------------|----------|------------------|----------|----------|----------|
| Naive Bayes    | **97%**  | 0.97             | 0.96     | 0.96     | 0.99     |
| Random Forest  | 96%      | 0.96             | 0.95     | 0.95     | 0.99     |

### 🧾 Classificação Naive Bayes

          precision    recall  f1-score   support
       0       0.95      0.97      0.96        40
       1       0.98      0.94      0.96        50
       2       0.97      1.00      0.99        34

### 🌲 Classificação Random Forest (ajustada)

          precision    recall  f1-score   support
       0       0.97      0.93      0.95        40
       1       0.94      0.96      0.95        50
       2       0.97      1.00      0.99        34

---

## 📌 Conclusões

- Ambos os modelos apresentaram ótimo desempenho, com destaque para o **Naive Bayes** em termos de acurácia global.
- O **Random Forest** teve vantagem em robustez e permite maior customização via tuning de hiperparâmetros.
- O projeto ilustra como diferentes abordagens podem ser comparadas com base em **métricas objetivas** e análises interpretáveis.

---

## ✍️ Autor

Fernando ✨
📚 Bacharel em Física | Técnico em Eletrotécnica | Ciência de Dados



