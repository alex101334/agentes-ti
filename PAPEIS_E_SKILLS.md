# Papéis e Skills — Time agentes-ti

Documento gerado a partir de pesquisa de mercado (web) sobre o que define cada papel em nível SENIOR/ESPECIALISTA em 2025/2026. Serve de base para a criação dos agentes de IA do projeto — ainda não são os agentes em si, apenas o levantamento de skills/ferramentas/metodologias que cada um deve incorporar.

## Índice

- [Product Owner (PO)](#product-owner-po)
- [Gerente de Projeto](#gerente-de-projeto)
- [Arquiteto de Soluções](#arquiteto-de-soluções)
- [Scrum Master](#scrum-master)
- [Desenvolvedor (Dev)](#desenvolvedor-dev)
- [DevOps / SRE](#devops--sre)
- [QA (Quality Assurance)](#qa-quality-assurance)
- [UX/UI Designer](#uxui-designer)
- [Segurança / AppSec](#segurança--appsec)
- [Tech Lead / Code Reviewer](#tech-lead--code-reviewer)

---

## Product Owner (PO)

**Papel:** Product Owner Sênior / Especialista de mercado (2025/2026) — dono do backlog e da entrega de valor de negócio, com foco em extração de requisito, definição de regra de negócio e escrita de critério de aceite testável.


Em 2025/2026, o mercado descreve o PO sênior como a ponte entre stakeholders de negócio e o time de desenvolvimento, dona da visão e do backlog do produto, com autonomia para gerenciar produtos complexos com pouca ou nenhuma supervisão (diferente do pleno, que ainda atua com supervisão moderada e domina apenas a execução tática). O PO sênior lidera a extração de requisito e regra de negócio via entrevistas, workshops de refinamento e técnicas como Event Storming e Story Mapping, traduz isso em user stories no formato INVEST, escreve/aprova critérios de aceite (formato Given-When-Then/Gherkin para comportamento, ou checklist "rule-oriented" para regras de sistema), mantém Definition of Ready e Definition of Done, prioriza o backlog com frameworks como MoSCoW, RICE, WSJF e Kano (nunca só "achismo"), e opera ferramentas de mercado como Jira, Azure DevOps, Confluence e Miro no dia a dia. Certificações de referência citadas pelo mercado são CSPO (Scrum Alliance) e PSPO I/II/III (Scrum.org), com o BABOK (IIBA) como corpo de conhecimento de análise de negócio que sustenta a elicitação de requisito mesmo fora de contexto puramente Scrum. O que separa sênior de pleno não é a ferramenta usada, e sim: autonomia de decisão estratégica sem supervisão, capacidade de mentorar POs juniores, condução (não apenas participação) de workshops multi-stakeholder, uso de dado/priorização quantitativa em vez de intuição, e responsabilidade final pela qualidade e completude dos itens de backlog antes de entrarem no sprint.

#### Responsabilidades

- Definir e evoluir a visão de produto e alinhar com a estratégia do negócio
- Ser o principal ponto de contato entre stakeholders de negócio, clientes e o time de desenvolvimento, navegando perspectivas divergentes até alinhamento
- Conduzir (não só participar de) reuniões e workshops de levantamento de requisito e mapeamento de processo com stakeholders e arquitetos de sistema
- Escrever, priorizar e manter o backlog do produto atualizado, com user stories detalhadas e critérios de aceite bem documentados
- Escrever e aprovar critérios de aceite, dando a aceitação final da user story antes de considerá-la 'pronta'
- Conduzir backlog refinement, sprint planning, release planning e demonstrações de produto dentro do framework Agile/Scrum
- Traduzir requisitos de negócio brutos em user stories claras e regras de negócio explícitas e testáveis
- Garantir que cada item do backlog atenda à Definition of Ready antes de entrar no sprint e à Definition of Done antes de ser aceito como concluído
- Priorizar funcionalidades com base em valor de negócio/ROI usando frameworks formais (MoSCoW, RICE, WSJF, Kano) em vez de opinião isolada
- Realizar análise de mercado e de dados para embasar decisão de priorização e roadmap
- Mentorar e orientar POs juniores/plenos (diferencial explícito do nível sênior)
- Gerenciar o ciclo de vida completo do produto, incluindo dependências entre itens de backlog e riscos


#### Hard skills

- Escrita de user story seguindo critérios INVEST (Independent, Negotiable, Valuable, Estimable, Small, Testable)
- Escrita de critério de aceite em formato Given-When-Then/Gherkin (BDD) para comportamento, e em formato checklist ('rule-oriented') para regras de sistema mais amplas
- Elicitação de requisito via entrevista estruturada com stakeholder
- Facilitação de workshop de levantamento de requisito e mapeamento de processo (requirements gathering workshop)
- Event Storming — técnica colaborativa (Alberto Brandolini) para modelar domínio de negócio complexo com post-its, usada para achar eventos, comandos, regras de negócio (políticas) e sistemas externos
- Story Mapping — organizar user stories no contexto de uso para priorizar e sequenciar entrega
- Priorização de backlog com MoSCoW, RICE (Reach, Impact, Confidence, Effort), WSJF (Weighted Shortest Job First) e Kano Model
- Definição e manutenção de Definition of Ready (DoR) e Definition of Done (DoD)
- Análise de dados e pesquisa de mercado para decisão orientada a dado
- Gestão de stakeholder e comunicação executiva
- Conhecimento de técnicas de análise de negócio do BABOK (ex. scope modeling, context diagram) mesmo fora de um BA formal
- Noções básicas de SQL/XML e business intelligence (citado em vagas seniores como diferencial técnico)


#### Ferramentas de mercado

- Jira (gestão de backlog, sprint, épicos/stories)
- Azure DevOps (backlog, work items, boards)
- Confluence (documentação de requisito, regra de negócio, DoR/DoD)
- Miro (workshops remotos, Event Storming, Story Mapping, integração bidirecional com Azure DevOps via Azure Cards)
- Rally (citado em vaga sênior como ferramenta Agile alternativa)


#### Metodologias / certificações de referência

- CSPO — Certified Scrum Product Owner (Scrum Alliance): curso de 2 dias sem exame, cobre framework/princípios/valores do Scrum, gestão de backlog, visão de produto; renovação a cada 2 anos via Scrum Education Units; progressão para A-CSPO (Advanced) e CSP-PO (Certified Scrum Professional - Product Owner)
- PSPO I/II/III — Professional Scrum Product Owner (Scrum.org): PSPO I é nível fundamental (teoria do Scrum Guide); PSPO II é nível avançado (visão, backlog, engajamento de stakeholder); PSPO III é nível distinguished (domínio profundo de accountability do PO e Scrum Values em cenários organizacionais variados) — avaliação por exame, sem curso obrigatório, taxas de US$200/US$2.550/US$500 respectivamente
- BABOK Guide (IIBA) — corpo de conhecimento de análise de negócio, com a área 'Elicitation and Collaboration' cobrindo preparação, condução e confirmação de elicitação de requisito, mais de 50 técnicas (ex. entrevista, workshop, análise de documento) e uma perspectiva Agile explícita que conecta ao vocabulário de user story/backlog
- Scrum/Agile/Lean/Kanban como base metodológica geral exigida em praticamente toda vaga de PO pleno/sênior no Brasil e no mercado internacional


#### Entregáveis típicos

- Backlog do produto priorizado e atualizado
- User stories no formato padrão (papel/ação/valor) atendendo aos critérios INVEST
- Critérios de aceite por story (Given-When-Then/Gherkin ou checklist de regra)
- Definition of Ready (DoR) — critério de entrada de item no sprint
- Definition of Done (DoD) — critério de conclusão/aceite de item, muitas vezes padronizado para toda a organização
- Documento de regra de negócio derivado da elicitação (entrevista/workshop/Event Storming)
- Roadmap e visão de produto
- Relatórios/artefatos de priorização (matriz RICE, score WSJF, etc.)
- Ata/artefato de workshop de requisito (ex. board de Event Storming ou Story Map)


#### O que diferencia sênior de pleno

- Autonomia: PO sênior gerencia produto complexo com pouca ou nenhuma supervisão; pleno ainda atua com supervisão/orientação e domina majoritariamente a execução tática do backlog
- Escopo de decisão: sênior influencia decisões estratégicas e modelo de entrega, não só mantém o backlog do dia a dia
- Liderança de workshop: sênior conduz e facilita reuniões de elicitação com múltiplos stakeholders e arquitetos; pleno participa e mantém contato direto mas com menor protagonismo de condução
- Mentoria: sênior orienta e treina POs juniores/plenos — atribuição explicitamente listada só no nível sênior
- Uso de dado vs. intuição: sênior usa análise de mercado, dado quantitativo e frameworks formais de priorização (RICE/WSJF) para decisão, não opinião isolada
- Experiência: faixas de mercado citam de 3-5 anos para pleno e vagas seniores pedindo 3-12+ anos combinando PO e Business Analyst, com formação avançada (mestrado) valorizada
- Remuneração como proxy de mercado: no Brasil, PO pleno citado em torno de R$12.000 e sênior R$15.500-18.000+ (fonte Robert Half via agregador), refletindo maior responsabilidade e menor necessidade de supervisão
- Certificação: nível sênior frequentemente associado a certificação avançada (PSPO II/III, A-CSPO/CSP-PO) e não apenas ao nível de entrada (PSPO I/CSPO básico)


<details>
<summary>Fontes (20)</summary>

- https://interviewkickstart.com/job-description/product-owner
- https://www.velvetjobs.com/job-descriptions/senior-product-owner
- https://carreirasfiveacts.factorialhr.com.br/job_posting/product-owner-pleno-senior-294964
- https://analisederequisitos.com.br/product-owner-salario/
- https://www.scrumalliance.org/get-certified/product-owner-track/certified-scrum-product-owner
- https://www.scrum.org/professional-scrum-product-owner-certifications
- https://www.scrum.org/resources/blog/how-pass-product-owner-certification-pspo-i-pspo-ii-and-pspo-iii
- https://www.iiba.org/knowledgehub/business-analysis-body-of-knowledge-babok-guide/
- https://www.iiba.org/knowledgehub/business-analysis-body-of-knowledge-babok-guide/10-techniques/
- https://www.altexsoft.com/blog/acceptance-criteria-purposes-formats-and-best-practices/
- https://testquality.com/gherkin-user-stories-acceptance-criteria-guide/
- https://www.xolv.io/blog/event-storming-the-visual-requirements-facilitation-technique-to-accelerate-software-design-and-development
- https://www.romanpichler.com/blog/the-definition-of-ready/
- https://resources.scrumalliance.org/Article/definition-vs-ready
- https://www.resolution.de/post/product-backlog-prioritization-techniques/
- https://productschool.com/blog/product-fundamentals/ultimate-guide-product-prioritization
- https://blog.logrocket.com/product-management/writing-meaningful-user-stories-invest-principle/
- https://www.boost.co.nz/blog/2021/10/invest-criteria/
- https://miro.com/strategic-planning/storymapping/
- https://miro.com/marketplace/azure-cards/

</details>


---

## Gerente de Projeto

**Papel:** Gerente de Projetos de TI Sênior / Especialista (Senior IT Project Manager — em algumas estruturas também chamado de Program Manager, Head of PMO ou Project Executive), com foco em planejamento estratégico de fases de entrega, definição de MVP e roadmap até a entrega final. Panorama 2025/2026 com base em fontes de mercado (PMI, vagas reais, comparativos de ferramentas e metodologia).


Em 2025/2026 o Gerente de Projetos de TI Sênior/Especialista deixou de ser só "executor de cronograma" para atuar como conector entre a visão executiva e a execução técnica, entrando cedo nas discussões estratégicas, ajudando a definir o próprio projeto (não só entregá-lo) e traduzindo objetivos de negócio em roadmap de tecnologia. O PMI (Pulse of the Profession 2025) chama isso de "business acumen": só 18% dos profissionais de projeto hoje demonstram alto acumen de negócio, mas esse grupo entrega 83% de aderência a metas de negócio, 63% a prazo e 73% a orçamento, contra desempenho bem inferior do restante. O nível sênior/especialista se diferencia do pleno por escopo (iniciativas enterprise multi-sistema vs. projeto único de escopo definido), autonomia (interlocução direta com C-level, ponto de escalonamento de bloqueios), e por identificar problemas ainda não endereçados e construir consenso/orçamento para resolvê-los — não só executar escopo já definido por outros.

#### Responsabilidades

- Planejamento estratégico de projeto: traduzir metas organizacionais em plano acionável com escopo, objetivos, cronograma e riscos alinhados à visão de negócio (Edstellar, 2026)
- Entrar em discussões de planejamento inicial/estratégico e ajudar a DEFINIR o projeto (não só recebê-lo pronto), moldando roadmap e prioridades de investimento junto à liderança executiva (PMO Partners, 2025)
- Gestão de portfólio: priorizar iniciativas por valor de negócio e disponibilidade de recursos, atuando como agente de mudança entre áreas de TI (LaunchNotes / DevOpsSchool, 2026)
- Definir e validar o project charter com outcomes e métricas de sucesso claras, e produzir o plano integrado com marcos e mapa de dependências (LaunchNotes, 2026)
- Definir o escopo do MVP ('MVP scope locked' como marco formal de entrega) e conduzir a validação incremental de hipóteses antes do build completo (LaunchNotes 2026; Netguru, MVP Roadmap Guide)
- Gerenciar equipes multidisciplinares e multi-sistema, coordenando dependências cross-departamento e integrações complexas em iniciativas enterprise (PMO Partners, 2025)
- Gestão de fornecedores/contratos: seleção de vendor, negociação contratual (custo, prazo, qualidade) e fiscalização de obrigações contratuais em múltiplos parceiros externos (Edstellar 2026; PMO Partners 2025)
- Gestão de riscos: identificar, avaliar, priorizar top riscos com dono e data de mitigação designados, plano de contingência (LaunchNotes 2026; Edstellar 2026)
- Gestão de stakeholders e comunicação executiva: mapear interessados, gerenciar expectativas, reportar direto a executivos e servir de ponto de escalonamento (PMO Partners 2025; Edstellar 2026)
- Gestão de mudança (change management), documentação viva de decisões e relatórios de progresso/risco ao longo do ciclo de vida (Edstellar, 2026)


#### Hard skills

- Gestão de escopo, prazo e custo (triple constraint) segundo as áreas de conhecimento do PMBOK — integração, escopo, cronograma, custos, qualidade, recursos, comunicação, riscos, aquisições e partes interessadas (GestaoIndustrial.com; PMI)
- Gestão de riscos com registro formal (RAID log/registro de riscos), dono e data de mitigação por item, não apenas lista qualitativa (LaunchNotes, 2026)
- Construção e manutenção de roadmap de produto/projeto: sequenciamento de entregas e iniciativas num horizonte de 6–18 meses, amarrado à estratégia de negócio (Product School, 2025)
- Definição de MVP: escopar a versão mínima testável para validar hipótese de negócio com o menor esforço, distinguindo MVP (experimento pontual) de roadmap (plano de evolução contínua pós-mercado) (Atlassian; Product School; Netguru)
- Planejamento em fases (phase-gate/stage-gate): descoberta → priorização de features → mapeamento de jornada → planejamento técnico → estratégia de lançamento → iteração contínua (Netguru/Rapidops, framework de 6 fases para MVP roadmap)
- Gestão de stakeholders e 'power skills': comunicação, negociação, influência sem autoridade formal, liderança de equipes distribuídas multi-timezone (PMI Talent Triangle)
- Business acumen: entender como o projeto se conecta à estratégia do negócio, ler indicadores financeiros, falar a língua do executivo — hoje o maior gap de capacitação do mercado segundo o PMI (só 25% do tempo de treinamento vai para isso, contra 46% para skills técnicas) (PMI Pulse of the Profession 2025)
- Gestão financeira e orçamentária do projeto: alocação de budget, fluxo de pagamentos, controle de burn rate e prevenção de overrun (Artia; Edstellar)
- Gestão de contratos e compliance/governança, inclusive leitura jurídica básica para SLAs e obrigações de fornecedor (PMO Partners, 2025)
- Gestão de qualidade: definição de critérios de aceite, processos de QA e ações corretivas ao longo do ciclo (Edstellar, 2026)


#### Ferramentas de mercado

- Jira (Atlassian) — padrão de mercado para times ágeis/dev em 2026, com Atlassian Intelligence e integração nativa com Confluence e Bitbucket (Monday.com blog, Jira vs Azure DevOps 2026)
- Azure DevOps — cobre todo o ciclo de vida de desenvolvimento (ALM), com CI/CD nativo, Azure Test Plans embutido (sem precisar de plugin como o Zephyr do Jira) e forte integração com stack Microsoft; escala bem para grandes empresas (GetGuru; Monday.com)
- Monday.com — 'Work OS' com CRM, Dev e Service nativos; interface mais simples, indicado para times menores a médios que também querem visão de portfólio (Monday.com, MS Project Alternative 2026)
- Microsoft Project (MS Project) — forte em gestão de recursos complexa e cronograma tradicional/waterfall; usado como referência de planejamento formal em contextos PMBOK/PRINCE2 (Monday.com; LarkSuite, Jira vs MS Project 2026)
- Confluence — documentação viva de decisões, project charter e plano de fases, companion natural do Jira
- Ferramentas de portfólio enterprise (ex.: Planview AdaptiveWork) — para controle financeiro, otimização de recursos e dashboards que conectam execução a outcome de negócio em grandes organizações (Till Freitag, Best PM Tools)


#### Metodologias / certificações de referência

- PMBOK 7ª edição / PMP (PMI) — passou de guia baseado em processos para um guia baseado em princípios e entrega de valor (outcome-focused), cobrindo abordagens preditiva, ágil e híbrida na mesma certificação; é a credencial mais reconhecida globalmente para PM sênior (Visual Paradigm; KnowledgeHut)
- PMI Talent Triangle — framework de PDU/recertificação em 3 eixos: Ways of Working (técnica/ferramentas), Power Skills (liderança e comunicação) e Business Acumen (leitura de negócio/estratégia); é hoje o critério de desenvolvimento contínuo cobrado pelo PMI (PMI.org, Talent Triangle)
- PRINCE2 (Practitioner) — metodologia baseada em processos e governança por estágios (7 princípios, 7 temas, 7 processos), mais forte em ambientes regulados/controlados; mais difundida na Europa/Ásia, crescendo no Brasil (Tempest; GestaoIndustrial.com)
- Modelo híbrido PMBOK+PRINCE2 ou PMBOK+Ágil — comum em grandes empresas reguladas: PMBOK/Ágil conduz a execução enquanto PRINCE2 (ou um framework de governança equivalente) garante controle e compliance; exige papéis e governança bem definidos para não gerar ambiguidade (KnowledgeHut, PRINCE2 vs PMP vs Agile)
- Agile/Scrum híbrido — usado majoritariamente na fase de MVP e iteração (sprints, backlog, entrega incremental) combinado com marcos/fases formais de governança tipo waterfall para reporte executivo e contratos; é a abordagem dominante recomendada para roadmap de MVP (Product School; Rapidops)
- CAPM — certificação de entrada do PMI, geralmente não é o diferencial de senioridade, mas serve de base antes do PMP (Manager2Be, PMP vs CAPM vs PRINCE2 vs Agile)


#### Entregáveis típicos

- Project Charter alinhado a PMBOK — objetivos SMART, critérios de sucesso, riscos, premissas, restrições, orçamento, lista de stakeholders e marco-resumo por fase (ProjectManagement.com, Project Charter Template)
- Roadmap de projeto/produto — sequenciamento de iniciativas e entregas em horizonte de 6 a 18 meses, amarrado à estratégia de negócio e não apenas a uma lista de features (Product School, 2025)
- MVP scope document / escopo de MVP travado ('MVP scope locked') como marco formal e verificável de entrega, distinto do roadmap de evolução pós-MVP (LaunchNotes 2026; Atlassian)
- Plano integrado de fases (phase plan) com marcos, mapa de dependências e baseline de cronograma/custo (LaunchNotes, 2026)
- Registro de riscos (RAID log) com top riscos, dono e data de mitigação por item (LaunchNotes, 2026)
- Registro/matriz de stakeholders com plano de comunicação e cadência de reporte executivo (Edstellar 2026; ProjectManagement.com)
- Business case / justificativa de negócio — obrigatório em PRINCE2 e recomendado no PMBOK como base de decisão go/no-go por estágio (GestaoIndustrial.com)
- Relatórios de status e documentação de decisões/mudanças (change log) mantidos vivos durante todo o ciclo de vida do projeto (Edstellar, 2026)


#### O que diferencia sênior de pleno

- Escopo e complexidade: pleno cuida de projeto único com entregáveis e prazos definidos; sênior/especialista responde por iniciativas enterprise multi-sistema, com dependências cross-departamento e prazos estendidos (PMO Partners, 2025)
- Momento de entrada: pleno recebe o escopo já definido; sênior entra nas discussões de planejamento inicial e ajuda a DEFINIR o projeto, moldando roadmap e prioridades de investimento (PMO Partners, 2025)
- Autonomia e interlocução: sênior opera com mais autonomia, visibilidade e influência, fala direto com liderança executiva e é ponto de escalonamento de bloqueios; pleno normalmente reporta a um sênior/PMO (PMO Partners, 2025)
- Profundidade técnica: sênior tem conhecimento multidisciplinar suficiente para entender e questionar detalhes técnicos e conduzir integrações de plataforma sozinho; pleno depende mais de especialistas de domínio para validação técnica (PMO Partners, 2025)
- Gestão de fornecedores e governança: sênior administra múltiplos parceiros externos, negocia e fiscaliza obrigações contratuais e navega política organizacional (exige leitura jurídica/negociação); esse escopo é limitado no nível pleno (PMO Partners, 2025)
- Business acumen: só 18% dos profissionais de projeto no mercado hoje têm alto business acumen — é esse grupo que trava as métricas de sucesso de negócio, prazo e orçamento consistentemente melhores; é o diferencial mais citado entre 'PM que executa' e 'PM estratégico' em 2025 (PMI Pulse of the Profession 2025)
- Anos de experiência de mercado: vagas reais de Senior IT PM pedem tipicamente 8+ anos liderando projetos enterprise de integração de aplicação/dados, com ferramentas de portfólio, contra 2–4 anos e foco de função única no nível pleno (PMO Partners, 2025)
- Capacidade de identificar problemas não endereçados: a diferença central citada por practitioners não é 'executar bem o que já foi decidido', mas achar um problema que ninguém está resolvendo, construir consenso de que ele existe e importa, e conseguir o orçamento/patrocínio para resolvê-lo (Simon Cross, PM Levels, citado nos resultados de busca sobre senior vs mid-level PM)


<details>
<summary>Fontes (27)</summary>

- https://pmopartners.com/2025/07/07/what-separates-senior-it-project-roles-from-mid-level-positions/
- https://www.edstellar.com/blog/it-project-manager-roles-responsibilities
- https://www.launchnotes.com/blog/senior-project-manager-salary-a-comprehensive-guide
- https://www.pmi.org/certifications/certification-resources/maintain/talent-triangle
- https://www.pmi.org/learning/thought-leadership/boosting-business-acumen
- https://www.pmi.org/-/media/pmi/documents/public/pdf/learning/thought-leadership/pulse/pulse_of_the_profession_2025-1.pdf
- https://www.atlassian.com/agile/product-management/minimum-viable-product
- https://productschool.com/blog/product-strategy/what-is-a-product-roadmap
- https://www.netguru.com/blog/roadmap-mvp
- https://www.rapidops.com/blog/planning-your-minimum-viable-product-mvp-roadmap/
- https://www.f22labs.com/blogs/mvp-milestones-deliverables/
- https://skills.visual-paradigm.com/docs/pmbok-essentials-for-beginners/pmbok-fundamentals/pmbok-vs-prince2/
- https://www.knowledgehut.com/blog/project-management/prince2-vs-pmp-vs-agile
- https://www.manager2be.com/post/pmp-vs-capm-vs-prince2-vs-agile-certifications-which-one-is-right-for-you
- https://monday.com/blog/rnd/jira-vs-azure-devops/
- https://monday.com/blog/project-management/ms-project-alternative/
- https://www.getguru.com/reference/jira-vs-azure-devops
- https://www.larksuite.com/en_us/blog/jira-vs-microsoft-project
- https://till-freitag.com/en/blog/best-project-management-tools
- https://www.projectmanagement.com/deliverables/538317/project-charter-template
- https://gestaoindustrial.com/gestao-de-projetos-comparativo-entre-pmbok-e-prince-2/
- https://www.tempest.com.br/sidechannel/prince2-boas-praticas-da-tempest-na-gestao-de-projetos-em-ambiente-controlado
- https://artia.com/blog/gerente-de-projetos/
- https://hub.asimov.academy/blog/gerente-de-projetos-de-ti/
- https://www.roberthalf.com/br/pt/insights/guia-salarial/tecnologia
- https://parsons.wd5.myworkdayjobs.com/en-US/Search/job/Senior-IT-Project-Manager---Strategy-and-Roadmap_R185078
- https://www.simoncross.com/p/pm-levels

</details>


---

## Arquiteto de Soluções

**Papel:** Arquiteto(a) de Soluções Sênior / Especialista (2025-2026)


Em 2025/2026 o Arquiteto de Soluções Sênior é a ponte entre a visão de negócio e a implementação técnica: projeta soluções de ponta a ponta (não só um componente), tanto para sistemas novos (greenfield) quanto para sistemas legados (brownfield). Para sistemas novos, escolhe stack, padrão de arquitetura e contratos de comunicação; para sistemas legados, primeiro conduz um levantamento/discovery estruturado (mapear arquitetura existente, modelo de dados e pontos de integração) antes de propor qualquer mudança, e planeja modernização incremental em vez de reescrita "big bang". A demanda em 2025/2026 é puxada por migração para nuvem e transformação digital, com domínio prático multi-cloud (AWS+Azure+GCP) virando expectativa padrão, não diferencial. O papel se distingue do Arquiteto de Empresa (Enterprise Architect, escopo mais estratégico/portfólio) e do Arquiteto de Software/Técnico (mais fundo em padrões de código): o Arquiteto de Soluções conecta os dois, do conceito de negócio ao blueprint técnico executável.

#### Responsabilidades

- Levantar requisitos de negócio e requisitos não funcionais junto a stakeholders e traduzi-los em blueprint de arquitetura alinhado aos objetivos do negócio (Interview Kickstart, Betterteam)
- Escolher linguagem de programação e stack tecnológico avaliando trade-offs de custo, performance, maturidade da equipe e ecossistema — não por preferência pessoal ou modismo
- Desenhar a arquitetura de integração entre sistemas internos e externos, optando entre padrões como hub-and-spoke, API Gateway (facade/adapter/mediator) e, cada vez menos, ESB tradicional, hoje visto como acoplado demais para times DevOps
- Definir contratos de comunicação entre serviços: REST vs gRPC (síncrono, request-response, caso o chamador precise esperar a resposta) vs mensageria/streaming tipo Kafka/RabbitMQ (assíncrono, orientado a eventos, para desacoplamento)
- Produzir e manter diagramas de arquitetura (C4: Contexto/Container/Componente/Código) e Architecture Decision Records documentando o porquê de cada decisão, não só o quê foi decidido
- Em sistemas legados: conduzir fase de discovery (tipicamente 1-2 semanas) mapeando arquitetura existente, modelo de dados e pontos de integração ANTES de propor mudança, já que o código legado costuma ser a única documentação confiável que sobrou
- Planejar modernização incremental de legado via Strangler Fig Pattern (fachada/proxy redirecionando gradualmente tráfego do sistema antigo para o novo), evitando o risco de reescritas totais
- Atuar como liderança técnica em reuniões de cliente, demos e propostas/RFPs, traduzindo conceitos técnicos complexos para stakeholders de negócio
- Prover liderança técnica, revisão de arquitetura por pares (inclusive peer review de ADRs antes de aceitá-los) e mentoria a arquitetos e desenvolvedores plenos/juniores
- Avaliar atributos de qualidade concorrentes entre si (segurança, escalabilidade, disponibilidade, performance, modificabilidade) e documentar a análise de trade-off por trás da decisão final


#### Hard skills

- Padrões de arquitetura de sistema: microsserviços, monolito modular e arquitetura orientada a eventos (event-driven) — saber qual se aplica a cada contexto, não aplicar por modismo de conferência
- Clean Architecture (Robert C. Martin / 'Uncle Bob') — regra de dependência e separação de camadas independente de framework, UI e banco de dados
- Domain-Driven Design (DDD) — bounded context, ubiquitous language e context mapping; bounded contexts mapeiam naturalmente para microsserviços, módulos ou times
- C4 Model (Simon Brown) — os 4 níveis Contexto/Container/Componente/Código para comunicar arquitetura a públicos diferentes
- ADR (Architecture Decision Record) — estrutura título/status/contexto/decisão/consequências, log append-only, decisão revista vira novo ADR que 'supera' o anterior, nunca edição retroativa
- Enterprise Integration Patterns — pub/sub, saga, CQRS, event sourcing, dead letter channel, message router
- Design de API contract-first: OpenAPI para REST síncrono e AsyncAPI para eventos/mensageria/streaming (Kafka, MQTT, WebSockets)
- Domínio prático multi-cloud (AWS + Azure + GCP) — hoje esperado pela maioria das organizações contratantes, não domínio de uma nuvem só
- Métodos formais de trade-off de atributos de qualidade, como o ATAM (SEI/Carnegie Mellon), para decisão de arquitetura orientada a risco em vez de opinião


#### Ferramentas de mercado

- draw.io / diagrams.net — gratuito, cobre diagramação básica
- Lucidchart — padrão de mercado para colaboração empresarial em tempo real
- PlantUML — DSL para C4, UML, BPMN e ERD versionável como código
- Miro — quadro colaborativo de tela infinita para workshops e revisões cross-funcionais
- Structurizr — ferramenta de referência para 'C4 as code': um único modelo em DSL gera automaticamente as views de Contexto/Container/Componente
- Mermaid e D2 — alternativas emergentes de diagram-as-code, com renderização nativa em GitHub/GitLab/Notion sem dependência de servidor


#### Metodologias / certificações de referência

- TOGAF 10 (The Open Group) — foco estratégico/enterprise (ADM), mais sobre alinhamento negócio-TI do que tecnologia específica; ainda referência para cargos sêniores de Solutions/Enterprise Architect em 2025
- AWS Certified Solutions Architect – Associate e Professional
- Microsoft Certified: Azure Solutions Architect Expert (exame AZ-305)
- Google Professional Cloud Architect
- ATAM — Architecture Tradeoff Analysis Method (SEI, Carnegie Mellon) — método formal de avaliação de arquitetura por cenários de atributo de qualidade


#### Entregáveis típicos

- Diagramas C4 (Contexto, Container, Componente e, quando necessário, Código)
- ADRs indexados, um por decisão arquitetural relevante, com status Proposto/Aceito/Superado e link entre decisões relacionadas
- Contrato de API formal: especificação OpenAPI para REST e/ou AsyncAPI para eventos e mensageria
- Blueprint/roadmap de arquitetura com fases de migração, incluindo plano de Strangler Fig quando há substituição de legado
- Relatório de discovery de sistema legado: arquitetura existente, modelo de dados, pontos de integração e riscos levantados antes de propor mudança
- Documento de análise de trade-off de atributos de qualidade (linha ATAM) justificando decisões não óbvias com cenários e sensibilidades


#### O que diferencia sênior de pleno

- Tempo e profundidade: pleno tipicamente tem 3-5 anos dominando 2-3 linguagens/frameworks; sênior tem 5+ anos e arquiteta com fluência independente da linguagem específica
- Velocidade de diagnóstico: sênior chega à decisão em minutos por já ter mapa mental do domínio e das armadilhas conhecidas; pleno ainda gasta tempo relevante pesquisando a mesma resposta
- Escopo da decisão: sênior toma decisões de arquitetura de sistemas inteiros e lidera tecnicamente o projeto; pleno normalmente implementa dentro de uma arquitetura já decidida por outra pessoa
- Mentoria e revisão de pares: sênior faz peer review de ADRs de outros arquitetos e mentora plenos/juniores — não é expectativa de papel do pleno
- Ponte com negócio: sênior lidera a conversa com RFP, stakeholders e proposta comercial; pleno raramente conduz essa interface sozinho
- Trade-off documentado, não opinião: sênior demonstra raciocínio de arquitetura em ADR com consequência assumida por escrito, em vez de 'geralmente é assim' sem lastro
- Anos de experiência não é sinônimo automático de senioridade — anos de carteira de habilitação não tornam alguém motorista habilidoso; senioridade se mede pela qualidade da decisão sob trade-off, não só pelo tempo de casa


<details>
<summary>Fontes (46)</summary>

- https://interviewkickstart.com/job-description/solutions-architect
- https://www.indeed.com/hire/job-description/solution-architect
- https://www.betterteam.com/senior-solutions-architect-job-description
- https://interviewguy.com/senior-solutions-architect-job-description/
- https://www.ardoq.com/knowledge-hub/enterprise-architecture-vs-solution-architecture
- https://www.indeed.com/career-advice/finding-a-job/solutions-architect-vs-enterprise-architect
- https://www.leanix.net/en/wiki/ea/enterprise-architect-vs-solution-architect-vs-technical-architect-whats-the-difference
- https://c4model.com/
- https://simonbrown.je/
- https://structurizr.com/
- https://adr.github.io/
- https://adr.github.io/adr-templates/
- https://www.techtarget.com/searchapparchitecture/tip/4-best-practices-for-creating-architecture-decision-records
- https://learn.microsoft.com/en-us/azure/well-architected/architect-role/architecture-decision-record
- https://aws.amazon.com/blogs/architecture/master-architecture-decision-records-adrs-best-practices-for-effective-decision-making/
- https://solguruz.com/blog/brownfield-development-guide/
- https://hexaware.com/blogs/a-practical-guide-to-reverse-engineering-legacy-systems/
- https://www.knowledgehut.com/blog/it-service-management/togaf-certification-value
- https://www.advisedskills.com/blog/enterprise-architecture/why-togaf-r-certification-still-matters-in-2025
- https://www.opengroup.org/certifications/togaf-certification-portfolio
- https://www.coursera.org/articles/cloud-architect-certification
- https://www.analyticsinsight.net/career/best-cloud-architect-certifications-in-2026-aws-vs-azure-vs-gcp
- https://medium.com/@kittikawin_ball/microservices-vs-monoliths-architecture-decision-framework-for-2025-98c8ff2ec484
- https://www.ness.com/blog/modular-monolith-vs-microservices/
- https://bishrulhaq.com/posts/modern-software-architecture-in-2026-modular-monoliths-microservices-event-driven-systems-and-ai-agents
- https://dhnavd.medium.com/clean-architecture-and-domain-driven-design-f4171786c0ed
- https://blog.glen-thomas.com/architecture/2025/01/15/domain-driven-design-for-architects.html
- https://solutions-architect.medium.com/system-design-domain-driven-design-bounded-context-and-context-mapping-c6ecda3c935f
- https://blog.cleancoder.com/
- https://medium.com/@sergey.prusov/rest-vs-grpc-vs-message-brokers-the-architecture-decision-that-could-make-or-break-your-next-2453d56eaa04
- https://www.instaclustr.com/education/apache-kafka/kafka-message-queue-architecture-use-cases-best-practices/
- https://www.asyncapi.com/docs/tutorials/getting-started/coming-from-openapi
- https://apiscout.dev/guides/api-documentation-openapi-vs-asyncapi-2026
- https://www.api-contract-testing.com/api-contract-fundamentals-tool-selection/openapi-specification-deep-dive/how-to-choose-between-openapi-and-asyncapi-for-microservices/
- https://icepanel.io/blog/2025-03-12-the-best-alternatives-to-lucidchart-for-software-architecture-diagrams
- https://infrasketch.net/blog/best-system-architecture-diagramming-tools-2026
- https://infrasketch.net/blog/best-diagram-as-code-tools-2026
- https://proxify.io/knowledge-base/software-development/difference-between-junior-mid-senior-developers
- https://www.deptagency.com/insight/junior-vs-mid-vs-senior-software-engineers-experience-skills-expectations-2/
- https://www.zippia.com/software-architect-jobs/software-architect-vs-senior-software-development-engineer-differences/
- https://ezintegrations.ai/enterprise-integration-patterns/
- https://en.wikipedia.org/wiki/Architecture_tradeoff_analysis_method
- https://www.sei.cmu.edu/documents/629/2000_005_001_13706.pdf
- https://learn.microsoft.com/en-us/azure/architecture/patterns/strangler-fig
- https://www.thoughtworks.com/en-us/insights/articles/embracing-strangler-fig-pattern-legacy-modernization-part-one
- https://brainhub.eu/library/strangler-pattern-legacy-modernization

</details>


---

## Scrum Master

**Papel:** Scrum Master Senior / Especialista (2025/2026), com foco em quebra de historia com o time de Dev, estimativa de entrega e gestao de prazo de tarefa


Em 2025/2026 o mercado (job descriptions, Atlassian, Scrum.org, Mountain Goat Software) descreve o Scrum Master Senior como alguem que vai alem de facilitar cerimonias: ele lidera tecnicamente o refinamento e a quebra de historias com o time de desenvolvimento (INVEST, SPIDR), conduz estimativa via Planning Poker/story points, monitora metricas de fluxo (velocity, burndown, burnup, cycle time, lead time, throughput) para prever e proteger prazo de entrega, remove impedimentos e gerencia dependencias entre times, e reporta status de forma transparente a stakeholders e lideranca. A diferenca central para o Scrum Master pleno e escopo (multiplos times/escala), autonomia, dominio de metricas preditivas e mentoria de outros Scrum Masters, nao apenas execucao de cerimonia.

#### Responsabilidades

- Facilitar as cerimonias ageis (sprint planning, daily, sprint review/demo, retrospectiva) protegendo o time de overcommitment e scope creep (Atlassian, GoRetro)
- Conduzir e coachear o refinamento do backlog junto ao time de Dev e ao Product Owner, garantindo historias com criterio INVEST e Definition of Ready antes da sprint planning (Mountain Goat Software)
- Quebrar historias grandes em itens menores e entregaveis usando tecnicas como SPIDR (Spikes, Paths, Interfaces, Data, Rules) (Mountain Goat Software)
- Facilitar a estimativa de esforco com o time (Planning Poker/story points), evitando ancoragem e convergencia apressada (Mountain Goat Software, Scrum.org)
- Identificar dependencias entre tarefas/times e considera-las na estimativa e no planejamento de release, cuidando de prazos e restricoes de capacidade, orcamento e qualidade (VelvetJobs - Senior Scrum Master JD)
- Monitorar e reportar metricas ageis (velocity, burndown, burnup, cycle time) para dar visibilidade real de prazo a stakeholders (AgileSeekers, Scrum Institute)
- Identificar, rastrear e remover impedimentos, escalando bloqueios organizacionais e dependencias cross-team quando necessario (Azure DevOps docs)
- Coordenar multiplos times Scrum e atuar como ponte com a alta lideranca em cenarios de escala (Senior Scrum Master vs Scrum Master, ProThoughts Solutions)
- Mentorar e desenvolver outros Scrum Masters e apoiar a maturidade agil da organizacao (ProThoughts Solutions, LinkedIn - Riaan Roos)
- Gerenciar end-to-end a entrega, controlando as restricoes do projeto (escopo, prazo, qualidade) em vez de apenas assistir o time (VelvetJobs, ProThoughts Solutions)


#### Hard skills

- Facilitacao de cerimonias ageis (planning, daily, review, retrospectiva, refinamento)
- Refinamento e quebra de user story (INVEST, SPIDR - spikes/paths/interfaces/data/rules)
- Tecnicas de estimativa: Planning Poker, story points (sequencia Fibonacci), T-shirt sizing
- Metricas ageis: velocity, burndown chart, burnup chart, cycle time, lead time, throughput
- Gestao de impedimentos e dependencias cross-team
- Gestao de risco, capacidade e prazo de release/roadmap
- Coaching de time e de Product Owner; facilitacao de conflito
- Leitura e comunicacao de dados de entrega para stakeholders e lideranca (reporting)
- Mentoria de outros Scrum Masters e maturidade agil organizacional


#### Ferramentas de mercado

- Jira (backlog, sprints, relatorios de burndown/velocity)
- Azure DevOps / Azure Boards (backlog, work item 'impediment', sprint reports)
- Miro (ou Mural) para refinamento colaborativo e backlog grooming remoto
- Confluence (documentacao de processo e Definition of Done/Ready)
- Ferramentas de Planning Poker online (ex.: Scrumpoker-online, Planning Poker da Mountain Goat Software)
- Dashboards de metricas de fluxo (relatorios nativos do Jira/Azure DevOps, Power BI)
- Slack/Microsoft Teams para comunicacao assincrona com o time e stakeholders


#### Metodologias / certificações de referência

- CSM - Certified ScrumMaster (Scrum Alliance) - certificacao de entrada com foco em facilitacao e coaching de time, exige treinamento com trainer credenciado
- A-CSM / CSP-SM (Scrum Alliance) - trilha avancada/profissional sobre o CSM, voltada a Scrum Masters com experiencia
- PSM I - Professional Scrum Master I (Scrum.org) - exame sem treinamento obrigatorio, validade vitalicia, considerado rigoroso para nivel de entrada
- PSM II / Professional Scrum Master - Advanced (Scrum.org) - nivel avancado para Scrum Masters com pelo menos 1 ano de experiencia, aprofunda resolucao de problemas complexos e as responsabilidades do Scrum Master
- SAFe Scrum Master (SSM) e SAFe Advanced Scrum Master (SASM) (Scaled Agile) - voltadas a escala multi-time/portfolio em ambiente enterprise, procuradas quando ha coordenacao de varios times no mesmo produto
- Kanban / metricas de fluxo (cycle time, lead time, throughput) como complemento ao Scrum em times hibridos


#### Entregáveis típicos

- Backlog priorizado e refinado, com historias no padrao INVEST e Definition of Ready cumprida
- Sprint plan / sprint backlog com escopo e capacidade do time definidos
- Relatorio de metricas ageis (velocity chart, burndown chart, burnup chart, cycle time) para acompanhamento de prazo
- Log de impedimentos com status de resolucao e escalonamentos
- Atas de retrospectiva com plano de acao e follow-up
- Plano de release/roadmap com dependencias entre times mapeadas
- Relatorio de status de entrega para stakeholders e lideranca


#### O que diferencia sênior de pleno

- Escopo: pleno atua em 1 time; senior lida com multiplos times, cenarios de escala e maior complexidade organizacional (VelvetJobs, ProThoughts Solutions)
- Autonomia: pleno suporta e assiste o time; senior gerencia a entrega end-to-end e controla restricoes de projeto (escopo, prazo, qualidade, orcamento) (VelvetJobs)
- Metricas: senior tem dominio de planejamento, metricas e reporting em nivel mais analitico/preditivo, nao so acompanhamento basico de burndown (ProThoughts Solutions)
- Relacionamento com lideranca: senior sabe operar com a alta gestao, identifica aliados e coordena entre times para melhorar entrega de valor (LinkedIn - Riaan Roos)
- Mentoria: senior desenvolve outros Scrum Masters, atuando tambem como coach de coaches (ProThoughts Solutions)
- Gestao de dependencia entre tarefas/times: senior antecipa e negocia dependencias que afetam prazo antes que virem bloqueio (VelvetJobs)


<details>
<summary>Fontes (22)</summary>

- https://www.atlassian.com/agile/scrum/scrum-master
- https://www.goretro.ai/post/scrum-master-roles-and-responsibilities
- https://www.velvetjobs.com/job-descriptions/senior-scrum-master
- https://www.mountaingoatsoftware.com/agile/story-points/planning-poker
- https://www.mountaingoatsoftware.com/agile/five-simple-but-powerful-ways-to-split-user-stories
- https://www.mountaingoatsoftware.com/agile/product-backlog-refinement-grooming
- https://www.scrum.org/resources/blog/story-points-are-not-problem-velocity
- https://www.scrum-institute.org/Burndown_Chart.php
- https://agileseekers.com/blog/mastering-scrum-metrics-velocity-burndown-flow-based-insights
- https://www.knowledgehut.com/blog/agile/difference-csm-psm-certification
- https://agilemania.com/psm-vs-csm
- https://www.scrum.org/assessments/professional-scrum-master-ii-certification
- https://www.scrum.org/professional-scrum-certifications/professional-scrum-master-assessments
- https://www.scrum.org/courses/professional-scrum-master-advanced-training
- https://scaledagile.com/blog/what-is-a-scrum-master/
- https://miro.com/blog/scrum-masters-backlog-refinement/
- https://miro.com/agile/what-is-backlog-refinement/
- https://learn.microsoft.com/en-us/azure/devops/organizations/settings/work/change-process-scrum-to-agile?view=azure-devops
- https://github.com/MicrosoftDocs/azure-devops-docs/blob/main/docs/boards/backlogs/manage-issues-impediments.md
- https://www.scrum.org/forum/scrum-forum/62074/whats-difference-between-scrum-master-and-senior-scrum-master
- https://www.linkedin.com/pulse/scrum-master-vs-senior-what-difference-riaan-johannes-roos
- https://prothoughtssolutions.com/blog/senior-scrum-master-and-scrum-master-in-disciplined-agile/

</details>


---

## Desenvolvedor (Dev)

**Papel:** Desenvolvedor(a) de Software Sênior/Especialista Full-Stack Polyglot — profissional de engenharia de aplicação (front-end + back-end + dados/integrações), papel explicitamente separado de DevOps/Infraestrutura. Projeta, implementa, testa e evolui sistemas ponta a ponta trocando de linguagem/stack conforme a exigência do projeto (PHP, JavaScript/TypeScript, HTML/CSS, Java, Node.js, Python, Go, Perl), mantendo o mesmo rigor de arquitetura, teste e qualidade em qualquer stack escolhida.


Em 2025/2026 o "sênior/especialista full-stack polyglot" não é definido por saber sintaxe de várias linguagens, mas por aplicar os mesmos princípios de engenharia (SOLID, Clean Architecture, teste automatizado, Clean Code, Git disciplinado) de forma consistente em qualquer stack que o projeto exigir, e por ir além da execução de tarefas: questiona requisitos, rastreia causa raiz sistêmica (não só o sintoma), toma e documenta decisões de arquitetura (ADRs), mentora quem é pleno/júnior e responde pelo ciclo de vida completo de um sistema — do design ao incidente em produção. É um papel de aplicação, não de infraestrutura: configura e mantém a parte do pipeline de CI que valida o próprio código (lint, teste, build a cada PR), mas a infraestrutura de deploy/observabilidade/nuvem é escopo de DevOps/SRE, um papel separado. No mercado de 2026, TypeScript já é a linguagem mais usada no GitHub e domina o front-end via React/Next.js; no back-end, Node.js (NestJS/Fastify/Express), Python (FastAPI ultrapassando Django/Flask em projetos novos), Java+Spring Boot (ainda dominante em enterprise), PHP (Laravel domina adoção, Symfony domina sistemas grandes/legados) e Go (Gin/Fiber/Echo) convivem conforme o domínio do problema; Perl segue relevante apenas como manutenção de sistemas legados críticos (telecom, financeiro, bioinformática), não para projetos novos. A diferença entre pleno e sênior está mais no raciocínio sistêmico, autonomia arquitetural e impacto sobre o time do que no número de linguagens dominadas; a diferença entre sênior e staff/principal está no raio de impacto (um time/sistema vs. múltiplos times/organização).

#### Responsabilidades

- Projetar e implementar funcionalidades ponta a ponta (front-end, back-end, integrações e modelagem de dados), escolhendo a linguagem/stack mais adequada ao problema do projeto entre PHP, JS/TS, Java, Node.js, Python, Go e Perl
- Tomar decisões de arquitetura e design dentro do escopo de uma aplicação/sistema, documentando-as (ex.: Architecture Decision Records) em vez de decidir só de memória
- Escrever e manter testes automatizados (unitários e de integração) como parte da própria entrega, não como etapa separada feita por QA
- Revisar código de outros desenvolvedores (pull/merge request) focando em lógica, segurança, manutenibilidade e aderência à arquitetura — não em estilo, que fica a cargo de linter/formatter automatizado
- Refatorar e reduzir dívida técnica de forma contínua, identificando causa raiz sistêmica de bugs recorrentes (ex.: schema de dado inconsistente) em vez de só corrigir o sintoma pontual
- Mentorar desenvolvedores plenos/júniores via pareamento e revisão de código, elevando o nível técnico do time (função de multiplicador de força)
- Configurar e manter a parte do pipeline de CI relativa ao próprio código-fonte (lint, testes automatizados, build a cada PR/commit) — sem assumir a infraestrutura de deploy, orquestração ou observabilidade, que é escopo de DevOps/SRE
- Responder pelo ciclo de vida completo de um componente/sistema que possui: do design inicial ao comportamento em produção, incluindo troubleshooting de incidentes
- Questionar e, quando necessário, desafiar requisitos técnicos recebidos, propondo alternativas mais simples/robustas antes de implementar
- Adaptar-se a diferentes paradigmas e stacks mantendo o mesmo padrão de qualidade (postura polyglot), reconhecendo quando uma linguagem legada (ex.: Perl) deve ser mantida como está em vez de reescrita sem necessidade de negócio


#### Hard skills

- PHP: PHP 8.x moderno (typed properties, enums, readonly, attributes) — 89% dos devs PHP já em 8.x; Laravel (framework dominante, ~64% de adoção, ideal para iteração rápida) e Symfony (~23% de adoção, arquitetura explícita e componentizada, preferido em sistemas grandes/longevos); Composer para dependências; PHPUnit para teste unitário (padrão de fato em Laravel e Symfony há duas décadas); PHPStan para análise estática
- JavaScript/TypeScript: TypeScript como padrão de fato — ultrapassou Python e JavaScript como linguagem mais usada no GitHub em agosto/2025 e ~40% dos devs já escrevem só TS; back-end em Node.js com Express (ainda maior base instalada, mas majoritariamente legado), Fastify (2-3x mais throughput que Express, schema-driven) ou NestJS (estrutura com injeção de dependência estilo Angular, padrão para times grandes e microsserviços com gRPC/Kafka); front-end React (uso majoritário entre profissionais) com Next.js, com Vue 3.5, Angular 21 e Astro como alternativas relevantes
- HTML5/CSS3: semântica correta, acessibilidade (WCAG), layout responsivo com Grid/Flexbox/Container Queries, performance de renderização (Core Web Vitals)
- Java: Java 21/25 LTS como baseline de todo app enterprise moderno; Spring Boot (framework enterprise dominante, versão 4.0 GA desde novembro/2025, cobre microsserviços, cloud-native e reativo) com Quarkus/Micronaut como alternativas cloud-native de startup rápido; Maven/Gradle para build; JUnit 5 (e JUnit 6 emergente em times Java 17+) para teste unitário
- Node.js: runtime de back-end JavaScript/TypeScript consolidado; escolha de framework (Express/Fastify/NestJS) orientada por trade-off de throughput vs. estrutura, não por hábito
- Python: FastAPI (crescimento mais acelerado, já referência para APIs novas e back-ends de IA) e Django (ainda líder para aplicações full-stack e sites orientados a conteúdo) como frameworks principais; pytest como framework de teste unitário padrão de fato do ecossistema; tipagem gradual com type hints
- Go: Gin (framework mais usado, ~48% de share no ecossistema, testado em produção em empresas como Google/NVIDIA), Fiber (maior throughput via fasthttp, sem HTTP/2) e Echo (API mais limpa, meio-termo) para APIs/microsserviços; pacote testing nativo + biblioteca Testify como padrão de teste
- Perl: leitura e manutenção responsável de código legado crítico (Perl 5.4x, ainda com releases anuais ativas) em domínios como telecom, financeiro e bioinformática; CPAN/cpanm para dependências; Perl::Critic para análise estática; discernimento de quando manter vs. quando justificar reescrita
- Padrões de projeto (GoF) aplicados por trade-off consciente (Factory, Strategy, Adapter, Observer, Repository etc.), nunca por reflexo ou 'porque é o certo a fazer'
- SOLID e Clean Architecture (Robert C. Martin) como base de desenho: separação entre domínio, aplicação e infraestrutura, núcleo de negócio independente de framework/banco/UI e altamente testável
- Teste unitário como prática central da entrega (não acessório de QA): pirâmide de testes (unitário > integração > E2E), TDD/BDD quando aplicável, cobertura como sinal de risco e não como meta absoluta
- Clean Code: nomes intencionais, funções pequenas e coesas, eliminação de duplicação, código que se explica sem depender de comentário
- Versionamento Git avançado: trunk-based development com branches curtas ou Git Flow conforme maturidade do time, commits atômicos e semânticos (Conventional Commits), rebase interativo, branch protection exigindo CI verde antes do merge


#### Ferramentas de mercado

- IDEs/editores: VS Code (editor mais usado, ~76% dos devs profissionais, forte em JS/TS/Python/Go), JetBrains por linguagem (IntelliJ IDEA para Java — ~84% de adoção entre devs Java, PhpStorm para PHP, PyCharm para Python, GoLand para Go), editores assistidos por IA (ex. Cursor) em crescimento acelerado
- Linters/formatters por stack: ESLint (+ Prettier/Oxlint) para JS/TS; Ruff para Python (substituiu boa parte do ecossistema antigo de lint Python, ordens de magnitude mais rápido, escrito em Rust); PHPStan (+ Larastan para Laravel, PHP-CS-Fixer) para PHP; Checkstyle/SpotBugs para Java; golangci-lint (runner que agrega dezenas de linters Go em paralelo); Perl::Critic para Perl
- Gerenciadores de dependência por linguagem: npm/pnpm para JS/TS; Composer para PHP; pip/uv/Poetry para Python (uv como recomendação para projetos novos em 2026, 10-100x mais rápido que pip); Maven/Gradle para Java; módulos nativos (go mod) para Go; CPAN/cpanm para Perl
- Frameworks de teste unitário: Jest/Vitest para JS/TS (Vitest crescendo mais de 400% desde 2023 em projetos baseados em Vite); PHPUnit para PHP; JUnit 5/6 para Java; pytest para Python; testing nativo + Testify para Go
- Controle de versão e colaboração: Git com GitHub/GitLab/Bitbucket, fluxo via pull/merge request obrigatório antes de integrar ao branch principal
- CI local ao código (visão de dev, não de infra): GitHub Actions/GitLab CI/Jenkins configurados para rodar lint, suíte de testes e build a cada pull request, bloqueando merge se falhar
- Documentação técnica: Architecture Decision Records no formato Nygard (Contexto/Decisão/Consequências) versionados em Markdown junto ao repositório; especificação de API via OpenAPI/Swagger


#### Metodologias / certificações de referência

- SOLID (Robert C. Martin) como base de design orientado a objetos
- Clean Architecture / arquitetura hexagonal (Ports & Adapters) para separar domínio de framework/infraestrutura
- TDD/BDD como prática de desenvolvimento guiado por teste quando o contexto do projeto favorece
- Conventional Commits combinado com Trunk-Based Development (branches curtas, CI obrigatório antes do merge) ou Git Flow, conforme a maturidade e o tamanho do time
- Architecture Decision Records no formato Nygard (Contexto/Decisão/Consequências) para registrar decisões técnicas relevantes
- Code review estruturado e integrado ao pipeline de CI, com checks automatizados (lint/teste/build) bloqueando merge antes mesmo da revisão humana entrar no mérito de lógica/arquitetura


#### Entregáveis típicos

- Código-fonte funcional, testado e aderente ao padrão de arquitetura e estilo do projeto (aplicando SOLID/Clean Architecture e Clean Code, não apenas 'código que funciona')
- Pull Request pequeno e focado (uma mudança lógica por PR), com descrição clara do porquê da mudança, não só do o quê, e passando pelos checks automatizados de CI antes de pedir revisão humana
- Suíte de testes automatizados (unitários e, quando aplicável, de integração) cobrindo o comportamento novo/alterado, entregue junto com o código — não depois
- Documentação técnica das decisões relevantes: Architecture Decision Records para escolhas de arquitetura/stack, comentários/docstrings apenas onde o código não se explica sozinho, documentação de API (OpenAPI/Swagger) quando expõe endpoints
- Participação registrada em code review como autor (respondendo comentários) e como revisor (avaliando lógica, segurança e manutenibilidade do código de outros)
- Configuração/manutenção da etapa de CI relativa ao próprio código (lint + testes + build por PR) — entregável de dev, distinto da infraestrutura de deploy/observabilidade que cabe ao DevOps


#### O que diferencia sênior de pleno

- Pleno executa dentro de um escopo já definido; Sênior questiona o requisito antes de implementar e frequentemente propõe uma solução mais simples ou mais robusta que a pedida originalmente
- Pleno identifica o bug imediato; Sênior rastreia a causa raiz sistêmica por trás dele (ex.: schema de dado inconsistente) e abre um item de trabalho para corrigir a causa, não só o sintoma
- Sênior possui e defende decisões de arquitetura (registra ADRs, participa/lidera reviews de arquitetura); Pleno majoritariamente implementa dentro de uma arquitetura que já existe
- Sênior mentora ativamente plenos/júniores via pareamento e revisão de código; Pleno ainda está, na maior parte do tempo, do lado de quem recebe esse suporte
- Sênior responde pelo ciclo de vida completo de um sistema/componente — do design ao comportamento em produção e ao incidente —; a responsabilidade de Pleno tende a ser mais pontual, por tarefa ou funcionalidade isolada
- Postura polyglot real de sênior: domina princípios (SOLID, testes automatizados, Clean Code) que transcendem sintaxe, por isso consegue trocar de stack (PHP/JS/Java/Python/Go/Perl) mantendo o mesmo padrão de qualidade; Pleno costuma ainda depender fortemente de uma stack específica
- Diferença para o próximo nível (Staff/Principal): o impacto de um Sênior é profundo mas localizado a um time/sistema; Staff+ tem impacto horizontal, atravessando múltiplos times e sistemas e funcionando como multiplicador de força para outros engenheiros


<details>
<summary>Fontes (24)</summary>

- https://interviewkickstart.com/job-description/senior-software-engineer
- https://proxify.io/knowledge-base/software-development/difference-between-junior-mid-senior-developers
- https://www.indeed.com/hire/job-description/full-stack-developer
- https://leaddev.com/technical-direction/an-engineering-leaders-guide-to-solid-principles
- https://javarevisited.substack.com/p/how-to-be-a-solid-programmer-in-2026
- https://adr.github.io/
- https://www.techtarget.com/searchapparchitecture/tip/4-best-practices-for-creating-architecture-decision-records
- https://underdog.io/blog/staff-engineer-vs-senior-engineer
- https://blog.alexewerlof.com/p/senior-engineer-to-staff-engineer
- https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development
- https://graphite.com/guides/role-code-review-ci-cd
- https://survey.stackoverflow.co/2025/technology
- https://www.hirenodejs.com/blog/nodejs-frameworks-compared-2026
- https://mecanik.dev/en/posts/symfony-vs-laravel-2026/
- https://encore.dev/articles/best-go-backend-frameworks
- https://blog.jetbrains.com/pycharm/2025/02/django-flask-fastapi/
- https://keyholesoftware.com/java-trends-2026/
- https://perlhacks.com/2025/06/stop-using-your-system-perl/
- https://www.devclass.com/development/2026/02/10/javascript-survey-reveals-gripes-against-date-handling-webpack-and-nextjs-and-that-typescript-has-won/4090262
- https://testomat.io/blog/unit-testing-tools/
- https://scopir.com/posts/best-python-package-managers-2026/
- https://www.secondtalent.com/resources/most-used-ides/
- https://golangci-lint.run/docs/linters/
- https://dev.to/moksh/top-static-code-analysis-tools-every-developer-should-know-in-2026-hi8

</details>


---

## DevOps / SRE

**Papel:** Engenheiro(a) DevOps/SRE Senior/Especialista de Infraestrutura (Cloud, Mensageria e Banco de Dados) - papel separado de Desenvolvimento de Aplicacao


Em 2025/2026 o DevOps/SRE Senior de infraestrutura e o dono tecnico do "como roda em producao": AWS (compute, rede, IAM), bancos de dados relacionais (MySQL) e NoSQL (DynamoDB, MongoDB, Redis), mensageria (Kafka, RabbitMQ, SQS/SNS) e a cadeia de entrega (CI/CD, IaC, observabilidade). E um papel de engenharia de plataforma/confiabilidade, distinto de quem escreve a logica de negocio da aplicacao: o SRE aplica principios de engenharia de software a operacoes (SLOs, orcamento de erro, eliminacao de toil, conforme o SRE book do Google), enquanto o DevOps foca em automatizar a esteira de build-teste-deploy e a infraestrutura como codigo. Senioridade nessa trilha (5-8+ anos, faixa salarial tipica de US$155k-US$200k/ano no mercado americano) se mede menos por conhecer mais ferramentas e mais por escopo: desenho de arquitetura resiliente multi-regiao, lideranca tecnica em incidentes P1/P2 sob pressao com informacao incompleta, definicao de padroes organizacionais (seguranca, FinOps, disaster recovery) e mentoria - versus o pleno, que executa tarefas, resolve problemas pontuais e comeca a questionar o "porque" dos processos mas ainda nao desenha o sistema como um todo.

#### Responsabilidades

- Infraestrutura como Codigo (IaC): modelar, versionar e revisar toda a infraestrutura AWS via Terraform/CloudFormation/CDK, com modulos reutilizaveis publicados como pacotes internos, em vez de mudanca manual no console
- CI/CD: desenhar e manter pipelines de build/teste/deploy (Jenkins, GitHub Actions, GitLab CI, ArgoCD/GitOps) com rollback automatizado, deploy progressivo (blue-green/canary) e gates de qualidade/seguranca embutidos no pipeline
- Observabilidade: instrumentar metricas, logs e tracing distribuido (Prometheus/Grafana, Datadog, New Relic, ELK, OpenTelemetry/Jaeger), definir SLIs/SLOs e orcamento de erro, e alertar por sintoma de usuario, nao so por causa interna
- Escalabilidade e capacity planning: dimensionar EC2/EKS/RDS para carga, projetar arquitetura multi-regiao com failover, auto scaling e testes de carga/caos antes do pico de trafego real
- Seguranca de infraestrutura: IAM com privilegio minimo, gestao de segredos (AWS Secrets Manager/HashiCorp Vault), rotacao de credenciais, hardening de rede (VPC/SG/NACL), compliance e automacao de controles de seguranca no pipeline (shift-left security)
- Administracao de banco de dados em producao: MySQL relacional (replicacao, indexacao, failover, backup/restore testado) e NoSQL (DynamoDB, MongoDB, Redis/Cassandra) cobrindo sharding, particionamento, cache e alta disponibilidade cross-region
- Mensageria e streaming: operar e dimensionar Kafka (particionamento, retencao, KRaft), RabbitMQ (filas, clustering) e SQS/SNS (filas gerenciadas e pub/sub) como espinha dorsal de comunicacao assincrona entre servicos
- Resposta a incidentes e gestao de on-call: participar de rotacao de plantao, diagnosticar e mitigar incidentes Sev1/Sev2, conduzir post-mortem sem culpa (blameless) e converter licoes aprendidas em automacao
- Reducao de toil: escrever ferramentas e automacoes (Python/Go/Bash) para eliminar trabalho manual repetitivo, em vez de resolver o mesmo incidente operacional toda semana na mao
- FinOps e governanca de custo de nuvem: acompanhar e otimizar gasto AWS como parte da rotina de engenharia, nao como projeto isolado


#### Hard skills

- Terraform e/ou AWS CloudFormation/CDK (IaC) com 3+ anos de experiencia pratica
- Docker e Kubernetes (idealmente AWS EKS) incluindo ciclo de vida de cluster, upgrades, scheduling e Helm
- AWS core: EC2, VPC, IAM, S3, EBS, ALB/NLB expostos via ELB, CloudWatch, ECS/EKS, Lambda
- AWS mensageria e integracao: SQS, SNS, EventBridge
- AWS banco de dados: RDS (MySQL) e servicos NoSQL gerenciados como DynamoDB
- MySQL: replicacao, indexacao, modelagem, tuning de query, backup/restore e alta disponibilidade
- NoSQL: MongoDB, DynamoDB e Redis (cache/particionamento/replicacao), com familiaridade adicional em Cassandra
- Mensageria e streaming: Apache Kafka (particoes, retencao, operacao de cluster), RabbitMQ (filas, clustering), SQS/SNS
- Observabilidade: Prometheus, Grafana, Datadog, New Relic, stack ELK/OpenSearch, tracing distribuido (OpenTelemetry/Jaeger)
- Linguagens de automacao: Python e/ou Go para tooling, Bash para scripts operacionais
- Seguranca de infraestrutura: IAM de privilegio minimo, gestao de segredos (Vault/Secrets Manager), identidade federada de workload, auditoria e logging centralizado
- Configuration management: Ansible (ou Chef/Puppet) para provisionamento idempotente
- Linux avancado e redes (TCP/IP, DNS, balanceamento de carga, VPN/peering)


#### Ferramentas de mercado

- Terraform / AWS CloudFormation / AWS CDK
- Docker, Kubernetes, Helm, Amazon EKS
- Jenkins, GitHub Actions, GitLab CI, ArgoCD (GitOps)
- Prometheus + Grafana, Datadog, New Relic, ELK/OpenSearch
- PagerDuty ou Opsgenie para on-call e gestao de incidentes
- HashiCorp Vault, AWS Secrets Manager
- Ansible (config management)
- Amazon RDS (MySQL), DynamoDB, MongoDB, Redis
- Apache Kafka, RabbitMQ, Amazon SQS/SNS
- AWS CLI/SDK, CloudWatch, AWS Cost Explorer (FinOps)


#### Metodologias / certificações de referência

- AWS Certified DevOps Engineer - Professional (DOP-C02) - valida implementacao de entrega continua, automacao de seguranca/governanca, monitoramento/metricas/logging e sistemas altamente disponiveis/self-healing na AWS; certificacao valida por 3 anos
- Certified Kubernetes Administrator (CKA), da Linux Foundation/CNCF - exame pratico de 2h (linha de comando), hoje alinhado ao Kubernetes v1.35, cobrindo arquitetura de cluster, redes/servicos, workloads/scheduling, storage e troubleshooting (30% do peso)
- Site Reliability Engineering (livro e pratica do Google/sre.google) - SLOs e orcamento de erro, eliminacao de toil, monitoramento de sistemas distribuidos, engenharia de release, gestao de risco/embracing risk como corpo de principios que fundamenta o papel de SRE
- GitOps como metodologia de entrega (estado declarativo versionado + reconciliacao automatica via ferramentas como ArgoCD)
- FinOps como pratica continua de governanca de custo de nuvem integrada a engenharia


#### Entregáveis típicos

- Pipeline de CI/CD documentado, versionado e reutilizavel (templates/modulos compartilhados), com deploy progressivo e rollback automatizado
- Infraestrutura como codigo versionada em repositorio (modulos Terraform/CloudFormation), revisada por pull request, nunca mudanca manual direta no console AWS
- Runbooks/playbooks de incidente para cenarios de falha conhecidos (banco de dados fora do ar, fila engasgada, regiao AWS degradada), usados durante plantao
- Dashboards de observabilidade (Grafana/Datadog) com SLIs/SLOs explicitos por servico e alertas atrelados a sintoma de usuario
- Politicas de IAM de privilegio minimo e segredos centralizados em cofre (Vault/Secrets Manager), auditaveis
- Plano de disaster recovery e backup testado periodicamente (nao so documentado) para MySQL e para os bancos NoSQL em producao
- Relatorio de capacity planning e resultado de teste de carga/caos antes de eventos de pico
- Post-mortem blameless por incidente relevante, com item de acao rastreado ate o fechamento


#### O que diferencia sênior de pleno

- Escopo: pleno executa tarefas e resolve problemas pontuais dentro de um sistema dado; senior desenha a arquitetura do sistema, antecipa falhas futuras e define padroes organizacionais (seguranca, FinOps, DR)
- Incidente P1: a diferenca entre pleno e senior num incidente critico costuma ser menos conhecimento tecnico e mais capacidade de manter a calma, comunicar com clareza, delegar investigacao e decidir com informacao incompleta
- Autonomia e mentoria: senior lidera design de sistema e resposta a incidente, e mentora outros engenheiros; pleno e um contribuidor independente e confiavel mas ainda em transicao do "como" para o "porque"
- Faixa de experiencia tipica no mercado americano: pleno 2-5 anos, senior 5-8+ anos, com faixa salarial aproximada de US$120k-155k (pleno) contra US$155k-200k (senior)
- Amplitude organizacional: a transicao de pleno para senior e menos sobre acumular conhecimento de mais ferramentas e mais sobre ampliar o escopo de responsabilidade - de execucao tatica para resiliencia de sistema e alinhamento com o negocio


<details>
<summary>Fontes (22)</summary>

- https://www.indeed.com/hire/job-description/devops-engineer
- https://docs.aws.amazon.com/aws-certification/latest/devops-engineer-professional-02/devops-engineer-professional-02.html
- https://certificationpractice.com/exam-overviews/aws-certified-devops-engineer-professional-quick-facts
- https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/
- https://www.cncf.io/training/certification/cka/
- https://dev.to/suzuki0430/cka-certified-kubernetes-administrator-exam-report-2026-dont-rely-on-old-guides-mastering-the-534m
- https://sre.google/sre-book/table-of-contents/
- https://sre.google/sre-book/introduction/
- https://research.google/pubs/site-reliability-engineering-how-google-runs-production-systems/
- https://handbook.gitlab.com/job-description-library/engineering/infrastructure/database-reliability-engineer/
- https://resources.workable.com/senior-database-reliability-engineer-job-description
- https://ably.com/topic/apache-kafka-vs-rabbitmq-vs-aws-sns-sqs
- https://cloudurable.com/blog/kafka-vs-jms-2025/
- https://medium.com/devops-dudes/differences-between-junior-devops-and-senior-devops-engineers-8d0f28b8b30b
- https://techlynxrecruiters.com/devops-hiring/
- https://humanitec.com/blog/the-role-of-infrastructure-teams-in-the-platform-engineering-era
- https://infrastructure-as-code.com/post/infrastructure-platform-teams.html
- https://aembit.io/blog/why-devops-struggles-least-privilege-static-credentials-2025/
- https://roadmap.sh/devops
- https://www.computerweekly.com/br/tip/SRE-vs-DevOps-qual-a-diferenca
- https://www.claranet.com/br/blog/sre-vs-devops-quais-as-diferencas
- https://microsoft.github.io/code-with-engineering-playbook/observability/observability-pipelines/

</details>


---

## QA (Quality Assurance)

**Papel:** Analista de QA Sênior / Especialista em Qualidade de Software (QA Full-Stack — testa backend e frontend contra requisito, regra de negócio e critério de aceite, e depois automatiza)


Em 2025/2026, o Analista de QA Sênior (também chamado de QA Especialista, Senior QA Engineer ou, na variante mais técnica, SDET) é um contribuidor individual sênior dentro da engenharia de qualidade, responsável por validar se o sistema (API/backend e UI/frontend) atende ao requisito de negócio e ao critério de aceite antes de decidir o quê e como automatizar. Diferente do QA pleno, que executa o ciclo de teste dentro de um escopo definido, o Sênior desenha a estratégia de teste de sistemas que não necessariamente construiu, prioriza teste por risco, atua como gate de qualidade cross-funcional (dev, produto, negócio), mentora QAs juniores/plenos e é medido por resultado de qualidade (taxa de escape de defeito, cobertura de risco, estabilidade de pipeline) e não pela quantidade de casos de teste escritos. O ciclo típico é: entender requisito/regra de negócio → desenhar plano e casos de teste → testar manualmente/exploratoriamente o que for novo ou de alto risco → validar API (contrato, dados, regra de negócio no backend) → validar fluxo end-to-end na UI → automatizar o que for regressivo e estável → integrar ao CI/CD → reportar defeito e métrica de qualidade. Tendência 2025/2026: forte deslocamento para Playwright como padrão de automação web (ultrapassando Cypress em downloads e crescendo mais que Selenium em vagas), fluência em IA aplicada a teste (geração de caso de teste, self-healing de automação) já citada pelo World Quality Report 2025 como prioridade de upskilling, e a linha entre QA Sênior e SDET cada vez mais tênue — ambos com shift-left (testar desde o requisito/código, não só no fim do ciclo).

#### Responsabilidades

- Analisar requisito funcional, regra de negócio e critério de aceite (histórias de usuário) antes de qualquer execução, identificando ambiguidade ou lacuna e levando de volta ao time de produto/negócio
- Desenhar a estratégia e o plano de teste (escopo, riscos, entrada/saída, cronograma, recursos) para features e sistemas complexos, inclusive os que o QA não construiu
- Escrever e manter casos de teste funcionais, de regressão, de integração e de aceite (UAT), rastreáveis ao requisito de origem
- Executar teste exploratório dirigido por sessão para cobrir cenários não previstos em caso de teste escrito, principalmente sob prazo apertado ou especificação incompleta
- Testar a camada de API/backend (REST/SOAP): contrato, códigos de resposta, validação de dado, regra de negócio, autenticação/autorização, integração entre serviços e consistência com o banco (SQL)
- Testar a camada de frontend/UI e o fluxo ponta a ponta (E2E) do ponto de vista do usuário, cobrindo os principais 'user journeys' contra o critério de aceite
- Planejar e (quando aplicável) executar teste de performance/carga para validar tempo de resposta e comportamento sob concorrência
- Decidir o que automatizar e o que manter manual/exploratório (não automatiza tudo por padrão), priorizando por risco e estabilidade do fluxo
- Construir e manter suíte de automação (API e E2E) integrada ao pipeline de CI/CD, incluindo dados de teste e ambiente
- Registrar, priorizar e acompanhar defeito até o fechamento, com causa-raiz quando relevante, e reportar métrica de qualidade a stakeholders técnicos e de negócio
- Mentorar QAs júnior/pleno em técnica de teste, revisão de caso de teste e pensamento crítico de qualidade
- Atuar como gate de qualidade cross-funcional, participando de refinamento/planning para trazer testabilidade e critério de aceite testável desde o início (shift-left)


#### Hard skills

- Plano de teste: escopo, estratégia por risco, critérios de entrada/saída, cronograma e matriz de rastreabilidade requisito→caso de teste
- Caso de teste: técnicas de design (particionamento de equivalência, análise de valor limite, tabela de decisão, transição de estado) e escrita clara de passo/resultado esperado
- Teste exploratório: sessão dirigida por carta/heurística, sem script fixo, para achar o que o caso de teste escrito não cobre
- Teste de API/backend: validação de contrato (schema), autenticação/autorização, código de status, payload, regra de negócio no servidor e consistência de dado via SQL
- Teste E2E (frontend/UI): fluxo completo do usuário contra critério de aceite, cross-browser/cross-device quando aplicável
- Teste de performance e carga: definição de cenário, métrica (latência, throughput, taxa de erro) e leitura de resultado sob concorrência
- Automação de teste: construção de framework/suíte de API e E2E, page object/boas práticas de manutenibilidade, integração em CI/CD e controle de flakiness
- Leitura e escrita de SQL para validação de dado em banco relacional
- Uso de sistema de controle de versão (Git) e leitura básica de log/pipeline de CI/CD para diagnosticar falha de build/teste
- BDD/Gherkin: tradução de critério de aceite em cenário Given/When/Then compreensível por negócio e QA


#### Ferramentas de mercado

- Playwright — hoje o padrão dominante para automação web/E2E em 2025/2026 (maior adoção e crescimento de vaga entre as três)
- Cypress — forte para times frontend/JavaScript, boa experiência de desenvolvimento, porém limitado a Chromium/Firefox
- Selenium — ainda relevante para cobertura ampla de linguagem (Java, Python, C#, Ruby) e navegador legado, em queda relativa de adoção
- Postman e Newman — teste manual/exploratório e automação de coleção de API, com Newman rodando as coleções em linha de comando/CI/CD
- Apache JMeter — teste de performance/carga tradicional, forte para banco de dados e protocolo legado
- k6 (Grafana k6) — teste de carga moderno, scriptável em JavaScript/TypeScript, leve e nativo de CI/CD, recomendado para times DevOps/microsserviços
- Cucumber/Gherkin — framework de BDD para escrever cenário de teste em linguagem natural rastreável ao requisito, integrável com Selenium/Cypress/Playwright
- Ferramenta de gestão de teste/rastreabilidade (ex.: TestRail, Zephyr, Xray) para plano de teste, caso de teste e matriz de rastreabilidade
- Ferramenta de bug tracking (ex.: Jira) para registro e ciclo de vida do defeito
- Pipeline de CI/CD (ex.: Jenkins, GitHub Actions) para execução automática da suíte de regressão


#### Metodologias / certificações de referência

- ISTQB CTFL (Certified Tester Foundation Level, versão 4.0) — certificação de entrada, pré-requisito para toda a trilha ISTQB, cobre princípios, técnica de design e vocabulário de teste
- ISTQB Advanced Level (Test Analyst, Technical Test Analyst, Test Manager) — citado como diferencial esperado em vaga de QA Sênior
- CSTE (Certified Software Tester) — mencionado como certificação avançada alternativa em descrições de vaga sênior
- Teste baseado em risco (risk-based testing) — priorização de esforço de teste pelo impacto/probabilidade do risco de negócio
- BDD (Behavior-Driven Development) com Gherkin/Cucumber — tradução de critério de aceite em cenário compartilhado com negócio
- Shift-left testing — envolvimento do QA desde o requisito/design, não só no fim do ciclo, tendência central de 2025
- Metodologia ágil (Scrum/Kanban) aplicada a teste, com QA participando de refinamento e planning
- Fluência crescente em IA aplicada a teste (geração assistida de caso de teste, automação self-healing) — citada pelo World Quality Report 2025 como prioridade de upskilling


#### Entregáveis típicos

- Plano de teste (escopo, estratégia, riscos, cronograma, critérios de entrada/saída)
- Casos de teste funcionais, de regressão e de aceite, com matriz de rastreabilidade ligando cada caso ao requisito/critério de aceite de origem
- Registro e evidência de teste exploratório (carta de teste, nota de sessão, achados fora do script)
- Suíte de automação de API e E2E versionada e integrada ao CI/CD, com relatório de execução (passou/falhou, flakiness, cobertura)
- Relatório/registro de bug (defect report) com passos de reprodução, resultado esperado x obtido, severidade, prioridade, ambiente e evidência (log/screenshot/vídeo)
- Relatório de teste de performance/carga com métrica de resposta e limite observado
- Relatório de QA/status de qualidade da release para stakeholders técnicos e de negócio


#### O que diferencia sênior de pleno

- Pleno executa o ciclo de teste dentro de um escopo já definido; Sênior desenha a estratégia de teste para um sistema que muitas vezes não construiu, incluindo arquitetura de automação
- Pleno é medido por quantidade/cobertura de teste executado; Sênior é medido por resultado de qualidade (defeito que escapou para produção, estabilidade de pipeline, decisão de risco)
- Sênior lidera teste de projeto grande/complexo e mentora QA júnior/pleno em técnica, revisão de caso de teste e pensamento crítico — não é esperado do pleno
- Sênior tem voz em decisão de arquitetura de automação e integração com CI/CD, não só execução de suíte já existente
- Sênior atua como gate de qualidade cross-funcional, negociando com produto/negócio/dev o critério de aceite testável desde o refinamento (shift-left) — pleno costuma herdar o requisito já fechado
- Sênior costuma ter certificação avançada (ISTQB Advanced/CSTE) ou experiência equivalente, enquanto o Foundation Level (CTFL) já é esperado desde nível pleno/júnior
- Sênior transita fluentemente entre teste manual/exploratório, API, E2E e performance, decidindo o que automatizar e o porquê — pleno tende a dominar bem um ou dois desses eixos


<details>
<summary>Fontes (28)</summary>

- https://ca.indeed.com/hire/job-description/senior-qa-analyst
- https://devsdata.com/senior-qa-analyst-job-description-template/
- https://www.velvetjobs.com/job-descriptions/senior-qa-analyst
- https://careers.cognizant.com/global-en/jobs/00069581171/senior-backend-qa-engineer-api-data-testing/
- https://www.devopsschool.com/blog/senior-qa-analyst-role-blueprint-responsibilities-skills-kpis-and-career-path/
- https://www.alooba.com/roles/senior-software-quality-assurance/
- https://www.qamadness.com/job-grades-in-qa-common-roles-skills-and-responsibilities/
- https://yrkan.com/blog/qa-engineer-roadmap-2025/
- https://www.testbooster.ai/en/blog/junior-mid-level-and-senior-qa
- https://istqb.org/certifications/certified-tester-foundation-level-ctfl-v4-0/
- https://astqb.org/certifications/foundation-level-certification/
- https://istqb.org/
- https://www.testrail.com/blog/create-a-test-plan/
- https://www.testlio.com/blog/write-qa-test-plan
- https://www.botgauge.com/blog/testing-documents-in-qa-guide
- https://contextqa.com/blog/what-is-playwright-vs-selenium-vs-cypress-2026/
- https://testdino.com/blog/selenium-vs-cypress-vs-playwright
- https://blog.magmalabs.io/2025/07/16/api-testing-postman-supertest-jmeter.html
- https://testsigma.com/blog/jmeter-vs-postman/
- https://pflb.us/blog/k6-vs-jmeter/
- https://www.browserstack.com/guide/learn-about-cucumber-testing-tool
- https://www.tricentis.com/learn/introduction-to-cucumber-test-automation
- https://www.softwaretestinghelp.com/sample-bug-report/
- https://marker.io/blog/bug-report-template
- https://www.softwaretestinghelp.com/requirements-traceability-matrix/
- https://marutitech.com/differences-between-sdet-and-qa/
- https://quashbugs.com/blog/qa-to-sdet-ai-2026
- https://prepare.sh/articles/qa-and-sdet-is-the-safest-job-during-ai-boom-analysis-of-qa-2025-job-market-trends

</details>


---

## UX/UI Designer

**Papel:** UX/UI Designer Sênior / Especialista em pré-desenvolvimento de software (2025/2026)


Em 2025/2026, o UX/UI Designer Sênior/Especialista que atua ANTES do desenvolvimento começar é definido menos por "anos de experiência" e mais por ownership de ponta a ponta do processo de descoberta e design (da pesquisa à especificação de handoff para o Dev), por influência estratégica sobre roadmap e decisões de negócio, e por autonomia em ambiguidade. Ele lidera pesquisa com usuário, traduz achados em arquitetura de informação/fluxo/jornada, produz wireframes e protótipos navegáveis, mantém e evolui um design system, roda testes de usabilidade e entrega uma especificação de tela rastreável para engenharia — normalmente via Figma Dev Mode. O grande diferencial frente ao pleno é conectar decisão de design a impacto de negócio, mentorear designers juniores/plenos e liderar workshops de descoberta com stakeholders, não apenas executar bem uma etapa isolada do processo.

#### Responsabilidades

- Liderar (não apenas participar de) a fase de descoberta/discovery: alinhamento com stakeholders, entrevistas de negócio, enquadramento inicial do problema antes de qualquer wireframe existir (aloa.co/UX Discovery; Digital Waffle)
- Conduzir pesquisa de usuário mista — qualitativa (entrevistas, card sorting, estudos de campo) e quantitativa (surveys, analytics) — e transformar achados em insights acionáveis (huntr.co; theiotacademy.co)
- Desenhar arquitetura de informação: sitemaps, fluxos de usuário (user flows) e sistemas de navegação (andacademy.com; theiotacademy.co)
- Mapear jornada do usuário (customer/user journey mapping) ligando pontos de contato, emoções e lacunas do produto à estratégia de negócio (NN/g — nngroup.com/topic/customer-journeys)
- Produzir wireframes de baixa e alta fidelidade para visualizar e validar conceitos antes de qualquer código (huntr.co)
- Construir protótipos navegáveis/interativos (clicáveis) para validar fluxo e interação com usuários reais e com stakeholders (careerfoundry.com; Google UX Certificate — grow.google)
- Criar, manter e governar o design system / biblioteca de componentes, com aderência a requisitos de marca e reuso entre squads (Digital Waffle; VelvetJobs)
- Planejar e rodar testes de usabilidade (moderados e não-moderados), sintetizar resultados e traduzir em recomendações de iteração (NN/g — Usability Testing 101)
- Entregar a especificação de tela para o time de Dev: specs inspecionáveis (Figma Dev Mode), tokens nomeados, anotação de estados/casos de borda, ao invés de redlines manuais (figma.com/best-practices/guide-to-developer-handoff)
- Influenciar priorização de roadmap e estratégia de produto junto à liderança, indo além da execução tática (builtin.com; uxdesign.cc)
- Mentorear designers juniores e plenos, elevar a cultura de design do time/empresa (Digital Waffle; uxdesign.cc)
- Trabalhar com times de analytics/dados para avaliar impacto de mudanças de UI/usabilidade após o lançamento (homerun.co)


#### Hard skills

- Pesquisa de usuário (qualitativa e quantitativa): entrevistas, card sorting, surveys, análise de dados (huntr.co; theiotacademy.co)
- Arquitetura da informação (IA): sitemaps, taxonomias, fluxos de navegação (andacademy.com)
- Design de interação (IxD): microinterações, gestos, princípios de animação (theiotacademy.co)
- Wireframing e prototipação em múltiplas fidelidades (huntr.co)
- Design visual/UI: tipografia, cor, grid, hierarquia visual (careerfoundry.com)
- Design systems e design tokens: criação e governança de bibliotecas de componentes (Digital Waffle)
- Usabilidade e testes com usuário: definição de protocolo, moderação, síntese (NN/g)
- Acessibilidade (WCAG) e design inclusivo/equity-focused design (Google UX Certificate — grow.google)
- Design responsivo (mobile/web) (grow.google)
- Letramento em dados/analytics para avaliar impacto de UI (careerfoundry.com; homerun.co)
- UX writing / microcopy
- Especificação de handoff para engenharia: nomenclatura de camadas alinhada ao código, documentação de estados e casos de borda (figma.com/blog/the-designers-handbook-for-developer-handoff)
- Fluência crescente em ferramentas de IA aplicadas a UX (geração assistida, síntese de pesquisa) (grow.google; bestfolios.substack.com)
- Facilitação de workshops (discovery, design sprint, co-design) (Design Council)


#### Ferramentas de mercado

- Figma — ferramenta dominante de design/prototipação/handoff em 2025, com ~82% de market share segundo pesquisa UX Tools (uxtools.co/survey/interface-design/trends)
- Figma Dev Mode — inspeção de specs, medidas, tokens e anotações para handoff ao Dev (figma.com/best-practices/guide-to-developer-handoff)
- FigJam — quadro colaborativo do Figma para workshops, brainstorm e mapeamento de jornada
- Maze — plataforma de teste de usabilidade e pesquisa rápida (concept/prototype testing), usada por mais de 60 mil times (maze.co/guides/ux-research/tools)
- Hotjar — heatmaps, gravação de sessão e pesquisas on-site para analytics comportamental (webdevelopmentgroup.com)
- Miro — colaboração visual e mapeamento (citado junto a Figma/Maze/Hotjar como top choice, webdevelopmentgroup.com)
- UserTesting / Lookback — testes de usabilidade moderados/não-moderados com usuários reais
- Optimal Workshop / UsabilityHub — card sorting, tree testing, first-click testing
- Dovetail / Condens — repositório e síntese de pesquisa qualitativa
- Sketch e Adobe XD — ainda presentes no mercado, mas defasados frente ao Figma (uxtools.co)
- Google Analytics / Mixpanel — dados quantitativos de uso pós-lançamento
- Storybook — documentação viva de design system integrada ao código


#### Metodologias / certificações de referência

- Design Thinking — Empatizar, Definir, Idear, Prototipar, Testar; base conceitual citada tanto pelo Google UX Certificate quanto pelo Design Council (nngroup.com/videos/design-thinking-designers-definition)
- Double Diamond (Design Council, Reino Unido, criado em 2005) — Discover, Define, Develop, Deliver; framework oficial de referência para dividir pré-desenvolvimento (1º diamante: entender o problema) de entrega da solução (2º diamante) (designcouncil.org.uk/resources/the-double-diamond)
- Google UX Design Professional Certificate (Coursera/Google, coursera.org/professional-certificates/google-ux-design) — 7 cursos, 200+ horas, cobre pesquisa, wireframe, protótipo, acessibilidade e portfólio com 3 projetos end-to-end; certificação de entrada amplamente citada mas também usada por profissionais em transição/atualização
- Nielsen Norman Group (NN/g) UX Certification — combina treinamentos presenciais/online com exame; oferece especialidades em Interaction Design, Mobile, UX Management, UX Research e Web Design (nngroup.com/ux-certification e nngroup.com/ux-certification/specialties)
- Interaction Design Foundation (IxDF) — cursos e certificação self-paced reconhecidos no mercado, com trilha avançada voltada a quem já é sênior aprofundar craft (en.wikipedia.org/wiki/Interaction_Design_Foundation; interaction-design.org/courses)
- HFI Certified Usability Analyst (CUA) — certificação de mercado focada em usabilidade, citada como referência complementar ao NN/g e IxDF
- Lean UX / Jobs-to-be-Done — metodologias citadas em job descriptions sênior para conectar design a hipótese de negócio testável antes do dev começar


#### Entregáveis típicos

- Relatório de pesquisa de usuário (personas, insights, síntese qualitativa/quantitativa)
- Mapa de jornada do usuário (user/customer journey map) e user flows
- Wireframes de baixa fidelidade (esqueleto de tela/fluxo)
- Wireframes/mockups de alta fidelidade (visual final antes de interatividade completa)
- Protótipo navegável/clicável no Figma para validação com usuários e stakeholders
- Design system / biblioteca de componentes com style guide (cor, tipografia, tokens, estados)
- Relatório de teste de usabilidade (metodologia, achados, severidade, recomendações de iteração)
- Especificação de tela para o Dev via Figma Dev Mode: specs inspecionáveis, tokens nomeados, anotação de interações/estados/casos de borda, nomenclatura de camada alinhada ao código (não mais redline manual) (figma.com/best-practices/guide-to-developer-handoff; figma.com/blog/the-designers-handbook-for-developer-handoff)
- Checklist/relatório de acessibilidade (WCAG)


#### O que diferencia sênior de pleno

- Ownership de ponta a ponta: sênior está envolvido do discovery até a entrega, não só executa uma etapa (medium.com/ux-school — Junior vs Mid vs Senior)
- É tratado como subject matter expert do produto inteiro, não só da sua feature/área (medium.com/ux-school)
- Influencia priorização de roadmap e estratégia de design, não só recebe brief (builtin.com; uxdesign.cc)
- Conecta decisão de design a métrica/impacto de negócio de forma explícita e demonstrável em portfólio (resumestudio.io; uxdesign.cc)
- Lidera workshops de discovery e facilita alinhamento de stakeholders multi-área (Digital Waffle)
- Mentora e desenvolve designers juniores/plenos, eleva processo e cultura de design do time (Digital Waffle; uxdesign.cc)
- Autonomia real em ambiguidade: o pleno é autônomo dentro do seu escopo definido; o sênior define o escopo (medium.com/@uxsurvivalguide)
- Qualidade da experiência pesa mais que tempo de carreira — não há corte fixo de anos que defina senioridade (medium.com/ux-school)
- Consegue articular e defender racional de decisão de design perante liderança não-design (medium.com/ux-school)


<details>
<summary>Fontes (26)</summary>

- Design Council — The Double Diamond (framework oficial): https://www.designcouncil.org.uk/resources/the-double-diamond/
- Design Council — Framework for Innovation: https://www.designcouncil.org.uk/resources/framework-for-innovation/
- Nielsen Norman Group — UX Certification: https://www.nngroup.com/ux-certification/
- Nielsen Norman Group — UX Certification Specialties: https://www.nngroup.com/ux-certification/specialties/
- Nielsen Norman Group — Customer Journeys (artigos/vídeos): https://www.nngroup.com/topic/customer-journeys/
- Nielsen Norman Group — Artigos de UX/Usabilidade: https://www.nngroup.com/articles/
- Google UX Design Professional Certificate (Coursera): https://www.coursera.org/professional-certificates/google-ux-design
- Google UX Design Certificate (Grow with Google): https://grow.google/certificates/ux-design/
- Interaction Design Foundation — Wikipedia: https://en.wikipedia.org/wiki/Interaction_Design_Foundation
- Interaction Design Foundation — cursos: https://www.interaction-design.org/courses
- Figma — Guide to developer handoff (Dev Mode): https://www.figma.com/best-practices/guide-to-developer-handoff/
- Figma Blog — The Designer's Handbook for Developer Handoff: https://www.figma.com/blog/the-designers-handbook-for-developer-handoff/
- UX Tools — Design Tools Survey 2025 (market share Figma etc.): https://www.uxtools.co/survey/interface-design/trends
- Maze — UX Research Tools guide: https://maze.co/guides/ux-research/tools/
- Web Development Group — Best Tools for UX Design 2025: https://www.webdevelopmentgroup.com/insights/best-tools-for-ux-design/
- CareerFoundry — UI Designer Job Descriptions Guide 2025: https://careerfoundry.com/en/blog/ui-design/ui-designer-job-descriptions-guide/
- AND Academy — Guide to UI/UX Designer Job Descriptions 2025: https://www.andacademy.com/resources/blog/ui-ux-design/ui-ux-designer-job-descriptions/
- Built In — UX Designer: Job Description & Duties: https://builtin.com/articles/ux-designer-job-description
- Indeed — UX Designer Job Description 2025: https://www.indeed.com/hire/job-description/ux-designer
- Homerun — Senior UI/UX Designer Job Description Template: https://www.homerun.co/job-description-templates/senior-ux-ui-designer
- Digital Waffle — Senior UX Designer Job Description: https://www.digitalwaffle.co/job-descriptions/senior-ux-designer
- VelvetJobs — Senior UX Designer Job Description: https://www.velvetjobs.com/job-descriptions/senior-ux-designer
- Medium/UX School — Understanding design levels: Junior vs Mid vs Senior UX Designer: https://medium.com/ux-school/understanding-design-levels-junior-vs-mid-level-vs-senior-ux-designer-ade66d8994df
- UX Collective — The truth about becoming a Senior UX Designer: https://uxdesign.cc/the-truth-about-becoming-a-senior-ux-designer-649d23ee9b32
- Huntr — 50+ Best UX Designer Skills for Resume 2025: https://huntr.co/resume-skills/ux-designer
- The IOTA Academy — 20 Best UI/UX Design Skills 2025: https://www.theiotacademy.co/blog/ui-ux-design-skills/

</details>


---

## Segurança / AppSec

**Papel:** Especialista/Engenheiro(a) Senior de Seguranca da Informacao e AppSec em time de desenvolvimento de software (2025/2026)


Em 2025/2026 o especialista senior de AppSec dentro de um time de desenvolvimento deixou de ser so quem "roda scanner": ele e dono ponta a ponta do risco de aplicacao, do design (threat modeling) ate producao (deteccao e resposta), integrado ao SDLC via DevSecOps/shift-left. Responde por tres frentes simultaneas: (1) engenharia - threat modeling, revisao de codigo por vulnerabilidade, pentest/red team, gestao de dependencias vulneraveis (SCA) e SBOM contra supply chain attacks (que cresceram mais de 300% desde 2024); (2) governanca tecnica - SAST/DAST/SCA no pipeline CI/CD, metricas de MTTR e backlog de vulnerabilidade, priorizacao via CVSS+EPSS+KEV (nao so CVSS puro); e (3) compliance regulatorio - LGPD no Brasil (com a ANPD aplicando multas diarias desde a Deliberacao CD-10/2025) e GDPR/outras leis quando aplicavel, privacy by design e articulacao com o DPO/juridico. O ano marca dois marcos de referencia atualizados: OWASP Top 10 2025 (anunciado nov/2025, finalizado jan/2026, com Software Supply Chain Failures como nova categoria A03) e OWASP ASVS 5.0 (mai/2025, ~350 requisitos em 17 capitulos). O que separa senior de pleno nao e conhecer as ferramentas, e a capacidade de conduzir pentest manual (nao so automatizado), desenhar threat model sozinho, influenciar arquitetura, negociar risco com lideranca/juridico e escalar seguranca via programa de security champions, normalmente com 5+ anos de experiencia e certificacao de peso (CISSP, OSCP e/ou CEH).

#### Responsabilidades

- Conduzir threat modeling (STRIDE/PASTA/DREAD) em fases de design, mapeando data flow diagrams e superficie de ataque antes da primeira linha de codigo, em colaboracao com arquitetos e devs
- Revisar codigo-fonte por vulnerabilidade (manual + SAST), identificando padroes inseguros, segredos expostos e falhas de logica de negocio que scanners automatizados nao pegam
- Coordenar e/ou executar pentest (web, API, mobile, cloud) cobrindo autenticacao, autorizacao, IDOR e fluxos de negocio complexos, alem de suportar exercicios de purple team
- Gerir vulnerabilidades de dependencias de terceiros (SCA) e gerar/manter SBOM, com triagem por CVSS + EPSS + CISA KEV em vez de CVSS isolado
- Integrar SAST, DAST, SCA e secrets scanning ao pipeline CI/CD (shift-left/shift-smart), definindo gates de bloqueio e reduzindo ruido de falso positivo para nao afogar o time de dev
- Garantir compliance com LGPD (e GDPR quando aplicavel): principios de finalidade, necessidade, transparencia, seguranca, prevencao e responsabilizacao; apoiar o DPO/juridico em relatorio de impacto (RIPD/DPIA) e resposta a incidente de dados
- Gerir o ciclo de vida completo da vulnerabilidade: triagem, priorizacao, suporte a remediacao, validacao (retest) e SLA por severidade
- Definir e evoluir politicas de seguranca e controles alinhados a ISO/IEC 27001:2022 (Anexo A, Clausula 5.3 de papeis e responsabilidades) e a frameworks como NIST SSDF e OWASP SAMM
- Rodar/patrocinar programa de Security Champions dentro dos times de desenvolvimento, com treinamento de secure coding e threat modeling para devs
- Gerar metricas e reporte executivo (MTTR, backlog de vulnerabilidade aberto, cobertura de scanning, maturidade OWASP SAMM/ASVS) para lideranca tecnica e de negocio
- Apoiar resposta a incidente de seguranca de aplicacao e realizar analise pos-incidente (root cause) alimentando de volta o threat model e os controles preventivos


#### Hard skills

- Conhecimento solido de pelo menos uma linguagem de programacao (Python, Java, C#, JavaScript/TypeScript) para ler codigo e propor correcao, nao so apontar o problema
- Threat modeling estruturado (STRIDE, PASTA, DREAD) e leitura/criacao de diagramas de fluxo de dados (DFD)
- Dominio pratico de OWASP Top 10 e OWASP ASVS (niveis 1-3) como checklist de requisito verificavel, nao so lista de risco
- Configuracao e tuning de SAST, DAST e SCA (reducao de falso positivo, integracao em pipeline, gate de bloqueio por severidade)
- Pentest manual em aplicacao web/API/mobile: autenticacao, autorizacao, IDOR, SSRF, injecao, logica de negocio - alem do uso de scanner automatizado
- Priorizacao de vulnerabilidade via CVSS 4.0 combinado com EPSS (probabilidade de exploracao) e catalogo CISA KEV, nao CVSS isolado
- Seguranca de containers/Kubernetes e cloud (AWS/Azure/GCP): IAM, hardening, secrets management
- Seguranca de pipeline CI/CD e supply chain de software: geracao/leitura de SBOM, conceitos de SLSA, hardening de build
- Conhecimento de LGPD (principios, ANPD, papel do DPO, prazos e penalidades) e nocao comparativa de GDPR (extraterritorialidade, DPO obrigatorio para controlador e operador, notificacao de 72h)
- Privacy by design / data protection by design (minimizacao de dados, controle de acesso baseado em papel, retencao)
- Automacao e scripting (Python/Bash) para criar ferramenta interna, integracao de API de scanner e enriquecimento de relatorio
- Comunicacao tecnica para publico nao tecnico: negociar risco residual com produto/juridico/lideranca e escrever relatorio executivo


#### Ferramentas de mercado

- Burp Suite Professional (PortSwigger) - pentest manual/automatizado, Collaborator, BApp Store - padrao de mercado para teste manual de aplicacao web
- OWASP ZAP - DAST open-source, alternativa gratuita ao Burp para varredura dinamica
- SonarQube - SAST + qualidade de codigo; desde 2025 tambem oferece SCA via add-on Advanced Security (Enterprise), com deteccao de pacote malicioso e geracao de SBOM
- Snyk (Snyk Code + Snyk Open Source) - SAST developer-friendly e SCA integrado a IDE/Git/CI/CD/containers
- Dependabot (GitHub) - abertura automatica de PR de atualizacao de dependencia vulneravel
- Semgrep e Checkmarx - SAST adicionais citados como referencia de mercado ao lado de SonarQube
- OWASP Dependency-Check - SCA open-source
- Trivy - varredura de vulnerabilidade em container/imagem e geracao de SBOM
- Microsoft Threat Modeling Tool e OWASP Threat Dragon - modelagem de ameaca com diagrama e relatorio exportavel
- Nessus/Tenable e Nuclei - varredura de infraestrutura/rede e templates de exploracao
- GitHub Advanced Security / GitLab Security - secret scanning e SAST/SCA nativos de plataforma
- Jira (ou equivalente) - rastreamento de vulnerabilidade, SLA e ciclo de remediacao


#### Metodologias / certificações de referência

- OWASP Top 10 2025 - anunciado nov/2025 no OWASP Global AppSec (Washington DC), finalizado jan/2026; A01 Broken Access Control permanece no topo e absorve SSRF; A03 Software Supply Chain Failures e categoria nova
- OWASP ASVS 5.0 (mai/2025) - ~350 requisitos verificaveis em 17 capitulos, cobre arquitetura cloud-native; complementa o Top 10 transformando risco em requisito testavel
- OWASP SAMM (Software Assurance Maturity Model) - avaliacao de maturidade de AppSec e desenho de programa Security Champions
- STRIDE / PASTA / DREAD - metodologias de threat modeling
- NIST SSDF (Secure Software Development Framework) - referencia junto com ASVS/SAMM para Secure by Design
- CVSS 4.0 (FIRST, nov/2023, rollout 2025-2026) combinado com EPSS v4 (mar/2025) e CISA KEV para priorizacao de vulnerabilidade
- ISO/IEC 27001:2022 - Clausula 5.3 e Anexo A Controle 5.2 (papeis e responsabilidades de seguranca da informacao)
- LGPD (Lei 13.709/2018) e regulamentacao ANPD 2025-2026 (ex.: Deliberacao CD-10/2025 sobre multa diaria); GDPR como referencia comparativa para empresa com operacao/dado na UE
- CISSP - certificacao ampla de governanca/arquitetura/gestao de risco, tipicamente exigida para papel senior/lideranca, requer 5 anos de experiencia
- OSCP (Offensive Security Certified Professional) - certificacao hands-on de pentest, altamente valorizada para trabalho tecnico profundo de exploracao
- CEH (Certified Ethical Hacker) - certificacao mais reconhecida em contratos de governo e triagem de RH, geralmente ponto de entrada comparado a OSCP


#### Entregáveis típicos

- Relatorio de pentest/teste de vulnerabilidade com severidade (CVSS/EPSS), prova de conceito (PoC), impacto de negocio e recomendacao de remediacao
- Documento de threat model (diagrama DFD + lista de ameacas STRIDE priorizadas + mitigacao proposta) por feature/arquitetura nova
- Checklist/matriz de compliance LGPD (e GDPR quando aplicavel), incluindo mapeamento de dado pessoal, base legal, e gaps frente aos principios da lei
- SBOM (Software Bill of Materials) versionado como artefato de pipeline, para resposta rapida a CVE de dependencia
- Politica de seguranca e documentacao de ISMS alinhada a ISO/IEC 27001:2022 (papeis e responsabilidades, Clausula 5.3/Anexo A 5.2)
- Dashboard/relatorio executivo de metricas: MTTR, backlog de vulnerabilidade por severidade, cobertura de SAST/DAST/SCA no pipeline, maturidade OWASP SAMM/ASVS
- Material de treinamento e trilha do programa Security Champions para times de desenvolvimento
- Runbook de resposta a incidente de seguranca de aplicacao / vazamento de dado pessoal


#### O que diferencia sênior de pleno

- Pleno normalmente executa: roda scanner, aplica checklist OWASP, corrige vulnerabilidade apontada, participa de threat model conduzido por outro. Senior desenha e conduz o threat model sozinho, influencia decisao de arquitetura antes do design fechar
- Senior tem capacidade de pentest manual real (logica de negocio, encadeamento de falha, bypass de controle) - nao apenas interpretar saida de ferramenta automatizada
- Senior assume ownership de metrica e reducao de backlog/MTTR ao longo do tempo, com relato quantificado de impacto para lideranca, nao so relatorio pontual de achado
- Senior negocia risco residual diretamente com produto, juridico/DPO e lideranca executiva, incluindo decisao de aceitar/mitigar/transferir risco - pleno normalmente escala essa decisao
- Senior lidera/mentora (formalmente ou nao) devs e AppSec pleno/junior via programa de Security Champions, revisao de codigo e pareamento, mesmo sem cargo de gestao formal
- Senior e dono da integracao de ferramenta no pipeline (tuning de SAST/DAST/SCA, reducao de falso positivo, definicao de gate) - pleno tipicamente consome a ferramenta ja configurada
- Senior articula compliance regulatorio (LGPD/GDPR) com decisao tecnica de arquitetura (privacy by design), atuando como ponte entre juridico e engenharia - competencia raramente exigida de pleno
- Senior costuma ter 5+ anos de experiencia e certificacao de peso (CISSP para governanca/arquitetura; OSCP/CEH para trilha ofensiva), enquanto pleno tem certificacao inicial ou nenhuma


<details>
<summary>Fontes (37)</summary>

- https://www.wiz.io/academy/application-security/appsec-engineers
- https://destcert.com/career-guide/application-security-engineer-career-path/
- https://www.hackerone.com/knowledge-center/application-security-engineer
- https://www.securitycompass.com/blog/what-is-owasp-asvs/
- https://softwaremill.com/whats-new-in-asvs-5-0/
- https://owasp.org/Top10/2025/
- https://patrowl.io/en/blog/owasp-top-10-2025-what-s-changed-and-the-2026-data
- https://codific.com/owasp-top-10-2025-what-it-is-what-changed-and-what-to-do-with-it/
- https://www.securecodinghub.com/blog/owasp-asvs-developers-complete-guide
- https://aneps.org.br/blog/lgpd-em-2025-lei-geral-de-protecao-de-dados/
- https://tiinside.com.br/20/02/2026/lgpd-compliance-e-ciberseguranca-tres-temas-que-o-juridico-nao-pode-mais-tratar-separadamente/
- https://blog.estudesemfronteiras.com/seguranca-da-informacao-lgpd-e-governanca-digital-aplicada-conceitos-funcoes-areas-e-carreira-profissional/
- https://gdpr.eu/gdpr-vs-lgpd/
- https://securiti.ai/lgpd-vs-gdpr/
- https://www.endpointprotector.com/blog/lgpd-vs-gdpr-the-biggest-differences/
- https://www.stackhawk.com/blog/best-sast-tools-comparison/
- https://vulnify.app/blog/sast-vs-dast-vs-sca-which-scanner-do-you-actually-need
- https://wpnewsify.com/blog/sast-vs-dast-semgrep-vs-owasp-zap-and-other-tools-for-application-security-testing
- https://www.ox.security/blog/application-security-testing-tools/
- https://deepstrike.io/blog/top-cybersecurity-certifications-2025
- https://www.stationx.net/ceh-vs-oscp/
- https://www.stationx.net/cissp-vs-ceh/
- https://destcert.com/resources/cissp-vs-oscp/
- https://ambacia.eu/careers-post/security-certifications/
- https://medium.com/@jsocitblog/from-junior-to-senior-security-engineer-skills-nobody-tells-you-about-2b0ecfab5782
- https://www.jit.io/resources/app-security/stride-threat-model-a-complete-guide
- https://owasp.org/www-community/Threat_Modeling_Process
- https://hightable.io/iso-27001-clause-5-3-organisational-roles-responsibilities-and-authorities/
- https://www.isms.online/iso-27001/annex-a-2022/5-2-information-security-roles-responsibilities-2022/
- https://www.helpnetsecurity.com/2026/05/26/cybersecurity-jobs-available-right-now-may-26-2026/
- https://deepstrike.io/blog/devsecops-statistics
- https://www.ox.security/blog/application-security-trends-in-2026/
- https://www.picussecurity.com/resource/blog/vulnerability-prioritization-why-cvss-isnt-enough
- https://appscale.blog/en/blog/vulnerability-prioritisation-epss-kev-cvss-exploitability-triage-2026
- https://devguide.owasp.org/en/02-foundations/02-secure-development/
- https://owaspsamm.org/model/governance/education-and-guidance/stream-a/
- https://codific.com/embedding-security-into-the-sdlc/

</details>


---

## Tech Lead / Code Reviewer

**Papel:** Tech Lead / Code Reviewer Senior-Especialista (2025/2026)


Em 2025/2026 o Tech Lead senior/especialista que revisa codigo e garante padrao de arquitetura e definido por um duplo perfil: (a) em projeto NOVO ele e o guardiao ativo da Clean Architecture de Robert C. Martin e dos principios SOLID, definindo a estrutura de camadas (entities/use cases/interface adapters/frameworks e a Dependency Rule apontando sempre para dentro) antes da primeira linha de codigo de negocio e automatizando essa regra com testes de arquitetura (ArchUnit ou equivalente) para que ela nao dependa de boa vontade humana no review; (b) em projeto LEGADO ele inverte a ordem: primeiro mapeia a arquitetura real existente (nao a que deveria existir) usando tecnicas como C4 model, mapa de dependencias e analise de acoplamento de mudanca (change coupling), so depois cobra padrao, e usa tecnicas de modernizacao incremental como Strangler Fig (Martin Fowler) e testes de caracterizacao/seams (Michael Feathers) em vez de reescrita big-bang. Em ambos os casos ele passa 30%+ do tempo em code review, atua como multiplicador via mentoria (nao so aprova/rejeita PR), usa ferramentas de analise estatica (SonarQube + linter especifico da linguagem) como filtro mecanico para liberar o review humano para design e logica, documenta decisoes relevantes via ADR (Architecture Decision Record, formato Nygard) e nunca aprova uma mudanca arquitetural relevante so por instinto/opiniao estetica sem checklist objetivo por tras. O que separa senior de pleno nao e saber mais sintaxe: e revisar arquitetura e nao so linha a linha, escolher a batalha certa (nem todo desvio de padrao vale bloquear PR), ensinar via review em vez de so corrigir, e ter escopo de influencia que atravessa um time inteiro (vs. pleno, que ainda revisa sobretudo dentro do proprio modulo/feature).

#### Responsabilidades

- Definir e documentar o padrao de codigo do time/projeto (guia de estilo, convencoes de nomenclatura, estrutura de pastas) e mante-lo atualizado conforme o codigo evolui
- Conduzir e presidir o processo de code review: revisar pull requests quanto a design, complexidade, corretude, testes, legibilidade e aderencia ao padrao antes de aprovar merge
- Garantir aderencia a Clean Architecture e SOLID em projeto NOVO desde o desenho inicial: definir camadas, a Dependency Rule (dependencias sempre apontando para dentro, em direcao as regras de negocio) e os limites de cada circulo/camada antes do primeiro modulo de negocio ser escrito
- Automatizar a regra arquitetural com testes de arquitetura (ex. ArchUnit) para que violacao de camada quebre o build, em vez de depender so de revisao humana
- Em projeto LEGADO, mapear a arquitetura real existente antes de cobrar qualquer padrao novo: identificar modulos, acoplamento, fronteiras de fato (nao as documentadas) e pontos de mudanca frequente, usando tecnicas como C4 model e analise de dependencias/acoplamento de mudanca
- Planejar e conduzir modernizacao incremental de legado com o padrao Strangler Fig (substituir aos poucos por um proxy/roteador, nunca reescrita completa de uma vez) e proteger comportamento existente com testes de caracterizacao antes de refatorar (tecnica de seams de Michael Feathers)
- Exercer mentoria tecnica: usar o code review como momento de ensino (pair programming, feedback detalhado, explicacao do porque, nao so do que corrigir), elevando o nivel tecnico de plenos e juniores
- Tomar e registrar decisoes arquiteturais relevantes como ADR (Architecture Decision Record), documentando contexto, decisao e consequencias para rastreabilidade futura
- Configurar e manter o pipeline de qualidade (linter, formatter, analise estatica, quality gate no CI/CD) para que checagem mecanica nunca dependa de humano lembrar de rodar
- Escalar e nao decidir sozinho cortes de escopo tecnico relevantes; reportar riscos arquiteturais ao dono do produto/arquitetura quando a pressao de prazo colide com padrao de qualidade
- Balancear pragmatismo: em legado, aceitar debito tecnico existente como dado do sistema e priorizar risco/impacto da mudanca, em vez de exigir Clean Architecture retroativa em uma unica PR


#### Hard skills

- Dominio pratico de Clean Architecture (camadas, Dependency Rule, portas e adaptadores) e Arquitetura Hexagonal como variante correlata
- Dominio dos 5 principios SOLID (SRP, OCP, LSP, ISP, DIP) e capacidade de apontar violacao concreta no codigo, nao so citar o nome do principio
- Leitura e escrita de testes automatizados em multiplos niveis (unitario, integracao, contrato, caracterizacao) e entendimento de test doubles/mocks para isolar camadas
- Capacidade de mapear arquitetura existente a partir do codigo (nao da documentacao) em sistemas legados: leitura de acoplamento, ciclos de dependencia, hotspots de mudanca
- Conhecimento de padroes de modernizacao incremental (Strangler Fig, branch by abstraction, anti-corruption layer) para evoluir legado sem parar a operacao
- Escrita de ADR (Architecture Decision Record) claro e objetivo, incluindo contexto, alternativas consideradas e consequencias
- Configuracao de pipelines de CI/CD com quality gate (bloqueio automatico por cobertura, duplicidade, complexidade ciclomatica, vulnerabilidade)
- Fluencia em pelo menos uma stack de forma profunda (para dar review com autoridade tecnica) e leitura cruzada de outras linguagens do stack do time
- Comunicacao tecnica escrita (feedback de review nao-ambigo, documentacao de decisao) e habilidade de mentoria/coaching tecnico


#### Ferramentas de mercado

- SonarQube / SonarCloud (analise estatica, quality gate, deteccao de code smell, duplicidade e vulnerabilidade)
- ESLint + Prettier (JavaScript/TypeScript) — ESLint para regras/qualidade, Prettier para formatacao, com ESLint Stylistic substituindo as regras de formatacao depreciadas do ESLint desde a v8.53
- Pylint / Ruff + Bandit (Python) para lint, qualidade e seguranca basica
- RuboCop (Ruby), Checkstyle/PMD/SpotBugs (Java), golangci-lint (Go), clippy (Rust) como linters especificos de linguagem
- ArchUnit (Java) para escrever testes de arquitetura que travam o build quando uma camada viola a Dependency Rule ou uma convencao de pacote
- dependency-cruiser (JS/TS) para validar e visualizar grafo de dependencias contra regras declaradas
- C4 model / Structurizr (Simon Brown) para diagramar e documentar arquitetura em niveis (contexto, container, componente, codigo), inclusive de sistemas legados
- CodeScene para analise comportamental via historico do Git (acoplamento de mudanca, hotspots de complexidade/debito tecnico em legado)
- Ferramentas de PR/review (GitHub/GitLab code review, revisao obrigatoria via CODEOWNERS, checks obrigatorios antes de merge)
- adr-tools / templates Markdown de ADR (formato Nygard) versionados junto do repositorio


#### Metodologias / certificações de referência

- Clean Architecture — Robert C. Martin (Uncle Bob), publicado originalmente em blog.cleancoder.com em 13/08/2012 e depois no livro Clean Architecture (2017)
- Principios SOLID — tambem formalizados por Robert C. Martin
- Architecture Decision Records (ADR) — formato original de Michael Nygard, publicado no blog da Cognitect em 15/11/2011
- Strangler Fig Pattern — cunhado por Martin Fowler para modernizacao incremental de legado, documentado tambem no Azure Architecture Center
- Working Effectively with Legacy Code — Michael Feathers (seams, testes de caracterizacao como pre-requisito para refatorar legado com seguranca)
- Building Evolutionary Architectures (fitness functions) — Neal Ford, Rebecca Parsons e Patrick Kua (ThoughtWorks), para governanca automatizada de atributos arquiteturais ao longo do tempo
- Google Engineering Practices (google.github.io/eng-practices) — padrao de mercado citado por multiplas fontes para o que constitui um code review de qualidade
- C4 Model — Simon Brown, para documentacao de arquitetura em niveis, usado tanto em projeto novo quanto para mapear legado


#### Entregáveis típicos

- Guia de padrao de codigo do time/projeto (coding standards guide): convencoes de nomenclatura, estrutura de pastas, regras de estilo, versionado junto do repositorio
- Checklist de code review objetivo (design, complexidade, testes, seguranca, performance, legibilidade), tipicamente com criterio explicito do que bloqueia PR versus o que e sugestao
- Configuracao de pipeline de quality gate (SonarQube + linter da linguagem) integrada ao CI/CD, com limiares definidos (cobertura minima, duplicidade maxima, zero vulnerabilidade critica)
- Testes de arquitetura automatizados (ex. suite ArchUnit) que travam merge quando uma camada da Clean Architecture e violada
- Relatorio de mapeamento de arquitetura legada: diagrama C4 (contexto/container/componente) da arquitetura REAL encontrada, lista de acoplamentos e modulos de alto risco, e pontos de entrada seguros para modernizacao
- Plano de modernizacao incremental (Strangler Fig) com fases, proxy/roteamento de transicao e criterio de corte de cada fatia migrada
- Colecao de ADRs (Architecture Decision Records) documentando decisoes arquiteturais relevantes, formato Nygard (titulo, status, contexto, decisao, consequencias)
- Suite de testes de caracterizacao cobrindo comportamento atual do modulo legado antes de qualquer refatoracao
- Registro de mentoria/feedback recorrente de code review (padroes de erro repetidos, plano de evolucao tecnica do time)


#### O que diferencia sênior de pleno

- Senior revisa arquitetura e estrutura do arquivo primeiro (a mudanca de alto nivel esta certa?) antes de entrar linha a linha; pleno tende a pular direto para leitura linha a linha
- Senior sabe quando NAO bloquear um PR por desvio cosmetico de padrao (escolhe a batalha certa); pleno tende a aplicar a regra de forma rigida e identica em todo contexto
- Senior usa o code review como ferramenta de mentoria (explica o porque, ensina o principio); pleno tende a so corrigir o ponto especifico sem generalizar o ensinamento
- Senior tem escopo de influencia que atravessa times/modulos (proximo de principal engineer, cujo escopo e organizacional); pleno normalmente influencia so o proprio time/feature
- Senior reconhece a diferenca entre projeto novo (pode e deve exigir Clean Architecture/SOLID desde o inicio) e legado (mapeia antes de exigir, aceita debito tecnico como dado do sistema e prioriza por risco); pleno tende a aplicar a mesma regra de projeto novo em qualquer contexto, gerando atrito desnecessario em legado
- Senior formaliza decisao relevante em ADR e regra arquitetural em teste automatizado (ArchUnit/fitness function); pleno tende a manter a regra so na memoria do time ou em documentacao que desatualiza
- Senior aplica tecnica de modernizacao incremental comprovada (Strangler Fig, testes de caracterizacao) para legado; pleno tende a propor reescrita completa (big bang) por falta de repertorio de alternativas menos arriscadas
- Segundo dado de mercado, dev senior gasta pelo menos 30% do tempo em code review, tempo que pleno normalmente nao aloca de forma estruturada


<details>
<summary>Fontes (28)</summary>

- https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html
- https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions
- https://adr.github.io/
- https://www.archunit.org/
- https://www.martinfowler.com/articles/2024-strangler-fig-rewrite.html
- https://learn.microsoft.com/en-us/azure/architecture/patterns/strangler-fig
- https://www.thoughtworks.com/en-us/insights/articles/embracing-strangler-fig-pattern-legacy-modernization-part-one
- https://c4model.com/
- https://en.wikipedia.org/wiki/C4_model
- https://nealford.com/books/buildingevolutionaryarchitectures.html
- https://www.thoughtworks.com/en-us/insights/books/building-evolutionaryarchitectures-second-edition
- https://aws.amazon.com/blogs/architecture/using-cloud-fitness-functions-to-drive-evolutionary-architecture/
- https://google.github.io/eng-practices/review/
- https://github.com/google/eng-practices
- https://www.sonarsource.com/products/sonarqube/
- https://docs.sonarsource.com/sonarqube-server/2025.3/quality-standards-administration/managing-quality-gates/introduction-to-quality-gates
- https://github.com/sverweij/dependency-cruiser
- https://docs.enterprise.codescene.io/versions/5.1.0/guides/technical/change-coupling.html
- https://en.wikipedia.org/wiki/Robert_C._Martin
- https://understandlegacycode.com/blog/key-points-of-working-effectively-with-legacy-code/
- https://bssw.io/items/working-effectively-with-legacy-code
- https://finnnannestad.com/blog/linting-and-formatting
- https://betterstack.com/community/guides/scaling-nodejs/prettier-vs-eslint/
- https://waydev.co/tech-lead-responsibilities/
- https://leaddev.com/career-development/who-are-staff-principal-and-distinguished-engineers
- https://dev.to/swapnilmg/what-senior-engineers-actually-do-during-code-reviews-its-not-just-finding-bugs-eja
- https://dev.to/rahulxsingh/static-code-analysis-tools-the-definitive-guide-2026-19cg
- https://www.rocketseat.com.br/blog/artigos/post/tech-lead-papel-desafios-habilidades-essenciais

</details>


---
