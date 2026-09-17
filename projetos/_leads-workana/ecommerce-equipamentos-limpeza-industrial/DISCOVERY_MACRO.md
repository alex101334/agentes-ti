# Discovery macro — Lead Workana: E-commerce para equipamentos de limpeza industrial (painéis solares/estufas)

> Status: **PROSPECTO — projeto ainda não aceito.** Esta pasta vive fora de `projetos/<cliente>/` de propósito (ver `CLAUDE.md` raiz do repo agentes-ti: a pasta de cliente só nasce depois do projeto aceito). Este arquivo é o registro do skill `estimativa-macro-projeto`, **passos 1-2 apenas** (discovery macro + mapa de escopo). Passos 3-7 (estimativa por agente, PERT de custo, consolidação do Gerente de Projeto) **não foram executados** — não fazem parte do que foi pedido nesta rodada.

## 1. Dados da vaga (fonte: anúncio Workana, não houve entrevista real — não existe cliente para entrevistar)

- **Título:** Desenvolvimento de E-commerce Completo para Equipamentos de Limpeza Industrial
- **URL:** https://www.workana.com/job/desenvolvimento-de-e-commerce-completo-para-equipamentos-de-limpeza-industrial (fetch direto bloqueado por 403 — Workana não permite leitura anônima da página completa; todo o levantamento abaixo vem do texto do anúncio já fornecido pelo usuário)
- **Categoria:** TI e Programação / Lojas Virtuais (e-commerce)
- **Orçamento no anúncio:** Aberto (cliente não fixou valor)
- **Prazo no anúncio:** Não estabelecido
- **Concorrência:** 64 propostas / 79 freelancers interessados no momento da consulta (17/09/2026)
- **Cliente:** 1 projeto publicado, 0 projetos pagos — sem histórico de contratação na plataforma
- **Nicho do cliente:** fabricante/comercializador de equipamentos para limpeza de painéis solares e "estufas patenteadas", venda B2B/industrial para todo o Brasil

## 2. Mapa de escopo macro (épicos, não stories) — ver StructuredOutput desta sessão para a versão entregue ao usuário

Registrado apenas como referência de rastreio; a lista completa com leitura de plataforma e riscos foi entregue via `StructuredOutput` na conversa que gerou este arquivo (não duplicar aqui para evitar divergência entre duas fontes — se o mapa mudar, atualizar os dois juntos).

## 3. Pesquisa de domínio feita antes de opinar (Regra 1 — pesquisar antes de decidir)

- Comparativo de plataforma de e-commerce BR 2026 (Nuvemshop/VTEX/WooCommerce/Magento) — ver fontes citadas na resposta estruturada.
- Integração de frete BR (API Correios, gateways de frete tipo Melhor Envio/Frenet/Kangu/Intelipost).
- Gateways de pagamento BR com parcelamento (Pagar.me, Mercado Pago, PagSeguro/PagBank) — taxas aproximadas e observação de que a aprovação de conta em adquirente é dependência externa (não comprime com velocidade de agente).
- Obrigatoriedade de NF-e (modelo 55) para venda de produto por e-commerce no Brasil — não citada no anúncio, tratada como risco de escopo (ver StructuredOutput).
- Padrão de venda B2B industrial (orçamento sob consulta, preço por CNPJ/volume) — nicho de "equipamento industrial" tende a fugir do carrinho 100% auto-serviço padrão de e-commerce B2C.

## 4. Próximos passos, SE o usuário decidir seguir com uma proposta

1. Não orçar/prometer prazo fechado sem antes obter resposta do cliente às perguntas de risco listadas no StructuredOutput (orçamento sob consulta ou preço fixo? volume de SKU? plataforma existente ou zero? NF-e via qual emissor/ERP? dimensão/peso típico do equipamento para frete?).
2. Se o usuário decidir propor, considerar uma "fase 0 paga" de descoberta/discovery formal antes de fechar escopo e preço — mitiga o risco de cliente sem histórico + orçamento aberto + alta concorrência (64 propostas), que juntos empurram para subestimar.
3. Só depois de o cliente responder e o projeto ser de fato aceito: criar `projetos/<slug-do-cliente>/`, rodar os passos 3-7 do skill `estimativa-macro-projeto` (estimativa por agente em T-shirt size, PERT de custo via `CUSTO_MERCADO_SP.md`, consolidação do Gerente de Projeto) e só então iniciar o fluxo normal do `CLAUDE.md` (backlog detalhado, DoR/DoD, etc.).

## 5. Histórico

- 2026-09-17 — Discovery macro (passos 1-2) feito a partir do texto do anúncio Workana fornecido pelo usuário + pesquisa de mercado de domínio (Regra 1). Entregue como resposta estruturada (mapa de escopo, leitura de stack, riscos). Nenhum agente técnico foi consultado ainda (passos 3+ pendentes, condicionados à decisão do usuário de seguir com a proposta).
- 2026-09-17 — Passo 3 (fatia do UX/UI Designer) estimado em cima do mapa de escopo do PO, com pesquisa de domínio prévia (Regra 1: UX de e-commerce B2B industrial, padrão carrinho×orçamento-sob-consulta, guideline de handoff/acessibilidade WooCommerce). Entregue via `StructuredOutput` na conversa (não duplicado aqui — ver nota da seção 2 sobre evitar divergência entre fontes). Cobre IA/fluxos, wireframes lo-fi, UI visual + design system, protótipo navegável + handoff Dev Mode, e apoio a QA de usabilidade pré-sign-off; **não** cobre implementação, conteúdo/fotografia de produto, nem decisão de plataforma (isso seguirá sendo pergunta de descoberta ao cliente, como já registrado na seção 4). Ainda pendente: estimativa dos demais agentes (Dev, Arquiteto, QA, etc.) e consolidação do Gerente de Projeto (passos 3 restantes → 6).
