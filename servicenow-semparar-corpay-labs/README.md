# 🏎️ ServiceNow Engineering Portfolio — Sem Parar (Corpay)

[![ServiceNow](https://img.shields.io/badge/ServiceNow-Washington%20%7C%20Xanadu-009688?style=for-the-badge&logo=servicenow&logoColor=white)](https://www.servicenow.com)
[![Platform](https://img.shields.io/badge/Approach-Low--Code%20%2F%20No--Code%20First-0052CC?style=for-the-badge&logo=target&logoColor=white)]()
[![Governance](https://img.shields.io/badge/Release%20Governance-Update%20Sets%20Audited-E65100?style=for-the-badge&logo=git&logoColor=white)]()
[![Methodology](https://img.shields.io/badge/Framework-ITIL%20v4%20%7C%20Scrum-455A64?style=for-the-badge&logo=scrumalliance&logoColor=white)]()
[![License](https://img.shields.io/badge/License-MIT-2E7D32?style=for-the-badge)]()

---

## 📌 Visão Executiva & Contexto Operacional

Este repositório reúne soluções de engenharia de software, modelagem de dados e automações corporativas desenvolvidas especificamente para os desafios operacionais do **Sem Parar (Unidade de Negócio Corpay)** na plataforma ServiceNow.

O propósito central é comprovar a aplicação da diretriz **"Configuration over Customization"** (Configuração Declarativa antes de Customização), entregando:
* **Digitalização de Serviços de Mobilidade:** Interfaces ágeis de autoatendimento para frotistas, eliminando falhas em pistas e desvios operacionais.
* **Sustentabilidade de Release:** Governança técnica que protege a integridade do ecossistema corporativo contra débitos técnicos e quebras durante upgrades de versão (Washington/Xanadu).
* **Eficiência de Processos:** Automação de esteiras com *Flow Designer* e validações em tempo real para reduzir o tempo médio de atendimento (MTTR) e mitigar triagens manuais.

---

## 🏛️ Matriz de Soluções & Laboratórios Práticos

| Módulo / Lab | Domínio Arquitetural | Tecnologias & Componentes-Chave | Impacto no Negócio | Status |
| :--- | :--- | :--- | :--- | :---: |
| **[Lab 01: Service Portal & Client Governance](./lab-01-service-portal-client-governance)** | Frontend & Regras de Interface | Record Producer, Catalog UI Policies, Mapeamento No-Code (`Map to field`), Priorização Dinâmica, Update Sets | Autoatendimento para troca de tags avariadas/furtadas, blindando o banco contra dados incompletos | 🟢 Concluído |
| **[Lab 02: Flow Designer Tag Approval](./lab-02-flow-designer-tag-approval)** | Automação de Processos & Workflows | Flow Designer, Data Pills, `Ask for Approval` Multinível, Notificações Automáticas, Subtarefas Operacionais | Eliminação da triagem manual para liberações de limite e roteamento de logística de entrega | 🟢 Concluído |
| **[Lab 03: Gestão à Vista & Dashboards](./lab-03-dashboards-performance-reports)** | Analytics & Tomada de Decisão | Report Designer, Interactive Filters, SLAs Operacionais, Matrizes de Volumetria | Gestão à vista em tempo real para lideranças monitorarem gargalos e cumprimento de contratos de frotas | 🟡 Em Breve |
| **[Lab 04: Governança de Tarefas & Task Engine](./lab-04-data-model-task-governance)** | Modelagem de Dados & Integridade | Herança de Tabela Base (`Task [task]`), Data Policies (Server-Side), Dictionary Overrides, Numeração Sequencial | Arquitetura relacional escalável garantindo rastreabilidade e herança de ciclo de vida nativo | 🟡 Em Breve |
| **[Lab 05: Matriz de Segurança & Perfis](./lab-05-security-acls-governance)** | Segurança da Informação & Acessos | Roles Corporativas, Access Control Lists (ACLs Table-First), Scripted Security, *Impersonate User* | Isolamento seguro de dados cadastrais confidenciais entre diferentes contas e clientes frotistas | 🟡 Em Breve |
| **[Lab 06: Integrações Assíncronas & REST](./lab-06-rest-integrations-scripts)** | Integração de Sistemas & Scripting | Outbound REST Messages, JSON Parsing, `Script Includes` (POO), `GlideAjax` com Callback Assíncrono | Validação de dados cadastrais de frota e endereços de entrega sem travamento de interface | 🟡 Em Breve |

---

## ⚙️ Padrões de Governança, Release & Engenharia

Todos os artefatos técnicos construídos neste repositório seguem rigorosamente as melhores práticas corporativas da ServiceNow:
