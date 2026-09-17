---
name: estimativa-macro-projeto
description: Use este skill quando o Product Owner estiver avaliando um projeto de cliente NOVO, antes de aceitar/iniciar qualquer trabalho real — produz uma estimativa macro (grosseira, tipo ROM, não assertiva) de prazo total e de custo do projeto. Separa dois eixos: esforço humano-equivalente por papel (T-shirt size, usado só para custo via tabela de mercado sênior em São Paulo) e velocidade real de execução do time de agentes (usada para o prazo de calendário, sempre limitada por espera externa que não acelera com o agente). Inclui cenário otimista/provável/pior-caso (PERT) e um período de manutenção pós-entrega com quadro reduzido. Não substitui o roadmap de fases/MVP detalhado do Gerente de Projeto nem o backlog detalhado do Product Owner, que vêm depois, já dentro do fluxo normal do projeto aceito (ver CLAUDE.md §4).
---

# Estimativa Macro de Prazo e Custo — agentes-ti

Este skill é o **passo 0** de qualquer projeto de cliente: acontece ANTES do fluxo descrito em `CLAUDE.md` §4 (antes de qualquer história ser quebrada pelo Scrum Master, antes de qualquer linha de código, antes até do backlog detalhado do Product Owner). Serve para o usuário decidir, com uma faixa grosseira de prazo e de custo, se aceita o projeto e em que condição.

**Princípio central: prazo e custo usam réguas DIFERENTES, nunca a mesma.**

- **Custo** é calculado em cima de **esforço humano-equivalente** (quanto um profissional sênior de mercado levaria) × **valor de mercado sênior em São Paulo** (`CUSTO_MERCADO_SP.md`, na raiz do projeto). Isso é o que ancora o preço cobrado do cliente num valor de mercado real e reconhecível, não em custo de computação do agente.
- **Prazo** é calculado em cima da **velocidade real de execução do time de agentes**, que é mais rápida que o esforço humano-equivalente para a parte do trabalho que o time controla sozinho — mas **nunca trate isso como compressão uniforme ou "quase instantânea" sem ressalva** (ver seção dedicada abaixo). A pesquisa de mercado 2026 sobre produtividade de agente de IA mostra ganho real, mas desigual por tipo de tarefa, e um "paradoxo de produtividade" documentado (retrabalho/incidente que aparece depois quando a revisão é pulada) — a régua de conversão abaixo já incorpora essa nuance em vez de assumir um multiplicador único otimista demais.

## Quando usar

Sempre que um projeto de cliente novo estiver sendo avaliado — antes de criar a pasta `projetos/<cliente>/` como um projeto "aceito e em andamento". Também vale reaplicar este skill se o escopo macro mudar substancialmente no meio do projeto (cliente pede algo que muda o tamanho do projeto de forma relevante).

## Quem conduz

O **Product Owner** inicia e conduz o processo (é dono da relação de entendimento de escopo com o cliente), mas a estimativa em si é **colaborativa**: cada agente relevante estima a própria fatia, e o **Gerente de Projeto** consolida tudo numa faixa única de prazo e custo. Nenhum agente estima a fatia de outro por conta própria.

## Passo a passo

### 1. Product Owner faz discovery macro com o cliente

Não é o backlog detalhado (isso vem depois, já dentro do projeto aceito). É um levantamento de alto nível, usando as mesmas técnicas de elicitação já documentadas no próprio arquivo do PO (entrevista estruturada, Event Storming leve), mas em escopo reduzido: quais os módulos/funcionalidades principais, quais integrações externas, qual plataforma (web/mobile/ambos), volume esperado de usuário/carga, e qualquer restrição de prazo ou orçamento que o cliente já tenha em mente.

### 2. Product Owner traduz o levantamento num "mapa de escopo macro"

