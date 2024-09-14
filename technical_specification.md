# Documentação Técnica Detalhada - ExpenseChain

## Sumário

1. [Visão Geral do Sistema](#1-visão-geral-do-sistema)
2. [Arquitetura da Aplicação](#2-arquitetura-da-aplicação)
3. [Fluxo de Operações](#3-fluxo-de-operações)
4. [Diagramas de Componentes](#4-diagramas-de-componentes)
5. [Modelos de Dados](#5-modelos-de-dados)
6. [Fluxo de Transações](#6-fluxo-de-transações)
7. [Segurança e Autenticação](#7-segurança-e-autenticação)
8. [Integração com Web2](#8-integração-com-web2)
9. [Regras de Negócio em Smart Contracts](#9-regras-de-negócio-em-smart-contracts)
10. [Processo de Contratação e Pagamento do Sistema](#10-processo-de-contratação-e-pagamento-do-sistema)
11. [Processo de Recarga de Tokens](#11-processo-de-recarga-de-tokens)
12. [Gestão do Tesouro do Projeto](#12-gestão-do-tesouro-do-projeto)
13. [Monitoramento do Saldo de Tokens](#13-monitoramento-do-saldo-de-tokens)
14. [Autenticação e Autorização](#14-autenticação-e-autorização)
15. [Processo de Aprovação Hierárquica](#15-processo-de-aprovação-hierárquica)
16. [Relatórios e Auditoria](#16-relatórios-e-auditoria)
17. [Detalhes de Deploy e Infraestrutura](#17-detalhes-de-deploy-e-infraestrutura)

---

## 1. Visão Geral do Sistema

**ExpenseChain** é uma aplicação de gestão de despesas corporativas de viagens baseada em tecnologia Web3. O sistema utiliza smart contracts e tokens nativos na blockchain para registrar, monitorar e gerenciar despesas de viagens corporativas de forma transparente, segura e imutável. A aplicação integra-se com sistemas ERP e financeiros legados (Web2) através de APIs RESTful, permitindo sincronização de dados e relatórios financeiros.

**Funcionalidades Principais:**

- **Registro de Despesas:** Funcionários podem registrar despesas relacionadas a viagens corporativas.
- **Gestão de Tokens:** Utilização de um token nativo para representar cotas de transações e controlar orçamentos.
- **Smart Contracts:** Automação de políticas de gastos e aprovação hierárquica.
- **Integração com ERP:** Sincronização de dados financeiros com sistemas legados.
- **Relatórios e Auditoria:** Geração de relatórios detalhados e manutenção de logs de auditoria imutáveis.
- **Segurança e Autenticação:** Implementação de mecanismos robustos de segurança e controle de acesso.

---

## 2. Arquitetura da Aplicação

A arquitetura da ExpenseChain é baseada em uma integração híbrida entre componentes Web3 e Web2, permitindo a interoperabilidade entre sistemas descentralizados e centralizados.

**Componentes Principais:**

1. **Aplicação Frontend:**
   - Interface de usuário baseada em web, construída com frameworks como React ou Angular.
   - Responsável por interagir com os usuários (funcionários, gerentes, administradores).

2. **Aplicação Backend:**
   - Servidor de aplicação que gerencia a lógica de negócio, autenticação e comunicação com a blockchain.
   - Implementado em Node.js, Python ou outra linguagem adequada.

3. **Blockchain Layer:**
   - Rede blockchain (por exemplo, Ethereum ou uma rede privada) onde os smart contracts e tokens residem.
   - Responsável por registrar transações de forma imutável.

4. **Smart Contracts:**
   - Código escrito em Solidity ou outra linguagem de contrato inteligente.
   - Gerencia tokens, políticas de despesas e fluxos de aprovação.

5. **Integração com ERP:**
   - APIs RESTful que permitem a comunicação entre o sistema ExpenseChain e os sistemas ERP existentes.
   - Webhooks para notificações em tempo real.

6. **Banco de Dados Off-Chain:**
   - Armazena dados que não precisam estar na blockchain, como informações de usuários e logs de atividade.
   - Utiliza bancos de dados como PostgreSQL ou MongoDB.

**Diagrama de Arquitetura:**

[Não é possível incluir imagens aqui, mas o diagrama deve mostrar a interação entre os componentes mencionados acima.]

---

## 3. Fluxo de Operações

**Fluxo Geral:**

1. **Registro de Usuário:**
   - Administrador cria contas de funcionários e define permissões.
   - Funcionários recebem credenciais de acesso.

2. **Registro de Despesa:**
   - Funcionário insere detalhes da despesa na aplicação frontend.
   - A aplicação valida os dados e interage com o smart contract.

3. **Validação e Aprovação:**
   - Smart contract verifica políticas de despesas e orçamentos.
   - Se necessário, a despesa é encaminhada para aprovação hierárquica.

4. **Registro na Blockchain:**
   - Despesa aprovada é registrada na blockchain como uma transação.
   - Tokens correspondentes são consumidos.

5. **Integração com ERP:**
   - Dados da despesa são sincronizados com o sistema ERP via API.
   - Atualização dos registros financeiros.

6. **Monitoramento e Relatórios:**
   - Administradores e gerentes acessam relatórios e dashboards.
   - Logs de auditoria são mantidos para conformidade.

**Fluxograma:**

[Um fluxograma deve representar visualmente este processo, destacando as interações entre usuário, aplicação, smart contracts e ERP.]

---

## 4. Diagramas de Componentes

**1. Módulo de Gerenciamento de Usuários:**

- **Funções:**
  - Cadastro de usuários.
  - Definição de permissões e roles.
  - Autenticação e autorização.

- **Componentes:**
  - Interface de cadastro.
  - Serviço de autenticação (OAuth 2.0, JWT).
  - Banco de dados de usuários.

**2. Módulo de Alocação de Cotas:**

- **Funções:**
  - Definição de orçamentos por departamento ou usuário.
  - Distribuição de tokens.
  - Monitoramento de consumo de cotas.

- **Componentes:**
  - Interface de configuração de orçamentos.
  - Smart contracts para controle de tokens.
  - Dashboard de monitoramento.

**3. Módulo de Integração com ERP:**

- **Funções:**
  - Sincronização de dados financeiros.
  - Exportação e importação de dados.
  - Mapeamento de campos.

- **Componentes:**
  - APIs RESTful.
  - Conectores específicos para diferentes ERPs.
  - Serviço de webhook.

**4. Módulo de Gestão de Tokens:**

- **Funções:**
  - Criação e emissão de tokens.
  - Consumo de tokens em transações.
  - Monitoramento de saldo.

- **Componentes:**
  - Smart contracts de token (ERC-20 ou similar).
  - Interface de gestão de tokens.
  - Serviço de alertas.

---

## 5. Modelos de Dados

**1. Tokens:**

- **Estrutura:**
  - `tokenId`: Identificador único do token.
  - `owner`: Endereço da carteira da empresa.
  - `balance`: Saldo de tokens disponíveis.
  - `metadata`: Informações adicionais (opcional).

**2. Transações de Despesas:**

- **Estrutura:**
  - `transactionId`: Identificador único da transação.
  - `userId`: Identificador do funcionário que registrou a despesa.
  - `amount`: Valor da despesa.
  - `category`: Categoria da despesa (passagem aérea, hospedagem, etc.).
  - `timestamp`: Data e hora do registro.
  - `status`: Estado atual (pendente, aprovado, rejeitado).
  - `approverId`: Identificador do aprovador (se aplicável).

**3. Comprovantes Fiscais:**

- **Estrutura:**
  - `receiptId`: Identificador único do comprovante.
  - `transactionId`: Associação com a transação de despesa.
  - `fileUrl`: Localização do arquivo armazenado (pode ser IPFS ou armazenamento seguro off-chain).
  - `hash`: Hash do arquivo para verificação de integridade.

---

## 6. Fluxo de Transações

**Criação e Consumo de Tokens:**

1. **Aquisição de Tokens:**
   - Empresa adquire tokens através da aplicação.
   - Smart contract emite novos tokens e os credita na carteira da empresa.

2. **Alocação de Tokens:**
   - Administrador distribui tokens para departamentos ou usuários.
   - Smart contract atualiza os saldos correspondentes.

3. **Registro de Despesa:**
   - Funcionário registra uma despesa.
   - Smart contract verifica o saldo disponível e consome os tokens correspondentes.
   - Transação é registrada na blockchain.

4. **Atualização de Saldos:**
   - Saldos de tokens são atualizados em tempo real.
   - Alertas são enviados se o saldo atingir níveis críticos.

**Fluxograma:**

[Fluxograma deve mostrar o ciclo completo desde a aquisição de tokens até o consumo em transações de despesas.]

---

## 7. Segurança e Autenticação

**Mecanismos Implementados:**

1. **Autenticação:**

   - **OAuth 2.0 / OpenID Connect:**
     - Utilizado para autenticação segura de usuários.
     - Suporta login via provedores externos, se necessário.

   - **JWT (JSON Web Tokens):**
     - Tokens de acesso e refresh tokens para sessões de usuário.
     - Incluem claims com informações de permissão e expiração.

2. **Autorização:**

   - **RBAC (Role-Based Access Control):**
     - Permissões atribuídas com base em roles (administrador, gerente, funcionário).
     - Controle de acesso a funcionalidades e dados sensíveis.

3. **Segurança da Aplicação:**

   - **HTTPS/TLS:**
     - Criptografia de tráfego entre cliente e servidor.
   - **Proteção contra CSRF e XSS:**
     - Implementação de tokens anti-CSRF e validação de inputs.

4. **Segurança na Blockchain:**

   - **Assinaturas Digitais:**
     - Todas as transações na blockchain são assinadas digitalmente.
   - **Carteiras Seguras:**
     - Uso de wallets seguras para armazenamento de chaves privadas.

5. **Armazenamento Seguro de Dados:**

   - **Hashing e Criptografia:**
     - Senhas armazenadas com hashing seguro (bcrypt).
     - Dados sensíveis criptografados no banco de dados.

---

## 8. Integração com Web2

**Comunicação via APIs RESTful:**

1. **Endpoints API:**

   - **Autenticação:**
     - `/api/auth/login`
     - `/api/auth/logout`
   - **Usuários:**
     - `/api/users`
     - `/api/users/{id}`
   - **Despesas:**
     - `/api/expenses`
     - `/api/expenses/{id}`
   - **Tokens:**
     - `/api/tokens/balance`
     - `/api/tokens/purchase`

2. **Formatos de Dados:**

   - **JSON:**
     - Todas as requisições e respostas utilizam o formato JSON.

3. **Webhooks:**

   - **Eventos Suportados:**
     - Registro de nova despesa.
     - Aprovação ou rejeição de despesa.
     - Alteração de saldo de tokens.

   - **Configuração:**
     - Empresas podem configurar URLs para receber notificações.

4. **Segurança na API:**

   - **Autenticação de API:**
     - Utilização de tokens de API seguros.
     - Limitação de taxa (rate limiting) para prevenir abuso.

---

## 9. Regras de Negócio em Smart Contracts

**Implementação de Políticas de Gastos:**

1. **Definição de Orçamentos:**

   - Smart contracts mantêm os orçamentos por categoria e usuário.
   - Verificam se a despesa está dentro do limite antes de aprovar.

2. **Fluxo de Aprovação:**

   - Despesas acima de certo valor acionam fluxo de aprovação.
   - Smart contracts gerenciam estados de aprovação (pendente, aprovado, rejeitado).

3. **Validação de Permissões:**

   - Verificam se o usuário tem permissão para registrar despesas em determinada categoria.

**Diagrama de Regras:**

[Um diagrama de atividade ou de estados pode ilustrar como as regras de negócio são aplicadas pelos smart contracts.]

---

## 10. Processo de Contratação e Pagamento do Sistema

**Fluxo de Assinatura do Serviço:**

1. **Seleção do Plano:**

   - Empresa escolhe um plano com base no número de transações mensais.

2. **Cadastro e Contrato:**

   - Preenchimento de informações da empresa.
   - Aceite dos termos de serviço e contrato via smart contract.

3. **Pagamento:**

   - Métodos suportados: Boleto, Cartão de Crédito, Transferência Bancária.
   - Integração com gateways de pagamento.

4. **Emissão de Faturamento:**

   - Faturas são geradas e enviadas automaticamente.
   - Registro de pagamento atualiza o saldo de tokens.

5. **Renovação de Licença:**

   - Notificações enviadas antes do vencimento.
   - Processo de renovação simplificado.

**Fluxograma:**

[Fluxograma detalhando cada etapa do processo de contratação e pagamento.]

---

## 11. Processo de Recarga de Tokens

**Etapas:**

1. **Solicitação de Recarga:**

   - Administrador solicita aquisição de tokens adicionais via painel.

2. **Processamento do Pagamento:**

   - Seleção do método de pagamento.
   - Integração com gateway de pagamento para processar a transação.

3. **Confirmação do Pagamento:**

   - Confirmação automática ou manual do recebimento.

4. **Emissão de Tokens:**

   - Smart contract emite tokens correspondentes.
   - Tokens são creditados na carteira da empresa.

5. **Notificações:**

   - Alertas enviados para confirmar a recarga.

**Fluxograma:**

[Fluxograma mostrando o processo desde a solicitação até a distribuição dos tokens.]

---

## 12. Gestão do Tesouro do Projeto

**Gestão de Reserva de Tokens:**

1. **Emissão Controlada:**

   - Tokens são emitidos apenas mediante pagamento confirmado.
   - Previne inflação ou emissão descontrolada.

2. **Reserva de Liquidez:**

   - Sistema mantém uma reserva de tokens para garantir operações contínuas.
   - Políticas definem limites mínimos de reserva.

3. **Redistribuição de Tokens:**

   - Tokens não utilizados podem ser reabsorvidos pelo sistema após certo período (se aplicável).

4. **Políticas de Tesouro:**

   - Transparência nas operações do tesouro.
   - Relatórios disponíveis para empresas sobre o estado do tesouro.

---

## 13. Monitoramento do Saldo de Tokens

**Mecanismos de Monitoramento:**

1. **Atualização em Tempo Real:**

   - Saldos são atualizados imediatamente após cada transação.

2. **Dashboards:**

   - Visualização gráfica do consumo de tokens.
   - Projeções de uso futuro com base em históricos.

3. **Alertas de Saldo Baixo:**

   - Notificações enviadas quando o saldo atinge níveis pré-definidos.
   - Possibilidade de configurar múltiplos níveis de alerta.

4. **Relatórios Periódicos:**

   - Envio de relatórios semanais ou mensais com resumo do uso de tokens.

---

## 14. Autenticação e Autorização

**Detalhamento Técnico:**

1. **Autenticação:**

   - **OAuth 2.0:**
     - Fluxo de autorização implementado para segurança.
     - Suporte a múltiplos grant types (authorization code, client credentials).

   - **JWT Tokens:**
     - Tokens incluem informações como `user_id`, `roles`, `exp` (tempo de expiração).
     - Armazenamento seguro no cliente (HttpOnly cookies ou armazenamento seguro).

2. **Autorização:**

   - **RBAC:**
     - Definição de roles como `Admin`, `Manager`, `Employee`.
     - Permissões associadas a cada role.
     - Middleware no backend verifica permissões em cada endpoint.

   - **ABAC (Attribute-Based Access Control):**
     - Possibilidade de implementar controles mais granulares baseados em atributos.

3. **Fluxo de Login:**

   - Usuário insere credenciais.
   - Backend valida e emite JWT.
   - Token é utilizado para autenticar requisições subsequentes.

4. **Sessões e Segurança:**

   - Tokens têm tempo de expiração curto.
   - Refresh tokens utilizados para renovar a sessão.

---

## 15. Processo de Aprovação Hierárquica

**Fluxo de Aprovação:**

1. **Registro de Despesa:**

   - Funcionário registra uma despesa que excede um limite ou requer aprovação.

2. **Encaminhamento para Aprovador:**

   - Smart contract ou lógica de negócio identifica o aprovador responsável (gerente imediato, por exemplo).

3. **Notificação de Aprovação:**

   - Aprovador recebe notificação via e-mail ou dentro da aplicação.

4. **Ação do Aprovador:**

   - Aprovador revisa os detalhes e decide aprovar ou rejeitar.

5. **Atualização do Status:**

   - Decisão é registrada na blockchain.
   - Se aprovada, tokens são consumidos e a despesa é finalizada.
   - Se rejeitada, o funcionário é notificado e nenhuma alteração de tokens ocorre.

**Regras de Negócio:**

- Limites de aprovação podem ser definidos por valor, categoria ou usuário.
- Fluxo de aprovação pode ser configurado para múltiplos níveis, se necessário.

---

## 16. Relatórios e Auditoria

**Módulo de Relatórios:**

1. **Tipos de Relatórios:**

   - Gastos por categoria.
   - Gastos por departamento ou usuário.
   - Consumo de tokens ao longo do tempo.
   - Despesas pendentes de aprovação.

2. **Customização:**

   - Filtros por data, categoria, valor, etc.
   - Possibilidade de exportar em formatos como PDF, Excel.

3. **Dashboards Interativos:**

   - Gráficos e visualizações interativas.
   - Indicadores-chave de desempenho (KPIs).

**Logs de Auditoria:**

1. **Registro Imutável:**

   - Todas as ações relevantes são registradas na blockchain.
   - Inclui registros de login, alterações de configuração, transações.

2. **Acesso aos Logs:**

   - Administradores podem consultar logs através da aplicação.
   - Logs incluem timestamp, usuário, ação realizada.

3. **Conformidade:**

   - Auxilia no cumprimento de normas regulatórias.
   - Fornece trilha de auditoria completa.

---

## 17. Detalhes de Deploy e Infraestrutura

**Ambiente de Deploy:**

1. **Blockchain:**

   - **Rede:** Pode ser uma rede pública (como Ethereum) ou uma rede privada.
   - **Nós:** Configuração de nós próprios para maior controle e desempenho.

2. **Servidores de Aplicação:**

   - **Backend:** Hospedado em servidores seguros, com balanceamento de carga.
   - **Frontend:** Servido através de CDNs para melhor desempenho.

3. **Banco de Dados:**

   - **Tipo:** Bancos de dados relacionais (PostgreSQL) ou NoSQL (MongoDB) conforme necessidade.
   - **Replicação e Backup:** Implementação de estratégias de alta disponibilidade e recuperação de desastres.

4. **Infraestrutura como Código:**

   - Uso de ferramentas como Terraform ou Ansible para gerenciar a infraestrutura.

**Escalabilidade:**

1. **Aplicação:**

   - Arquitetura de microserviços para facilitar o escalonamento horizontal.
   - Contêineres (Docker) e orquestração (Kubernetes) para gestão eficiente.

2. **Blockchain:**

   - Uso de soluções de camada 2 (Layer 2) para aumentar a capacidade de transações e reduzir custos.

**Segurança da Infraestrutura:**

1. **Firewall e Segurança de Rede:**

   - Implementação de firewalls, regras de segurança e segmentação de rede.

2. **Monitoramento e Logging:**

   - Ferramentas de monitoramento (Prometheus, Grafana) para acompanhar o desempenho.
   - Sistemas de detecção de intrusão (IDS) e prevenção (IPS).

**Processo de Deploy:**

1. **Integração Contínua / Entrega Contínua (CI/CD):**

   - Pipelines automatizados para build, testes e deploy.

2. **Ambientes Separados:**

   - Ambientes de desenvolvimento, teste e produção separados.

3. **Testes Automatizados:**

   - Testes unitários, de integração e de segurança automatizados antes do deploy.

---

## Conclusão

Esta documentação técnica detalhada do **ExpenseChain** fornece uma visão abrangente de todos os aspectos críticos do sistema, desde a arquitetura e fluxos de operações até detalhes específicos de segurança, integração e deploy. O objetivo é servir como um guia completo para desenvolvedores, arquitetos de sistemas e equipes de operação para entender, implementar e manter o sistema de forma eficaz.

