# 🐾 AuMiau Pet Shop - ServiceNow End-to-End Architecture

[![ServiceNow](https://img.shields.io/badge/ServiceNow-Platform-green.svg)](https://www.servicenow.com)
[![Role Target](https://img.shields.io/badge/Focus-ServiceNow%20Developer%20(Junior%2FPleno)-orange.svg)]()

Bem-vindo ao repositório de arquitetura da **AuMiau Pet Shop**. Este projeto é um *Business Case* completo onde atuei como Engenheiro ServiceNow para digitalizar toda a operação de uma rede de lojas pet, substituindo planilhas soltas e WhatsApp por uma aplicação escopada centralizada na Now Platform.

## 🎯 Objetivo Arquitetural
Demonstrar a construção de uma solução *End-to-End*, provando o domínio das competências exigidas para Desenvolvedores ServiceNow. O projeto está metodicamente dividido em duas fases de engenharia: a base sólida da plataforma (*Core*) e os desafios de integração e orquestração de processos.

---

## 🛠️ FASE 1: Core da Plataforma (Júnior Avançado)
Esta fase estabelece a fundação do aplicativo, modelagem de banco de dados, interface do cliente e relatórios operacionais.

* 📦 **[Lab 01: Scoped App & Foundation](./lab-01-app-engine-foundation/)**
  * *Competências:* App Engine Studio, Criação de Aplicação Escopada (`x_aumiau`), Role-Based Access Control (RBAC).
* 🗄️ **[Lab 02: Modelagem de Dados & Governança](./lab-02-data-model-tables/)**
  * *Competências:* Extensão da tabela `Task`, Master Data (Tabelas Standalone), Importação Massiva via Excel, Access Control Lists (ACLs) limitando a exclusão de registros.
* ⚡ **[Lab 03: Service Catalog & Flow Designer](./lab-03-catalog-flow-automation/)**
  * *Competências:* Diferenciação arquitetural entre *Catalog Items* (com REQ/RITM) e *Record Producers* (com *Map to field* direto em tabela customizada). Automação de Back-end com Triggers e lógica If/Else.
* 🎨 **[Lab 04: Service Portal & UX/UI](./lab-04-service-portal-ux/)**
  * *Competências:* Criação de Service Portal customizado, aplicação de variáveis CSS via Branding Editor e customização de Widgets via *Instance Options*.
* 📊 **[Lab 05: Platform Analytics & Dashboards](./lab-05-platform-analytics/)**
  * *Competências:* Geração de Data Visualizations (Single Score, Bar Charts, List Views) e estruturação de painéis de Business Intelligence.

---

## 🚀 FASE 2: Engenharia Avançada & Integrações (Pleno)
Esta fase eleva a complexidade técnica da aplicação, introduzindo consumo de APIs externas e interfaces de nova geração.

* 🌐 **[Lab 06: Integração REST & GlideAjax (Busca CEP) - EM BREVE](./lab-06-rest-integration-viacep/)**
  * *Competências:* Configuração de *Outbound REST Message*, processamento de JSON via *Script Include* e autopreenchimento assíncrono no Client-Side.
* 🚦 **[Lab 07: Automação Dinâmica de Aprovações - EM BREVE](./lab-08-advanced-flow-approvals/)**
  * *Competências:* Orquestração de BPM com aprovações dinâmicas de gerência diretamente no Flow Designer.
