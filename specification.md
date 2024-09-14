# Especificação de Negócios para o Sistema de Gestão de Despesas Corporativas de Viagens na Web3

## Sumário

1. **Introdução**
2. **Visão Geral do Sistema**
3. **Componentes Principais**
   - 3.1. **Tecnologia Web3**
   - 3.2. **Token Nativo**
   - 3.3. **Smart Contracts**
4. **Gerenciamento de Usuários e Hierarquia**
   - 4.1. **Processo de Criação de Novos Usuários**
   - 4.2. **Definição de Permissões e Limites**
5. **Gestão de Tokens e Orçamentos**
   - 5.1. **Distribuição e Alocação de Tokens**
   - 5.2. **Processo de Aquisição de Cotas Adicionais de Transações**
   - 5.3. **Liquidez Interna dos Tokens**
6. **Processo de Registro de Despesas**
   - 6.1. **Fluxo de Trabalho para Funcionários**
   - 6.2. **Aprovação e Monitoramento de Despesas**
7. **Integração com Sistemas Web2**
   - 7.1. **Requisitos de Integração**
   - 7.2. **APIs e Sincronização de Dados**
8. **Relatórios e Análises**
9. **Segurança e Conformidade**
10. **Conclusão**

---

## 1. Introdução

Este documento detalha a especificação de negócios para um sistema de gestão de despesas corporativas de viagens utilizando tecnologia Web3. O objetivo é criar uma plataforma segura, transparente e eficiente para o registro e gerenciamento de despesas relacionadas a viagens corporativas, alavancando a blockchain para registrar transações de forma imutável.

## 2. Visão Geral do Sistema

O sistema permitirá que empresas gerenciem despesas de viagens corporativas, como passagens aéreas, hospedagem e aluguel de carros, através de um token nativo e smart contracts na blockchain. A plataforma integrará com sistemas Web2 existentes, como ERPs e sistemas financeiros, para sincronização de dados e relatórios financeiros.

## 3. Componentes Principais

### 3.1. Tecnologia Web3

- **Blockchain**: Utilizada para registrar todas as transações de despesas de forma imutável.
- **Token Nativo**: Servirá como unidade de registro para as despesas.
- **Smart Contracts**: Automatizarão processos de registro, aprovação e monitoramento de despesas.

### 3.2. Token Nativo

- **Função**: Representa a cota de transações disponíveis para a empresa.
- **Uso Interno**: Não terá valor monetário fora do sistema e não será convertido em moeda fiduciária.
- **Gestão**: O saldo de tokens será gerenciado pela empresa e alocado para diferentes departamentos e usuários.

### 3.3. Smart Contracts

- **Registro de Despesas**: Cada lançamento de despesa aciona um smart contract que registra a transação na blockchain.
- **Controle de Orçamento**: Smart contracts monitoram e aplicam limites de orçamento definidos pela empresa.
- **Permissões**: Gerenciam a hierarquia de usuários e suas permissões dentro do sistema.

## 4. Gerenciamento de Usuários e Hierarquia

### 4.1. Processo de Criação de Novos Usuários

- **Cadastro Inicial**: Administradores podem adicionar novos usuários através de um painel de controle.
- **Definição de Perfil**:
  - **Funcionário**: Pode lançar despesas dentro dos limites estabelecidos.
  - **Gerente**: Pode aprovar despesas e tem limites de gastos maiores.
  - **Administrador**: Controle total sobre o sistema, incluindo gestão de tokens e usuários.

### 4.2. Definição de Permissões e Limites

- **Categorias de Despesa**: Passagens aéreas, hospedagem, aluguel de carro, etc.
- **Permissões Personalizadas**: Definidas por categoria e por usuário ou departamento.
- **Limites Orçamentários**: Estabelecidos para cada usuário ou grupo, controlados via smart contracts.

*Resposta à Pergunta 1*: O processo de criação de um novo usuário envolve o cadastro pelo administrador, que define o perfil do usuário (funcionário, gerente, etc.) e atribui permissões específicas para categorias de despesas. Isso permite que as empresas controlem quem pode lançar despesas em cada categoria, com limites orçamentários definidos.

