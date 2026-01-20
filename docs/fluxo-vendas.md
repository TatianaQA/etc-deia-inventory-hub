\# 💰 Fluxo de Vendas — Etc \& Deia Inventory Hub



Documento que descreve o \*\*fluxo funcional do módulo de Vendas (PDV)\*\*,  

detalhando comportamentos esperados, decisões do sistema, mensagens ao usuário  

e critérios de aceite associados.



Este fluxo foi desenhado com foco em \*\*operação real de loja\*\*,  

priorizando rapidez, redução de erros e clareza visual durante o atendimento ao cliente.



---



\## 🎯 Objetivo do fluxo



Permitir que o usuário:



\- realize vendas de forma rápida

\- encontre produtos por nome ou código de barras

\- visualize valores corretamente

\- finalize vendas com segurança

\- tenha controle claro do que foi vendido



---



\## 👤 Perfil principal envolvido



\*\*Operador de loja\*\*



\- não técnico

\- atendimento ao cliente em tempo real

\- precisa de respostas rápidas do sistema

\- não pode “pensar demais” durante a venda



---



\## 🔄 Fluxos cobertos neste documento



1\. Acesso à tela de Vendas  

2\. Busca de produto para venda  

3\. Produto encontrado  

4\. Produto não encontrado durante a venda  

5\. Inclusão de item na venda  

6\. Múltiplos itens na mesma venda  

7\. Finalização da venda  

8\. Cancelamento / ajuste de itens  

9\. Mensagens e feedbacks do sistema  



---



\## 🧭 Fluxo 1 — Acesso à tela de Vendas



\### Passos



1\. Usuário acessa o menu \*\*Vendas\*\*

2\. Sistema carrega:

&nbsp;  - campo de busca de produto

&nbsp;  - lista de itens da venda (inicialmente vazia)

&nbsp;  - resumo financeiro da venda



\### Critérios de aceite



\- Tela deve carregar rapidamente

\- Campo de busca deve estar focado para digitação

\- Sistema deve estar pronto para o primeiro item



---



\## 🔍 Fluxo 2 — Busca de produto para venda



\### Passos



1\. Usuário:

&nbsp;  - digita o nome do produto \*\*ou\*\*

&nbsp;  - informa o código de barras

2\. Sistema identifica o tipo de busca

3\. Executa a consulta



\### Critérios de aceite



\- Busca por nome segue normalização de texto

\- Busca por código segue normalização numérica

\- Sistema não deve travar o fluxo de venda



---



\## ✅ Fluxo 3 — Produto encontrado



\### Comportamento do sistema



\- Exibe o produto encontrado

\- Adiciona automaticamente à venda \*\*ou\*\*

\- solicita confirmação visual (dependendo da UX)



\### Critérios de aceite



\- Produto correto deve ser exibido

\- Preço deve estar visível

\- Item deve entrar na lista da venda



---



\## ❌ Fluxo 4 — Produto não encontrado durante a venda



\### Comportamento do sistema



\- Exibe mensagem clara

\- Oferece opções:

&nbsp; - tentar nova busca

&nbsp; - cadastrar produto (quando permitido)



\### Critérios de aceite



\- Venda não deve ser perdida

\- Mensagem deve orientar o operador

\- Sistema não deve exibir erro técnico



---



\## ➕ Fluxo 5 — Inclusão de item na venda



\### Passos



1\. Produto é adicionado à lista

2\. Sistema atualiza:

&nbsp;  - subtotal

&nbsp;  - quantidade de itens

3\. Operador pode seguir adicionando produtos



\### Critérios de aceite



\- Valores devem atualizar automaticamente

\- Item deve ser facilmente identificado

\- UX deve permitir correção rápida



---



\## 🧾 Fluxo 6 — Múltiplos itens na mesma venda



\### Comportamento do sistema



\- Permite adicionar vários produtos

\- Exibe lista clara dos itens

\- Mantém resumo financeiro visível



\### Critérios de aceite



\- Ordem dos itens deve ser clara

\- Sistema deve responder rápido

\- Totais devem refletir corretamente a soma



---



\## ✅ Fluxo 7 — Finalização da venda



\### Passos



1\. Operador confirma a venda

2\. Sistema:

&nbsp;  - valida itens

&nbsp;  - registra a venda

&nbsp;  - atualiza estoque

3\. Exibe confirmação de sucesso



\### Critérios de aceite



\- Venda deve ser registrada com segurança

\- Estoque deve ser atualizado

\- Feedback visual deve ser claro



---



\## 🔄 Fluxo 8 — Cancelamento ou ajuste de itens



\### Comportamento do sistema



\- Permite remover item da venda

\- Atualiza valores automaticamente

\- Não exige reiniciar a venda



\### Critérios de aceite



\- Ajustes devem ser simples

\- Sistema não deve confundir o operador

\- Valores devem ser recalculados corretamente



---



\## 💬 Mensagens e feedbacks



O sistema deve sempre:



\- informar o estado atual da venda

\- orientar o operador

\- evitar mensagens técnicas



Exemplos esperados:



\- “Produto adicionado à venda”

\- “Item removido com sucesso”

\- “Venda finalizada”



---



\## 🧪 Base para testes (QA)



Este fluxo serve como base para:



\- testes manuais de PDV

\- automação E2E com Cypress

\- validação de cenários críticos

\- prevenção de regressões em vendas



---



\## 🔮 Evolução futura



Na Fase 2, o fluxo de vendas poderá incluir:



\- formas de pagamento

\- cálculo de lucro real

\- relatórios de vendas

\- integração com estoque e dashboard



