# 📊 Análise de Sentimentos de Avaliações de Clientes

Projeto de **Processamento de Linguagem Natural (NLP)** e **Machine Learning** desenvolvido em Python para analisar automaticamente o sentimento presente em avaliações de clientes de um e-commerce brasileiro.

O projeto utiliza o dataset **B2W-Reviews01** e compara dois modelos de classificação — **Naive Bayes** e **Regressão Logística** — para identificar avaliações como **positivas, negativas ou neutras**.

---

## 🎯 Objetivo

O objetivo deste projeto é desenvolver um modelo capaz de classificar automaticamente avaliações de clientes de acordo com seu sentimento.

A partir das avaliações textuais, o projeto busca demonstrar como técnicas de **NLP e Machine Learning** podem ser utilizadas para transformar dados não estruturados em informações úteis para análise de negócios.

---

## 📦 Dataset

Foi utilizado o dataset **B2W-Reviews01**, composto por avaliações reais de clientes de um grande e-commerce brasileiro.

O dataset contém informações relacionadas às avaliações, como:

* Texto da avaliação
* Nota atribuída pelo cliente
* Produto
* Categoria
* Informações do avaliador
* Data da avaliação
* Recomendação do produto

O arquivo original do dataset **não está incluído neste repositório** devido ao seu tamanho.

Para executar o projeto, é necessário baixar o dataset e disponibilizá-lo no ambiente do Google Colab.

### Classificação dos sentimentos

A variável de sentimento foi criada a partir da nota atribuída pelo cliente:

| Nota | Sentimento  |
| ---- | ----------- |
| 1–2  | 🔴 Negativo |
| 3    | 🟡 Neutro   |
| 4–5  | 🟢 Positivo |

---

## 🛠️ Tecnologias utilizadas

* **Python**
* **Google Colab**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Scikit-learn**
* **NLP — Processamento de Linguagem Natural**
* **TF-IDF**
* **Naive Bayes**
* **Regressão Logística**

---

## 🔎 Etapas do projeto

O projeto foi desenvolvido seguindo as principais etapas de um pipeline de Machine Learning para classificação de textos.

### 1. Carregamento dos dados

Importação do dataset e análise inicial da estrutura dos dados.

### 2. Análise exploratória

Investigação das características do conjunto de dados, incluindo:

* Quantidade de registros
* Colunas disponíveis
* Valores ausentes
* Distribuição das notas
* Distribuição das classes de sentimento

### 3. Criação da variável de sentimento

As avaliações foram transformadas em três classes:

* Negativo
* Neutro
* Positivo

Essa classificação foi baseada na nota atribuída pelo cliente.

### 4. Pré-processamento dos textos

As avaliações passaram por etapas de limpeza e normalização, incluindo:

* Conversão para letras minúsculas
* Remoção de acentos
* Remoção de caracteres especiais
* Normalização dos espaços
* Remoção de textos vazios

Um cuidado importante foi **não remover indiscriminadamente palavras como "não"**, pois termos de negação podem ser importantes para determinar o sentimento de uma avaliação.

### 5. Análise das palavras

Foi realizada uma análise da frequência das palavras presentes nas avaliações para identificar os termos mais recorrentes no conjunto de dados.

### 6. Separação dos dados

Os dados foram divididos em:

* **80% para treinamento**
* **20% para teste**

Foi utilizada estratificação para preservar a proporção das classes durante a divisão.

### 7. Vetorização com TF-IDF

Os textos foram transformados em representações numéricas utilizando **TF-IDF (Term Frequency–Inverse Document Frequency)**.

Também foram utilizados **unigramas e bigramas**, permitindo que o modelo considere tanto palavras individuais quanto combinações de duas palavras.

### 8. Treinamento dos modelos

Foram treinados dois algoritmos de classificação:

* Multinomial Naive Bayes
* Regressão Logística

### 9. Avaliação

Os modelos foram avaliados utilizando:

* Acurácia
* Precisão
* Recall
* F1-score
* Matriz de confusão

### 10. Teste com novas avaliações

Após o treinamento, foram inseridas novas avaliações manualmente para verificar como o modelo classificaria textos que não estavam presentes no conjunto de treinamento.

---

## 🤖 Modelos utilizados

### Naive Bayes

O **Multinomial Naive Bayes** é um algoritmo tradicionalmente utilizado para classificação de textos.

Ele apresenta baixo custo computacional e funciona bem em problemas envolvendo representação de documentos por frequência ou pesos de palavras.

### Regressão Logística

A **Regressão Logística** foi utilizada como segundo modelo para comparação.

Neste projeto, apresentou desempenho superior ao Naive Bayes, sendo selecionada como o melhor modelo entre os dois avaliados.