## 5. Gestão de Tokens e Orçamentos

### 5.1. Distribuição e Alocação de Tokens

- **Alocação Inicial**: A empresa adquire uma cota de tokens que representa o número de transações disponíveis.
- **Distribuição**: Tokens são distribuídos para departamentos ou usuários com base nos orçamentos estabelecidos.
- **Monitoramento**: O consumo de tokens é monitorado em tempo real conforme as despesas são registradas.

### 5.2. Processo de Aquisição de Cotas Adicionais de Transações

- **Solicitação de Cotas**: A empresa pode adquirir cotas adicionais diretamente pelo sistema.
- **Atualização de Saldo**: Os tokens adicionais são creditados no saldo da empresa após a confirmação do pagamento.
- **Notificações**: Alertas são enviados quando o saldo de tokens está baixo.

*Resposta à Pergunta 2*: A liquidez interna dos tokens é garantida pela gestão centralizada do saldo de tokens pela empresa. Como os tokens não têm valor fora do sistema, eles servem exclusivamente para registrar despesas. A empresa pode adquirir cotas adicionais de transações quando necessário, mantendo o fluxo contínuo de operações.

### 5.3. Liquidez Interna dos Tokens

- **Uso Exclusivo Interno**: Tokens não são negociáveis externamente.
- **Controle de Fluxo**: Smart contracts asseguram que os tokens são usados apenas para transações de despesas.
- **Saldo Centralizado**: Facilita a gestão e a previsão de necessidades futuras de tokens.

## 6. Processo de Registro de Despesas

### 6.1. Fluxo de Trabalho para Funcionários

1. **Lançamento de Despesa**: O funcionário insere os detalhes da despesa no sistema.
2. **Validação Automática**: O smart contract verifica se a despesa está dentro dos limites e permissões.
3. **Registro na Blockchain**: Se aprovado, a despesa é registrada e o saldo de tokens é ajustado.
4. **Notificações**: O gerente recebe notificações para aprovação, se necessário.

### 6.2. Aprovação e Monitoramento de Despesas

- **Aprovação Hierárquica**: Despesas acima de certos valores ou fora das políticas requerem aprovação de um gerente.
- **Monitoramento em Tempo Real**: Painéis de controle exibem o consumo de tokens e orçamentos.
- **Relatórios Personalizados**: Possibilidade de gerar relatórios por usuário, departamento ou categoria.

*Resposta à Pergunta 3*: O saldo de tokens para cada funcionário é gerenciado pelo sistema com base nas alocações feitas pelo administrador. A hierarquia permite que diferentes níveis de usuários tenham limites de gastos distintos, controlados por smart contracts que aplicam as regras de negócio definidas.

## 7. Integração com Sistemas Web2

### 7.1. Requisitos de Integração

- **Compatibilidade**: O sistema deve ser compatível com os principais ERPs e sistemas financeiros.
- **APIs RESTful**: Fornecer APIs para comunicação bidirecional.
- **Segurança**: Autenticação e autorização seguras para acesso aos dados.

### 7.2. APIs e Sincronização de Dados

- **Exportação de Dados**: Possibilidade de exportar relatórios em formatos como CSV e Excel.
- **Webhooks**: Para notificar sistemas externos sobre eventos, como novas despesas registradas.
- **Sincronização Automática**: Dados financeiros são sincronizados em tempo real ou em intervalos definidos.

*Resposta à Pergunta 4*: A integração com sistemas Web2 é realizada através de APIs RESTful e webhooks, permitindo a sincronização eficiente de dados entre a blockchain e os sistemas corporativos existentes. Requisitos principais incluem segurança na autenticação, compatibilidade com formatos de dados comuns e capacidade de comunicação em tempo real.

## 8. Relatórios e Análises

