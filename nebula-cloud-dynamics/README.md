# 🏢 Nebula Cloud Dynamics - Corporate Architecture & Solutions

Bem-vindo ao centro de engenharia da **Nebula Cloud Dynamics**, minha empresa fictícia e "Laboratório Vivo" no ecossistema ServiceNow. 

## 🎯 Objetivo Corporativo
Este espaço é dedicado à arquitetura e implementação de soluções de TI que resolvem problemas complexos de negócios. Aqui, a teoria se transforma em fluxos de trabalho reais, modelagem de dados estendida, scripts de validação, integrações e governança robusta.

---

## 📂 Portfólio de Projetos Corporativos

### 🚀 [Projeto 01: Nebula Incident Express (Fast-Track Logging)](./project-01-incident-express/)
**Cenário:** Otimização do tempo de abertura de chamados críticos de infraestrutura para reduzir a fricção do usuário final e garantir SLAs.
* *Técnicas aplicadas:* Implementação de *Record Producers* desviando o fluxo nativo de Catálogo, mapeamento nativo (`Map to field`) para a tabela `incident` e automação *Server-Side* via Javascript para cálculo de prioridade.
* *UX/UI:* Estruturação visual de formulários em múltiplas colunas no Service Portal utilizando a lógica de contêineres (`Container Start`, `Split` e `End`).

### 🛡️ [Projeto 02: Critical Cloud Access Engine (Governance)](./project-02-cloud-access-engine/)
**Cenário:** Sistema rigoroso e auditável de governança exigido pelo time de InfoSec para solicitação de acessos privilegiados a ambientes Cloud (AWS/Azure).
* *Arquitetura de Dados:* Criação de uma **Tabela Customizada** (`u_nebula_access_request`) estendendo a tabela base `task` para herdar comportamentos nativos do ServiceNow (numeração, estado, SLA).
* *Front-end Dinâmico:* Validação técnica em tempo real de datas de expiração via **Catalog Client Scripts** (`onChange`) e injeção de campos condicionais através de **Catalog UI Policies**.
* *Back-end Avançado:* Script de servidor processando uma Matriz de Risco dinâmica, injetando *logs* descritivos complexos de auditoria e utilizando métodos da API `producer` para executar redirecionamentos controlados no Portal.
