# 📊 Predição de Concentração de CO com Sensores de Gás usando Machine Learning

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Scikit-Learn](https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)

---

## 📌 Visão Geral

Este projeto tem como objetivo estimar a concentração de Monóxido de Carbono (CO) em ppm a partir dos sinais elétricos de sensores químicos (R1–R14), combinados com variáveis ambientais como temperatura e umidade relativa.

Foram comparadas duas abordagens de modelagem:

- 🔹 Regressão Linear (modelo base)
- 🔹 Rede Neural Multicamadas (MLP Regressor)

O objetivo foi avaliar se a relação entre os sensores e a concentração de CO é linear ou não linear.

---

## 🧪 Fundamentação Física

Sensores de gás do tipo MOS (Metal Oxide Semiconductor) não medem CO diretamente.  
Eles respondem à presença de gases através de variações na resistência elétrica.

A resposta do sensor pode ser modelada como:

Rs = f(CO, Temperatura, Umidade Relativa)

Como sensores químicos são altamente sensíveis a condições ambientais, as variáveis de temperatura e umidade foram incluídas no modelo para permitir compensação ambiental.

---

## 📂 Conjunto de Dados

### 🔹 Variáveis de Entrada (16 no total):

- 14 Sensores de gás (R1–R14)
- Temperatura (T)
- Umidade Relativa (RH)

### 🔹 Variável Alvo:
- Concentração de CO (ppm)

Foram utilizadas **300.000 amostras** para treinamento e avaliação.

---

## ⚙️ Metodologia

### 1️⃣ Pré-processamento

- Amostragem aleatória de 300 mil instâncias
- Divisão Treino/Teste (80/20)
- Normalização com StandardScaler

A normalização foi aplicada para:

- Garantir estabilidade no treinamento da rede neural
- Permitir comparação direta dos coeficientes na regressão linear

---

### 2️⃣ Modelos Avaliados

#### 🔹 Regressão Linear

Modelo base assumindo relação linear:

CO = w₁R₁ + w₂R₂ + ... + w₁₆X₁₆ + b

#### 🔹 MLP Regressor

Arquitetura utilizada:

- Camadas ocultas: (64, 32)
- Função de ativação: ReLU
- Otimizador: Adam
- Early stopping ativado

---

## 📊 Resultados Obtidos

| Modelo              | R² Score | RMSE |
|--------------------|----------|------|
| Regressão Linear  | 0.525    | 4.41 |
| MLP Regressor     | 0.703    | 3.49 |

---

## 📈 Análise dos Resultados

- A Regressão Linear explicou aproximadamente 52% da variância do CO.
- A MLP explicou aproximadamente 70% da variância.
- Houve redução significativa do erro médio (RMSE).

### 🔎 Conclusão

Os resultados indicam que a relação entre os sensores de gás e a concentração de CO apresenta comportamento não linear.

A inclusão de temperatura e umidade relativa foi fundamental para melhorar o desempenho do modelo, permitindo compensação ambiental.

Redes neurais foram mais eficazes na captura de interações complexas entre sensores e variáveis ambientais.

---

## 🚀 Como Executar o Projeto

### 1️⃣ Clonar o repositório

```bash
git clone https://github.com/arthurgoncalvesfarias/gas-sensor-mlp-regression.git
cd gas-sensor-mlp-regression

👤 Autor

Arthur Gonçalves Farias

📜 Licença

Projeto desenvolvido para fins acadêmicos e estudo de Machine Learning aplicado.
