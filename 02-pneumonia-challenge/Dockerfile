# Ambiente Python para executar o notebook de classificação de pneumonia.
# Esta configuração utiliza PyTorch em CPU para funcionar sem GPU dedicada.
FROM python:3.11-slim

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    PIP_NO_CACHE_DIR=1

WORKDIR /app

# Dependências de sistema necessárias para bibliotecas científicas e gráficos.
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    libgomp1 \
    && rm -rf /var/lib/apt/lists/*

# Instala versões CPU do PyTorch compatíveis entre si.
RUN pip install --upgrade pip && \
    pip install --index-url https://download.pytorch.org/whl/cpu \
      torch==2.5.1 torchvision==0.20.1

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY Pneumonia_Challenge_FIAP_ResNet18.ipynb .

EXPOSE 8888

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