Uma lista curta de épicos/blocos de trabalho (não user stories detalhadas) — cada um com uma frase de escopo e, quando souber, a integração/tecnologia envolvida. Esse mapa é o input que todo o resto do time vai usar para estimar; sem ele, ninguém estima nada.

### 3. Cada agente relevante estima esforço humano-equivalente (para custo)

Cada agente consultado estima sua fatia usando **T-shirt size**, sempre pensando "quanto tempo um profissional sênior de mercado, humano, levaria" — essa régua não é o prazo real do projeto, é só o insumo de custo do passo 5:

| Tamanho | Esforço humano-equivalente |
|---|---|
| PP | 1–2 dias úteis |
| P | 3–5 dias úteis |
| M | 1–2 semanas |
| G | 3–4 semanas |
| GG | mais de 1 mês — o agente deve tentar quebrar em 2+ blocos menores em vez de deixar como GG único; GG é sinal de que o escopo daquela fatia ainda está grande demais para estimar com confiança |

Cada agente também informa **quantas instâncias paralelas** dele fariam sentido para aquele escopo específico (ex.: normalmente 1 Arquiteto de Soluções; 2–3 Devs em paralelo se houver módulos claramente independentes; geralmente 1 QA, salvo escopo muito grande) — isso entra tanto no cálculo de custo (mais instância = mais custo simultâneo) quanto no de prazo (mais instância = mais paralelismo = prazo menor).

Nem todo projeto aciona todos os agentes — só os relevantes ao escopo levantado no passo 2. Guia do que cada um tipicamente estima:

| Agente | O que estima nesta fase |
|---|---|
| Arquiteto de Soluções | Desenho de arquitetura de sistema novo, ou levantamento de arquitetura se houver legado envolvido; definição de contratos de integração. |
| UX/UI Designer | Pesquisa + wireframe + protótipo, só se o projeto tiver tela nova ou fluxo existente a redesenhar. |
| Desenvolvedor (Dev) | Implementação por bloco/épico do mapa de escopo — normalmente a maior fatia, e a mais sensível à quantidade de instâncias paralelas. |
| DevOps/SRE | Setup de infraestrutura inicial (se ambiente novo) e o que é recorrente (pipeline de CI/CD, observabilidade básica). |
| Tech Lead/Code Reviewer | Overhead de revisão — normalmente um percentual do tempo de Dev (referência do próprio arquivo: 30%+ do tempo de um sênior), não um bloco isolado à parte. |
| Segurança/AppSec | Só entra como bloco separado se o projeto pedir threat modeling formal ou compliance regulatório (LGPD/GDPR etc.); em projeto pequeno sem dado sensível, pode não gerar bloco próprio. |
| QA | Ciclo de teste manual + automação do escopo levantado. |
| Scrum Master | Não estima bloco próprio (papel de facilitação contínua, não uma entrega isolada) — em vez disso, ajuda o Gerente de Projeto a identificar dependência/sequência entre os blocos que os outros estimaram. |

### 4. Converter esforço humano-equivalente em prazo real de calendário (velocidade do time de agentes)

**Este é o passo mais sujeito a erro do skill inteiro — trate o multiplicador abaixo como ponto de partida a calibrar com a experiência real de projetos rodados por este time, não como fato assentado.** A pesquisa de mercado 2026 sobre produtividade de agente de IA (METR, rollout de agente de linha de comando em empresa, estudos de "paradoxo de produtividade") mostra ganho real mas **desigual por tipo de tarefa**, e aponta retrabalho/incidente escondido como o erro mais caro quando o ganho de velocidade é tratado como uniforme. Por isso a conversão é por **tipo de trabalho**, não um fator único:

| Tipo de trabalho | Exemplos | Conversão de partida (esforço humano-equivalente → calendário do time de agentes) |
|---|---|---|
| Pesquisa, análise estruturada, redação, backlog/critério de aceite, diagrama/ADR | PO levantando requisito, Arquiteto desenhando C4/ADR, UX/UI produzindo wireframe/protótipo | Compressão forte: 1 dia de esforço humano-equivalente tende a sair em **horas** de agente — mas sempre seguido de uma janela de revisão humana do usuário antes de virar decisão final; essa revisão não compre nunca. |
| Implementação de código com escopo bem definido, revisão de PR, ciclo de teste | Dev implementando um bloco, Tech Lead revisando, QA testando | Compressão real porém moderada: esforço humano-equivalente em dias tende a reduzir para uma fração de **1/3 a 1/8** em dias de calendário (ex. um bloco M de "1–2 semanas humano" tende a sair em 1–3 dias de calendário de agente, já incluindo o ciclo de revisão) — não zere o tempo de revisão/correção: é exatamente aí que a pesquisa de 2026 registra o "paradoxo de produtividade" (retrabalho e incidente que aparecem semanas depois quando esse tempo é comprimido a zero). |
| Trabalho com espera externa dominante | Aprovação/feedback do cliente, provisionamento de infraestrutura regulada, aprovação de terceiro/parceiro, revisão jurídica/compliance, publicação em loja de app | **Não comprime.** Mantém o tempo real de calendário da espera, independente da velocidade do agente. |

O prazo final de qualquer bloco do caminho crítico é o **maior** entre (trabalho do time em velocidade de agente) e (soma das esperas externas daquele bloco) — nunca simplesmente a soma otimista de tudo em velocidade de agente.

### 5. Estimar custo com a tabela de mercado (três cenários — PERT)

Para cada bloco/papel estimado no passo 3, calcule o custo de referência usando `CUSTO_MERCADO_SP.md` (valor sênior de mercado em São Paulo, dia-equivalente por papel) × esforço humano-equivalente (T-shirt) × quantidade de instâncias paralelas. Produza **três cenários**, no formato PERT (estimativa de três pontos), em vez de um número único:

- **Otimista (O):** T-shirt do passo 3 como estimado, sem retrabalho.
- **Provável (M):** T-shirt do passo 3 + margem usual de ida-e-volta de revisão/ajuste (referência de partida: +20% a +30% sobre o otimista).
- **Pessimista / pior caso (P):** um nível de T-shirt acima do estimado (ex. M vira G) OU +50-70% sobre o otimista, o que for maior — representa retrabalho real, escopo mal entendido no discovery, ou dependência externa que atrasou. Esse é o número que o usuário chamou de "pior caso".

Estimativa final ponderada: **E = (O + 4M + P) / 6** (fórmula PERT padrão), aplicada tanto ao custo quanto, se fizer sentido, ao prazo do passo 4.

### 6. Gerente de Projeto consolida

A partir das estimativas individuais de prazo (passo 4) e custo (passo 5), o Gerente de Projeto:

- Soma o que é **sequencial** no prazo (ex.: Arquitetura/UX antes de Dev poder começar aquele bloco específico) e soma o custo de todos os blocos.
- Sobrepõe, no prazo, o que pode rodar **em paralelo** (ex.: DevOps preparando infraestrutura enquanto Dev já avança no que não depende dela) — isso não muda o custo total, só o tempo de calendário.
- Produz o resultado final: uma faixa de duração total de calendário (ex. "2 a 4 semanas úteis", já em velocidade de agente + espera externa do passo 4), o custo total nos três cenários PERT (otimista / provável / pior caso) do passo 5, a tabela de papel × quantidade × duração × custo, e o nível de confiança explícito (ROM — não é compromisso de prazo/custo fechado).

### 7. Período de manutenção pós-entrega (quadro reduzido)

Depois da entrega, estipule com o cliente um período de manutenção/garantia em **semanas** (parâmetro do projeto, não um valor fixo universal — referência de mercado usual para software sob medida no Brasil gira em torno de 2 a 4 semanas de garantia inicial, ajustável por contrato). Durante esse período:

