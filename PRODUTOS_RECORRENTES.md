# Produtos recorrentes (SaaS/mensalidade) — a partir do Radar de Demanda

## 0. Contexto e objetivo

Este documento consolida a leitura macro do `radar-demanda/` (630 vagas reais do 99Freelas + Workana, snapshot 2026-09-18) em **5 propostas de produto/sistema recorrente** que a agência pode construir uma vez e vender por mensalidade, em vez de cotar projeto sob medida cliente a cliente. A leitura não ficou nas tags/contagens do radar: cada grupo de demanda com mais de 10 vagas (excluindo `jogos`, por instrução do usuário) teve a **descrição completa de cada vaga lida por um agente dedicado**, não só o título — os números e citações abaixo são rastreáveis a vagas específicas do dataset, não estimativa.

Objetivo de negócio: quando um padrão de demanda se repete dezenas de vezes entre clientes não relacionados, vale mais manter **um produto configurável** do que reescrever a mesma solução do zero a cada cotação — isso reduz o preço para o cliente (mensalidade < projeto do zero) e dá receita recorrente para a agência.

**Princípio arquitetural inegociável para o próximo passo (arquitetura/requisitos por ferramenta): modularidade e independência.** Os 5 produtos abaixo compartilham padrões e às vezes dados (ex.: cadastro de cliente, agenda), mas cada um deve poder ser vendido, provisionado, cobrado e desligado **independentemente** por cliente. Comunicação entre produtos é sempre integração explícita (API/webhook versionado, opt-in por cliente) — nunca leitura direta de banco/tabela de outro produto, nunca deploy conjunto obrigatório. Isso vale com força especial para o Produto 2 (WhatsApp + IA), detalhado no §3.

---

## 1. Panorama de origem (recap)

Grupos do radar com >10 vagas, excluindo `jogos` (24 vagas, fora de escopo por instrução do usuário) e `outro` (36, não é categoria real):

| Grupo (categoria_principal do radar) | Vagas | Achado de sobreposição | Mapeado para |
|---|---|---|---|
| `whatsapp_automacao` | 121 | ~25% é só "site com botão de WhatsApp" (ruído); ~30 vagas quase idênticas de "resposta automática com IA" | Produto 2 |
| `ecommerce_loja` | 92 | — | Produto 4 |
| `app_mobile` | 89 | Tag aplicada de forma ampla — parte relevante é site/jogo/hardware sem relação real com app | Produto 5 (parte) |
| `agente_ia_voz_chat` | 77 | Só ~35-40 das 77 são de fato sobre agente/IA — resto é cross-tag de site/app/jogo | Produto 2 (parte) + Produto 5 (parte) |
| `site_institucional_lp` | 49 | 12 das 14 vagas de `marketing_tracking_seo` também levam esta tag — é o mesmo momento de compra | Produto 3 |
| `dashboard_bi_planilha` | 38 | 17/38 (~45%) também levam a tag `sistema_sob_medida_gestao` | Produto 1 |
| `crm_erp_vendas` | 37 | 13/37 (~35%) também levam a tag `sistema_sob_medida_gestao` | Produto 1 |
| `sistema_sob_medida_gestao` | 14 | é o mesmo pool de `dashboard_bi_planilha`+`crm_erp_vendas` visto de outro ângulo | Produto 1 |
| `marketing_tracking_seo` | 14 | ver `site_institucional_lp` acima | Produto 3 |

**Achado transversal que atravessa os 6 relatórios de análise, independentemente:** cliente que começou um app/site/agente num no-code ou IA-builder (FlutterFlow, Base44, Lovable, Manus, Framer, Bubble) e **travou** — pedindo para terminar, não para recomeçar do zero. Isso não é exclusivo de nenhum grupo — é o Produto 5.

