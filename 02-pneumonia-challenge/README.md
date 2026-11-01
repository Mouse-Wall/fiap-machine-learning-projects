# Pneumonia Challenge FIAP — Classificação de Radiografias com ResNet18

## Sobre o projeto

Projeto desenvolvido como parte do Tech Challenge Extra da FIAP, com o objetivo de aplicar Deep Learning na classificação de radiografias de tórax.

A solução utiliza uma rede neural convolucional ResNet18, pré-treinada no ImageNet e adaptada por fine-tuning para classificar imagens em duas categorias:

- **NORMAL:** radiografia sem indicação de pneumonia.
- **PNEUMONIA:** radiografia classificada como pneumonia.

Este projeto tem finalidade acadêmica e experimental. Não deve ser utilizado para diagnóstico médico ou decisões clínicas.

## Tecnologias utilizadas

- Python 3.11
- PyTorch
- Torchvision
- ResNet18
- Scikit-learn
- NumPy
- Matplotlib
- KaggleHub
- Docker
- Jupyter Notebook

## Dataset

Foi utilizado o dataset público **Chest X-Ray Images (Pneumonia)**, disponibilizado no Kaggle:

https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

O notebook utiliza o KaggleHub para baixar os arquivos automaticamente.

O conjunto informado no material do projeto possui:

| Conjunto | NORMAL | PNEUMONIA |
|---|---:|---:|
| Treinamento | 1.341 | 3.875 |
| Teste | 234 | 390 |

O dataset não é armazenado neste repositório, pois possui aproximadamente 2,29 GB e é obtido durante a execução.

## Etapas desenvolvidas

1. Importação das bibliotecas e definição dos hiperparâmetros.
2. Seleção automática do dispositivo de processamento, CUDA ou CPU.
3. Download e organização do dataset com KaggleHub.
4. Pré-processamento das imagens e data augmentation.
5. Criação dos DataLoaders para treinamento e teste.
6. Carregamento da ResNet18 pré-treinada no ImageNet.
7. Adaptação da camada final para duas classes.
8. Configuração do otimizador AdamW e da função de perda ponderada.
9. Treinamento e avaliação do modelo.

## Pré-processamento

As imagens são redimensionadas para 224 × 224 pixels e normalizadas utilizando os parâmetros do ImageNet.

Durante o treinamento, são aplicadas técnicas de data augmentation:

- Espelhamento horizontal aleatório.
- Rotação aleatória de até 10 graus.
- Variação de brilho e contraste.

## Configuração do treinamento

| Parâmetro | Valor |
|---|---:|
| Arquitetura | ResNet18 |
| Épocas | 4 |
| Learning rate | 0.00003 |
| Weight decay | 0.01 |
| Batch size | 20 |
| Otimizador | AdamW |

A camada final original da ResNet18 foi substituída por uma camada com duas saídas, correspondentes às classes NORMAL e PNEUMONIA.

## Avaliação

O desempenho do modelo é acompanhado por métricas como:

- Acurácia (Accuracy).
- Recall.
- F1-score.
- Loss de treinamento e validação.

**Observação metodológica:** a pasta `val/` original do dataset contém apenas 16 imagens. Por esse motivo, o conjunto `test/` foi utilizado no notebook para acompanhar o modelo durante as épocas e também para avaliação. Essa limitação deve ser considerada na interpretação dos resultados.

No material original do projeto, executado no Google Colab com GPU T4, foi reportada acurácia de validação próxima de 90% e recall acima de 98%. Esses valores não representam ainda uma medição independente da execução local no Docker.

## Executar com Docker

### Pré-requisitos

- Docker Desktop instalado e em execução.
- Conexão com a internet para baixar o dataset e os pesos pré-treinados da ResNet18.

### Construir a imagem

Na pasta do projeto, execute:

```bash
docker build -t fiap-pneumonia .
```

### Iniciar o Jupyter Notebook

```bash
docker run --rm -p 8889:8888 fiap-pneumonia
```

Acesse no navegador:

http://localhost:8889

Utilize o token apresentado no terminal, caso seja solicitado.

### Observações sobre a execução local

- A imagem Docker utiliza PyTorch em CPU, permitindo executar o projeto sem GPU NVIDIA dedicada.
- O treinamento em CPU pode ser consideravelmente mais lento do que no Google Colab com GPU.
- O notebook baixa o dataset automaticamente pelo KaggleHub.
- Os pesos pré-treinados da ResNet18 também são obtidos pela internet na primeira utilização.
- O dataset e os arquivos de cache não devem ser enviados ao GitHub.

## Arquivo principal

`Pneumonia_Challenge_FIAP_ResNet18.ipynb`

Notebook contendo o desenvolvimento, treinamento e avaliação do modelo.

## Referências

- Dataset Chest X-Ray Images (Pneumonia): https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia
- PyTorch: https://pytorch.org/
- Torchvision: https://pytorch.org/vision/
- KaggleHub: https://github.com/Kaggle/kagglehub

---

Projeto acadêmico desenvolvido para a FIAP.