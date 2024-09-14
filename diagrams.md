# Diagramas em Mermaid

Conforme solicitado, abaixo estão todos os diagramas mencionados na documentação técnica, escritos em sintaxe Mermaid para facilitar a visualização e entendimento técnico do sistema **ExpenseChain**.

## Sumário dos Diagramas

1. [Diagrama de Arquitetura da Aplicação](#1-diagrama-de-arquitetura-da-aplicação)
2. [Fluxograma do Fluxo de Operações](#2-fluxograma-do-fluxo-de-operações)
3. [Diagramas de Componentes](#3-diagramas-de-componentes)
   - 3.1. [Módulo de Gerenciamento de Usuários](#31-módulo-de-gerenciamento-de-usuários)
   - 3.2. [Módulo de Alocação de Cotas](#32-módulo-de-alocação-de-cotas)
   - 3.3. [Módulo de Integração com ERP](#33-módulo-de-integração-com-erp)
   - 3.4. [Módulo de Gestão de Tokens](#34-módulo-de-gestão-de-tokens)
4. [Fluxograma do Fluxo de Transações](#4-fluxograma-do-fluxo-de-transações)
5. [Diagrama das Regras de Negócio em Smart Contracts](#5-diagrama-das-regras-de-negócio-em-smart-contracts)
6. [Fluxograma do Processo de Contratação e Pagamento do Sistema](#6-fluxograma-do-processo-de-contratação-e-pagamento-do-sistema)
7. [Fluxograma do Processo de Recarga de Tokens](#7-fluxograma-do-processo-de-recarga-de-tokens)
8. [Fluxograma do Processo de Aprovação Hierárquica](#8-fluxograma-do-processo-de-aprovação-hierárquica)

---

## 1. Diagrama de Arquitetura da Aplicação

```mermaid
flowchart TD
    subgraph Frontend
        A[Aplicação Web]
    end

    subgraph Backend
        B[Servidor de Aplicação]
        B --> C[APIs RESTful]
        B --> D[Autenticação e Autorização]
    end

    subgraph Blockchain
        E[Smart Contracts]
        F[Token Nativo]
    end

    subgraph Banco de Dados Off-Chain
        G[(Banco de Dados)]
    end

    subgraph Sistemas ERP
        H[Sistema ERP]
    end

    A -- Solicitações --> B
    B -- Interações --> E
    E -- Registros --> F
    B -- Consulta e Armazenamento --> G
    B -- Integração --> H
```

---

## 2. Fluxograma do Fluxo de Operações

```mermaid
flowchart TD
    Start([Início]) --> |Login| A[Funcionário]
    A --> B[Registrar Despesa]
    B --> C{Despesa dentro do orçamento?}
    C -- Sim --> D[Registrar na Blockchain]
    D --> E[Atualizar Saldo de Tokens]
    E --> F[Sincronizar com ERP]
    F --> G[Despesa Registrada]
    C -- Não --> H{Requer Aprovação?}
    H -- Sim --> I[Encaminhar para Aprovador]
    I --> J[Aprovador Analisa]
    J --> K{Aprovar Despesa?}
    K -- Sim --> D
    K -- Não --> L[Notificar Rejeição]
    L --> M[Fim]
    H -- Não --> L
    G --> M([Fim])
```

---

## 3. Diagramas de Componentes

### 3.1. Módulo de Gerenciamento de Usuários

```mermaid
classDiagram
    class GerenciamentoDeUsuarios {
        +cadastrarUsuario()
        +editarUsuario()
        +excluirUsuario()
        +atribuirPermissoes()
        +autenticarUsuario()
    }
    class Usuario {
        -id
        -nome
        -email
        -senha
        -permissoes
    }
    class Autenticacao {
        +login()
        +logout()
        +gerarToken()
    }
    GerenciamentoDeUsuarios --> Usuario
    GerenciamentoDeUsuarios --> Autenticacao
```

### 3.2. Módulo de Alocação de Cotas

```mermaid
classDiagram
    class AlocacaoDeCotas {
        +definirOrcamentos()
        +distribuirTokens()
        +monitorarConsumo()
    }
    class Orcamento {
        -departamento
        -categoriaDespesa
        -valorAlocado
    }
    class Token {
        -saldo
        -historicoTransacoes
    }
    AlocacaoDeCotas --> Orcamento
    AlocacaoDeCotas --> Token
```

### 3.3. Módulo de Integração com ERP

```mermaid
classDiagram
    class IntegracaoERP {
        +sincronizarDados()
        +exportarDados()
        +importarDados()
    }
    class API {
        +endpoints
        +autenticacaoAPI
    }
    class Webhook {
        +configurarWebhook()
        +receberNotificacoes()
    }
    IntegracaoERP --> API
    IntegracaoERP --> Webhook
```

### 3.4. Módulo de Gestão de Tokens

```mermaid
classDiagram
    class GestaoDeTokens {
        +emitirTokens()
        +consumirTokens()
        +monitorarSaldo()
    }
    class SmartContractToken {
        +transferir()
        +consultarSaldo()
        +registrarTransacao()
    }
    GestaoDeTokens --> SmartContractToken
```

---

## 4. Fluxograma do Fluxo de Transações

```mermaid
flowchart TD
    Start([Início]) --> A[Empresa Adquire Tokens]
    A --> B[Tokens Emitidos pelo Smart Contract]
    B --> C[Tokens Creditados na Carteira da Empresa]
    C --> D[Administrador Aloca Tokens para Usuários/Departamentos]
    D --> E[Funcionário Registra Despesa]
    E --> F{Saldo de Tokens Suficiente?}
    F -- Sim --> G[Smart Contract Consome Tokens]
    G --> H[Despesa Registrada na Blockchain]
    H --> I[Atualizar Saldos]
    I --> J([Fim])
    F -- Não --> K[Notificar Saldo Insuficiente]
    K --> J
```

---

## 5. Diagrama das Regras de Negócio em Smart Contracts

```mermaid
stateDiagram-v2
    [*] --> VerificarPermissoes
    VerificarPermissoes --> VerificarOrcamento
    VerificarOrcamento --> ValidarDespesa
    ValidarDespesa --> AprovacaoNecessaria
    AprovacaoNecessaria --> |Sim| EncaminharParaAprovacao
    AprovacaoNecessaria --> |Não| RegistrarDespesa
    EncaminharParaAprovacao --> AguardandoAprovacao
    AguardandoAprovacao --> Aprovado
    Aprovado --> RegistrarDespesa
    AguardandoAprovacao --> Rejeitado
    Rejeitado --> NotificarRejeicao
    RegistrarDespesa --> AtualizarSaldos
    AtualizarSaldos --> [*]
```

---

## 6. Fluxograma do Processo de Contratação e Pagamento do Sistema

```mermaid
flowchart TD
    Start([Início]) --> A[Empresa Seleciona Plano]
    A --> B[Empresa Preenche Cadastro]
    B --> C[Aceita Termos de Serviço]
    C --> D[Seleciona Método de Pagamento]
    D --> E{Pagamento Aprovado?}
    E -- Sim --> F[Contrato Registrado via Smart Contract]
    F --> G[Tokens Creditados]
    G --> H[Conta Ativada]
    H --> I([Fim])
    E -- Não --> J[Notificar Falha no Pagamento]
    J --> I
```

---

## 7. Fluxograma do Processo de Recarga de Tokens

```mermaid
flowchart TD
    Start([Início]) --> A[Administrador Solicita Recarga de Tokens]
    A --> B[Seleciona Quantidade de Tokens]
    B --> C[Processa Pagamento]
    C --> D{Pagamento Confirmado?}
    D -- Sim --> E[Smart Contract Emite Tokens]
    E --> F[Tokens Creditados na Carteira da Empresa]
    F --> G[Notificar Recarga Bem-Sucedida]
    G --> H([Fim])
    D -- Não --> I[Notificar Falha no Pagamento]
    I --> H
```

---

## 8. Fluxograma do Processo de Aprovação Hierárquica

```mermaid
flowchart TD
    Start([Início]) --> A[Funcionário Registra Despesa]
    A --> B{Despesa Exige Aprovação?}
    B -- Sim --> C[Encaminhar para Aprovador]
    C --> D[Aprovador Recebe Notificação]
    D --> E[Aprovador Analisa Despesa]
    E --> F{Aprovar Despesa?}
    F -- Sim --> G[Despesa Aprovada]
    G --> H[Registrar na Blockchain]
    H --> I[Atualizar Saldos]
    I --> J([Fim])
    F -- Não --> K[Despesa Rejeitada]
    K --> L[Notificar Funcionário]
    L --> J
    B -- Não --> M[Registrar na Blockchain]
    M --> I
```
