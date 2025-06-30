# Sistema Bancário 🏦

Este projeto define a estrutura de um banco de dados relacional para um sistema bancário, com suporte a clientes, contas, cartões e transações.

## 📂 Banco de Dados: `sistemaBancario`

### 📑 Tabelas Criadas

#### 🧑 Cliente
Contém os dados dos clientes do banco.

- `id_cliente` (PK)
- `nome_completo`, `cpf`, `data_nasc`, `telefone`, `email`, `cidade`, `renda_mensal`

#### 🏦 Conta
Informações de contas bancárias vinculadas a clientes.

- `id_conta` (PK)
- `id_cliente` (FK)
- `numero_conta`, `agencia`, `tipo_conta`, `saldo`, `data_abertura`, `status_conta`

#### 💳 Cartão
Cartões associados às contas (débito ou crédito).

- `id_cartao` (PK)
- `id_conta` (FK)
- `tipo`, `numero`, `validade`, `bandeira`, `limite_credito`, `saldo_fatura`

#### 💸 Transação
Registra movimentações entre contas.

- `id_transacao` (PK)
- `id_conta_origem` (FK)
- `id_conta_destino` (FK)
- `tipo_transacao`, `valor`, `data_hora`, `status_transacao`, `canal`

## ⚙️ Requisitos

- MySQL ou MariaDB
- Um cliente para executar os scripts (como MySQL Workbench ou phpMyAdmin)

## ▶️ Execução

1. Abra o seu gerenciador de banco de dados.
2. Copie e cole o conteúdo do arquivo `.sql`.
3. Execute o script para criar o banco e suas tabelas.

## 🧠 Observações

- O campo `cpf` é `UNIQUE`, evitando duplicações.
- As tabelas estão relacionadas por **chaves estrangeiras** (`FOREIGN KEY`).
- Os tipos `ENUM` foram usados para campos como `tipo`, `status_conta`, `status_transacao`, garantindo consistência.

## 📁 Estrutura de Arquivo

