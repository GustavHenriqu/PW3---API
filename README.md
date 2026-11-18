# API REST com Node.js e MySQL

**Aluno:** SEU NOME COMPLETO
**Turma:** SUA TURMA
**Disciplina:** Programação Web III (PW3)

API REST com Node.js, Express e MySQL, usando SQL direto via `mysql2` (sem ORM) e queries parametrizadas contra SQL Injection.

## Pré-requisitos

- [Node.js](https://nodejs.org/) 18 ou superior
- [MySQL](https://dev.mysql.com/downloads/) rodando localmente

## Instalação

1. Clone o repositório e entre na pasta:
   ```bash
   git clone https://github.com/SEU-USUARIO/SEU-NOME-API-node-com-sql.git
   cd SEU-NOME-API-node-com-sql
   ```
2. Instale as dependências:
   ```bash
   npm install
   ```

## Criando o banco de dados

Execute o script `schema.sql` no MySQL:

```bash
mysql -u SEU_USUARIO -p < schema.sql
```

(ou abra o arquivo no MySQL Workbench e execute).

## Configurando o ambiente

Copie o modelo e preencha com suas credenciais:

```bash
cp .env.example .env
```

| Variável      | Descrição                  |
|---------------|----------------------------|
| DB_HOST       | Host do MySQL              |
| DB_USER       | Usuário do MySQL           |
| DB_PASSWORD   | Senha do MySQL             |
| DB_DATABASE   | Nome do banco (`dev_db`)   |
| DB_PORT       | Porta do MySQL (`3306`)    |
| PORT          | Porta da API (`3000`)      |

## Executando

```bash
npm start        # execução normal
npm run watch    # reinicia automaticamente ao salvar
```

A API ficará em `http://localhost:3000`.

## Rotas

| Método | Rota             | Descrição                    | Corpo (JSON)        |
|--------|------------------|------------------------------|---------------------|
| POST   | `/usuarios`      | Cria um usuário              | `nome`, `email`     |
| GET    | `/usuarios`      | Lista todos os usuários      | —                   |
| PUT    | `/usuarios/:id`  | Atualiza um usuário          | `nome` e/ou `email` |
| DELETE | `/usuarios/:id`  | Remove um usuário            | —                   |

### Exemplo

```bash
curl -X POST http://localhost:3000/usuarios \
  -H "Content-Type: application/json" \
  -d '{"nome":"Maria","email":"maria@exemplo.com"}'
```

## Códigos HTTP

`200` sucesso · `201` criado · `400` dados inválidos · `404` não encontrado · `409` email duplicado · `500` erro interno