- **Quadro reduzido, não o time completo:** normalmente só **Dev** (correção de bug/ajuste simples) + **QA** (validar a correção) seguem alocados, com **Tech Lead** em revisão leve pontual — em fração de tempo/alocação parcial, não dedicação plena como durante o projeto.
- **PO, Gerente de Projeto, Arquiteto, UX/UI, DevOps, Segurança/AppSec e Scrum Master ficam sob demanda/escalonamento** durante a manutenção, não continuamente engajados — só entram se o achado exigir (ex. um bug de segurança real aciona Segurança/AppSec mesmo em manutenção).
- Custo da manutenção = (dia-equivalente de mercado dos papéis reduzidos, de `CUSTO_MERCADO_SP.md`) × (fração de alocação combinada, ex. 20-30% de um dia útil) × (duração em dias úteis do período combinado) — registre como uma linha separada do custo do projeto principal, nunca somado sem distinção.

### 8. Registro do resultado

A estimativa macro é registrada em `projetos/<cliente>/ESTIMATIVA_MACRO.md`, contendo pelo menos:

- Data da estimativa.
- O mapa de escopo macro levantado no passo 2 (para rastrear se o escopo mudou depois — se mudou, reaplique este skill em vez de considerar a estimativa antiga ainda válida).
- A tabela de papel × quantidade paralela sugerida × esforço humano-equivalente × prazo real de calendário (passo 4) × custo nos três cenários PERT (passo 5).
- A faixa de duração total do projeto e o custo total (otimista / provável / pior caso), com o nível de confiança explícito (ROM).
- O período de manutenção pós-entrega combinado (semanas), o quadro reduzido e o custo dessa fase, à parte do custo do projeto principal.
- Uma nota explícita do trade-off prazo × custo: mais instâncias paralelas do mesmo papel tendem a encurtar o prazo mas aumentam o custo simultâneo; menos instâncias custam menos mas alongam o prazo. A escolha de onde ficar nessa faixa é do usuário, não do time.

## O que essa estimativa NÃO é

- **Não é** o roadmap de fases/MVP detalhado — isso continua sendo o Gerente de Projeto fazendo o trabalho real dele, já dentro do fluxo normal (`CLAUDE.md` §4), com base no backlog detalhado que o Product Owner escreve depois que o projeto é aceito.
- **Não precisa ser assertiva.** É uma faixa grosseira para decidir prazo/custo com o cliente antes de comprometer o time de verdade. Uma vez que o cliente aceita seguir, o backlog detalhado (PO) e o roadmap de fases (Gerente de Projeto) refinam essa estimativa com precisão real.
- **Não trata a velocidade do agente como uniforme nem como desculpa para pular revisão.** O passo 4 já separa por tipo de trabalho exatamente para não repetir o "paradoxo de produtividade" documentado em 2026 (ganho de velocidade aparente, retrabalho/incidente que aparece depois quando a revisão é comprimida a zero).
- **Não dispensa** a regra 1 do `CLAUDE.md` §6 (pesquisar antes de implementar) — se um agente estiver estimando algo que depende de uma tecnologia/integração desconhecida, uma pesquisa rápida de viabilidade conta para a estimativa, mas não precisa ser a pesquisa profunda que só acontece quando o trabalho real começar.

## Fontes usadas para calibrar a régua de velocidade do passo 4

- https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/ (METR — desenvolvedor experiente pode ficar mais lento com IA quando o tempo de revisão entra na conta)
- https://arxiv.org/pdf/2607.01418 (rollout de agente de linha de comando tipo Claude Code/Copilot CLI em empresa — ganho de produtividade desigual por senioridade: júnior ~26-40%, sênior ~7%)
- https://arxiv.org/pdf/2607.01904 ("AI Writes Faster Than Humans Can Review" — estudo longitudinal do mandato de dobrar uso de IA numa empresa, custo de revisão como gargalo real)
