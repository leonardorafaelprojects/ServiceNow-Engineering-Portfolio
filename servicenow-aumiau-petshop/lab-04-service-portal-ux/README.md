# 🎨 Lab 04: Service Portal, UX/UI Branding & Homepage Design

## 🎯 Objetivo Técnico
Desenvolver e estilizar a interface de contato com o cliente final (*Front-End*) criando um **Service Portal** customizado para a aplicação. O foco deste laboratório é a aplicação de princípios de *User Experience* (UX), governança de menus e personalização de *Widgets* via `sp_config`, mantendo a plataforma *Upgrade-Safe*.

## 🏢 O Desafio de Negócio
Após a estruturação do back-end e da automação de pedidos, a AuMiau Pet Shop precisava de uma "Vitrine Digital" para seus clientes. O portal padrão de TI do ServiceNow era complexo demais para o varejo. O desafio foi desenhar uma interface limpa, focada em conversão e com a identidade visual da marca (Logo, Ícones, Cores), sem realizar customizações pesadas de código que prejudicassem futuras atualizações do sistema.

## 💡 Decisões Arquiteturais e Execução (Visão de Engenharia)

1. **Roteamento e Isolamento (`sp_portal`):**
   * Foi criado um portal dedicado com o sufixo `/aumiau`. 
   * **Justificativa Arquitetural:** Separar a URL de varejo da URL de TI corporativa (`/sp`) garante métricas de acesso isoladas e evita o vazamento de catálogos internos para clientes externos.

2. **Governança de Navegação (Clean UI):**
   * O menu superior (*SP Header Menu*) foi enxugado para exibir estritamente as necessidades do tutor do pet: **Base de Conhecimento** (para dúvidas de entrega) e **Requisições** (para acompanhamento de pedidos).
   * **Justificativa:** Reduzir a carga cognitiva do usuário final e focar nas ações de conversão e autoatendimento.

3. **Branding Editor vs. Custom CSS (Upgrade-Safe):**
   * A identidade visual foi aplicada utilizando o **Branding Editor**, injetando as cores HEX da AuMiau (Marrom, Turquesa e Laranja) diretamente nas variáveis SCSS globais do tema.
   * **Justificativa Arquitetural:** Modificar variáveis de tema via painel é uma prática muito superior a escrever e injetar folhas de estilo (`.css`) manualmente. Isso assegura que o portal permaneça intacto (*Upgrade-Safe*) durante grandes atualizações da plataforma ServiceNow.

4. **Sobrescrita de Widgets (Instance Options):**
   * Para alterar o texto do buscador principal nativo para *"Como posso AUjudar?"*, o Widget OOTB (*Out-of-the-Box*) **não foi clonado**. 
   * A alteração foi feita através do recurso avançado de **Instance Options**, modificando os parâmetros JSON apenas na instância renderizada naquela página. Isso poupa o banco de dados de armazenar códigos legados e facilita a manutenção contínua.

## 📸 Evidências do Laboratório Prático

> Visão da Homepage finalizada com o banner aplicado via *Container Background* e os *Instance Options* customizados no buscador.
*(Insira a imagem aqui, ex: `![Service Portal - Homepage](../images/lab4_portal_homepage.png)`)*

> Configuração de variáveis SCSS de marca aplicada pelo Branding Editor em tempo real.
*(Insira a imagem aqui, ex: `![Branding Editor - Colors](../images/lab4_branding_colors.png)`)*