**Validação direta do modelo de mensalidade, nas próprias palavras de dois clientes reais:** um pediu um ERP "multi-CNPJ, com login para outras empresas usarem e **pagarem mensalidade**" (`crm_erp_vendas` #003) — descreveu o próprio modelo de negócio que a agência está avaliando; outro já paga fixo mensal por manutenção de sistema sob medida (`crm_erp_vendas` #009).

**Sinal de orçamento em todos os grupos:** o campo estruturado do radar não presta — 99Freelas grava R$50 fixo (piso da plataforma) em 100% das vagas, Workana grava `None` em 100%. O sinal real é a contagem de `propostas` (concorrência) e a linguagem do texto: pedidos genéricos e comoditizados atraem 100-300+ propostas (ex.: site institucional simples de contabilidade, 311 propostas — a maior contagem do dataset inteiro); pedidos verticais com múltiplos módulos não têm concorrência alta mas também nunca declaram preço, só estrutura de pagamento por marco.

---

## 2. Os 5 produtos

### Produto 1 — Núcleo Modular de Gestão (mini-ERP multi-tenant)

**Origem:** `dashboard_bi_planilha` (38) + `crm_erp_vendas` (37) + `sistema_sob_medida_gestao` (14), com ~30 vagas sobrepostas entre os três.

**Sub-padrões identificados (com evidência):**
- **A. Sair de planilha Excel/Sheets para sistema web** (~7 vagas) — controle de estoque em VBA de fábrica de caixinhas plásticas; sistema de gestão de consultório de fonoaudiologia hoje em Excel/Sheets; CRM de escritório de advocacia construído em Google Apps Script.
- **B. CRM de funil simples para negócio pequeno de serviço local** (~6) — clínica e barbearia, ambas já usando Kommo e pedindo reconfiguração/automação.
- **C. Integração de CRM/ERP existente com outro canal** (~9) — Bling + TikTok Shop, Pipedrive + site/canais de mídia, HubSpot migrando para Zoho.
- **D. Sistema de gestão comercial/ERP sob medida — o núcleo real da demanda** (~12) — inclui o pedido literal de ERP multi-CNPJ com mensalidade (#003) e o cliente que já paga retainer mensal de manutenção (#009); também um pedido de "SaaS/ERP" completo com módulos de RH, DP, Ponto, Financeiro e Portal do Colaborador.
- **E. Dashboard/BI multi-fonte sem sistema próprio por trás** (~7) — inclui um caso que exige explicitamente funcionar só com ferramentas gratuitas (Google Forms + Sheets + Looker Studio + Apps Script, "sem necessidade de assinaturas pagas").
- **F. Verticais de nicho com o mesmo módulo-set repetido** (~13) — ERP de academia (alunos, planos, financeiro, treinos), sistema de aluguel de bikes elétricas (cadastro + contrato + pagamento semanal), hospedagem por temporada, delivery, agência de turismo — todos reduzem ao mesmo conjunto (cadastro cliente/produto + financeiro + agenda + dashboard).

**Ferramentas citadas (contexto: substituir ou integrar):** Excel/VBA e Google Sheets/Apps Script (base a evoluir), Power BI e Looker Studio (camada de visualização isolada), Zoho (suíte a expandir), Kommo e Pipedrive (CRM a reconfigurar/integrar), Bling e Tiny ERP (a integrar), Base44/Lovable (migrando **de**, no-code que travou).

**Ausências notáveis:** RD Station, Conta Azul, Omie e Airtable não aparecem nenhuma vez nos 89 registros — não assumir demanda por eles.

**O que é:** motor único de cadastro de cliente/produto, estoque, financeiro (contas a pagar/receber, DRE simples), agenda de recurso e dashboard gerencial, com módulos ativáveis por assinatura e multiempresa desde o design.

**O que substitui:** cotação de "ERP próprio" sob medida (uma das vagas do dataset tinha 215 páginas de caderno técnico) ou planilha frágil que quebra quando o negócio cresce.

**Por que mensalidade funciona:** o próprio dataset já mostra cliente pagando fixo mensal por manutenção de sistema sob medida (#009) e cliente pedindo o modelo multiempresa com mensalidade por extenso (#003) — a demanda pelo formato de cobrança já existe, falta o produto ser genérico o bastante para não custar reconstrução a cada venda.

---

### Produto 2 — Atendente WhatsApp Config (WhatsApp + IA, via integração oficial com a Meta)

**Origem:** `whatsapp_automacao` (121, maior grupo do radar) + parte de `agente_ia_voz_chat` (atendimento automatizado para PME) + parte de `crm_erp_vendas` (CRM + WhatsApp para clínica/barbearia/turismo/imobiliária).

**Sub-padrões identificados:**
- **A. Atendente de IA genérico 24h no WhatsApp, sem integração de sistema real** — o padrão mais repetido do dataset inteiro: pelo menos 6 títulos quase verbatim idênticos ("Desenvolvimento de Sistema de Respostas Automáticas com IA para WhatsApp") e ~24 variações do mesmo pedido curto, quase todos no Workana, sem contexto de negócio específico.
- **B. Site/LP/loja com WhatsApp só como botão de contato** (~30 vagas, quase todas 99Freelas) — ruído a descartar da leitura de "automação de verdade", mas confirma que WhatsApp é o canal de contato padrão do pequeno negócio brasileiro.
- **C. CRM comercial + WhatsApp Business API com funil e/ou agendamento** (~13) — clínica de estética em Dublin explicitamente recusando "chatbot básico ou prototype"; ecossistema completo de clínica médica (LP + IA omnichannel + agenda anti-no-show + CRM + BI); agendamento com marcos de pagamento de 5% a 30% por etapa.
- **D. Disparo em massa/lista de transmissão** (~6) — inclui pedido de 5.000 contatos via API oficial + ManyChat.
- **E. Integração de WhatsApp com sistema/ERP já existente** (~6) — inclui bot conectando a Oracle MICROS Simphony de rede de restaurante via n8n.
- **F. Qualificação/recuperação de vendas via IA** (~6) — recuperação de carrinho abandonado em 2-10 minutos + régua de recompra em 15 dias (loja de vinhos).
- **G. Diagnóstico/compliance de conta Meta, sem escrever código** (~3) — **dois clientes recusam explicitamente "disparadores, extensões, automações não oficiais"** por medo de bloqueio de número — validação direta, nas palavras do próprio cliente, da dor que a decisão do §3 resolve.

**Ferramentas citadas:** n8n (motor de orquestração em 11 vagas, nunca o produto final), Kommo (CRM+WhatsApp mais citado, 5 vagas), Evolution API (2, modo não-oficial), WhatsApp Business API/Cloud API citada nominalmente 10x, OpenAI/GPT/Claude (sempre como "motor" chamado via API, nunca treino próprio), ManyChat (2).

**Ligação com `agente_ia_voz_chat`:** o mesmo padrão de "atendimento automatizado para PME" aparece lá, incluindo um caso documentado de DIY que fracassou — cliente que tentou construir o próprio agente internamente e relata "erros frequentes e alto custo de tokens" — validação direta de produto pronto vs. construir sozinho.

**O que é:** SaaS de configuração sem código de atendimento no WhatsApp Cloud API oficial (FAQ, catálogo, horário, transbordo humano), com módulo vertical de agenda+funil para clínica/barbearia/turismo/imobiliária por cima.

**O que substitui:** contratar freelancer para montar o mesmo bot em n8n/Typebot do zero a cada vaga — e a prática hoje comum de rodar em Evolution API/Z-API não-oficial, com risco de banimento.

**Por que mensalidade funciona:** o pedido já vem sem particularidade de negócio real — é configuração, não código sob medida; cobrança por volume de mensagem acompanha o próprio custo variável (que já é recorrente por natureza).

**Ver §3 para a decisão de integração direta com a Meta e as implicações de arquitetura por cliente.**

---

### Produto 3 — Resgate & Blindagem WordPress + Site-Assinatura para Profissional Liberal

**Origem:** `site_institucional_lp` (49) + `marketing_tracking_seo` (14, 12 das 14 sobrepostas com o grupo anterior).

**Sub-padrões identificados:**
- **A. Site institucional simples (profissional liberal/pequeno negócio)** (~13-15) — o maior bloco; a vaga de site institucional de contabilidade teve **311 propostas**, a maior contagem de todo o dataset de 630 vagas.
- **B. Landing page de infoproduto/curso/lançamento** (~8).
- **C. Migração/resgate de site legado quebrado** (~7-8) — site rodando em PHP 7.4 descontinuado e vulnerável; cliente que comprou hospedagem + domínio e travou no meio do setup do WordPress; migração de Framer para WordPress; migração de builders de IA (**Base44**, **Manus**) para código próprio "sem depender da plataforma original".
- **D. Construtor no-code já escolhido pelo cliente, não pedido de feature** (~5) — Elementor, Lovable, Framer, Wix.
- **E. Pixel/tag de conversão quebrado** (2 vagas, dor pequena em volume mas "invisível até doer" — cliente só percebe quando já perdeu conversão de campanha paga).
- **F. SEO técnico/conteúdo** (~7).
- **G. Sistema sob medida disfarçado de "site"** (~5-6) — o caso mais revelador é um funil ponta-a-ponta completo (tráfego pago → LP → qualificação de lead → contrato digital → assinatura eletrônica → pagamento → área do cliente → **renovação anual**), descrito por um cliente que não sabe nomear que está pedindo um mini-SaaS de funil+CRM.

**Ferramentas citadas:** WordPress (~16 vagas, de longe a mais citada, tanto como destino de migração quanto como fonte de dor por update quebrado), Elementor (5), Wix (3), Framer (2, tanto destino "profissional" quanto algo que o cliente quer abandonar), Lovable (2), Base44/Manus (2, migrando **de**).

**O que é:** (i) onboarding padronizado de migração/resgate para WordPress + plano mensal de manutenção (backup automatizado, staging em toda atualização, monitoramento de quebra pós-update); (ii) template configurável (não site sob medida) para profissional liberal/PME com as 3-5 páginas padrão que se repetem entre profissões distintas.

**O que substitui:** cotação avulsa de site institucional simples via marketplace (que concorre com 100-300 outras propostas de preço baixíssimo) e o ciclo de "só mais um ajuste emergencial" quando o WordPress quebra sem manutenção contratada.

**Por que mensalidade funciona:** WordPress quebra de forma recorrente e previsível (ciclo de update de core/PHP/plugin) — não é evento único, é manutenção contínua por natureza; o adapter MCP oficial de WordPress (lançado fev/2026) torna essa manutenção operável por agente de IA em vez de dev humano monitorando manualmente.

---

### Produto 4 — Painel Ponte (middleware ERP ↔ loja ↔ marketplace)

**Origem:** `ecommerce_loja` (92 vagas).

**Sub-padrões identificados:**
- **A. Middleware ERP (Bling/Tiny) ↔ loja própria ↔ marketplaces + NF-e/estoque** (~12) — cliente querendo centralizar Monetizze + Bling + Envio Ecom + Melhor Envio num sistema próprio; NF-e emitida no Bling demorando para refletir no pedido do WooCommerce.
- **B. Catálogo com variação complexa (cor/tamanho/kit)** (~10) — **duas clientes diferentes, sem relação entre si, reportaram o mesmo problema exato de fotos de produto associadas ao produto errado** — sinal direto de padrão real, não coincidência.
- **C. "Quero um Mercado Livre do meu nicho" — marketplace multivendedor MVP** (~11) — **duas vagas quase idênticas** pedindo marketplace estilo GGMAX para público gamer, postadas por clientes diferentes.
- **D. Cadastro/gestão em marketplaces terceiros como serviço recorrente** (~9) — cliente já sinaliza explicitamente "possibilidade de continuarmos mensalmente se o trabalho apresentar bons resultados".
- **E. "Não quero do zero, quero terminar/configurar" loja já criada** — o maior bucket do grupo (~15-20).
- **F. Tracking/pixel/conversão quebrado** (~6) — inclui GTM Server-side sem o cliente essencial configurado.
- **G. Retomada de projeto abandonado** (~5).
- **H. Motor de precificação multicanal / margem** (3 vagas, perfil "cliente enterprise") — recalculo de margem por SKU considerando comissão + frete + Ads de 5 marketplaces, com a exigência explícita de que "não serão aceitos diagnósticos, dashboards isolados ou templates vazios".

**Ferramentas citadas (com direção):** Shopify (12, destino de migração e uso direto), Nuvemshop (10), Mercado Livre (10, canal a integrar, nunca migração), Bling (9), WooCommerce (8), Shopee (8), GA4 (7), Amazon/Magalu (5 cada), Meta Pixel/CAPI (5), TikTok Shop (4), NF-e (4). **Magento não aparece nenhuma vez; VTEX aparece só 1x.**

**O que é:** middleware que sincroniza Bling/Tiny/WooCommerce/Nuvemshop/Shopify de um lado com Mercado Livre/Shopee/Magalu/Amazon/TikTok Shop do outro (estoque, pedido, NF-e, status), com webhook + fila + idempotência já embutidos.

**O que substitui:** contratar um dev para escrever esse script individualmente a cada cliente, e o trabalho manual repetitivo de cadastro em múltiplos marketplaces.

**Por que mensalidade funciona:** é operação perpétua — roda todo dia, quebra a cada mudança de API de plataforma — nunca é "projeto fechado" de verdade mesmo quando o cliente pede assim nominalmente.

---

### Produto 5 — "Terminar o que Começou" (resgate de no-code / IA-builder)

**Não é um SaaS — é um serviço produtizado** (playbook de auditoria + retomada + handoff, preço fixo + retainer de manutenção opcional). Vale nomear como produto separado porque **apareceu de forma independente nos 6 relatórios de análise**, sem que os agentes soubessem uns dos outros:

- `app_mobile`: app de saúde/bem-estar/finanças "já iniciado no FlutterFlow (esqueleto gerado)... preciso de alguém para finalizar"; app fitness "em fase avançada... não desejamos refazer do zero"; app sobre a plataforma "lovable" (~7 vagas) — mais um bloco de "app care" de manutenção/publicação de app já existente, incluindo dificuldade explícita com políticas da Apple (~9 vagas).
- `agente_ia_voz_chat`: cliente pedindo literalmente um "mini Lovable" revendido ("não estamos buscando desenvolver essa tecnologia do zero... base funcional que possa ser adaptada"), e ~5 vagas de evoluir/consertar agente já parcialmente construído — incluindo o caso de DIY fracassado citado no Produto 2.
- `site_institucional_lp`: migração de Framer, Base44 e Manus para código próprio; herança de projeto parcialmente pronto no GitHub.
- `ecommerce_loja`: "protótipo funcional... desenvolvido com ajuda de IA... corrigir o que for necessário"; clientes que perderam contato com o desenvolvedor anterior.
- `dashboard_bi_planilha`/`crm_erp_vendas`: sistema herdado em Google Apps Script sem documentação.

**O que é:** processo padronizado de auditoria técnica + retomada + handoff para quem travou num no-code/IA-builder (FlutterFlow, Base44, Lovable, Manus, Bubble, Framer).

**O que substitui:** o cliente reescrever do zero (caro, lento, perde o que já funciona) ou ficar preso sem conseguir editar o próprio produto.

**Por que faz sentido mesmo sem ser SaaS puro:** baixo custo de construir (é checklist/processo, não plataforma nova), gera receita e leads **imediatos** enquanto os Produtos 1-4 ainda não existem como plataforma, e quem contrata esse resgate pontual é candidato natural a assinar depois um dos outros 4 (ex.: quem resgata um app de agendamento é candidato ao Produto 1; quem resgata um site é candidato ao Produto 3).

---

## 3. WhatsApp + IA — decisão de integração direta com a Meta

Pesquisa dedicada (setembro/2026, fontes oficiais Meta for Developers + relatos de mercado 2025-2026) para responder: dá para integrar direto com a Meta sem BSP, e isso resolve o risco de banimento que hoje existe no Evolution API/Z-API?

### 3.1 Decisão

**Sim — o Produto 2 nasce sobre a WhatsApp Cloud API oficial da Meta, via modelo Tech Provider + Embedded Signup, não sobre Evolution API/Z-API em modo QR/não-oficial.**

A Cloud API é hospedada pela própria Meta desde 2022 (não existe "API diferente" atrás de um BSP — é a mesma API com uma camada de conveniência em cima). Empresas grandes no Brasil (Magazine Luiza, Itaú, Banco Inter) já operam direto, sem BSP. Não há taxa de entrada da Meta para acessar a Cloud API nem para virar Tech Provider — só se paga por mensagem entregue.

### 3.2 Passos burocráticos reais

| Etapa | O que exige | Prazo relatado |
|---|---|---|
| App Business + WABA | Criar app em developers.facebook.com, conectar a uma WhatsApp Business Account no Business Manager | — |
| Business Verification | CNPJ, contrato social/estatuto, comprovante de endereço comercial | 2-10 dias úteis (comum); até 2-4 semanas em casos complexos |
| Display Name | Nome real da empresa + site funcional (só depois da verificação) | 1-7 dias úteis |
| Aprovação de template de mensagem | Categorização Marketing/Utility/Authentication | 30 min a 24h |
| Infra própria | Webhook HTTPS público, token de sistema permanente (`business_management`, `whatsapp_business_messaging`, `whatsapp_business_management`) | trabalho de dev, não burocracia com a Meta |
| Tech Provider (para gerenciar contas de múltiplos clientes) | Business Verification da própria agência + App Review com vídeo real (3-5 min) do fluxo ponta a ponta; **não exige cliente pagante já ativo** | 1-5 dias úteis 1ª resposta; 3-10 dias úteis aprovação completa (pode passar de 30 dias com correção) |

Existe sandbox gratuito para testar (até 5 destinatários na allowlist) sem nenhuma verificação de negócio.

### 3.3 Modelo de parceria para atender múltiplos clientes

A Meta renomeou os níveis em 2026: o antigo "BSP" agora é oficialmente **Solution Partner**; abaixo dele existem **Tech Provider** (entrada, self-service, sem taxa, sem volume mínimo documentado) e **Tech Partner** (Tech Provider "graduado").

- **Tech Provider + Embedded Signup é o nível certo para este produto.** Por desenho, cada cliente cria e mantém a própria WABA/número/Business Portfolio; a agência recebe só um token de acesso técnico via seu app — **nunca a posse do ativo**. A Meta proíbe explicitamente o parceiro de restringir o acesso do cliente à própria conta ou impedi-lo de trocar de fornecedor.
- Limite prático: 10 onboardings novos/semana recém-aprovado, sobe para 200/semana após Business Verification + App Review + Access Verification completos. Só acima disso vale considerar Solution Partner.
- **Solution Partner (ex-BSP)** é processo mais pesado (linha de crédito da Meta, faturamento direto ao cliente) — não é necessário só para ter posse técnica da integração, e não é um formulário simples de autoatendimento.

### 3.4 Risco de banimento: muda de forma, não desaparece

| | Não-oficial (Evolution API modo QR/Baileys, Z-API) | Oficial (Cloud API, Tech Provider) |
|---|---|---|
| Natureza do risco | Emulação do protocolo do WhatsApp Web = uso não autorizado, detectado por fingerprint de cliente | "Quality rating" (verde/amarelo/vermelho, recalculado a cada 6h sobre bloqueios/denúncias dos últimos 7 dias) + tiers de mensagem (250→2.000→10.000→100.000→ilimitado) |
| Gatilho principal | Detecção de protocolo, não depende de qualidade de conteúdo | Taxa de bloqueio pelo usuário acima de ~2%; causa nº1 é mensagem de marketing sem opt-in explícito |
| Recurso/apelação | Praticamente inexistente — número cai sem aviso | Processo formal de apelação (formulário in-app + suporte Meta); distinção clara entre restrição (reversível) e ban (permanente) |
| Dado de mercado | ~40-60% das contas em modo QR/Baileys banidas em até 48h só em março/2026 (relatos de fórum/mercado) | — |

**Achado relevante:** o próprio Evolution API tem um "modo oficial" que roda sobre a Cloud API da Meta — nesse modo ele é compliant e não carrega o risco de protocolo. O problema nunca foi a ferramenta Evolution API em si, foi especificamente o modo QR/Baileys.

**Novidade que reduz o atrito de migração:** WhatsApp Coexistence (CoEx), lançado pela Meta em 2026, permite usar o app WhatsApp Business no celular e a Cloud API no mesmo número simultaneamente (mensagens espelhadas) — elimina a necessidade de trocar/sacrificar o chip do cliente para migrar.

**Nota de política de conteúdo:** desde 15/jan/2026 a Meta proíbe chatbots de propósito geral estilo assistente (ex. ChatGPT embutido) na plataforma, mas bots estruturados de atendimento/agendamento/vendas com IA de apoio continuam permitidos — não invalida o Produto 2.

### 3.5 O que o MCP novo da Meta resolve (e o que não resolve)

A Meta lançou em 15/09/2026 o **"WhatsApp Business Tools MCP"** (ainda em beta, rollout gradual), compatível com Claude/Cursor/Codex/ChatGPT.

**Automatiza via agente:** criar a WABA; adicionar número e disparar verificação; registrar na Cloud API; CRUD de templates com status de aprovação; enviar mensagens de teste; configurar webhook; checar pendências de ToS/pagamento/Business Verification que "falham silenciosamente" e devolver links para resolver.

**Continua manual mesmo com o MCP:** verificação do número por OTP (checkpoint humano obrigatório); a Business Verification em si (o MCP só linka/consulta, não acelera nem pula fila); aceitar ToS e cadastrar pagamento; revisão de conteúdo/política dos templates (mesma fila de sempre); geração do token de sistema (fora do MCP, no Business Settings).

**Conclusão:** o MCP acelera a implementação técnica do onboarding de cada cliente — vale usá-lo no fluxo de Embedded Signup do Produto 2 — mas não muda o cronograma real do projeto, que depende dos prazos de Business Verification e App Review.

### 3.6 Custo

Sem markup indo direto: paga-se só por mensagem entregue. Faixas de mercado citadas para o Brasil em 2026: Marketing ~R$0,40-0,55/msg, Utility ~R$0,06-0,09/msg, Authentication ~R$0,03-0,05/msg. **Atenção a partir de 1º/out/2026**: a Meta volta a cobrar acima de uma camada grátis de 1.000 mensagens de serviço/mês por número, e passa a cobrar também templates de utility dentro da janela de atendimento (hoje grátis) — embutir esse custo marginal na precificação da mensalidade do Produto 2 desde o desenho inicial. Via BSP (360dialog, Twilio, Zenvia, Take Blip) cobra-se markup de 10-30% ou mensalidade fixa em troca de dashboard pronto — só compensa se a agência não fosse construir a própria camada de atendimento por cima, que não é o caso aqui.

### 3.7 Implicação direta de arquitetura (para o próximo passo)

O modelo Embedded Signup **força** isolamento por cliente — não é uma escolha de design, é regra da Meta: "Business customers onboarded via Embedded Signup own all of their WhatsApp assets". Isso significa que o Produto 2, na arquitetura a desenhar depois, precisa nascer com:

- **WABA, número, token de acesso e Business Portfolio próprios por cliente** — nunca um pool compartilhado.
- **Consumo e custo de mensageria atribuível 1:1 por cliente** — billing direto Meta↔cliente sempre que possível, ou repasse auditável por cliente se a agência intermediar; nunca custo agregado sem atribuição individual.
- **Quality rating isolado por cliente** — a restrição/queda de qualidade de um cliente não pode, por desenho, afetar o tier de mensagem de outro cliente.
- O papel da agência é a **camada de configuração e orquestração** (motor de prompt/fluxo/FAQ/agenda) por cima do ativo de cada cliente — não é dona do "pool" de mensageria, é dona do software que opera o ativo de cada um.

---

## 4. Sequenciamento recomendado

**Fase 1 — imediata, em paralelo, cada peça nascendo independente desde o dia 1:**
- **Produto 2 (Atendente WhatsApp Config)** — maior grupo de demanda do radar (121 vagas), decisão de integração já tomada (§3), e janela de oportunidade real: o MCP oficial da Meta saiu há poucos dias, pouca concorrência local já migrou do Evolution/Z-API para isso.
- **Produto 1 (Núcleo Modular de Gestão)** — mas só o essencial para sustentar assinatura multi-tenant (autenticação, cadastro básico, billing) — não a ferramenta completa. Não esperar o Núcleo "terminar" para começar o Produto 2: eles devem se integrar depois via API, nunca por dependência de deploy conjunto.

**Fase 2:**
- **Produto 3 (Resgate & Blindagem WordPress + Site-Assinatura)** — segmento mais comoditizado e com ciclo de venda mais curto do radar inteiro (vaga com 311 propostas), bom para gerar fluxo de caixa rápido; custo de construção reduzido pelo adapter MCP oficial de WordPress.

**Fase 3:**
- **Produto 4 (Painel Ponte)** — mais complexo por depender de múltiplas integrações ERP/marketplace variadas, mas parcialmente reduzido pelos MCPs já existentes de Bling, Tiny, Nuvemshop e Shopify.

**Contínuo desde o dia 1, não é uma "fase":**
- **Produto 5 (Terminar o que Começou)** — não exige plataforma própria pronta, pode rodar como serviço avulso desde já, gera receita e leads enquanto os Produtos 1-4 são construídos, e continua depois como porta de entrada natural para os outros quatro.

---

## 5. Princípios não-negociáveis para a próxima etapa (arquitetura por ferramenta)

1. **Modularidade e independência entre os 5 produtos.** Cada um tem seu próprio banco/schema, autenticação, billing e deploy. Comunicação entre produtos é sempre API/webhook explícito e versionado, nunca leitura direta de tabela/banco de outro produto, nunca acoplamento que force deploy conjunto.
2. **Isolamento por cliente dentro do Produto 2 (WhatsApp + IA) é obrigatório, não uma preferência de design** — decorre diretamente do modelo Embedded Signup (§3.7): WABA própria, token próprio, consumo/custo de API atribuível por cliente, quality rating isolado por cliente.
3. **Onde módulos precisam de fato se comunicar** (ex.: Produto 2 consultando agenda do Produto 1 para confirmar horário; Produto 1 alimentando o Produto 4 com cadastro de produto) — a integração é sempre opt-in por cliente, via contrato de API versionado, nunca acoplamento silencioso assumido por padrão.
4. Isso vale como requisito de entrada para qualquer agente de arquitetura/requisitos que trabalhar em cada ferramenta a partir daqui — não é detalhe a resolver depois, é restrição a respeitar desde o primeiro desenho.

---

## 6. Próximo passo (registrado aqui, não iniciado ainda)

Por produto, acionar os agentes relevantes (arquiteto-solucoes, product-owner, dev, etc.) para produzir, respeitando os princípios do §5: arquitetura técnica, requisitos, proposta de entrega de valor, escopo de MVP e regras de negócio — pensando desde já em cada ferramenta como algo a **oferecer como serviço/assinatura** para múltiplos clientes, não como sistema interno de uso único.
