# 📘 Now Pro - Laboratórios Práticos

Bem-vindo ao braço de treinamento e certificação do meu portfólio. Aqui estão documentados os exercícios práticos da formação **Now Pro**, construídos com rigor técnico e foco nas melhores práticas de engenharia de software no ecossistema ServiceNow.

## 🎯 Objetivo desta Trilha
Este espaço serve como um *playbook* arquitetural. O foco não é apenas mostrar "como fazer na ferramenta", mas sim documentar as decisões técnicas por trás de cada configuração (ex: por que usar *Catalog Items* em vez de *Record Producers* para solicitações corporativas) e pavimentar um terreno sólido para as certificações oficiais (CSA e CAD).

---

## 📂 Diretório de Laboratórios

### 📦 Módulo 01: Service Catalog & UX Dinâmico
Focado na entrega de serviços ao usuário final através do *Service Portal*, garantindo governança arquitetural com a regra DRY e interfaces reativas de alto desempenho (Client-Side).

* 📄 **[Lab 01: Formulário de Solicitação de Acesso RH](./lab-01-form-acesso-rh/)**
  * *Técnicas aplicadas:* Geração de hierarquia padrão do Catálogo (REQ > RITM > SCTASK).
  * *Componentização:* Criação e injeção do componente *Variable Set* para gerenciar variáveis repetitivas (Solicitante, RG, Telefone).

* 📄 **[Lab 02: Formulário de Criação de Aplicação (App Dev)](./lab-02-form-criacao-aplicacao/)**
  * *UX/UI Dinâmica:* Desenvolvimento de motor condicional usando *Catalog UI Policies*.
  * *Performance:* Escolha arquitetural por regras declarativas ao invés de *Catalog Client Scripts* (OnChange) para manipular a visibilidade do DOM e não sobrecarregar o carregamento do usuário.

---

*Nota: Este repositório está em constante evolução. Novos módulos contemplando automação (Flow Designer), integrações via API (REST) e segurança de dados (ACLs) serão documentados e indexados aqui conforme a progressão da trilha de estudos.*
