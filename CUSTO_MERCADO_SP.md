# Custo de Mercado — São Paulo (capital), nível sênior/especialista

Referência de custo usada pelo skill `estimativa-macro-projeto` (ver `.claude/skills/estimativa-macro-projeto/SKILL.md`) para converter esforço humano-equivalente em custo de projeto. Pesquisa de mercado 2025/2026, cidade de São Paulo, nível sênior/especialista — CLT bruto mensal, sem 13º/férias/FGTS/benefícios, salvo indicação contrária.

**Como usar:** `custo do bloco = dia-equivalente do papel × esforço humano-equivalente em dias (T-shirt do passo 3) × quantidade de instâncias paralelas`, depois aplicado aos três cenários PERT (otimista/provável/pior caso) do skill.

**Data da pesquisa:** 2026-09-17. Revisite esta tabela periodicamente (salário de mercado muda) — não trate como definitiva para sempre.

## Tabela de referência

| Papel | Faixa mensal CLT bruto (SP, sênior) | Mediana usada como referência | Dia-equivalente (mediana ÷ 21) | PJ/hora ou dia (quando há dado real) |
|---|---|---|---|---|
| Product Owner | R$ 13.000–22.000 (faixa "sênior específico"; fontes que não segmentam por senioridade caem para R$ 7.700–14.000) | **R$ 17.500** | ≈ R$ 833/dia | Não encontrado dado de mercado real para PJ/hora específico do cargo. |
| Gerente de Projeto | R$ 20.000–35.000 | **R$ 27.000** | ≈ R$ 1.286/dia | Não encontrado dado de mercado real para PJ/hora específico do cargo. |
| Arquiteto de Soluções | R$ 15.500–22.000 (recorte mais provável; faixa ampla R$ 12.000–27.000) | **R$ 16.500** | ≈ R$ 786/dia | Não encontrado dado de mercado real para PJ/hora específico do cargo. |
| Scrum Master | R$ 11.000–18.000 | **R$ 13.500** | ≈ R$ 643/dia | Não encontrado dado de mercado real para PJ/hora específico do cargo. |
| Desenvolvedor (Dev) | R$ 12.250–20.600 (Glassdoor mostra cauda até R$ 27.560 no P90) | **R$ 16.000** | ≈ R$ 762/dia | **R$ 130–200/hora** (teto ~R$ 243/hora) ≈ R$ 1.000–1.600/dia (teto ~R$ 1.950/dia) — única função com PJ/hora real e citável (FreelaSemCrise, tabela SP 2026). |
| DevOps / SRE | R$ 14.000–25.000 (teto ~R$ 27.000 para trilha DevSecOps) | **R$ 18.500** | ≈ R$ 881/dia | Não encontrado dado de mercado real para PJ/hora específico do cargo. |
| QA | R$ 10.350–17.400 (institucional/Robert Half); dado autodeclarado roda mais baixo, R$ 8.000–9.700 | **R$ 13.500** | ≈ R$ 643/dia | Não encontrado dado de mercado real para PJ/hora específico do cargo. |
| UX/UI Designer | R$ 8.000–16.500 sob o título "UX/UI Designer Sênior"; sob "Product Designer Sênior" (mais comum em produto) a mediana sobe para ~R$13.700 | **R$ 11.000** | ≈ R$ 524/dia | R$ 70–250/hora — dado genérico de freelancer de UX/UI, não quebrado por senioridade; tratar como referência ampla, não tabela oficial "sênior SP". |
| Segurança / AppSec | R$ 9.000–19.500 | **R$ 13.200** | ≈ R$ 629/dia | **R$ 400–600/hora** ≈ R$ 3.200–4.800/dia — valor bem mais alto que o dia-equivalente CLT; provavelmente reflete consultoria especializada pontual (pentest, auditoria), não headcount contínuo — usar com essa ressalva. |
| Tech Lead / Code Reviewer | R$ 13.000–26.000 (grosso R$ 15.000–21.000; acima disso só quando já inclui gestão de pessoas) | **R$ 18.500** | ≈ R$ 881/dia | Não encontrado dado de mercado real para PJ/hora específico do cargo. |

## Notas importantes

- **Divergência entre fontes é real, não ruído.** Fonte institucional (Robert Half, Michael Page — baseadas em colocação real de vaga) tende a ficar acima de fonte autodeclarada (Glassdoor, salario.com.br/CAGED), especialmente em QA e UX/UI. A mediana escolhida acima prioriza a fonte institucional quando ela existe, por refletir melhor contratação real de nível sênior — mas a faixa completa está preservada na tabela para quem quiser recalibrar.
- **CLT bruto ≠ custo total de projeto.** Estes valores não incluem 13º, férias, FGTS, encargos, benefícios nem margem de operação do time `agentes-ti`. Um multiplicador comum no mercado brasileiro para ir de "salário CLT bruto" a "custo empresa completo" gira em torno de 1,5x a 2x — isso é regra geral de contabilidade de RH, não um número pesquisado especificamente nesta rodada; se for usar isso para orçar cliente de verdade, aplique esse ajuste conscientemente, não implicitamente.
- **PJ é a exceção, não a regra, nos dados encontrados.** Só Dev, UX/UI e Segurança/AppSec tiveram dado real de PJ/hora; os outros 7 papéis não têm tabela de mercado publicada nesse formato — nesse caso, use o dia-equivalente CLT como proxy, sabendo que é uma aproximação.
- **São Paulo capital paga acima da média nacional** na maioria dos papéis pesquisados — não reaproveite estes números para outra cidade/região sem revisitar a pesquisa.

## Fontes principais por papel

- **Product Owner:** Robert Half (Guia Salarial 2026, SP), Michael Page (Guia Salarial Brasil 2025, PDF), Indeed (SP), Glassdoor Brasil (via snippet, não confirmado por leitura direta), Tera/Somostera.
- **Gerente de Projeto:** Robert Half (SP, "PMO (P/M)" e "PMO (G)"), Glassdoor Brasil (SP), Salario.com.br (CAGED/RAIS), Michael Page.
- **Arquiteto de Soluções:** Glassdoor, Catho, Indeed, Robert Half, Michael Page (PJ não encontrado em nenhuma).
- **Scrum Master:** Robert Half (Guia Salarial 2026, SP), Glassdoor Brasil (SP, 173 amostras).
- **Desenvolvedor:** Robert Half (Guia Salarial 2026, SP), Glassdoor Brasil (SP, 105 amostras), Indeed (Dev Java Sênior, SP), FreelaSemCrise (tabela PJ SP 2026).
- **DevOps/SRE:** Robert Half (Analista de DevOps e DevSecOps, SP), Michael Page (Guia Salarial Brasil 2025, PDF), Glassdoor Brasil.
- **QA:** Robert Half (Guia Salarial 2026, SP e nacional), Glassdoor/salario.com.br (CAGED).
- **UX/UI Designer:** Glassdoor Brasil (UX/UI Designer Sênior e Product Designer Sênior, SP), Portal Salário/CAGED (Designer de UI Sênior, SP).
- **Segurança/AppSec:** salario.com.br (recorte SP + senioridade), Robert Half (majoritariamente nacional para este cargo específico).
- **Tech Lead:** Glassdoor (Tech Lead, SP, 2.066 amostras), Robert Half (Arquiteto de Software e Dev Full-Stack Sênior, SP), Código Fonte TV 2025 (nacional).
