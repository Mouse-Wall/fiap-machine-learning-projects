
# Projetos de Machine Learning — FIAP

Repositório dedicado ao desenvolvimento e à documentação de projetos acadêmicos realizados no contexto da FIAP, com foco em Inteligência Artificial, Machine Learning, Deep Learning e Visão Computacional.

## 📌 Sobre o repositório

Este repositório reúne dois projetos que exploram diferentes abordagens de Inteligência Artificial aplicadas à análise de dados e à classificação de informações.

Os projetos estão organizados em pastas independentes, cada uma contendo seus notebooks, arquivos de configuração, dependências e documentação específica.

## 🎯 Projetos

### 01 — Machine Learning

**Pasta:** `01-machine-learning/`

Projeto de classificação utilizando dados médicos estruturados, com foco no conjunto de dados **Breast Cancer Wisconsin (Diagnostic) Data Set**.

O objetivo é desenvolver modelos preditivos capazes de classificar diagnósticos em duas categorias:

- **Benigno**
- **Maligno**

O projeto envolve análise exploratória, preparação dos dados, treinamento de modelos de Machine Learning e avaliação de desempenho.

**Tecnologias e ferramentas:**
- Python
- Machine Learning
- Pandas e NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook
- Docker

Para conhecer os detalhes, consulte o README e o notebook dentro da pasta `01-machine-learning/`.

### 02 — Pneumonia Challenge

**Pasta:** `02-pneumonia-challenge/`

Projeto de Deep Learning voltado à classificação de radiografias de tórax, utilizando a arquitetura **ResNet18**, pré-treinada no ImageNet e adaptada por fine-tuning.

O objetivo é classificar imagens em duas categorias:

- **NORMAL:** radiografia classificada como normal.
- **PNEUMONIA:** radiografia classificada como pneumonia.

O projeto utiliza o dataset público Chest X-Ray Images (Pneumonia), disponibilizado no Kaggle.

**Tecnologias e ferramentas:**
- Python
- PyTorch
- Torchvision
- ResNet18
- Scikit-learn
- NumPy
- Matplotlib
- KaggleHub
- Jupyter Notebook
- Docker

Para conhecer os detalhes, consulte o README e o notebook dentro da pasta `02-pneumonia-challenge/`.

**Dataset:** [Chest X-Ray Images (Pneumonia) — Kaggle](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia)

## 🐳 Execução com Docker

Os projetos possuem configurações próprias para execução em ambientes Docker.

Cada pasta contém seus respectivos arquivos de configuração e instruções de execução.

Consulte o README de cada projeto para conhecer os pré-requisitos e os comandos necessários.

## 📁 Estrutura do repositório

```text
fiap-machine-learning-projects/
│
├── README.md
├── .gitignore
│
├── 01-machine-learning/
│   ├── README.md
│   ├── Dockerfile
│   ├── requirements.txt
│   ├── compose.yaml
│   ├── data.csv
│   └── Machine_Learning_FIAP_Docker.ipynb
│
└── 02-pneumonia-challenge/
    ├── README.md
    ├── Dockerfile
    ├── requirements.txt
    └── Pneumonia_Challenge_FIAP_ResNet18.ipynb
```

## ⚠️ Observação importante

Os projetos possuem finalidade acadêmica e experimental. Os modelos desenvolvidos não substituem a avaliação de profissionais de saúde e não devem ser utilizados isoladamente para diagnóstico ou decisões clínicas.

## 👥 Autoria

Projetos desenvolvidos no contexto acadêmico da FIAP.
