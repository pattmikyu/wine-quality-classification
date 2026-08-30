# wine-quality-classification
Tech Challenge Fase 2
# 🍷 Análise Exploratória e Classificação de Qualidade de Vinhos (WineQT)

Este repositório contém uma Análise Exploratória de Dados (EDA) e o pré-processamento para a criação de um modelo de aprendizado de máquina focado em prever e classificar a qualidade de vinhos tintos com base em suas propriedades físico-químicas.

---

## 📌 Visão Geral do Projeto

O objetivo principal deste projeto é investigar as características químicas que impactam a avaliação de qualidade de um vinho e transformar a variável alvo (`quality`) em um problema de **classificação binária**. 

Ao analisar as métricas estatísticas (média, mediana e moda) do conjunto de dados, definiu-se um ponto de corte metodológico para classificar os vinhos em:
* **0 (Baixa/Média Qualidade):** Notas inferiores a 7.
* **1 (Alta Qualidade):** Notas maiores ou iguais a 7 ($\ge 7$).

---

## 📊 Principais Descobertas da Análise Exploratória (EDA)

* **Distribuição da Qualidade Original:**
  * **Notas presentes:** `[3, 4, 5, 6, 7, 8]`
  * **Média:** 5.66 | **Mediana:** 6.0 | **Moda:** 5.0
* **Definição de Alta Qualidade:** Vinhos com nota 5 representam o padrão "médio" da base. Apenas cerca de **13.91%** das amostras atingem nota igual ou superior a 7, justificando o ponto de corte para identificar os vinhos excepcionais.
* **Prevenção de Vazamento de Dados (*Data Leakage*):** A coluna original `quality` e a coluna identificadora `Id` foram removidas do conjunto de dados após a criação da variável-alvo binária (`alta_qualidade`), garantindo que o modelo aprenda exclusivamente a partir das variáveis físico-químicas.
* **Ausência de Nulos:** A base de dados não apresentou valores ausentes em nenhuma das colunas.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3
* **Ambiente de Desenvolvimento:** Google Colab / Jupyter Notebook
* **Bibliotecas:**
  * `pandas`: Manipulação e análise estruturada de dados.
  * `numpy`: Operações matemáticas e criação da variável binária.
  * `matplotlib`: Renderização de gráficos e visualizações customizadas.
  * `seaborn`: Gráficos estatísticos avançados (histogramas, boxplots e gráficos de contagem).

---

## 📁 Estrutura da Base de Dados (`WineQT.csv`)

O dataset contém **1.143 entradas** e as seguintes variáveis físico-químicas:

| Coluna | Tipo | Descrição |
| :--- | :--- | :--- |
| **fixed acidity** | Float | Acidez fixa (ácido tartárico) |
| **volatile acidity** | Float | Acidez volátil (ácido acético, altos níveis causam gosto de vinagre) |
| **citric acid** | Float | Ácido cítrico (adiciona 'frescor' ao vinho) |
| **residual sugar** | Float | Açúcar residual após a fermentação |
| **chlorides** | Float | Quantidade de sal no vinho |
| **free sulfur dioxide** | Float | Dióxido de enxofre livre (previne crescimento microbiano) |
| **total sulfur dioxide** | Float | Dióxido de enxofre total ($SO_2$ livre + ligado) |
| **density** | Float | Densidade do vinho |
| **pH** | Float | Nível de acidez/alcalinidade (escala de 0 a 14) |
| **sulphates** | Float | Sulfatos (aditivo que contribui para os níveis de gás $SO_2$) |
| **alcohol** | Float | Percentual alcoólico do vinho |
| **alta_qualidade** | Int (0 ou 1) | **Target:** 1 para vinhos com nota $\ge 7$, 0 para os demais |

---

## 🚀 Como Executar o Projeto

### Pré-requisitos
Certifique-se de ter o Python 3.x instalado em sua máquina ou utilize o [Google Colab](https://colab.research.google.com/).

### Instalação das Dependências

Instale as bibliotecas necessárias via linha de comando:

```bash
pip install pandas numpy seaborn matplotlib
