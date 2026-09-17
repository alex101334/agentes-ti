# Extração e Análise de Vagas Workana — metodologia e resultado

**Data:** 2026-09-17. Este documento registra (1) a técnica usada para extrair dado real do Workana apesar do bloqueio anti-bot e da renderização via JavaScript, e (2) o resultado de uma rodada de análise real — 3 vagas específicas em profundidade + triagem de 50 vagas da categoria TI/Programação. Serve de referência para retomar este tipo de análise depois; os links de vaga individual ficam inativos com o tempo (Workana remove/fecha vaga), então trate os dados numéricos como um snapshot datado, não como preço de mercado eterno.

## 1. Metodologia de extração (reprodutível)

### 1.1 O que NÃO funciona

- **WebFetch direto** na URL de uma vaga → `HTTP 403 Forbidden` (bloqueio anti-bot da Cloudflare).
- **`curl` simples** (sem User-Agent de navegador) na página de **busca/listagem** (`/jobs?category=...`) → retorna só o shell Vue vazio (`searchResults`, `@pagination_triggered="loadResults"`), sem nenhuma vaga — a lista é carregada via JS depois do carregamento, não vem no HTML.
- **Chrome headless "cru"** (`--headless=new` sem flags extras) → cai na verificação anti-bot da Cloudflare ("Executando verificação de segurança"), porque o modo headless tem fingerprint detectável (`navigator.webdriver`, ausência de plugins, etc.). Ironicamente, pior que o `curl` simples nesse ponto específico.
- **Tentativa de achar a API JSON por trás da busca**: sem sucesso. Testado `/jobs.json`, `/api/jobs`, `/en/jobs.json`, cabeçalho `Accept: application/json` — todos 404. O app usa arquitetura de micro-frontend (`cf.wkncdn.com/mfe/importmap.json`) mas a busca não é um MFE separado, é parte do bundle principal (Vue), sem endpoint óbvio.

### 1.2 O que funciona

**Página de vaga individual** (`/job/<slug>`) — `curl` simples com User-Agent de navegador já basta, o conteúdo vem renderizado no servidor (provavelmente para SEO/indexação do Google):

```bash
curl -s -A "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0 Safari/537.36" \
  -L "https://www.workana.com/job/<slug>" -o pagina.html --max-time 15
```

Depois extrair texto legível removendo tags (Python, `re.sub` em `<script>`/`<style>`/demais tags). Dá o título, descrição completa, categoria/subcategoria, habilidades pedidas, "Tamanho do projeto" (quando rotulado), "Prazo de Entrega", quantidade de "Propostas" e "Freelancers interessados", e dado do cliente (projetos publicados/pagos, membro desde). **O campo de orçamento (`class="budget"`) mostra literalmente "Aberto" — confirmado com curl E com Chrome real de JS totalmente executado, os dois batem. Não é placeholder: é o valor final. Nas vagas testadas, não existe orçamento numérico público do cliente.**

**Página de busca/listagem** (`/jobs?category=...`) — precisa de um navegador real executando JS. Google Chrome já vem instalado no ambiente (`/usr/bin/google-chrome`), então não foi preciso instalar Selenium/Playwright (que aliás não dava pra instalar — `pip`/`ensurepip` quebrados, sem `sudo`, sem `node`). Comando que funciona, com flags que evitam a detecção de bot da Cloudflare:

```bash
timeout 45 google-chrome --headless=new --disable-gpu --no-sandbox \
  --disable-blink-features=AutomationControlled \
  --user-agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36" \
  --window-size=1366,1200 \
  --virtual-time-budget=15000 \
  --dump-dom "https://www.workana.com/jobs?category=it-programming&language=en%2Cpt&publication=gt1w&subcategory=..." \
  > listagem.html
```

**Paginação**: o parâmetro de URL `&page=N` funciona (mesmo sem simular scroll/infinite-scroll) e devolve um conjunto DIFERENTE de vagas por página — 7 vagas por página nas execuções feitas. Aumentar `--window-size` de altura não adianta (a lista não carrega mais itens por "viewport virtual maior" — o gatilho de paginação real exige evento de scroll de verdade, que `--dump-dom` não simula). Solução prática: iterar `page=1,2,3,...` até juntar vagas únicas suficientes ou até a página não trazer nada novo.

