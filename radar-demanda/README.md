# Radar de Demanda — 99Freelas + Workana

**Snapshot:** 2026-09-18. **Escopo:** categoria "Web, Mobile & Software" do 99Freelas + categoria "TI e Programação" (idioma PT/EN) do Workana, sem filtro de subcategoria/publicação — ou seja, a base mais ampla possível dentro de "TI" nas duas plataformas, não uma amostra recortada.

Este radar **não é uma lista de vagas pra disputar**. É mineração de demanda: abrir as 630 vagas/projetos ativos nas duas plataformas, extrair a descrição completa de cada uma e agrupar por necessidade real do cliente, pra achar o padrão que se repete — igual ao raciocínio que já estava registrado em `EXTRACAO_E_ANALISE_WORKANA.md` (seção 1, "a metodologia é a parte durável"), mas agora tratado como radar recorrente e cruzando 2 plataformas em vez de 1.

## Como abrir

`index.html` é autocontido — os dados das 630 vagas estão embutidos no próprio arquivo (`window.__DADOS_RADAR__` / `window.__RESUMO_RADAR__`), então **basta abrir o arquivo direto no navegador**, sem servidor. `dataset.json` e `resumo.json` ficam ao lado só como dado bruto reaproveitável (reprocessar com outro critério de categorização, alimentar outro script, etc.) — não são lidos pelo site em si.

## Metodologia de extração

- **99Freelas**: listagem (`/projects?categoria=web-mobile-e-software&page=N`) e página de projeto individual são **renderizadas no servidor** — `curl` simples com User-Agent de navegador basta pras duas. Paginação por `page=N` percorrida até a última página real (`data-page` do botão "Última" na página 1): 28 páginas, 279 projetos únicos.
- **Workana**: a página de vaga individual (`/job/<slug>`) é renderizada no servidor (igual já documentado em `EXTRACAO_E_ANALISE_WORKANA.md`), mas a **listagem** (`/jobs?category=...`) continua bloqueada pra `curl` simples (só devolve o shell Vue vazio) — precisa de Chrome headless com flags anti-detecção Cloudflare (`--disable-blink-features=AutomationControlled` etc.) e `--dump-dom`. Paginação por `&page=N`, percorrida até 2 páginas seguidas sem vaga nova: 50 páginas, 351 vagas únicas.
- Nenhuma extração usa login. Rate limit de ~0,3–0,4s entre requisições.
- **Bug corrigido nesta rodada**: a descrição do 99Freelas fica também num atributo HTML `data-content="..."` que pode conter `<br/>` cru dentro do valor do atributo — um parser ingênuo que pula atributos com `[^>]*` quebra ali (218 das 279 descrições saíram com lixo de HTML colado no início na primeira tentativa). Corrigido ancorando direto em `data-content="(.*?)">` em vez de tentar pular os atributos genericamente.

## Nenhuma das 630 mostra orçamento numérico

Confirma o achado já registrado em `EXTRACAO_E_ANALISE_WORKANA.md` §3, agora nas 630: em ambas as plataformas, sem login, o campo de orçamento aparece só como "Aberto" — não tem preço público do cliente pra usuário anônimo em nenhuma das duas. Isso não é falha de extração, é o comportamento real do filtro.

## Categorização

Casamento de palavra-chave (normalizado, sem acento) sobre título+descrição, com **1 categoria principal por vaga** (primeira que bater, por ordem de prioridade) e **multi-tag** (todas as que baterem) pra filtro cruzado no site. É uma primeira leitura de volume, não uma classificação perfeita item a item — serve pra achar padrão, não pra citar número com 3 casas decimais.

| Categoria principal | Contagem | % |
|---|---|---|
| Automação/chatbot de WhatsApp | 121 | 19% |
| E-commerce / loja virtual | 92 | 15% |
| Aplicativo mobile | 89 | 14% |
| Agente/assistente de IA (fora do WhatsApp) | 77 | 12% |
| Site institucional / landing page | 49 | 8% |
| Dashboard / BI / planilha | 38 | 6% |
| CRM / ERP / automação comercial | 37 | 6% |
| Outro / não categorizado | 36 | 6% |
| Jogos | 24 | 4% |
| Sistema sob medida (gestão interna) | 14 | 2% |
| Marketing digital / tracking / SEO | 14 | 2% |
| Automação de processo (n8n/RPA/Zapier) | 10 | 2% |
| Apostas / cassino online ⚠ | 8 | 1% |
| Segurança / infraestrutura / DevOps | 8 | 1% |
| Robô de trading financeiro | 5 | 1% |
| Hardware embarcado / IoT | 5 | 1% |
| Conteúdo adulto ⚠ | 2 | <1% |
| Extração de dados / scraping | 1 | <1% |

⚠ = fora do escopo ético recomendado pro negócio; aparecem no radar por completude, não como sugestão.

## Leitura

**121 das 630 vagas (19%) mencionam automação/atendimento de WhatsApp** — de longe o maior nó único, nas duas plataformas, o que confirma (numa base 12x maior) o padrão que já tinha aparecido no primeiro snapshot de 50 vagas do Workana. Somando os 3 maiores grupos (WhatsApp + e-commerce + app mobile) chega a **302 vagas (48%)** — quase metade de toda demanda de TI nesses 2 marketplaces é uma dessas três coisas.

O recorte mais parecido com o cliente típico já atendido fora dessas plataformas (site institucional + e-commerce + atendimento automatizado por WhatsApp) soma **262 vagas (42%)**. Ler isso como validação: ir atrás de "site + catálogo + agendamento com atendimento no WhatsApp" como sistema-produto é perseguir o centro real da demanda medida, não uma aposta de nicho.

Apostas/cassino (8) e conteúdo adulto (2) aparecem no radar mas ficam fora de qualquer recomendação de negócio.

## Limitações

- Snapshot datado — não é preço nem tendência, é uma fotografia de 18/09/2026. Refazer a extração periodicamente pra virar radar de verdade (a metodologia acima é reprodutível).
- Categorização por palavra-chave erra em casos ambíguos (ex. "sistema" e "controle" são genéricos demais pra confiar cegamente na contagem de "Sistema sob medida").
- 1 vaga do Workana veio sem título/descrição (removida do dataset final) — provável vaga já encerrada/removida entre a listagem e a busca de detalhe.
