# 🏷️ Sem Parar (Corpay) — Lab 01: Service Portal & Substituição de Tag de Frota

[![ServiceNow](https://img.shields.io/badge/ServiceNow-Zurich-009688?style=for-the-badge&logo=servicenow&logoColor=white)](https://www.servicenow.com)
[![Approach](https://img.shields.io/badge/Approach-Low--Code%20%2F%20No--Code%20First-0052CC?style=for-the-badge&logo=target&logoColor=white)]()
[![Release Governance](https://img.shields.io/badge/Release%20Governance-Update%20Set%20Managed-E65100?style=for-the-badge&logo=git&logoColor=white)]()
[![Module](https://img.shields.io/badge/Module-ITSM%20%2F%20Service%20Catalog-455A64?style=for-the-badge)]()

---

## 📌 1. Visão Geral & Cenário de Negócio (Business Case)
Na gestão de frotas e serviços de mobilidade do **Sem Parar (Corpay)**, veículos corporativos enfrentam imprevistos nas pistas como **danos físicos em tags** ou **perda/furto do dispositivo**. 

* **O Problema:** Aberturas descentralizadas de chamados sem dados críticos (ex.: placa do veículo, código da tag antiga ou motivo do bloqueio) geravam retenção em cancelas, desvios operacionais e triagem manual exaustiva do time de suporte.
* **A Solução:** Desenvolvimento de um canal direto de autoatendimento via **Record Producer** no **Service Portal**, aplicando validações nativas em tela (*Catalog UI Policy*), mapeamento declarativo (*Map to field*) e lógica de servidor para priorização crítica automática em caso de roubo.

---

## 📋 2. Requisitos & Especificações Ágeis (BDD)

### User Story
> **Como** gestor ou condutor de frota corporativa credenciada ao Sem Parar,  
> **Quero** solicitar a substituição emergencial de uma tag de forma rápida e intuitiva pelo portal,  
> **Para que** ocorrências de furto bloqueiem a tag imediatamente no sistema e avarias físicas contenham o número do dispositivo para rastreio logístico.

### Critérios de Aceite (Gherkin / BDD)
```gherkin
Cenário: Solicitação emergencial por Perda ou Roubo
  Dado que o condutor acessa o formulário de substituição no Service Portal
  Quando seleciona o motivo da troca como "Perda / Roubo"
  Então o campo "Número da Tag Danificada" não deve ser de preenchimento obrigatório
  E o script de servidor deve classificar o Incidente com Urgência Alta (1) e Impacto Médio (2)
  E a Short Description deve ser gravada no padrão "SUBSTITUIÇÃO DE TAG: Veículo <Placa>"

Cenário: Solicitação por Avaria Física (Validação Declarativa)
  Dado que o formulário está carregado
  Quando o condutor seleciona o motivo "Danificada / Quebrada"
  Então a Catalog UI Policy deve exibir o campo "Número da Tag Danificada"
  E o campo deve se tornar estritamente obrigatório antes da submissão