- **Relatórios Personalizáveis**: Por período, categoria, usuário, departamento, etc.
- **Análises de Tendências**: Identificação de padrões de gastos.
- **Exportação**: Relatórios podem ser exportados para integração com outros sistemas ou para análise externa.

## 9. Segurança e Conformidade

- **Imutabilidade dos Registros**: Garantida pela blockchain.
- **Controle de Acesso**: Baseado em permissões definidas na hierarquia de usuários.
- **Conformidade Legal**: Adequação às leis e regulamentos aplicáveis em relação a registros financeiros e proteção de dados.

## 10. Conclusão

O sistema proposto oferece uma solução inovadora para a gestão de despesas corporativas de viagens, combinando a transparência e segurança da tecnologia Web3 com a praticidade de integração com sistemas corporativos existentes. Através de um token nativo e smart contracts, as empresas podem controlar orçamentos, gerenciar permissões e monitorar gastos de forma eficiente e segura.

---

# Especificação Detalhada das Jornadas de Usuário

## Sumário

1. **Introdução**
2. **Jornadas de Usuário**
   - 2.1. **Compra da Licença e Gestão das Cotas de Transação**
     - 2.1.1. **Empresa Cliente**
   - 2.2. **Jornadas do Usuário Administrador**
   - 2.3. **Jornadas do Usuário Backoffice**
3. **Integração com Sistemas ERP**
   - 3.1. **Processo de Integração**
   - 3.2. **Fluxo de Dados Entre Sistemas**
4. **Conclusão**

---

## 1. Introdução

Este documento detalha todas as jornadas de usuário relacionadas ao sistema de gestão de despesas corporativas de viagens na Web3. O foco está nas interações desde a compra da licença, gestão das cotas de transação, até a integração com sistemas ERP, incluindo as jornadas específicas dos usuários administradores e backoffice.

## 2. Jornadas de Usuário

### 2.1. Compra da Licença e Gestão das Cotas de Transação

#### 2.1.1. Empresa Cliente

**Persona**: Representante da empresa responsável pela aquisição e gestão do sistema (por exemplo, Diretor Financeiro ou Gerente de TI).

**Objetivo**: Adquirir uma licença do sistema, gerenciar cotas de transação e configurar a plataforma para uso interno.

**Passos da Jornada**:

1. **Descoberta e Avaliação**
   - **Acesso ao Site do Fornecedor**: O representante acessa o site oficial do sistema.
   - **Consulta de Planos e Preços**: Visualiza os diferentes planos disponíveis, cada um com um limite de transações mensais.
   - **Solicitação de Demonstração**: Opcionalmente, solicita uma demonstração ou consulta com um representante de vendas.

2. **Registro e Criação de Conta**
   - **Formulário de Cadastro**: Preenche um formulário com as informações da empresa (nome, CNPJ, endereço, dados de contato).
   - **Aceitação dos Termos**: Lê e aceita os termos de serviço e a política de privacidade.
   - **Verificação de Conta**: Recebe um e-mail de confirmação e ativa a conta.

3. **Seleção do Plano e Compra da Licença**
   - **Escolha do Plano**: Seleciona o plano que melhor atende às necessidades da empresa com base no número de transações mensais.
   - **Personalização**: Adiciona cotas adicionais de transação, se necessário.
   - **Resumo do Pedido**: Revisa os detalhes da compra, incluindo custos e limites.
   - **Informação de Pagamento**: Fornece os dados para faturamento (boleto bancário, cartão de crédito, transferência, etc.).
   - **Confirmação de Compra**: Recebe a confirmação do pedido e a nota fiscal eletrônica.

4. **Configuração Inicial do Sistema**
   - **Acesso ao Painel Administrativo**: Faz login no sistema com credenciais de administrador.
   - **Configuração de Preferências**: Define as configurações iniciais, como moeda padrão, idiomas, políticas de despesas.
   - **Importação de Dados**: Opcionalmente, importa dados existentes de usuários e departamentos.

