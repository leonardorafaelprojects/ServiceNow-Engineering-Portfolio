# 🚦 Sem Parar (Corpay) — ServiceNow Engineering & Automação Low-Code

[![ServiceNow](https://img.shields.io/badge/ServiceNow-Zurich-green.svg)](https://www.servicenow.com)
[![Role Target](https://img.shields.io/badge/Focus-Analista%20de%20Sistemas%20Low%20Code%20Jr-orange.svg)]()

Bem-vindo ao meu centro de soluções desenvolvidas especificamente para o ecossistema operacional da **Sem Parar (Corpay)**. 

## 🎯 Visão Executiva
Este diretório agrupa provas de conceito (PoCs) e laboratórios práticos focados nas dores reais da gestão de frotas e serviços de mobilidade. O objetivo é demonstrar meu domínio sobre a arquitetura da plataforma ServiceNow aplicando o princípio **"Configuration over Customization"**, focado em entregas de alto valor com Low-Code e No-Code.

---

## 📂 Portfólio de Soluções (Sem Parar)

### 🚀 [Lab 01: Service Portal & Substituição de Tag de Frota](./lab-01-tag-replacement/)
**Desafio:** Eliminar chamados incompletos ou manuais para troca de tags veiculares avariadas ou furtadas.
* *Solução Aplicada:* Criação de **Record Producer** integrado à tabela de Incidentes com mapeamento direto de variáveis (`Map to field`).
* *UX/UI Dinâmica:* Implementação de **Catalog UI Policy** para validar a entrada de dados (avaria física) sem uso de código.
* *Automação Back-end:* Script de servidor para interceptar e elevar a criticidade (Urgência 1) automaticamente em casos de roubo.

### ⚙️ [Lab 02: Automação de Aprovação e Roteamento (Flow Designer)](./lab-02-flow-designer-approval/)
**Desafio:** Automatizar a cadeia de aprovação de frotas, eliminando a dependência de triagem humana para liberar novos dispositivos.
* *Solução Aplicada:* Construção de um fluxo completo no **Flow Designer** acionado via gatilho de registro (*Trigger: Record Created*).
* *Orquestração:* Bloco de aprovação multinível (*Ask for Approval*), lógica condicional estruturada (*If/Else*) e automação de atualização de registros e envio de e-mails dinâmicos consumindo *Data Pills*.

---
**Desenvolvido por:** Leonardo Rafael | *ServiceNow Administrator & Low-Code Developer*