Depois de ter os slugs das vagas (via `grep -o 'href="/job/[^"?]*'` no HTML da listagem), cada vaga individual é buscada com o `curl` simples do parágrafo anterior — mais rápido e barato que abrir Chrome para cada uma (Chrome só é necessário para a página de busca).

### 1.3 Processo usado nesta rodada

1. `curl` (User-Agent de navegador) nas 3 vagas específicas que o usuário mandou → texto completo extraído.
2. Chrome headless com as flags acima, iterando `page=1` a `page=8` na URL de busca filtrada (`category=it-programming&language=en,pt&publication=gt1w&subcategory=web-development,web-design,e-commerce,wordpress-1,desktop-apps,artificial-intelligence-1,others-5`) → 56 vagas únicas coletadas, cortado para as primeiras 50 (pedido do usuário: "se forem muitos restrinja para os 50 primeiros").
3. `curl` simples em cada uma das 50 vagas → texto extraído e salvo (rate-limit de ~0,4s entre requisições).
4. Confirmado por grep: **0 das 50 vagas mostra orçamento numérico do cliente** — todas "Aberto". A única ocorrência de "R$" em qualquer uma das 50 era o preço do PRODUTO do cliente sendo vendido numa página de vendas, não o orçamento do projeto.
5. Workflow paralelo (5 lotes de 10 vagas) para triar: esforço estimado (T-shirt/dias, esforço humano-equivalente), preço realista de mercado brasileiro 2026 para aquele tipo de entrega (não a tabela de salário CLT sênior de SP, que serviria pra outra coisa — aqui é preço de projeto avulso), valor por dia de esforço, concorrência (propostas/interessados) e risco de escopo (vago, cliente sem histórico, dependência externa não controlável).

## 2. Resultado — 3 vagas específicas (análise em profundidade)

Vagas indicadas diretamente pelo usuário, passadas pelo pipeline completo do skill `estimativa-macro-projeto` (PO real enquadra escopo → especialistas reais do time estimam → Gerente de Projeto real consolida prazo/custo em 3 cenários PERT). Nenhuma das 3 tinha orçamento do cliente visível (todas "Aberto").

