\# 🧩 Fluxo de Produtos — Etc \& Deia Inventory Hub



Documento que descreve o \*\*fluxo funcional do módulo de Produtos\*\*,  

detalhando comportamentos esperados, decisões do sistema, mensagens ao usuário  

e critérios de aceite associados.



Este fluxo foi desenhado com foco em \*\*operação real de loja\*\*,  

reduzindo erros, cliques desnecessários e dependência de conhecimento técnico.



---



\## 🎯 Objetivo do fluxo



Permitir que o usuário:



\- cadastre produtos com facilidade

\- busque produtos por nome ou código de barras

\- evite duplicidade de cadastro

\- tenha feedback claro em todos os cenários

\- mantenha controle simples e eficiente do estoque



---



\## 👤 Perfil principal envolvido



\*\*Operador de loja\*\*



\- não técnico

\- rotina corrida

\- necessidade de rapidez e clareza

\- pode errar digitação ou esquecer informações



---



\## 🔄 Fluxos cobertos neste documento



1\. Acesso à tela de Produtos  

2\. Busca de produto por nome  

3\. Busca de produto por código de barras  

4\. Produto encontrado  

5\. Produto não encontrado  

6\. Cadastro de novo produto  

7\. Produto duplicado  

8\. Mensagens e alertas do sistema  



---



\## 🧭 Fluxo 1 — Acesso à tela de Produtos



\### Passos



1\. Usuário acessa o menu \*\*Produtos\*\*

2\. Sistema carrega:

&nbsp;  - campo de busca

&nbsp;  - lista de produtos cadastrados

&nbsp;  - ações disponíveis (buscar / cadastrar)



\### Critérios de aceite



\- A tela deve carregar sem erros

\- O campo de busca deve estar visível e habilitado

\- A lista deve exibir produtos existentes ou estado vazio orientativo



---



\## 🔍 Fluxo 2 — Busca de produto por nome



\### Passos



1\. Usuário digita o \*\*nome do produto\*\*

2\. Sistema aplica normalização de texto:

&nbsp;  - lowercase

&nbsp;  - trim

&nbsp;  - colapso de espaços

3\. Sistema executa a busca

4\. Retorna resultado



\### Possíveis resultados



\- Produto encontrado

\- Lista de produtos similares

\- Nenhum produto encontrado



\### Critérios de aceite



\- Espaços extras não devem quebrar a busca

\- Letras maiúsculas/minúsculas não devem interferir

\- Busca por nome \*\*não deve\*\* usar regra de código de barras



---



\## 🔢 Fluxo 3 — Busca de produto por código de barras



\### Passos



1\. Usuário:

&nbsp;  - digita o código \*\*ou\*\*

&nbsp;  - utiliza scanner (ou câmera do celular)

2\. Sistema normaliza o código:

&nbsp;  - remove espaços

&nbsp;  - aceita apenas números

3\. Executa a busca



\### Critérios de aceite



\- Letras e símbolos devem ser ignorados

\- Código inválido deve gerar mensagem clara

\- Busca por código não deve aplicar normalização de nome



---



\## ✅ Fluxo 4 — Produto encontrado



\### Comportamento do sistema



\- Exibe informações do produto

\- Permite:

&nbsp; - visualizar dados

&nbsp; - seguir para venda

&nbsp; - editar (quando aplicável)



\### Critérios de aceite



\- Produto correto deve ser exibido

\- Não deve abrir fluxo de cadastro

\- Usuário deve entender claramente que o produto já existe



---



\## ❌ Fluxo 5 — Produto não encontrado



\### Comportamento do sistema



\- Exibe mensagem orientativa

\- Oferece ação:

&nbsp; - \*\*Cadastrar novo produto\*\*



\### Critérios de aceite



\- Mensagem deve ser clara e humana

\- Não deve parecer erro técnico

\- CTA de cadastro deve estar visível



---



\## ➕ Fluxo 6 — Cadastro de novo produto



\### Passos



1\. Usuário inicia cadastro

2\. Sistema apresenta formulário com:

&nbsp;  - nome do produto

&nbsp;  - código de barras (opcional)

&nbsp;  - categoria

&nbsp;  - preço de custo

&nbsp;  - preço de venda

&nbsp;  - estoque inicial

3\. Usuário salva



\### Critérios de aceite



\- Campos obrigatórios devem ser validados

\- Mensagens de erro devem orientar, não bloquear

\- Cadastro bem-sucedido deve gerar feedback visual



---



\## ⚠️ Fluxo 7 — Produto duplicado



\### Cenário



Usuário tenta cadastrar um produto que já existe.



\### Comportamento do sistema



\- Bloqueia o cadastro duplicado

\- Exibe mensagem clara

\- Direciona o usuário para o produto existente



\### Critérios de aceite



\- Sistema não deve permitir duplicidade

\- Usuário deve entender o motivo do bloqueio

\- A experiência não deve ser frustrante



---



\## 💬 Mensagens e feedbacks



O sistema deve sempre:



\- informar o que aconteceu

\- orientar o próximo passo

\- evitar mensagens técnicas



Exemplos esperados:



\- “Produto não encontrado. Deseja cadastrar?”

\- “Este produto já existe no sistema.”

\- “Cadastro realizado com sucesso.”



---



\## 🧪 Base para testes (QA)



Este fluxo serve como base para:



\- cenários de teste manuais

\- automação E2E com Cypress

\- validação de regressões

\- testes de borda (digitação errada, campos vazios, duplicidade)



---



\## 🔮 Evolução futura



Na Fase 2, este fluxo poderá incluir:



\- sugestões automáticas de preço

\- apoio à precificação baseada em mercado

\- integração com fontes externas

\- melhoria no fluxo via scanner/câmera



