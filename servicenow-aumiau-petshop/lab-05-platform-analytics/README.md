# 📊 Lab 05: Platform Analytics & Dashboards Gerenciais

## 🎯 Objetivo Técnico
Desenvolver a camada de *Business Intelligence* (BI) e Gestão à Vista da aplicação, consolidando dados transacionais e cadastrais em um **Dashboard Interativo** através do moderno motor do *Platform Analytics* da ServiceNow.

## 🏢 O Desafio de Negócio
Com toda a operação da AuMiau Pet Shop digitalizada, a diretoria e os gerentes de loja enfrentaram um novo problema: a falta de visibilidade em tempo real. Eles precisavam saber quantos pedidos estavam sendo feitos, quantos estavam parados sem atendimento e como estava a fila de reclamações na Ouvidoria. O desafio foi traduzir o banco de dados em indicadores de performance (KPIs) acionáveis.

## 💡 Decisões Arquiteturais e Execução (Visão de Engenharia)

1. **Geração de Massa de Dados (Data Seeding):**
   * Antes da construção dos painéis, foram gerados registros sintéticos (*Mock Data*) nas tabelas de `Pedido` e `Ouvidoria`, garantindo variância de status, prioridades e atribuições.
   * **Justificativa:** É uma premissa de arquitetura validar a responsividade dos filtros e agrupamentos dos gráficos em ambiente de desenvolvimento (DEV) antes de promover o Dashboard para Produção.

2. **Platform Analytics vs. Relatórios Legados:**
   * A solução foi construída utilizando os componentes de *Data Visualization* do **Platform Analytics**, alinhando o projeto com a arquitetura *Next Experience* da ServiceNow, que oferece melhor performance e *UI/UX* em comparação ao módulo clássico de relatórios (Core UI).

3. **Estruturação Tática e Estratégica dos KPIs:**
   * **Visão Estratégica (Single Scores):** Foram criados indicadores de contagem direta para o *Total de Pedidos* e *Pedidos Completos* (`State is Closed Complete`), medindo o volume e a taxa de sucesso.
   * **Visão Operacional/Gargalos (Single Score):** Implementação de um medidor crítico para *Pedidos sem atribuição* (Condição: `Assigned to is Empty`), alertando os líderes sobre tickets órfãos que impactam o SLA de entrega.
   * **Visão de Portfólio (Horizontal Bar):** Agrupamento do catálogo de produtos utilizando a dimensão de `Categoria`, permitindo entender a distribuição do estoque.
   * **Visão Tática de Resolução (List View):** Injeção de uma lista dinâmica exibindo as últimas manifestações da `Ouvidoria`, ordenadas por prioridade, permitindo que os agentes atuem nos chamados críticos sem sair do painel gerencial.

## 📸 Evidências do Laboratório Prático

> Painel gerencial construído no Platform Analytics, reunindo os 5 relatórios de desempenho e monitoramento da loja em uma única interface.
*(Insira a imagem aqui, ex: `![Dashboard AuMiau](../images/lab5_dashboard_gestao.png)`)*

---
**🏁 Conclusão da Fase 1 (Core Architecture):** 
Com esta entrega, o ciclo de vida base da aplicação **AuMiau Pet Shop** está perfeitamente orquestrado: 
`Modelagem de Dados ➔ Interface de Catálogo ➔ Automação de Back-end (Flow Designer) ➔ Service Portal (UX) ➔ Gestão à Vista (Dashboards)`.
