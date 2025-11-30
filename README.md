# Sample-Flask-Auth

## O que é este projeto

**Sample-Flask-Auth** é uma API simples construída com Flask, destinada a demonstrar funcionalidades de autenticação e gerenciamento de usuários.  
Ela permite criar, autenticar, ler, atualizar e deletar usuários, persistindo os dados em um banco MySQL rodando dentro de um container Docker.  
O objetivo principal é servir como base de estudo ou ponto de partida para projetos mais complexos.

<br>

## Tecnologias & Stack

- Python 3.x  
- Flask  
- Flask-SQLAlchemy  
- Flask-Login  
- PyMySQL  
- MySQL (via Docker)  
- Docker & Docker Compose  

<br>

## Como rodar localmente

<br>

### Pré-requisitos

- Docker instalado  
- Docker Compose (ou `docker compose`)

  <br>

### Passos:

1. Clone este repositório:  
   ```bash
   git clone https://github.com/LeonardDevv/sample-flask-auth.git
   cd sample-flask-auth


2. Suba o container do banco de dados:
   ```bash
   docker compose up -d db


3. Instale dependências do Python:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt


4. Configure a variável secreta (opcional, mas recomendado):
   ```bash
   export SECRET_KEY="sua_chave_secreta_aqui"


5. Execute a aplicação:
   ```bash
   flask run

<br>

## Estrutura do Projeto
```graphql
sample-flask-auth/
│
├── app.py            # Define rotas, endpoints e lógica principal
├── database.py       # Configuração do SQLAlchemy e conexão com o banco
├── models/           # Definição dos modelos ORM (ex: User)
├── docker-compose.yml# Configuração do container MySQL
├── requirements.txt  # Dependências Python
└── README.md         # Documentação do projeto (este arquivo)
```

<br>

## Endpoints Disponíveis
| Método | Endpoint     | Descrição                          | Autenticação |
| ------ | ------------ | ---------------------------------- | ------------ |
| POST   | `/login`     | Autenticação de usuário            | —            |
| GET    | `/logout`    | Logout do usuário logado           | ✔️           |
| POST   | `/user`      | Criação de novo usuário            | —            |
| GET    | `/user/<id>` | Ler dados de um usuário específico | ✔️           |
| PUT    | `/user/<id>` | Atualizar senha de usuário         | ✔️           |
| DELETE | `/user/<id>` | Deletar um usuário                 | ✔️           |

<br>

## Funcionalidades Implementadas
- Autenticação básica com Flask-Login
- Criação, leitura, atualização e deleção de usuários (CRUD)
- Persistência de dados em MySQL via container Docker
- Uso de SQLAlchemy para ORM
- Estrutura mínima de API REST

<br>

## Possíveis melhorias / Roadmap
- Hash de senhas (bcrypt / flask-bcrypt)
- Validação de dados (schemas, marshmallow ou pydantic)
- Tratamento de erros e respostas padronizadas
- Testes automatizados (unitários e integrados)
- Dockerização completa da API (backend + DB)
- Variáveis de ambiente para configuração sensível
- Documentação da API (ex: Swagger / OpenAPI)
- Uso de migrations (Flask-Migrate / Alembic)