5. **Gestão das Cotas de Transação**
   - **Visualização do Saldo de Transações**: Verifica o número de transações disponíveis no mês.
   - **Configuração de Alertas**: Define notificações para quando o saldo de transações estiver baixo.
   - **Aquisição de Cotas Adicionais**
     - **Identificação da Necessidade**: O sistema alerta que o saldo de transações está próximo do limite.
     - **Processo de Compra**: Adquire cotas adicionais através do painel, seguindo um processo similar ao da compra inicial.
     - **Atualização do Saldo**: As cotas adicionais são automaticamente adicionadas ao saldo disponível.

6. **Renovação da Licença**
   - **Notificação de Vencimento**: Recebe alertas sobre a proximidade da data de renovação.
   - **Processo de Renovação**: Revisa e atualiza o plano conforme necessário e confirma o pagamento.

---

### 2.2. Jornadas do Usuário Administrador

**Persona**: Usuário com privilégios administrativos, responsável pela gestão do sistema dentro da empresa.

**Objetivo**: Configurar o sistema, gerenciar usuários, definir orçamentos e monitorar despesas.

**Passos da Jornada**:

1. **Login no Sistema**
   - **Autenticação**: Insere credenciais de acesso e realiza autenticação de dois fatores, se habilitado.
   - **Dashboard Administrativo**: Acessa a visão geral das atividades e status do sistema.

2. **Gestão de Usuários**
   - **Cadastro de Novos Usuários**
     - **Adicionar Usuário**: Acessa a seção de usuários e clica em "Adicionar Novo Usuário".
     - **Inserção de Dados**: Preenche informações como nome, e-mail, departamento e cargo.
     - **Definição de Permissões**: Seleciona o perfil do usuário (funcionário, gerente, etc.) e atribui permissões específicas.
     - **Envio de Convite**: O sistema envia um e-mail de convite ao novo usuário para configurar sua senha.
   - **Edição de Usuários Existentes**
     - **Busca de Usuário**: Localiza o usuário na lista.
     - **Atualização de Informações**: Altera dados pessoais, permissões ou status ativo/inativo.
   - **Desativação de Usuários**
     - **Desativar Conta**: Remove o acesso de usuários que não fazem mais parte da empresa.

3. **Definição de Orçamentos e Limites**
   - **Configuração de Orçamentos por Departamento**
     - **Seleção de Departamento**: Escolhe o departamento na lista.
     - **Definição de Orçamento**: Estabelece o valor total de tokens alocados para o período.
     - **Distribuição por Categoria**: Aloca tokens para categorias específicas (passagens aéreas, hospedagem, etc.).
   - **Configuração de Limites por Usuário**
     - **Seleção de Usuário**: Acessa o perfil do usuário.
     - **Definição de Limites**: Estabelece limites de gastos e categorias permitidas para o usuário.

4. **Monitoramento de Despesas e Saldos**
   - **Visualização de Relatórios**
     - **Relatórios em Tempo Real**: Acessa painéis com informações sobre gastos, saldos de tokens e transações.
     - **Filtragem de Dados**: Filtra por período, categoria, departamento ou usuário.
   - **Alertas e Notificações**
     - **Configuração de Alertas**: Define notificações para gastos excessivos ou comportamentos anômalos.
     - **Recebimento de Notificações**: Recebe alertas sobre limites atingidos ou transações suspeitas.

5. **Aprovação de Despesas**
   - **Fluxo de Aprovação**
     - **Revisão de Solicitações**: Visualiza despesas que requerem aprovação.
     - **Análise de Detalhes**: Verifica informações da despesa e comprovantes anexados.
     - **Decisão**: Aprova ou rejeita a despesa, adicionando comentários se necessário.
   - **Delegação de Aprovação**
     - **Configuração de Aprovadores**: Define quais gerentes podem aprovar despesas de determinados usuários ou departamentos.

