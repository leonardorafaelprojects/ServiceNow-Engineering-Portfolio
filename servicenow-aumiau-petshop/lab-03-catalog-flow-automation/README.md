# ⚡ Lab 03: Service Catalog, Record Producers & Flow Designer

## 🎯 Objetivo Técnico
Desenvolver o *Front-end* transacional da aplicação via **Service Portal** e orquestrar as regras de negócio no *Back-end* utilizando a engine de automação **Flow Designer**.

## 🏢 O Desafio de Negócio
Com o banco de dados estruturado, a AuMiau precisava de duas portas de entrada distintas:
1. Um processo administrativo formal para a criação de novas categorias de produtos.
2. Uma via rápida (*Fast-Track*) para o cliente final realizar pedidos, caindo diretamente na fila de atendimento da loja.
Além disso, a triagem de pedidos críticos não podia depender de atualização manual (F5) por um analista, exigindo automação de alertas.

## 💡 Decisões Arquiteturais e Execução (Visão de Engenharia)

1. **Governança de Processos (Catalog Item):**
   * Criado o item *Solicitar nova categoria de produto*.
   * **Justificativa Arquitetural:** Como a inclusão de uma nova categoria afeta o *Master Data* da empresa, utilizamos um *Catalog Item* padrão. Isso garante que a solicitação passe pela esteira nativa de governança (`REQ` ➔ `RITM`), permitindo auditoria e aprovação gerencial antes da categoria ir para o ar.

2. **Inserção Direta de Dados (Record Producer):**
   * Criado o formulário *Solicitar produto* apontando diretamente para a custom table `x_aumiau_pedido`.
   * **Justificativa Arquitetural:** Transações de compra de clientes devem ser ágeis e não requerem a burocracia de RITMs. A injeção de dados no banco foi feita através do recurso *No-Code* **Map to field**, conectando as variáveis da interface perfeitamente às colunas do backend (ex: A variável de portal `Prioridade` injeta o valor na coluna `priority` da tabela estendida).

3. **Orquestração Assíncrona (Flow Designer):**
   * A triagem manual foi substituída por um fluxo automatizado e passivo.
   * **Trigger Otimizado:** Acionado em `Record Created` exclusivamente na tabela de Pedidos (`x_aumiau_pedido`).
   * **Engine de Regras:** 
     * O fluxo utiliza a ação nativa `Update Record` para mover o status do pedido para "Em atendimento" assim que ele entra no sistema.
     * **If/Else Logic:** O motor valida a *Data Pill* de Prioridade. Caso seja Crítica (1), aciona o nó `Send Email`, alertando a equipe de operações de forma imediata com os dados dinâmicos do solicitante.

## 📸 Evidências do Laboratório Prático

> Interface do usuário (*Front-end*) capturando o pedido e injetando a transação diretamente na tabela customizada via Map to Field.
*(Insira a imagem aqui, ex: `![Record Producer](../images/lab3_record_producer.png)`)*

> Orquestração visual do fluxo de atendimento, evidenciando o Trigger de criação e a condicional de notificação de prioridade.
*(Insira a imagem aqui, ex: `![Flow Designer](../images/lab3_flow_designer.png)`)*
