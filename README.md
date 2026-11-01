# Machine Learning FIAP — Docker

## Conteúdo
- `Dockerfile`: define a imagem Python e instala as dependências.
- `requirements.txt`: bibliotecas utilizadas pelo notebook.
- `compose.yaml`: facilita iniciar o container.
- `Machine_Learning_FIAP_Docker.ipynb`: cópia do notebook ajustada para ler o CSV local.
- `data.csv`: base de dados do projeto.

## Executar no Windows com Docker Desktop

Abra o PowerShell nesta pasta e execute:

```powershell
docker compose up --build
```

Quando o Jupyter iniciar, abra no navegador o endereço local exibido no terminal, normalmente
`http://localhost:8888/lab?token=...`.

Para encerrar:

```powershell
docker compose down
```

## Observações
- A cópia Docker do notebook lê `data.csv` da própria pasta do projeto.
- O notebook original enviado pelo usuário não foi modificado.
- A imagem foi preparada para CPU. O build ainda precisa ser testado no computador com Docker instalado.
