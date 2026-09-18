# 📘 Now Pro - Laboratórios Práticos

Bem-vindo ao braço de treinamento e certificação do meu portfólio. Aqui estão documentados os exercícios práticos da formação **Now Pro**, construídos com rigor técnico e foco nas melhores práticas de engenharia de software no ecossistema ServiceNow.

## 🎯 Objetivo desta Trilha
Este espaço serve como um *playbook* arquitetural. O foco não é apenas mostrar "como fazer na ferramenta", mas sim documentar as decisões técnicas por trás de cada configuração e pavimentar um terreno sólido para as certificações oficiais (CSA e CAD).

---

## 📂 Diretório de Laboratórios

### 📦 Módulo 01: Service Catalog & UX Dinâmico
Focado na entrega de serviços ao usuário final através do *Service Portal*, garantindo governança arquitetural com a regra DRY (Don't Repeat Yourself) e interfaces reativas de alto desempenho.

* 📄 **[Lab 01: Formulário de Solicitação de Acesso RH](./lab-01-form-acesso-rh/)**
  * *Técnicas aplicadas:* Geração da hierarquia padrão do Catálogo (REQ > RITM > SCTASK)[cite: 1].
  * *Componentização:* Criação e injeção do componente *Variable Set* para gerenciar pacotes de variáveis compartilhadas e repetitivas (como Solicitante, RG, Telefone)[cite: 3].

* 📄 **[Lab 02: Formulário de Criação de Aplicação (App Dev)](./lab-02-form-criacao-aplicacao/)**
  * *UX/UI Dinâmica:* Desenvolvimento de um motor condicional para alterar dinamicamente o comportamento das informações no formulário[cite: 1].
  * *Performance:* Escolha arquitetural pelo uso de *Catalog UI Policies*, que rodam estritamente no *Client-Side* (navegador), garantindo carregamento rápido e evitando a necessidade de *Client Scripts* complexos[cite: 1, 4].
 
* 📄 **[Lab 03: Record Producer e Lógica Server-Side (Incidentes)](./lab-03-record-producer-incidente/)**
  * *Técnicas aplicadas:* Mapeamento de variáveis diretas para a tabela de Incidentes (*Map to Field*).
  * *Automação Back-end:* Criação de script de servidor manipulando objetos `producer` e `current` para roteamento e classificação automática de chamados sem intervenção humana.

---

*Nota: Este repositório está em constante evolução. Novos módulos contemplando automação (Flow Designer), integrações via API (REST) e segurança de dados (ACLs) serão documentados e indexados aqui conforme a progressão da trilha de estudos.*