6. **Gestão de Tokens**
   - **Monitoramento do Saldo Global**: Verifica o total de tokens disponíveis para a empresa.
   - **Redistribuição de Tokens**
     - **Ajuste de Alocações**: Redistribui tokens entre departamentos ou usuários conforme necessário.
   - **Aquisição de Tokens Adicionais**
     - **Solicitação de Compra**: Inicia o processo de aquisição de cotas adicionais.
     - **Autorização**: Segue os procedimentos internos da empresa para aprovação de despesas com aquisição de tokens.

7. **Configurações do Sistema**
   - **Políticas de Despesas**
     - **Definição de Políticas**: Estabelece regras como categorias permitidas, valores máximos por despesa, requisitos de comprovantes.
   - **Integrações**
     - **Configuração de Integrações**: Gerencia as conexões com sistemas ERP e outros aplicativos.
     - **Testes de Conectividade**: Verifica se a integração está funcionando corretamente.

8. **Suporte e Treinamento**
   - **Acesso a Recursos de Ajuda**: Consulta documentação, tutoriais e FAQs.
   - **Contato com Suporte**: Abre tickets ou conversa com o suporte técnico para resolver questões.

---

### 2.3. Jornadas do Usuário Backoffice

**Persona**: Equipe interna responsável por tarefas administrativas e de suporte, como o departamento financeiro ou de contabilidade.

**Objetivo**: Monitorar transações, conciliar despesas, gerar relatórios e assegurar a conformidade com políticas internas e regulatórias.

**Passos da Jornada**:

1. **Login no Sistema**
   - **Autenticação Segura**: Acessa o sistema com credenciais fornecidas pelo administrador.

2. **Monitoramento de Transações**
   - **Visualização de Transações Recentes**: Acessa a lista de despesas lançadas recentemente.
   - **Detalhamento de Despesas**: Visualiza detalhes como data, categoria, valor, usuário e comprovantes.
   - **Verificação de Conformidade**: Confirma se as despesas estão de acordo com as políticas da empresa.

3. **Conciliação de Despesas**
   - **Exportação de Dados**
     - **Exportar para ERP**: Utiliza a funcionalidade de exportação para transferir dados para o sistema ERP.
     - **Formatos Compatíveis**: Escolhe entre CSV, Excel ou integrações diretas via API.
   - **Análise de Discrepâncias**
     - **Identificação de Inconsistências**: Compara dados entre o sistema e o ERP para identificar divergências.
     - **Ajustes Necessários**: Corrige informações incorretas ou solicita esclarecimentos.

4. **Geração de Relatórios Financeiros**
   - **Relatórios Personalizados**
     - **Criação de Relatórios**: Seleciona parâmetros para gerar relatórios específicos.
     - **Agendamento de Relatórios**: Programa relatórios periódicos para serem enviados automaticamente.
   - **Análise de Tendências**
     - **Identificação de Padrões**: Analisa dados para identificar tendências de gastos.
     - **Recomendações**: Fornece insights para otimização de custos.

5. **Gestão de Reembolsos**
   - **Processamento de Reembolsos**
     - **Verificação de Pedidos**: Analisa solicitações de reembolso submetidas pelos funcionários.
     - **Validação de Comprovantes**: Confirma a autenticidade e validade dos documentos anexados.
     - **Aprovação e Pagamento**: Autoriza o reembolso e encaminha para pagamento, se aplicável.

6. **Auditoria Interna**
   - **Rastreamento de Atividades**
     - **Logs de Sistema**: Acessa registros de atividades para fins de auditoria.
     - **Compliance**: Verifica aderência a regulamentos internos e externos.
   - **Relatórios de Auditoria**
     - **Preparação de Documentação**: Gera relatórios para auditorias internas ou externas.
     - **Colaboração com Auditores**: Fornece informações e esclarecimentos quando necessário.

7. **Suporte a Usuários**
   - **Assistência a Funcionários**
     - **Resolução de Dúvidas**: Responde a perguntas sobre o processo de lançamento de despesas.
     - **Treinamento**: Oferece orientações sobre o uso correto do sistema.
   - **Comunicação com Administradores**
     - **Relato de Problemas**: Informa aos administradores sobre quaisquer questões sistêmicas ou de compliance.
     - **Sugestões de Melhoria**: Propõe melhorias baseadas no feedback dos usuários.

