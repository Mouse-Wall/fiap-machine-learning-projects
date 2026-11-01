# Machine Learning FIAP — Execução com Docker

Projeto acadêmico de Machine Learning desenvolvido no contexto da FIAP, com ambiente preparado para execução do notebook Jupyter utilizando Docker.

O objetivo desta versão é facilitar a configuração do ambiente e permitir que outras pessoas executem o notebook sem precisar instalar manualmente todas as dependências Python no computador.

## Estrutura do projeto

| Arquivo | Descrição |
|---|---|
| `Dockerfile` | Define a imagem e configura o ambiente Python |
| `requirements.txt` | Lista as bibliotecas necessárias |
| `compose.yaml` | Facilita a criação e execução do container |
| `Machine_Learning_FIAP_Docker.ipynb` | Notebook adaptado para execução com Docker |
| `data.csv` | Base de dados utilizada pelo notebook |
| `.dockerignore` | Define arquivos ignorados durante o build da imagem |
| `.gitignore` | Define arquivos ignorados pelo Git |

## Pré-requisitos

Antes de iniciar, é necessário ter instalado:

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Git (opcional, caso queira clonar o repositório pelo terminal)

## Como executar

### 1. Clonar o repositório

```bash
git clone https://github.com/Mouse-Wall/machine-learning-fiap-docker.git
```

### 2. Entrar na pasta do projeto

```bash
cd machine-learning-fiap-docker
```

### 3. Construir e iniciar o ambiente

Com o Docker Desktop aberto e em execução, execute:

```bash
docker compose up --build
```

O Docker irá construir a imagem, instalar as dependências e iniciar o JupyterLab.

### 4. Acessar o JupyterLab

Após a inicialização, o terminal exibirá um endereço local com um token de acesso.

Abra esse endereço no navegador. Normalmente, ele será semelhante a:

```text
http://localhost:8888/lab?token=...
```

### 5. Executar o notebook

No JupyterLab, abra:

`Machine_Learning_FIAP_Docker.ipynb`

Execute as células do notebook para reproduzir o projeto.

## Como encerrar o ambiente

No terminal, dentro da pasta do projeto, execute:

```bash
docker compose down
```

## Validação

O ambiente Docker foi construído e executado localmente com sucesso.

Todas as células do notebook foram executadas sem erros no computador utilizado para o teste.

O comportamento em outros sistemas operacionais e configurações de hardware pode variar.

## Observações

- O notebook adaptado utiliza o arquivo `data.csv` disponível na pasta do projeto.
- O notebook original foi preservado separadamente; esta versão foi preparada para execução com Docker.
- A imagem Docker foi configurada para execução em CPU.

---

**Projeto acadêmico — FIAP | Machine Learning**