---

## 📈 Resultados

Os resultados obtidos no conjunto de teste foram:

| Modelo              |   Acurácia | Macro F1 |
| ------------------- | ---------: | -------: |
| Naive Bayes         | **82,38%** | **0,67** |
| Regressão Logística | **84,21%** | **0,69** |

### 🏆 Melhor modelo

A **Regressão Logística** apresentou o melhor desempenho geral:

* **84,21% de acurácia**
* **0,69 de Macro F1**

O modelo apresentou bons resultados principalmente na identificação das avaliações **positivas e negativas**.

Por outro lado, a classe **neutra apresentou desempenho significativamente inferior**, indicando que avaliações neutras são mais difíceis de distinguir utilizando apenas as características textuais utilizadas neste projeto.

---

## 📊 Matriz de confusão

A matriz de confusão foi utilizada para analisar os acertos e erros da classificação realizada pela Regressão Logística.

Ela permite observar não apenas a quantidade de previsões corretas, mas também quais classes são mais frequentemente confundidas pelo modelo.

A análise mostrou que o principal desafio está na identificação das avaliações **neutras**, enquanto as classes positiva e negativa apresentam uma separação mais consistente.

---

## 💼 Aplicação em negócios

A análise automática de sentimentos pode ser utilizada como uma ferramenta de apoio à tomada de decisão em empresas que recebem grandes volumes de avaliações de clientes.

Algumas possíveis aplicações são:

* 📌 Monitoramento da satisfação dos clientes
* 📌 Identificação de produtos com maior quantidade de avaliações negativas
* 📌 Acompanhamento da percepção dos consumidores
* 📌 Priorização de problemas relatados nas avaliações
* 📌 Monitoramento de tendências de satisfação
* 📌 Apoio à análise de feedbacks em larga escala

Em um cenário real, esse tipo de solução poderia ser integrado a um dashboard para acompanhar a evolução dos sentimentos dos clientes ao longo do tempo.

---

## 🚀 Próximos passos

Algumas possibilidades de evolução do projeto:

* [ ] Testar outros algoritmos de Machine Learning
* [ ] Realizar ajuste de hiperparâmetros
* [ ] Melhorar o tratamento de textos em português
* [ ] Experimentar técnicas mais avançadas de NLP
* [ ] Utilizar modelos baseados em Transformers
* [ ] Comparar o desempenho com modelos de linguagem em português
* [ ] Criar um dashboard para visualização dos resultados
* [ ] Disponibilizar o modelo através de uma API
* [ ] Desenvolver uma interface para classificação de novas avaliações
* [ ] Investigar técnicas específicas para melhorar a classificação da classe neutra

---

## 📁 Estrutura do projeto

```text
b2w-sentiment-analysis/
│
├── B2W_Sentiment_Analysis.ipynb
├── README.md
└── .gitignore
```

O notebook contém todo o processo de análise, desde o carregamento e tratamento dos dados até o treinamento, avaliação e utilização dos modelos.

---

## ▶️ Como executar

### 1. Clone o repositório

```bash
git clone https://github.com/Jbsam159/b2w-sentiment-analysis.git
```

### 2. Abra o notebook

O projeto foi desenvolvido no **Google Colab**.

Abra o arquivo:

```text
B2W_Sentiment_Analysis.ipynb
```

no Google Colab.

### 3. Disponibilize o dataset

Baixe o dataset **B2W-Reviews01** e faça o upload do arquivo CSV para o ambiente do Colab.

O notebook espera encontrar o arquivo:

```text
B2W-Reviews01.csv
```

### 4. Execute o notebook

Execute as células em ordem, desde o carregamento dos dados até as previsões das novas avaliações.

---

## 📚 Conceitos praticados

Este projeto permitiu aplicar conceitos de:

* Análise exploratória de dados
* Limpeza e pré-processamento de textos
* Processamento de Linguagem Natural
* Engenharia de atributos
* Vetorização TF-IDF
* Classificação supervisionada
* Naive Bayes
* Regressão Logística
* Avaliação de modelos
* Matriz de confusão
* Interpretação de resultados
* Aplicação de Machine Learning em problemas de negócio

---

## 👨‍💻 Autor

**João Victor Batista Sampaio**

Software Engineer | Data & AI

* 💼 LinkedIn: [João Victor Batista Sampaio](https://www.linkedin.com/in/joao-victor-bs/)
* 💻 GitHub: [Jbsam159](https://github.com/Jbsam159)

---

## 📌 Observação

Este projeto foi desenvolvido com finalidade **educacional e de portfólio**, buscando demonstrar a aplicação prática de técnicas de NLP e Machine Learning em um problema relacionado à análise de experiência e satisfação de clientes.