8. **Integração com Sistemas ERP**
   - **Configuração de Integrações**
     - **Teste de Conexões**: Garante que a integração com o ERP está funcionando corretamente.
     - **Mapeamento de Campos**: Assegura que os dados são transferidos para os campos corretos no ERP.
   - **Monitoramento de Sincronizações**
     - **Verificação de Logs**: Monitora logs de integração para identificar e resolver erros.
     - **Atualizações de Sistema**: Coordena com TI para aplicar atualizações necessárias.

---

## 3. Integração com Sistemas ERP

### 3.1. Processo de Integração

**Objetivo**: Sincronizar dados financeiros entre o sistema de gestão de despesas e o ERP da empresa para garantir consistência e eficiência nos processos contábeis.

**Passos da Jornada**:

1. **Configuração Inicial**
   - **Seleção do ERP**: Identifica o sistema ERP utilizado pela empresa.
   - **Credenciais de Acesso**: Insere as credenciais necessárias para estabelecer a conexão segura.
   - **Mapeamento de Dados**: Define como os dados serão correspondidos entre os sistemas (por exemplo, categorias de despesas, centros de custo).

2. **Testes de Conectividade**
   - **Teste de Sincronização**: Realiza testes com dados fictícios para garantir que a integração funciona corretamente.
   - **Validação de Dados**: Verifica se os dados são transferidos com precisão e integridade.

3. **Sincronização de Dados**
   - **Agendamento de Sincronizações**
     - **Em Tempo Real**: Configura para que as transações sejam sincronizadas imediatamente.
     - **Periódico**: Define intervalos específicos (diário, semanal).
   - **Tipos de Dados Sincronizados**
     - **Despesas**: Valores, categorias, datas, usuários.
     - **Orçamentos**: Limites estabelecidos e saldos disponíveis.
     - **Usuários e Departamentos**: Informações organizacionais relevantes.

4. **Monitoramento e Manutenção**
   - **Logs de Sincronização**: Acessa registros para monitorar o status das transferências de dados.
   - **Resolução de Erros**: Identifica e corrige problemas de integração.
   - **Atualizações de Sistema**: Mantém ambos os sistemas atualizados para garantir compatibilidade.

### 3.2. Fluxo de Dados Entre Sistemas

**Fluxo de Informações**:

- **Do Sistema de Despesas para o ERP**
  - **Transações de Despesas**: Cada despesa registrada é enviada para o ERP para fins contábeis.
  - **Atualização de Orçamentos**: Informações sobre o consumo de orçamentos e saldos remanescentes.
  - **Dados de Usuários**: Atualizações sobre novos usuários ou alterações em permissões.

- **Do ERP para o Sistema de Despesas**
  - **Planos de Contas**: Importação de planos de contas ou categorias financeiras.
  - **Centros de Custo**: Sincronização de estruturas organizacionais para alocação correta de despesas.
  - **Políticas Financeiras**: Importação de políticas ou regras que impactam a gestão de despesas.

**Benefícios da Integração**:

- **Eliminação de Duplicidade de Dados**: Evita a necessidade de inserção manual em ambos os sistemas.
- **Maior Precisão**: Reduz erros humanos e inconsistências.
- **Eficiência Operacional**: Acelera processos financeiros e contábeis.
- **Visibilidade Financeira**: Fornece uma visão consolidada das finanças da empresa.

---

## 4. Conclusão

As jornadas de usuário detalhadas fornecem uma visão abrangente das interações que diferentes personas terão com o sistema de gestão de despesas corporativas de viagens na Web3. Desde a aquisição da licença até a integração com sistemas ERP, cada passo foi projetado para oferecer eficiência, segurança e conformidade, atendendo às necessidades de administradores, equipe de backoffice e demais usuários. A implementação cuidadosa dessas jornadas garantirá uma adoção bem-sucedida e benefícios significativos para a gestão financeira da empresa.
