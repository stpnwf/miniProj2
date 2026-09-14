# DigitVision MNIST

### Classificação de Dígitos Manuscritos com Machine Learning

## Sobre o projeto

O **DigitVision MNIST** é um projeto de Ciência de Dados desenvolvido em Python para realizar a classificação automática de dígitos manuscritos utilizando técnicas de Machine Learning.

O projeto utiliza o dataset **MNIST**, composto por imagens em escala de cinza de dígitos de 0 a 9. Cada imagem possui resolução de **28 × 28 pixels**, totalizando **784 features**.

A solução contempla um pipeline completo de classificação, desde a análise exploratória e preparação dos dados até o treinamento, ajuste, avaliação e teste de generalização dos modelos.

---

# O problema

O reconhecimento automático de dígitos manuscritos é um problema clássico de classificação multiclasses.

O objetivo deste projeto é construir um modelo capaz de identificar corretamente qual dígito, de **0 a 9**, está representado em uma imagem manuscrita.

Cada imagem possui:

* **28 × 28 pixels**;
* **784 features** após a transformação em vetor;
* valores de intensidade entre **0 e 255** antes da normalização;
* uma classe correspondente ao dígito representado.

---

# Pipeline desenvolvido

O projeto foi organizado seguindo um fluxo completo de Machine Learning:

```text
Carregamento do MNIST
        │
        ▼
Análise Exploratória
        │
        ▼
Divisão Treino / Validação / Teste
        │
        ▼
Normalização dos Pixels
        │
        ▼
Treinamento dos Modelos
        │
        ▼
Ajuste de Hiperparâmetros
        │
        ▼
Avaliação no Conjunto de Teste
        │
        ▼
Seleção do Melhor Modelo
        │
        ▼
Testes de Generalização
        │
        ▼
Inferência com Imagens Próprias
```

---

# Técnicas utilizadas

Durante o desenvolvimento foram utilizadas as seguintes técnicas:

* Análise Exploratória de Dados (EDA);
* análise da distribuição das classes;
* visualização de imagens do dataset;
* divisão estratificada dos dados em treino, validação e teste;
* normalização dos pixels para o intervalo `[0, 1]`;
* ajuste de hiperparâmetros;
* comparação entre diferentes algoritmos de classificação;
* análise de overfitting;
* matriz de confusão;
* Accuracy;
* Precision ponderada;
* Recall ponderado;
* F1-score ponderado;
* análise de custo computacional;
* teste de generalização com classes ocultadas;
* análise de overconfidence;
* inferência com imagens manuscritas próprias.

---

# Algoritmos utilizados

Foram treinados e comparados três modelos de classificação supervisionada:

* **K-Nearest Neighbors (KNN)**
* **Random Forest**
* **Multi-Layer Perceptron (MLP)**

Cada modelo foi avaliado utilizando diferentes configurações de hiperparâmetros, permitindo comparar desempenho e capacidade de generalização.

---

# Tecnologias

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Jupyter Notebook
* Git
* GitHub
* Pillow

---

# Estrutura do projeto

```text
.
├── nums/
│   └── [imagens manuscritas próprias]
├── num2s/
│   └── [imagens manuscritas próprias]
├── notebook.ipynb
├── requirements.txt
├── README.md
└── ...
```

---

# Como executar

## 1. Clone o repositório

```bash
git clone https://github.com/stpnwf/miniProj2.git
```

## 2. Acesse a pasta

```bash
cd miniProj2
```

## 3. Instale as dependências

```bash
pip install -r requirements.txt
```

## 4. Execute o notebook

Abra o Jupyter Notebook e execute as células em sequência.

O dataset MNIST é carregado automaticamente durante a execução do notebook.

---

# Resultado

Após o treinamento e avaliação dos três modelos no conjunto de teste independente, foram obtidos os seguintes resultados:

| Modelo        |   Acurácia | Tempo de treinamento |
| ------------- | ---------: | -------------------: |
| KNN           | **96,93%** |              ~0,26 s |
| Random Forest | **96,49%** |             ~23,65 s |
| MLP           | **97,48%** |             ~28,09 s |

O **MLP apresentou a maior acurácia no conjunto de teste**, com **97,48%**, sendo selecionado como o melhor modelo para os testes de robustez e generalização.

Além do desempenho no conjunto de teste, foram realizadas análises adicionais utilizando imagens manuscritas próprias.

No primeiro conjunto de imagens, o MLP classificou corretamente **10 de 10 imagens (100%)**. Em um segundo conjunto, com maior variação de tamanho e formato dos dígitos, o desempenho caiu para **40%**, demonstrando a influência da distribuição e das características visuais dos dados sobre a capacidade de generalização do modelo.

---

# Testes de robustez e generalização

Para avaliar o comportamento do modelo em situações diferentes das encontradas durante o treinamento, foram realizados experimentos adicionais.

## Classes ocultadas

Duas classes foram completamente removidas do conjunto de treinamento.

O modelo foi posteriormente utilizado para classificar imagens pertencentes exclusivamente às classes ocultadas.

Esse experimento demonstrou uma limitação importante de classificadores tradicionais: mesmo quando recebem uma entrada pertencente a uma classe desconhecida, o modelo pode ser obrigado a classificá-la entre as classes que conhece.

Também foi analisada a confiança das previsões, permitindo observar situações de **overconfidence**, nas quais o modelo apresenta alta probabilidade mesmo em previsões incorretas.

## Imagens manuscritas próprias

O melhor modelo também foi utilizado para realizar inferências sobre imagens manuscritas produzidas especificamente para o projeto.

As imagens foram:

* convertidas para escala de cinza;
* normalizadas para `[0, 1]`;
* transformadas para o formato de 784 características;
* submetidas ao modelo treinado.

Foram utilizados dois conjuntos de imagens, permitindo comparar o desempenho em imagens mais próximas e mais distantes do padrão observado no MNIST.

---

# Melhorias futuras

Como evolução do projeto, poderiam ser implementadas as seguintes melhorias:

* utilização de redes neurais convolucionais (CNN);
* aplicação de técnicas de data augmentation;
* centralização e alinhamento automático dos dígitos;
* utilização de imagens manuscritas com maior diversidade;
* calibração das probabilidades dos modelos;
* utilização de técnicas de detecção de dados fora da distribuição (OOD);
* criação de uma interface para classificação de novos dígitos;
* disponibilização do modelo por meio de uma API;
* criação de uma aplicação web para reconhecimento dos dígitos.

---

# Versionamento

O desenvolvimento foi realizado utilizando Git e GitHub, adotando uma estratégia baseada em branches:

* `main`
* `develop`
* `feature/fase-4`
* `feature/fase-5`

As funcionalidades foram desenvolvidas em branches específicas e posteriormente integradas à branch `develop`.

Ao final do projeto, a versão final foi integrada à branch `master`.

---


# Autor

Arturo Cardoni
