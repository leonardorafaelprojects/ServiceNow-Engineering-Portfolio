
# 🚀 Nebula Incident Express - ServiceNow Record Producer (Junior Level)

## 📌 Visão Geral do Projeto
Este projeto implementa um fluxo otimizado de abertura de incidentes de infraestrutura no **ServiceNow Service Portal** para a empresa fictícia **Nebula Cloud Dynamics**.

O objetivo principal foi reduzir o tempo de preenchimento do formulário pelos colaboradores e garantir a padronização das categorias e urgências na tabela nativa `incident`.

## 🛠️ Funcionalidades Técnicas
- **Record Producer (`sc_cat_item_producer`)**: Interface amigável no Portal que desvia da cadeia tradicional de REQ/RITM e grava diretamente na tabela `incident`.
- **No-Code Mapping (`Map to field`)**: Mapeamento nativo dos campos `caller_id`, `short_description` e `description`.
- **Server-Side Automation**: Script em JavaScript que avalia o impacto selecionado (`producer.impacto_operacional`) e ajusta dinamicamente as colunas `urgency` e `impact` no registro final (`current`).
- **UI UX Layout**: Uso de `Container Start`, `Container Split` e `Container End` para organizar o formulário em duas colunas responsivas.

## 📐 Diagrama do Fluxo
`[ Usuário no Portal ]` ➔ `[ Record Producer Form ]` ➔ `[ Server Script Evaluation ]` ➔ `[ Registro Gerado na Tabela INCIDENT ]`

## 💻 Código Fonte (Server Script)
```javascript
// Atribui o tipo de contato como Self-Service
current.contact_type = 'self-service';

// Categoria fixa para o time de infraestrutura da Nebula
current.category = 'infrastucture';

// Se o usuário marcou impacto para toda a equipe, eleva a urgência
if (producer.impacto_operacional == '1') {
    current.urgency = 1; // High
    current.impact = 1;  // High
} else {
    current.urgency = 3; // Low
    current.impact = 3;  // Low
}

// Adiciona uma nota de trabalho informativa
current.work_notes = 'Incidente gerado via Portal Express por: ' + producer.solicitante.getDisplayValue();
