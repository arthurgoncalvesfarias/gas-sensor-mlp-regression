# Previsão da Concentração de CO Utilizando Rede Neural MLP Aplicada a Dados de Sensores Químicos

📌 Objetivo

Este projeto tem como objetivo estimar a concentração de Monóxido de Carbono (CO) em ppm a partir de sinais elétricos de sensores químicos (R1–R14), utilizando técnicas de regressão linear e redes neurais artificiais.

🧪 Contexto Físico

Sensores de gás do tipo MOS (Metal Oxide Semiconductor) não medem CO diretamente.
Eles apresentam variações na resistência elétrica quando expostos a gases.

A resposta do sensor pode ser descrita como:

𝑅
𝑠
=
𝑓
(
𝐶
𝑂
,
𝑇
,
𝑈
𝑅
)
R
s
	​

=f(CO,T,UR)

Onde:

𝑅
𝑠
R
s
	​

 → resposta elétrica do sensor

𝐶
𝑂
CO → concentração de monóxido de carbono

𝑇
T → temperatura

𝑈
𝑅
UR → umidade relativa

Como sensores são sensíveis a condições ambientais, foram incluídas variáveis ambientais no modelo para permitir compensação térmica e higrométrica.

📂 Dados Utilizados

14 sensores químicos (R1–R14)

Temperatura (T)

Umidade relativa (RH)

Variável alvo: CO (ppm)

Total de variáveis de entrada: 16

Foram utilizadas 300.000 amostras do dataset original.

⚙️ Metodologia
1️⃣ Pré-processamento

Amostragem de 300k instâncias

Divisão treino/teste (80/20)

Normalização com StandardScaler

A normalização foi aplicada para:

Garantir estabilidade no treinamento da MLP

Permitir comparação direta dos coeficientes na regressão linear

🔹 MLP (Rede Neural)

Arquitetura:

2 camadas ocultas (64, 32)

Função de ativação ReLU

Otimizador Adam

Early stopping

📊 Resultados
Modelo	R²	RMSE
Regressão Linear	0.525	4.41
MLP	0.703	3.49
📈 Análise dos Resultados

A regressão linear explicou aproximadamente 52% da variância do CO.

A MLP explicou aproximadamente 70% da variância.

A redução no RMSE indica melhora significativa na precisão.

Conclusão:

A relação entre os sensores e a concentração de CO apresenta comportamento não linear.
Modelos não lineares capturam melhor as interações entre sensores e variáveis ambientais.

🔬 Experimentos Realizados

Comparação entre modelo linear e não linear

Inclusão de variáveis ambientais

Análise de coeficientes da regressão linear

Avaliação via R² e RMSE

🧠 Conclusão

A inclusão de temperatura e umidade relativa foi fundamental para permitir compensação ambiental na resposta dos sensores.

A rede neural apresentou desempenho superior, indicando presença de não linearidades no comportamento dos sensores de gás.

Este trabalho demonstra aplicação prática de Machine Learning para calibração inteligente de sensores químicos.

🚀 Tecnologias Utilizadas

Python

Pandas

Scikit-learn

Matplotlib

NumPy
