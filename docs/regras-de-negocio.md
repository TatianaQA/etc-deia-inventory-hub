\# 📐 Regras de Negócio — Etc \& Deia Inventory Hub



Documento que descreve as \*\*regras de negócio centrais\*\* do sistema,  

conectando os domínios de \*\*Produtos\*\*, \*\*Vendas\*\* e \*\*Preço\*\*.



Estas regras definem \*\*como o sistema deve se comportar\*\*,  

independente de interface ou implementação técnica.



---



\## 🎯 Objetivo das regras



Garantir que o sistema:



\- reflita a operação real da loja

\- evite erros humanos

\- mantenha consistência entre estoque, vendas e valores

\- suporte tomada de decisão do lojista

\- sirva como base para testes e automação



---



\## 🧩 Domínios envolvidos



\- \*\*Produto\*\*

\- \*\*Venda\*\*

\- \*\*Preço\*\*

\- \*\*Estoque\*\*

\- \*\*Dashboard\*\*



---



\## 🏷️ Regras do domínio de Produto



\### RN-PROD-01 — Identificação única de produto



\- Todo produto deve possuir:

&nbsp; - nome

&nbsp; - código (quando aplicável)

\- O sistema deve evitar duplicidade de cadastro



\*\*Critério:\*\*

\- produtos com mesmo nome normalizado ou mesmo código não devem ser duplicados



---



\### RN-PROD-02 — Normalização de busca



\- Busca por \*\*código de barras\*\*:

&nbsp; - aceita apenas números

&nbsp; - remove espaços

\- Busca por \*\*nome\*\*:

&nbsp; - mantém espaços

&nbsp; - aplica lowercase, trim e colapso de múltiplos espaços



\*\*Objetivo:\*\*  

evitar falsos negativos e erros de busca.



---



\### RN-PROD-03 — Produto não encontrado



\- Quando um produto não for encontrado:

&nbsp; - o sistema deve informar claramente

&nbsp; - oferecer ação de cadastro quando permitido



---



\## 📦 Regras do domínio de Estoque



\### RN-EST-01 — Estoque mínimo



\- Todo produto deve possuir quantidade em estoque

\- Quantidade não pode ser negativa



---



\### RN-EST-02 — Alerta de estoque baixo



\- Quando o estoque atingir o limite mínimo:

&nbsp; - sistema deve sinalizar no dashboard

&nbsp; - produto entra na lista de atenção



\*\*Objetivo:\*\*  

evitar ruptura de estoque.



---



\### RN-EST-03 — Atualização automática de estoque



\- A cada venda finalizada:

&nbsp; - o estoque do produto deve ser reduzido automaticamente

\- Cancelamento de venda não deve impactar estoque



---



\## 💰 Regras do domínio de Preço



\### RN-PRE-01 — Preço obrigatório



\- Todo produto deve possuir um preço válido

\- Preço não pode ser zero ou negativo



---



\### RN-PRE-02 — Formatação monetária



\- Todos os valores exibidos devem:

&nbsp; - estar formatados corretamente

&nbsp; - seguir padrão monetário consistente



---



\### RN-PRE-03 — Preço como base de cálculo



\- O preço do produto é a base para:

&nbsp; - subtotal da venda

&nbsp; - total da venda

&nbsp; - indicadores do dashboard



---



\## 🧾 Regras do domínio de Venda



\### RN-VEN-01 — Venda deve conter ao menos um item



\- Não é permitido finalizar venda sem itens



---



\### RN-VEN-02 — Inclusão de item na venda



\- Ao adicionar um produto:

&nbsp; - sistema recalcula subtotal

&nbsp; - atualiza total

&nbsp; - mantém lista visível



---



\### RN-VEN-03 — Ajuste de itens



\- Operador pode:

&nbsp; - remover item da venda

\- Sistema deve:

&nbsp; - recalcular valores automaticamente

&nbsp; - manter consistência visual



---



\### RN-VEN-04 — Finalização de venda



\- Venda só pode ser finalizada se:

&nbsp; - houver itens

&nbsp; - valores estiverem válidos

\- Ao finalizar:

&nbsp; - venda é registrada

&nbsp; - estoque é atualizado

&nbsp; - feedback visual é exibido



---



\## 📊 Regras do Dashboard



\### RN-DASH-01 — Visão de vendas



\- Dashboard deve exibir:

&nbsp; - total de vendas

&nbsp; - quantidade de itens vendidos

&nbsp; - produtos com maior saída

&nbsp; - produtos com menor saída



---



\### RN-DASH-02 — Apoio à decisão



\- Produtos com alta saída:

&nbsp; - indicam necessidade de reposição

\- Produtos com baixa saída:

&nbsp; - indicam excesso de estoque

&nbsp; - possibilidade de promoção ou substituição



---



\## 🧪 Base para Qualidade e Testes



Estas regras servem como base para:



\- criação de cenários de teste

\- testes manuais

\- automação E2E

\- validação de regressão

\- alinhamento entre QA, PO e negócio



---



\## 🔮 Evolução futura



Na Fase 2, novas regras poderão incluir:



\- margem de lucro

\- precificação assistida

\- comparação com preços externos

\- indicadores financeiros mais avançados



