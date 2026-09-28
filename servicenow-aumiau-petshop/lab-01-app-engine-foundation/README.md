# 🏗️ Lab 01: Foundation & Application Engine (Scoped App)

## 🎯 Objetivo Técnico
Estabelecer a fundação segura da aplicação através do ServiceNow Studio, criando uma **Scoped Application** isolada, configurando os metadados do sistema e aplicando o princípio de *Role-Based Access Control* (RBAC) para governança de usuários.

## 🏢 O Desafio de Negócio (Business Case)
A AuMiau Pet Shop gerenciava as operações de 8 lojas físicas e um e-commerce através de planilhas descentralizadas e comunicação não rastreável. A exigência arquitetural era que a nova solução na Now Platform não interferisse nos processos globais de TI (ITSM/ITOM) da instância, garantindo segurança e isolamento de dados.

## 💡 Decisões Arquiteturais e Execução (Visão de Engenharia)

1. **Arquitetura de Isolamento (Scoped Application):**
   * Em vez de desenvolver no escopo `Global`, a solução foi instanciada no escopo dedicado `x_aumiau` (AuMiau Pet Shop).
   * **Justificativa:** Isso garante que todas as tabelas, scripts, ACLs e fluxos gerados pertençam exclusivamente a este pacote, prevenindo vazamento de dados, conflitos de nomenclatura com outras aplicações e facilitando futuras implantações (Upgrades/Deployments) via *Application Repository*.

2. **Governança de Acessos (RBAC):**
   * Foram estruturadas duas *Roles* fundamentais para segregar as permissões do sistema, aplicando o conceito de *Least Privilege* (Menor Privilégio):
     * `x_aumiau.aumiau_admin`: Perfil administrador, com permissões completas (CRUD) para gerenciar o catálogo, categorias e configurações do sistema.
     * `x_aumiau.aumiau_user`: Perfil operacional para os atendentes, com permissões focadas em leitura/escrita transacional de pedidos e chamados, sem privilégios de exclusão de dados mestres.

3. **Identidade Visual (Branding Base):**
   * Injeção dos ativos de marca (Logotipo e Ícones) diretamente nos metadados da aplicação, garantindo que o escopo seja visualmente identificável no *Application Navigator* e no *ServiceNow Studio*.

## 📸 Evidências do Laboratório Prático

> Criação da aplicação escopada no ServiceNow Studio, garantindo o prefixo `x_aumiau` para todos os artefatos futuros.
*(Insira a imagem aqui, ex: `![App Studio](../images/lab1_app_studio.png)`)*

> Definição da matriz de segurança (Roles) instanciada na criação do aplicativo.
*(Insira a imagem aqui, ex: `![Roles Setup](../images/lab1_roles.png)`)*
