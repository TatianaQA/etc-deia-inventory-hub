\# 🛠 Requisitos Técnicos — Etc \& Deia Inventory Hub



Este documento descreve os \*\*requisitos técnicos mínimos e recomendados\*\*

para execução, uso e evolução do \*\*Etc \& Deia Inventory Hub\*\*.



O foco é garantir \*\*uso simples, baixo custo e compatibilidade\*\*

com a realidade de pequenas lojas de varejo.



---



\## 🎯 Objetivo



Garantir que o sistema:



\- funcione em ambientes comuns (sem infraestrutura complexa)

\- seja acessível a usuários não técnicos

\- suporte leitura de código de barras

\- tenha desempenho aceitável em cenários reais

\- seja facilmente evolutivo



---



\## 💻 Ambiente de Execução



\### Requisitos mínimos



\- Dispositivo:

&nbsp; - Notebook ou desktop

&nbsp; - Smartphone (uso complementar)

\- Sistema operacional:

&nbsp; - Windows 10 ou superior

&nbsp; - macOS

&nbsp; - Android / iOS (navegador)

\- Conexão:

&nbsp; - Internet estável (banda comum residencial)



---



\### Requisitos recomendados



\- Notebook com:

&nbsp; - mínimo 8 GB RAM

&nbsp; - navegador atualizado

\- Uso de teclado + leitor de código de barras físico

&nbsp; \*\*ou\*\*

\- Smartphone com câmera funcional para leitura de código



---



\## 🌐 Navegadores Suportados



\### Navegadores recomendados



\- Google Chrome (principal)

\- Microsoft Edge (Chromium)

\- Safari (iOS/macOS)



\### Observações



\- O sistema depende de:

&nbsp; - suporte a JavaScript moderno

&nbsp; - APIs de câmera (quando usado scanner por câmera)

\- Navegadores desatualizados podem gerar comportamento inesperado



---



\## 📷 Leitura de Código de Barras



\### Modos suportados



1\. \*\*Scanner físico USB\*\*

&nbsp;  - Atua como teclado

&nbsp;  - Compatível com leitores padrão de mercado

&nbsp;  - Não requer driver específico no sistema



2\. \*\*Câmera do dispositivo\*\*

&nbsp;  - Utiliza câmera do celular ou notebook

&nbsp;  - Interface abre automaticamente para leitura

&nbsp;  - Requer permissão de câmera no navegador



---



\### Requisitos para uso de câmera



\- Navegador com permissão ativa de câmera

\- Ambiente com iluminação mínima

\- Câmera funcional



---



\## 📦 Limitações conhecidas



\- Leitura por câmera pode ser afetada por:

&nbsp; - baixa iluminação

&nbsp; - câmeras antigas

&nbsp; - códigos danificados

\- Busca por código depende de:

&nbsp; - normalização correta

&nbsp; - entrada numérica válida

\- Integrações externas ainda não são automáticas (Fase 1)



---



\## 🔐 Segurança e dados



\- O sistema:

&nbsp; - não exige login na Fase 1

&nbsp; - não armazena dados sensíveis de clientes

\- Dados manipulados:

&nbsp; - produtos

&nbsp; - preços

&nbsp; - estoque

&nbsp; - vendas



---



\## 🧪 Testes e Qualidade



\### Ferramentas



\- Cypress (testes E2E)



\### Escopo de testes



\- Navegação entre telas

\- Busca por nome e código

\- Fluxos de produto

\- Fluxos de venda

\- Atualização de estado visual



---



\## 🚀 Evolução técnica planejada (Fase 2)



\- Persistência em banco de dados

\- Integração com APIs externas

\- Estratégia de precificação assistida

\- Controle de usuários

\- Impressão de comprovante de venda (PDV)

\- Suporte a impressora térmica



---



\## 📌 Considerações finais



Os requisitos técnicos foram definidos com foco em:



\- \*\*baixo custo\*\*

\- \*\*simplicidade\*\*

\- \*\*manutenção fácil\*\*

\- \*\*aderência à realidade de lojas pequenas\*\*



A proposta é evoluir o sistema \*\*sem criar dependência de infraestrutura complexa\*\*.



