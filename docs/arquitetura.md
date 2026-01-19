\# Arquitetura — Etc \& Deia Inventory Hub



\## Visão geral

O \*\*Etc \& Deia Inventory Hub\*\* é um sistema web de gestão de \*\*produtos, estoque e vendas\*\* para \*\*pequenas lojas de varejo\*\*.  

O foco é \*\*usabilidade real\*\*, mensagens claras e fluxos simples, pensando em operação diária (ex.: cadastro rápido, busca por nome/código, alertas e visão de negócio).



> Este projeto foi construído no \*\*Lovable\*\* (React + TypeScript) por escolha consciente: acelera prototipação e evolução do produto, permitindo iterar rápido com qualidade mesmo sendo um projeto solo (QA + PO + PM + gestão).



---



\## Stack e abordagem

\- \*\*Frontend:\*\* React + TypeScript

\- \*\*Estilo/UI:\*\* componentes reutilizáveis por domínio (dashboard/produtos/vendas)

\- \*\*Dados:\*\* fase inicial com estrutura de domínio + serviços (mock/integrações evolutivas)

\- \*\*Qualidade:\*\* testes E2E com \*\*Cypress\*\* (pasta separada para automação)



---



\## Organização por camadas

O código é organizado por responsabilidade:



\### `src/pages/`

Telas principais do sistema.

\- `Dashboard.tsx`

\- `Products.tsx`

\- `Sales.tsx`



\### `src/components/`

Componentes reutilizáveis por domínio:

\- `layout/` (layout, sidebar, containers)

\- `dashboard/` (cards, gráficos, alertas)

\- `products/` (tabela, formulários, modais)

\- `sales/` (busca, seleção, itens da venda)

\- `common/` (componentes genéricos)



\### `src/services/`

Camada de serviços que centraliza regras de acesso/consulta:

\- `searchService.ts` (busca e regras de consulta)

\- `productService.ts` (operações do domínio de produto)

\- `pricingService.ts` (precificação e cálculos)



\### `src/hooks/`

Hooks para encapsular comportamento e estado:

\- `useProductSearch.ts` (busca por nome/código e controle do fluxo)



\### `src/utils/`

Funções utilitárias e normalização:

\- `normalizeBarcode.ts` (normalização de código de barras)

\- `normalizeText.ts` (normalização de nome/texto)

\- `formatCurrency.ts` (formatação monetária)



\### `src/types/`

Tipos do domínio:

\- `product.ts`



\### `src/data/`

Dados de apoio (mock) para fase inicial / simulação:

\- `mockData.ts`



---



\## Decisões técnicas (importantes)

\### 1) Separação de normalização: código vs nome

\- \*\*Código de barras:\*\* remove espaços e aceita apenas números.

\- \*\*Nome do produto:\*\* mantém espaços e normaliza apenas lowercase/trim/colapso de múltiplos espaços.  

Isso evita erros de busca e melhora a experiência real.



\### 2) Serviços como “fonte de verdade”

Regras de busca, seleção e mensagens ficam centralizadas em `services/` e `hooks/`, evitando lógica espalhada em componentes.



\### 3) UI guiada por fluxo real

As telas e mensagens foram pensadas para operação de loja:

\- reduzir erro humano

\- orientar o usuário

\- minimizar cliques

\- facilitar correção quando algo não é encontrado



---



\## Qualidade e testes

A automação E2E com \*\*Cypress\*\* é usada para validar fluxos críticos (Dashboard, Produtos, Vendas), garantindo regressão controlada ao evoluir o produto.



---



\## Evolução planejada

A Fase 2 prevê expansão do módulo de vendas (PDV), melhorias de UX, e estratégia de precificação assistida para apoiar lucro real da loja.



