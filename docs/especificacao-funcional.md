# 📘 Especificação Funcional — Etc & Deia Inventory Hub

Documento funcional que descreve **o que o sistema faz**,  
seus **fluxos principais**, **regras de negócio** e **critérios de aceite**,  
com foco na **operação real de uma loja de pequeno porte**.

Este documento é **independente de implementação técnica**  
e serve como base para:
- entendimento do produto
- validação de comportamento
- apoio à automação de testes
- evolução controlada do sistema

---

## 🎯 Visão geral

O **Etc & Deia Inventory Hub** é um sistema web de gestão de **produtos, estoque e vendas**,  
criado para apoiar a rotina de **pequenas lojas de varejo**, com foco em:

- simplicidade
- usabilidade real
- mensagens claras
- redução de erro humano
- apoio à tomada de decisão

O sistema foi pensado para usuários **sem experiência técnica**, priorizando fluxos guiados,
feedback visual e facilidade de uso no dia a dia da loja.

---

## 🎯 Escopo do sistema

### ✔️ O que o sistema faz

O sistema permite:

- Cadastro de produtos com:
  - nome do produto
  - código de barras (manual ou via leitura)
  - categoria
  - preço de custo
  - preço de venda
  - controle de estoque

- Busca de produtos:
  - por **nome**
  - por **código de barras**
  - com normalização para evitar erros de digitação

- Gestão de estoque:
  - visualização de quantidade disponível
  - alerta de estoque baixo
  - apoio à decisão de reposição

- Dashboard gerencial:
  - produtos com maior saída
  - produtos com menor saída
  - acompanhamento de vendas
  - visão de valor bruto e valor líquido

- Fluxo de vendas (base de PDV):
  - seleção de produtos
  - simulação de venda
  - cálculo de valores
  - estrutura preparada para evolução do PDV

- Mensagens claras e orientadas ao usuário:
  - feedback visual
  - orientação em caso de erro
  - fluxo assistido quando um produto não é encontrado

---

### ❌ O que o sistema não faz (nesta fase)

Nesta fase, o sistema **não contempla**:

- Integração com meios de pagamento
- Emissão de nota fiscal
- Impressão de comprovantes
- Controle fiscal ou contábil
- Integração direta com fornecedores
- Autenticação e controle de usuários

Essas funcionalidades são consideradas **fora do escopo da Fase 1**.

---

### 🔮 Evoluções previstas (Fase 2)

- Evolução do fluxo de vendas para PDV completo
- Integração com impressora térmica
- Apoio à precificação inteligente
- Sugestão de preços baseada em:
  - custo de compra
  - preços praticados no mercado
  - margem mínima de lucro
- Integrações externas para apoio à decisão

---

## 👥 Perfis de usuário

### Operador de loja

Usuário responsável pela operação diária.

Características:
- pouca ou nenhuma experiência com sistemas
- foco em rapidez e simplicidade
- necessidade de orientação clara

Principais ações:
- cadastrar produtos
- buscar produtos
- consultar estoque
- realizar vendas
- interpretar alertas

---

## 🔄 Fluxos principais

### Fluxo: Cadastro de produto

1. Usuário acessa a tela de produtos
2. Inicia o cadastro
3. Informa nome ou código de barras
4. Sistema valida e normaliza os dados
5. Usuário preenche informações complementares
6. Produto é salvo e disponibilizado no sistema

---

### Fluxo: Busca de produto

1. Usuário informa nome ou código
2. Sistema identifica o tipo de busca
3. Aplica normalização adequada
4. Retorna:
   - produto encontrado
   - lista de produtos
   - ou mensagem orientativa caso não encontre

---

### Fluxo: Venda (simulação)

1. Usuário acessa a tela de vendas
2. Busca e seleciona produtos
3. Sistema calcula valores
4. Exibe resumo da venda
5. Estrutura preparada para finalização futura (PDV)

---

## ✅ Critérios de aceite (base para QA)

- O sistema deve permitir cadastro de produto sem erros de validação indevidos
- A busca por nome não deve aplicar regras de código de barras
- A busca por código deve aceitar apenas números
- O sistema deve exibir mensagens claras em caso de erro
- Alertas de estoque devem ser visíveis no dashboard
- Nenhuma ação crítica deve ocorrer sem feedback ao usuário

---

## 🧪 Qualidade e testes

Este documento serve como base para:
- criação de cenários de teste
- automação E2E com Cypress
- validação de regressões
- evolução segura do sistema
