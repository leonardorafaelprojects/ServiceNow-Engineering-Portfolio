# 🗄️ Lab 02: Relational Data Model & Master Data Management

## 🎯 Objetivo Técnico
Projetar e instanciar a arquitetura de banco de dados da aplicação, aplicando conceitos de *Relational Data Modeling*, herança de tabelas nativas (*Table Extension*) e segurança em nível de registro (*Access Control Lists - ACLs*).

## 🏢 O Desafio de Negócio
A AuMiau Pet Shop possuía um catálogo de mais de 3.000 produtos e um histórico de pedidos geridos inteiramente através de planilhas desconectadas. O desafio foi desenhar um modelo de dados relacional que garantisse a integridade referencial entre o catálogo de produtos e os pedidos dos clientes, além de habilitar a rastreabilidade nativa de SLAs para a ouvidoria.

## 💡 Decisões Arquiteturais e Execução (Visão de Engenharia)

1. **Master Data (Standalone Tables):**
   * As tabelas `x_aumiau_categoria` e `x_aumiau_produto` foram criadas como *Blank Tables* (não extensíveis).
   * **Justificativa:** Dados de catálogo não exigem ciclo de vida operacional (aprovações, *State*, SLA). Mantê-las isoladas da tabela principal `Task` reduz o processamento (*overhead*) do banco de dados e melhora a performance de consultas (*Queries*).
   * **Data Load:** A carga inicial dos 3.000 produtos foi orquestrada via *Import Sets* (Upload de Excel), mapeando automaticamente as chaves estrangeiras (*Reference Fields*) para a tabela de Categorias.

2. **Herança Operacional (Extended Tables):**
   * As tabelas `x_aumiau_pedido` e `x_aumiau_ouvidoria` foram criadas estendendo a tabela nativa `Task`.
   * **Justificativa Arquitetural:** Ao herdar de `Task`, a aplicação ganha instantaneamente capacidades robustas de ITSM/CSM (Customer Service Management), como controle de *Assignment Group*, *Assigned To*, numeração automática (*Numbering*) e integração nativa com o motor de Service Level Agreements (SLAs), economizando semanas de desenvolvimento customizado.

3. **Governança de Dados (ACLs - Princípio do Menor Privilégio):**
   * Durante a criação das tabelas, as regras de segurança (*Access Control*) foram configuradas para impedir a quebra de integridade:
     * A *role* `aumiau_admin` possui acesso CRUD completo (Create, Read, Write, Delete).
     * A *role* `aumiau_user` teve a permissão de exclusão (Delete) revogada. Isso previne a geração de *Orphan Records* (ex: deletar uma categoria que já possui produtos vendidos vinculados a ela).

## 📸 Evidências do Laboratório Prático

> Importação massiva do catálogo de produtos e integridade referencial aplicada (Categoria vinculada ao Produto).
*(Insira a imagem aqui, ex: `![Data Import](../images/lab2_import_produtos.png)`)*

> Tabela de Pedidos evidenciando a herança da tabela Task e a numeração gerada.
*(Insira a imagem aqui, ex: `![Task Extension](../images/lab2_task_extension.png)`)*
