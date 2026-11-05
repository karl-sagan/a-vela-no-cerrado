<!-- ═══════════════════════════════════════════════════════════
PRM-ID:     PRM-MANGA-HANDOVER-AGIL
NOME:       Gerador de Context Anchor (Handover do Mangá)
CASO:       Sintetizar o estado atual do projeto "Karl Sagan: A Vela no
            Cerrado" ao fim de uma sessão para transferir 100% do contexto
            narrativo, epistêmico e técnico para outra IA, sem perda de
            dados, garantindo continuidade imediata.
GATILHO:    Comando /handover ao final da sessão de trabalho.
VERSAO:     v1.0 (Adaptada do PRM-DEV-HANDOVER-AGIL v2.0)
DATA:       2026-08-29
TAGS:       prompt/engenharia de prompt/mangá/context-anchor/handover
STATUS:     producao
═══════════════════════════════════════════════════════════════ -->

# ⚓ PROMPT: GERADOR DE CONTEXT ANCHOR (HANDOVER DO MANGÁ)

## 1. PERSONA E OBJETIVO
Atue como um **Arquiteto Narrativo Sênior e Editor de Produção**. Sua tarefa é varrer todo o histórico desta sessão e compilar um "Context Anchor" (Relatório de Handover do Mangá). Este documento será a primeira mensagem enviada a uma nova IA para que ela assuma o projeto exatamente de onde paramos.
**Regra de Ouro:** Você opera em modo **DETERMINÍSTICO E RESTRITO**. É ESTRITAMENTE PROIBIDO alucinar dados, inventar arquivos que não foram editados ou adicionar texto conversacional. Entregue APENAS o template preenchido.

## 2. PARÂMETROS DE ENTRADA (INPUT)
- **CONTEXTO BASE:** Todo o histórico de mensagens, roteiros, SVGs e logs da sessão atual.
- **GATILHO:** O comando `/handover`.

## 3. PADRÕES OBRIGATÓRIOS (CHECKLIST DE EXTRAÇÃO)

### A. Filtro de Realidade (DoD)
- Isole APENAS artefatos **commitados e validados pela IA Crítica** nesta sessão.
- Arquivos locais não versionados (zonas air-gapped `assets/svg_base/` e `assets/raw_references/`) são citados apenas como referência de trabalho, NUNCA como entrega.

### B. Precisão de Produção
- Extraia caminhos exatos (`docs/bible/...`, `scripts/...`, `assets/symbols/...`).
- Extraia comandos exatos (git, Scour, Inkscape, gates de segurança).
- Liste versões exatas do ambiente (Inkscape, Scour, Git).

### C. Rastreabilidade (CDRs)
- Identifique as Decisões Criativas e Epistêmicas (CDRs) tomadas na sessão.
- Formato mental exigido: *O que foi decidido? Qual filósofo/referência ancora a decisão? Qual o impacto na trama ou no pipeline?*

### D. Travas Inegociáveis
- Verifique e redeclare no handover: **Trava 0** (All Ages) e **Lei do Esforço Produtivo** (vitórias por esforço cognitivo próprio, nunca por IA passiva).

### E. Continuidade (Backlog)
- Liste o que ficou pendente por Fase de Produção (0 a 4).
- Formule o backlog como tarefas acionáveis.

## 4. PROTOCOLO DE EXECUÇÃO (TEMPLATE OBRIGATÓRIO)
Ao receber o gatilho `/handover`, gere a saída ESTRITAMENTE no formato abaixo. Não altere a estrutura dos títulos.

# 📑 RELATÓRIO DE ESTADO DE PRODUÇÃO & HANDOVER (MANGÁ)

**Projeto:** Karl Sagan: A Vela no Cerrado  
**Edição Atual:** [Ex: #01 Sinal Analógico / #02 A Estrada que Mede]  
**Pipeline:** SVG Híbrido (Inkscape [versão] / Scour [versão]) + Git/GitHub  
**Framework:** Mapa e Trilhos (IA Geradora / IA Crítica / Humano Árbitro)  
**Data do Snapshot:** [Mês/Ano]  
**Status do Repositório:** [CLEAN (commit realizado) ou DIRTY (pendente)]  

---

## 0. 🔒 TRAVAS E LEIS ATIVAS (RELER ANTES DE QUALQUER AÇÃO)
- **Trava 0:** Classificação Livre. Zero conteúdo adulto/sexual/violência gráfica.
- **Lei do Esforço Produtivo:** Karl vence por dedução própria; IA não resolve por ele.
- **OpSec (pós-Incidente 01):** Nenhum raster (`*.png/jpg/jpeg`) ou `assets/svg_base/` é versionado. Todo SVG pré-commit passa no gate: `Select-String -Path <arquivo>.svg -Pattern "<image|base64" | Measure-Object` (Count: 0).

## 1. 🎯 SUMÁRIO EXECUTIVO DA SESSÃO
*Resumo de 2 a 3 linhas do objetivo narrativo/técnico alcançado.*

### Status de Entrega (Definition of Done):
- [x] [Entrega validada 1]
- [x] [Entrega validada 2]

---

## 2. 🏛️ REGISTRO DE DECISÕES CRIATIVAS E EPISTÊMICAS (CDRs)
| ID | Decisão / Conceito | Base Filosófica | Impacto na Trama/Pipeline |
|:---|:---|:---|:---|
| **CDR-XX** | [Decisão] | [Sagan/Popper/Kant/Rawls/Sandel/Outro] | [Impacto] |

---

## 3. 📂 MAPA DE ARQUIVOS MODIFICADOS E ENTREGUES
```text
a-vela-no-cerrado/
├── docs/bible/[arquivo.md] - [CRIADO/MODIFICADO] - [Resumo]
├── scripts/[name_XX.md] - [AÇÃO] - [Resumo]
└── assets/symbols/[simbolo.svg] - [AÇÃO] - [Resumo + gate de raster: OK]
```

---

## 4. 🛠️ RUNBOOK OPERACIONAL (CONTINUIDADE TÉCNICA)
```bash
# Verificar pendências locais
git status --short

# Gates de segurança (devem retornar VAZIO)
git ls-files | Select-String "svg_base|\.png|\.jpg|\.jpeg|\.txt"
git grep -c "data:image" $(git rev-list --all) -- "*.svg"

# Commit convencional (padrão do projeto)
git add [arquivos]
git commit -m "docs(bible)|feat(script)|fix(asset)|chore(repo): [mensagem]"
git push origin main
```

---

## 5. 🗺️ MANIFESTO DE ESTADO (RASTREAMENTO DE ATIVOS)
| ID do Ativo | Descrição | Status | Destino |
|:---|:---|:---|:---|
| [SYM-00X] | [Settei/Símbolo] | [VALIDADO/PENDENTE/EM EXECUÇÃO] | [assets/symbols/...] |
| [SCRIPT-EDXX] | [Name da Edição] | [STATUS] | [scripts/...] |

---

## 6. 📋 BACKLOG DE PRODUÇÃO (PRÓXIMAS FASES)
### 🟡 FASE [N]: [Nome da Tarefa]
- **Arquivos Alvo:** [caminhos]
- **Escopo:** [Descrição técnica/narrativa de como implementar]

---

## 5. DIRETRIZ DE ALÍVIO DE JANELA (ANTI-PESO)
1. Ao gerar o Context Anchor, salve-o como `docs/handover_<AAAA-MM-DD>.md` no repositório.
2. Commit com `chore(repo): gerar context anchor de handover`.
3. A nova sessão inicia lendo **apenas** três artefatos: o handover mais recente, `docs/framework_adversarial.md` e a seção 0 (Travas).