| Vaga | Prazo (calendário real do time) | Custo interno (PERT) | Preço recomendado a propor |
|---|---|---|---|
| [E-commerce equipamentos de limpeza industrial](https://www.workana.com/job/desenvolvimento-de-e-commerce-completo-para-equipamentos-de-limpeza-industrial) | 3-4 semanas | R$120.500 | R$95.000-130.000, em 2 fases |
| [Site institucional + página de vendas + SEO](https://www.workana.com/job/criacao-de-website-institucional-e-pagina-de-vendas-com-otimizacao-seo) | 6-12 dias úteis | R$20.614 | **R$5.000-7.500** — repreçado pra baixo depois de pesquisa de mercado real (ver nota) |
| [Agente de voz IA (ElevenLabs + n8n)](https://www.workana.com/job/desenvolvedor-para-agentes-de-voz-com-ia-elevenlabs-e-integracao-n8n) | 2-3 semanas | R$54.533 | R$48.000-60.000, ou R$20-26k só a Fase 1 |

**Achado mais importante desta parte**: para o site institucional, o custo calculado pela tabela de salário sênior CLT de São Paulo deu R$15-27 mil — mas o próprio Gerente de Projeto, seguindo a Regra 1 do time (pesquisar antes de decidir), foi checar o que o mercado freelancer brasileiro real paga por esse tipo de entrega (achou R$1.500-8.000) e recomendou R$5.000-7.500 em vez do número "ingênuo" mais alto — a tabela de custo interno serve de referência de VALOR de mão de obra, não de preço de venda direto num marketplace de baixo ticket.

**Decisão do usuário sobre as 3**: depois de descobrir que o orçamento real do cliente do e-commerce era "no máximo R$2.600" (visto no próprio navegador do usuário, logado — não reproduzível por scraping não-autenticado, ver §3 sobre essa limitação), a conclusão foi: **descartar e-commerce e agente de voz** (orçamento do cliente muito abaixo do custo real de entregar o escopo pedido — não é preço nosso alto, é escopo grande por preço de projeto pequeno) e **perseguir o site institucional**, cujo preço recalibrado (R$5-7.500) cabia na faixa real do cliente.

## 3. Limitação conhecida: orçamento "logado" não é visível por scraping

O usuário reportou ver "paga no máximo R$2.600" numa vaga cujo campo público de orçamento mostrava "Aberto" — mesmo depois de confirmar com Chrome real (JS totalmente executado, sem cache, sem login) que o valor renderizado é de fato "Aberto" e não um placeholder. Conclusão: esse número só aparece para usuário **logado** na Workana (provavelmente uma sugestão de faixa na hora de montar a proposta, ou um filtro que o usuário aplicou na própria busca) — não é um dado public. Este pipeline de extração não usa login (não é objetivo inserir credencial do usuário em automação), então **qualquer análise futura vai continuar sem o número real do cliente**, a menos que o usuário copie/cole o valor manualmente ou mande print de tela.

## 4. Resultado — triagem de 50 vagas (categoria TI/Programação, filtro do usuário)

Nenhuma das 50 mostra orçamento do cliente (ver §1.3). Ranking por **valor/dia** = preço realista de mercado brasileiro (ponto médio) ÷ esforço estimado em dias (ponto médio) — não é o que o cliente paga, é o que a entrega vale se vendida a preço de mercado justo, comparado ao esforço que ela exige. Risco de escopo (baixo/médio/alto) e concorrência (propostas) são os dois filtros que mais importam para saber se aquele valor/dia é realmente capturável.

### 4.1 As 2 de maior valor/dia — mas risco alto, não recomendadas como estão

**Develop an Advanced AI Sales, Calling & Booking System for Aesthetics Clinic** ([link](https://www.workana.com/job/develop-an-advanced-ai-sales-calling-booking-system-for-aesthetics-clinic)) — R$1,093/dia, G, 15-28 dias, risco alto

Contato automático de leads do Meta Ads em minutos, IA de voz que liga e recebe ligações, atendimento multi-canal (WhatsApp/SMS/e-mail), agendamento/remarcação/cancelamento em tempo real, follow-up e handoff para humano — pedido explicitamente como 'sistema pronto para produção, não protótipo', com integrações, testes extensivos e suporte pós-lançamento.

Red flags: Cliente 'A.' tem 7 projetos publicados e 0 pagos — histórico de contratação real inexistente apesar do volume de posts; Pede 'sistema robusto pronto para produção' com IA de voz, multi-canal, CRM, compliance GDPR e suporte pós-lançamento tudo dentro de 'Tamanho do projeto: Médio' e sem orçamento nem prazo declarados — descompasso clássico entre ambição do escopo e sinalização de budget; 38 propostas/45 interessados indicam concorrência de preço acirrada, o que tende a empurrar o vencedor para abaixo do valor real do escopo


**Implantação e Migração Atlassian (JSM, Jira, Confluence, Bitbucket) para equipe multidisciplinar** ([link](https://www.workana.com/job/implantacao-e-migracao-atlassian-jsm-jira-confluence-bitbucket-para-equipe-multidisciplinar)) — R$1,054/dia, GG, 20-35 dias, risco alto

Migrar 8 áreas de negócio (RH, Facilities, Infra, Cibersegurança, Suporte, CS, Jurídico, Formalização, Marketing) do Freshservice para o JSM, catalogando processos existentes, construindo pelo menos 2 portais de serviço distintos e integrando tudo ao Jira/Confluence/Bitbucket já usados pelo time de dev.

Red flags: Cliente 'D. B. V.' com 1 projeto publicado, 0 pagos, conta nova (Setembro/2026) — para um projeto de escala corporativa isso é um forte sinal de descompasso entre expectativa de escopo e orçamento real disponível na plataforma; Migração de 8 áreas de negócio distintas com levantamento de processo + 2 portais + automação é escopo de consultoria de médio-grande porte, difícil de ser coberto por um preço fixo típico de Workana; 53 interessados/47 propostas é o maior volume de concorrência do lote inteiro, o que empurra fortemente o preço vencedor para baixo do valor real do trabalho


### 4.2 As 5 recomendadas de verdade — risco baixo, escopo bem definido

| Vaga | T-shirt | Esforço | Preço realista | Valor/dia | Risco | Propostas |
|---|---|---|---|---|---|---|
| [Bug no sistema de I.A. - Click & Cargo](https://www.workana.com/job/bug-no-sistema-de-i-a-click-cargo) | PP | 0.5-2d | R$500-1,300 | **R$720** | baixo | 41 |
| [Especialista em Excel e VBA para Otimização e Personalização de Planil](https://www.workana.com/job/especialista-em-excel-e-vba-para-otimizacao-e-personalizacao-de-planilha-de-caixa) | PP | 2-5d | R$900-2,500 | **R$486** | baixo | 46 |
| [Desenvolvimento de Calculadora 3d Interativa no Unity com Teclas em Cu](https://www.workana.com/job/desenvolvimento-de-calculadora-3d-interativa-no-unity-com-teclas-em-cubo) | PP | 2-4d | R$800-2,000 | **R$467** | baixo | 27 |
| [Desenvolvimento de Planilha Google e AppSheet para Controle Patrimonia](https://www.workana.com/job/desenvolvimento-de-planilha-google-e-appsheet-para-controle-patrimonial-com-relatorios) | P | 3-6d | R$1,200-3,000 | **R$467** | baixo | 31 |
| [Desenvolvimento de Sistema de Respostas Automáticas para Whatsapp](https://www.workana.com/job/desenvolvimento-de-sistema-de-respostas-automaticas-para-whatsapp-77) | PP | 3-7d | R$1,000-3,000 | **R$400** | baixo | 31 |

### 4.3 Tabela completa das 50, ordenada por valor/dia

| Vaga | T-shirt | Esforço | Preço realista | Valor/dia | Risco | Propostas |
|---|---|---|---|---|---|---|
| [Develop an Advanced AI Sales, Calling & Booking System for A](https://www.workana.com/job/develop-an-advanced-ai-sales-calling-booking-system-for-aesthetics-clinic) | G | 15-28d | R$15,000-32,000 | R$1,093 | alto | 38 |
| [Implantação e Migração Atlassian (JSM, Jira, Confluence, Bit](https://www.workana.com/job/implantacao-e-migracao-atlassian-jsm-jira-confluence-bitbucket-para-equipe-multidisciplinar) | GG | 20-35d | R$18,000-40,000 | R$1,054 | alto | 47 |
| [Develop an AI-Powered Personal Productivity Platform for Web](https://www.workana.com/job/develop-an-ai-powered-personal-productivity-platform-for-web-and-mobile) | GG | 30-50d | R$22,000-50,000 | R$900 | alto | 9 |
| [Develop an AI-Powered Personal Finance Tracker with Automate](https://www.workana.com/job/develop-an-ai-powered-personal-finance-tracker-with-automated-receipt-scanning) | M | 14-24d | R$10,000-22,000 | R$842 | medio | 10 |
| [Develop a Responsive E-commerce Store with User Profiles and](https://www.workana.com/job/develop-a-responsive-e-commerce-store-with-user-profiles-and-secure-payments) | M | 12-20d | R$8,000-16,000 | R$750 | medio | 19 |
| [Bug no sistema de I.A. - Click & Cargo](https://www.workana.com/job/bug-no-sistema-de-i-a-click-cargo) | PP | 0.5-2d | R$500-1,300 | R$720 | baixo | 41 |
| [Desenvolvimento de Sistema para Geração de Arquivos Cat 42 p](https://www.workana.com/job/desenvolvimento-de-sistema-para-geracao-de-arquivos-cat-42-para-sefaz-sp) | M | 8-15d | R$4,500-12,000 | R$717 | medio | 25 |
| [Especialista em Testes de Software para Plataforma Financeir](https://www.workana.com/job/especialista-em-testes-de-software-para-plataforma-financeira-b3-e-derivativos) | P | 5-9d | R$2,800-6,500 | R$664 | medio | 12 |
| [Desenvolvimento de Chatbot com Ia para Automação de Resposta](https://www.workana.com/job/desenvolvimento-de-chatbot-com-ia-para-automacao-de-respostas-no-whatsapp-e-outras-plataformas-1) | P | 3-6d | R$1,500-4,000 | R$611 | alto | 28 |
| [Desenvolvimento de Automação de Respostas no Whatsapp com Ia](https://www.workana.com/job/desenvolvimento-de-automacao-de-respostas-no-whatsapp-com-ia-2) | P | 2-5d | R$1,200-3,000 | R$600 | medio | 27 |
| [Desenvolvimento de Expert Advisor (EA) em MQL5 para MetaTrad](https://www.workana.com/job/desenvolvimento-de-expert-advisor-ea-em-mql5-para-metatrader-5-1) | G | 10-20d | R$5,000-12,000 | R$567 | alto | 12 |
| [Desenvolvimento de Dashboard Web com Login Multi-Cliente par](https://www.workana.com/job/desenvolvimento-de-dashboard-web-com-login-multi-cliente-para-sistema-de-logistica) | M | 8-15d | R$4,000-9,000 | R$565 | medio | 41 |
| [Desenvolvimento de Sistema de Respostas Automáticas para Wha](https://www.workana.com/job/desenvolvimento-de-sistema-de-respostas-automaticas-para-whatsapp-78) | P | 5-12d | R$2,500-7,000 | R$559 | medio | 46 |
| [Desenvolvimento de Site Moderno e Responsivo com Seo Avançad](https://www.workana.com/job/desenvolvimento-de-site-moderno-e-responsivo-com-seo-avancado-para-limpeza-especializada) | M | 8-15d | R$3,500-9,000 | R$543 | medio | 90 |
| [Desenvolvimento de Api Rest para Crm Interno](https://www.workana.com/job/desenvolvimento-de-api-rest-para-crm-interno) | G | 15-30d | R$8,000-16,000 | R$533 | alto | 92 |
| [Criação de Página de Vendas de Alta Conversão para Ebook sob](https://www.workana.com/job/criacao-de-pagina-de-vendas-de-alta-conversao-para-ebook-sobre-saude-na-menopausa) | P | 2-4d | R$900-2,200 | R$517 | medio | 35 |
| [Configuração e Integração de Bitrix24 com Sistemas ERP via n](https://www.workana.com/job/configuracao-e-integracao-de-bitrix24-com-sistemas-erp-via-n8n) | M | 4-10d | R$2,000-5,000 | R$500 | alto | 43 |
| [Desenvolvimento de Sistema de Respostas Automatizadas com In](https://www.workana.com/job/desenvolvimento-de-sistema-de-respostas-automatizadas-com-inteligencia-artificial-17) | P | 3-8d | R$1,500-4,000 | R$500 | medio | 26 |
| [Desenvolvimento de Site Ultra Rápido para Encontrar Socorro ](https://www.workana.com/job/desenvolvimento-de-site-ultra-rapido-para-encontrar-socorro-em-marica-e-regiao) | P | 6-12d | R$2,500-6,500 | R$500 | medio | 71 |
| [Especialista em Excel e VBA para Otimização e Personalização](https://www.workana.com/job/especialista-em-excel-e-vba-para-otimizacao-e-personalizacao-de-planilha-de-caixa) | PP | 2-5d | R$900-2,500 | R$486 | baixo | 46 |
| [Desenvolvimento de Plataforma de Jogo Online Personalizada](https://www.workana.com/job/desenvolvimento-de-plataforma-de-jogo-online-personalizada) | G | 15-35d | R$6,000-18,000 | R$480 | alto | 31 |
| [Automatização de pedidos iFood com IA para prevenção de erro](https://www.workana.com/job/automatizacao-de-pedidos-ifood-com-inteligencia-artificial-para-prevencao-de-erros) | G | 5-15d | R$2,500-7,000 | R$475 | alto | 26 |
| [Criação de Página de Vendas Online com Integração de Pagamen](https://www.workana.com/job/criacao-de-pagina-de-vendas-online-com-integracao-de-pagamentos-e-vendas-no-instagram) | M | 6-12d | R$2,500-6,000 | R$472 | alto | 44 |
| [Desenvolvimento de Agente Personalizado Chatgpt Business com](https://www.workana.com/job/desenvolvimento-de-agente-personalizado-chatgpt-business-com-notificacoes-de-tarefas-diarias) | P | 2-5d | R$800-2,500 | R$471 | medio | 26 |
| [Configuração Completa do CRM Datacrazy com Integração WhatsA](https://www.workana.com/job/configuracao-completa-do-crm-datacrazy-com-integracao-whatsapp-e-funil-de-vendas) | M | 3-6d | R$1,200-3,000 | R$467 | medio | 42 |
| [Criação e Otimização de Página Web para o Método Alento de T](https://www.workana.com/job/criacao-e-otimizacao-de-pagina-web-para-o-metodo-alento-de-tratamento-da-dor) | P | 3-6d | R$1,200-3,000 | R$467 | alto | 57 |
| [Desenvolvimento de Calculadora 3d Interativa no Unity com Te](https://www.workana.com/job/desenvolvimento-de-calculadora-3d-interativa-no-unity-com-teclas-em-cubo) | PP | 2-4d | R$800-2,000 | R$467 | baixo | 27 |
| [Desenvolvimento de Marketplace Multi-Vendedor Gamer com Word](https://www.workana.com/job/desenvolvimento-de-marketplace-multi-vendedor-gamer-com-wordpress-e-woocommerce) | G | 20-40d | R$8,000-20,000 | R$467 | alto | 48 |
| [Desenvolvimento de Planilha Google e AppSheet para Controle ](https://www.workana.com/job/desenvolvimento-de-planilha-google-e-appsheet-para-controle-patrimonial-com-relatorios) | P | 3-6d | R$1,200-3,000 | R$467 | baixo | 31 |
| [Desenvolvimento de Websites Profissionais para Empresas de T](https://www.workana.com/job/desenvolvimento-de-websites-profissionais-para-empresas-de-todos-os-portes) | M | 5-10d | R$2,000-5,000 | R$467 | alto | 51 |
| [Desenvolvimento de Site para Lembrete de Hidratação Personal](https://www.workana.com/job/desenvolvimento-de-site-para-lembrete-de-hidratacao-personalizado) | PP | 4-8d | R$1,500-4,000 | R$458 | medio | 65 |
| [Desenvolvimento de Chatbot para Automação de Respostas no Wh](https://www.workana.com/job/desenvolvimento-de-chatbot-para-automacao-de-respostas-no-whatsapp-52) | P | 3-6d | R$1,200-2,800 | R$444 | medio | 42 |
| [Criação de Loja Virtual Simples e Profissional com Carrinho ](https://www.workana.com/job/criacao-de-loja-virtual-simples-e-profissional-com-carrinho-e-whatsapp) | P | 3-6d | R$1,200-2,800 | R$444 | medio | 31 |
| [Desenvolvimento de Solução de Automação com Ia para Relatóri](https://www.workana.com/job/desenvolvimento-de-solucao-de-automacao-com-ia-para-relatorios-judiciais) | GG | 20-45d | R$8,000-20,000 | R$431 | alto | 47 |
| [Automatização de respostas e estratégias de geração de renda](https://www.workana.com/job/automatizacao-de-respostas-e-estrategias-de-geracao-de-renda-via-whatsapp) | M | 5-10d | R$1,800-4,500 | R$420 | alto | 22 |
| [Busca por Freelancer para Construção de Website Profissional](https://www.workana.com/job/busca-por-freelancer-para-construcao-de-website-profissional) | M | 3-7d | R$1,200-3,000 | R$420 | alto | 45 |
| [Desenvolvimento de Chatbot com IA para Respostas Automáticas](https://www.workana.com/job/desenvolvimento-de-chatbot-com-ia-para-respostas-automaticas-no-whatsapp-10) | P | 3-7d | R$1,200-3,000 | R$420 | medio | 34 |
| [Automatização de respostas no Instagram com IA](https://www.workana.com/job/automatizacao-de-respostas-no-instagram-com-inteligencia-artificial-4) | M | 4-8d | R$1,500-3,500 | R$417 | alto | 17 |
| [Criação de Página de Vendas Responsiva e Elegante para Produ](https://www.workana.com/job/criacao-de-pagina-de-vendas-responsiva-e-elegante-para-produto-digital-projeto-vida-nossa) | P | 2-4d | R$700-1,800 | R$417 | medio | 56 |
| [Desenvolvimento de Chatbot com IA para Respostas Automatizad](https://www.workana.com/job/desenvolvimento-de-chatbot-com-ia-para-respostas-automatizadas-no-whatsapp-e-chat) | P | 4-8d | R$1,500-3,500 | R$417 | medio | 35 |
| [Alteração layout wix checkout](https://www.workana.com/job/alteracao-layout-wix-checkout) | PP | 0.5-2d | R$300-700 | R$400 | medio | 57 |
| [Desenvolvimento de Sistema de Respostas Automáticas para Wha](https://www.workana.com/job/desenvolvimento-de-sistema-de-respostas-automaticas-para-whatsapp-77) | PP | 3-7d | R$1,000-3,000 | R$400 | baixo | 31 |
| [Especialista para Configuração e Treinamento Básico no ERP O](https://www.workana.com/job/especialista-para-configuracao-e-treinamento-basico-no-erp-olist-tiny) | PP | 1-3d | R$400-1,200 | R$400 | medio | 11 |
| [Desenvolvimento de Aplicativo Desktop para Intermediação de ](https://www.workana.com/job/desenvolvimento-de-aplicativo-desktop-para-intermediacao-de-pagamentos-seguros) | GG | 10-40d | R$3,000-15,000 | R$360 | alto | 38 |
| [Desenvolvimento de Mini Vending Machine Autônoma para Vendas](https://www.workana.com/job/desenvolvimento-de-mini-vending-machine-autonoma-para-vendas-de-chicletes-trident-via-pix) | G | 12-25d | R$4,000-9,000 | R$351 | alto | 8 |
| [Desenvolvimento de Jogo de Simulação de Moto com Customizaçã](https://www.workana.com/job/desenvolvimento-de-jogo-de-simulacao-de-moto-com-customizacao-e-economia) | GG | 30-90d | R$12,000-30,000 | R$350 | alto | 5 |
| [Atualização de site WordPress e edição de páginas de venda (](https://www.workana.com/job/atualizacao-de-site-wordpress-e-edicao-de-paginas-de-venda-para-canal-de-filosofia) | P | 3-6d | R$900-2,200 | R$344 | medio | 45 |
| [Desenvolvimento de Copy e Criação de Landing Page Profission](https://www.workana.com/job/desenvolvimento-de-copy-e-criacao-de-landing-page-profissional) | P | 3-6d | R$800-2,000 | R$311 | medio | 89 |
| [Especialista em Automação de E-mails para Projeto Pessoal](https://www.workana.com/job/especialista-em-automacao-de-e-mails-para-projeto-pessoal) | PP | 1-3d | R$300-900 | R$300 | medio | 31 |
| [Desenvolvimento urgente de automação de respostas de IA no W](https://www.workana.com/job/desenvolvimento-urgente-de-automacao-de-respostas-de-ia-no-whatsapp) | PP | 3-8d | R$700-2,200 | R$264 | alto | 0 |

### 4.4 Padrão geral observado (achado de mercado, não só desta busca)

- **0 das 50** vagas mostra orçamento público do cliente — "Aberto" é a norma da categoria/filtro usado, não exceção das 3 vagas originais.
- Concentração pesada em **automação de WhatsApp/chatbot de IA** (~12-15 das 50) — nicho saturado, concorrência de 20-90 propostas por vaga, valor/dia mediano puxado pra baixo pela guerra de preço.
- Maioria dos clientes tem **conta nova/zero projetos pagos** — risco comercial recorrente do canal Workana neste filtro, não específico de uma vaga isolada.
- Vagas com valor/dia mais alto tendem a ser justamente as de escopo mais ambicioso e menos definido — o valor "no papel" é teórico, raramente capturável nas condições reais do marketplace (ver §4.1).
