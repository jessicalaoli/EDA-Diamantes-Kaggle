# 💎 Análise Exploratória de Dados (EDA) e Fatores de Precificação de Diamantes

Este projeto demonstra habilidades em Análise Exploratória de Dados (EDA) e visualização de dados utilizando Python e o conjunto de dados de diamantes do Kaggle. O foco é desvendar as relações complexas entre as características dos diamantes (`carat`, `cut`, `clarity`, `color`) e seu preço final.

---

## 🎯 Objetivo do Projeto

* **Identificar o Principal Driver:** Determinar qual variável (peso ou qualidade) tem a maior correlação com o preço.
* **Analisar Distribuição:** Entender a assimetria e a necessidade de transformação de variáveis-chave como `price` e `carat`.
* **Explorar Correlações:** Visualizar como a qualidade (`cut`, `clarity`) se comporta em relação ao preço.

## 🛠️ Tecnologias e Ferramentas

| Ferramenta | Uso no Projeto |
| :--- | :--- |
| **Python** | Linguagem de programação principal. |
| **Pandas/NumPy** | Manipulação de dados e transformação logarítmica. |
| **Matplotlib/Seaborn** | Visualização de dados (**Heatmaps, Box Plots, Scatter Plots**). |

---

## 🔍 Análise e Principais Insights

### 1. Distribuição e Tratamento de Variáveis Numéricas

* **Carat (Peso):** O Histograma revelou uma **assimetria positiva severa** (a maioria dos diamantes é leve), com picos claros nos "pesos mágicos" ($1.0$ e $1.5$ Carat).

* **Price (Preço) Transformado:** Para modelagem, o preço foi transformado (Log). O gráfico revela uma distribuição **bimodal** (dois picos), indicando duas populações distintas de diamantes no mercado.

### 2. A Força da Correlação e Variância

* **Correlação Carat vs. Preço:** O gráfico mostra uma **correlação positiva extremamente forte e não linear**. A nuvem se alarga para a direita, indicando que a **variância do preço aumenta drasticamente** para diamantes mais pesados (acima de $1.0$ Carat).

* **Mapa de Calor da Correlação:** Confirma a correlação de **$\mathbf{0.92}$** entre `carat` e `price`. Além disso, mostra que `depth` e `table` (métricas de corte) têm correlações insignificantes com o preço, em comparação com o `carat`.

### 3. Análise das Variáveis de Qualidade

* **Composição do Corte:** O *dataset* é dominado por cortes de **alta qualidade** (`Ideal` e `Premium`).

* **Clareza vs. Preço:** O Box Plot demonstra um efeito **contraintuitivo**: a mediana do preço em categorias de clareza inferior (`SI2`) é por vezes mais alta que a de clareza superior (`IF`). Isso ocorre porque o **`carat` (peso) mascara o efeito**, sendo o fator dominante na precificação.

---

## ✅ Conclusão dos Insights

1.  **O Peso é o Fator Dominante:** O **`carat`** é o principal *driver* do preço (correlação de $0.92$).
2.  **Prêmio de Variância:** O preço é modulado pelas variáveis de qualidade, mas de forma mais significativa em diamantes de **alto peso**.
3.  **Próximo Passo:** O modelo de precificação deve ser construído usando o `log(price)` para lidar com a assimetria e a não-linearidade.

## 💾 Como Executar o Projeto

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/jessicalaoli/EDA-Diamantes-Kaggle.git](https://github.com/jessicalaoli/EDA-Diamantes-Kaggle.git)
    ```
2.  **Instale as Dependências:**
    ```bash
    pip install pandas numpy matplotlib seaborn jupyter
    ```
3.  **Execute:** Abra o arquivo `diamonds_eda.ipynb` em um ambiente Jupyter para visualizar a análise completa.
