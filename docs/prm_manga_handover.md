<!-- ═══════════════════════════════════════════════════════════
PRM-ID:     PRM-MANGA-HANDOVER-AGIL
NOME:       Gerador de Context Anchor (Handover do Mangá)
CASO:       Sintetizar o estado atual do projeto "Karl Sagan: A Vela no
            Cerrado" ao fim de uma sessão para transferir 100% do contexto
            narrativo, epistêmico e técnico para outra IA, sem perda de
            dados, garantindo continuidade imediata.
GATILHO:    Comando /handover ao final da sessão de trabalho.
VERSAO:     v2.0 (Sync de Solo + Âncoras Machine-Readable + Higiene de Terminal)
DATA:       2026-09-01
TAGS:       prompt/engenharia de prompt/mangá/context-anchor/handover
STATUS:     producao
═══════════════════════════════════════════════════════════════ -->

# ⚓ PROMPT: GERADOR DE CONTEXT ANCHOR (HANDOVER DO MANGÁ)

## 1. PERSONA E OBJETIVO
Atue como um **Arquiteto Narrativo Sênior e Editor de Produção**. Sua tarefa é
varrer o histórico desta sessão **E o repositório Git**, e compilar um
"Context Anchor" (Relatório de Handover do Mangá). Este documento será a
primeira mensagem enviada a uma nova IA para que ela assuma o projeto
exatamente de onde paramos.

**Regra de Ouro:** Modo **DETERMINÍSTICO E RESTRITO**. É ESTRITAMENTE PROIBIDO
alucinar dados, inventar arquivos não editados ou adicionar texto
conversacional. Entregue APENAS o template preenchido.

**Regra de Prata:** O Handover é hipótese; o repositório é verdade. Toda
afirmação do Handover deve ser ancorada em saída de comando Git executada
nesta sessão (Seção 8). Dado não verificável é marcado
`[NÃO VERIFICADO NESTA SESSÃO]` — nunca inventado.

## 2. PARÂMETROS DE ENTRADA (INPUT)
- **CONTEXTO BASE:** Histórico da sessão + repositório local + remoto.
- **GATILHO:** `/handover`.

## 3. PADRÕES OBRIGATÓRIOS (CHECKLIST DE EXTRAÇÃO)

### A. Filtro de Realidade (DoD)
- Isole APENAS artefatos **commitados e validados pela IA Crítica**.
- Zonas air-gapped (`assets/svg_base/`, `assets/raw_references/`) são citadas
  apenas como referência de trabalho, NUNCA como entrega.

### B. Precisão de Produção
- Caminhos exatos (`docs/bible/...`, `scripts/...`, `assets/symbols/...`).
- Comandos exatos (git, Scour, Inkscape, gates OpSec).
- Versões exatas do ambiente; se desconhecidas, `[NÃO VERIFICADO]`.

### C. Rastreabilidade (CDRs)
- Decisões Criativas e Epistêmicas da sessão.
- Formato: *O que foi decidido? Qual filósofo/referência ancora? Qual o
  impacto na trama ou no pipeline?*
- Numeração continua o registro central (`docs/bible/cdrs.md`, se existir;
  senão, sequencial a partir do último handover).

### D. Travas Inegociáveis
Redeclarar sempre, em todo handover:
- **Trava 0:** Classificação Livre (zero conteúdo adulto/sexual/violência gráfica).
- **Lei do Esforço Produtivo:** Karl vence por dedução própria; IA não resolve por ele.
- **OpSec pós-Incidente 01:** nenhum raster (`*.png/jpg/jpeg/webp`) ou
  `assets/svg_base/` versionado; gate de raster em todo SVG pré-commit.
- **Regra do Incidente 02:** certeza alta de IA sobre Classificação Indicativa
  não é evidência; exige verificação adversarial independente antes do commit.
- **Pessoas reais:** nomes reais vivem apenas em `docs/referencias/`;
  na diegese, somente transmutações fictícias.

### E. Continuidade (Backlog)
- Pendências por Fase de Produção (0–4), como tarefas acionáveis.

### F. Coleta de Âncoras (OBRIGATÓRIA antes de escrever o Handover)
Executar e capturar saída literal (redirecionar se longa — ver Higiene):
`git fetch origin`; `git status --short`; `git log origin/main..HEAD --oneline`;
`git log --oneline -6`; `git ls-files`; gates OpSec (Seção 8).

## 4. PROTOCOLO DE EXECUÇÃO (TEMPLATE OBRIGATÓRIO)
Ao receber `/handover`, gere a saída ESTRITAMENTE no formato abaixo.
Não altere a estrutura dos títulos. Salve como `docs/handover_<AAAA-MM-DD>.md`,
commit `chore(repo): gerar context anchor de handover`, `git push origin main`.

# 📑 RELATÓRIO DE ESTADO DE PRODUÇÃO & HANDOVER (MANGÁ)

**Projeto:** Karl Sagan: A Vela no Cerrado
**Edição Atual:** [preencher]
**Pipeline:** SVG Híbrido (Inkscape [versão ou NÃO VERIFICADO] / Scour [idem]) + Git/GitHub
**Framework:** Mapa e Trilhos (IA Geradora / IA Crítica / Humano Árbitro)
**Data do Snapshot:** [AAAA-MM-DD]
**Status do Repositório:** [CLEAN (commit realizado) ou DIRTY (listar pendentes)]

---

## 0. PROTOCOLO DE INTEGRAÇÃO DE SESSÃO (OBRIGATÓRIO — IA RECEPTORA)
O Handover é hipótese; o repositório é verdade. Antes de qualquer produção:

### 0.1 Sync de Solo
```bash
git fetch origin
git status --short                      # esperado: clean
git log origin/main..HEAD --oneline     # esperado: VAZIO (local == remoto)
git log --oneline -6                    # comparar com Âncoras (Seção 8)
git ls-files                            # comparar com a lista esperada
```

### 0.2 Relatório de Delta (emitir antes de produzir)
| Âncora | Esperado (Handover) | Observado (repo) | Status |
|---|---|---|---|
| HEAD | [SHA] (+tolerância abaixo) | [SHA] | OK / DRIFT |
| Arquivos Bible | [N] | [N] | OK / DRIFT |
| Gates OpSec | VAZIO | [saída] | OK / DRIFT |

**Tolerância:** HEAD pode estar até 2 commits `chore(repo):` à frente do SHA
ancorado (commit do próprio handover + patch do PRM). Qualquer outro desvio
(arquivo ausente, SHA divergente fora da tolerância, gate não vazio) = DRIFT.

### 0.3 Regra de Bloqueio
Se qualquer linha = DRIFT: declarar
`INSUFICIENTE PARA PRODUÇÃO — delta: [lista]` e **não gerar artefatos** até o
Humano arbitrar. Se tudo OK: prosseguir citando o HEAD verificado na primeira
linha de toda entrega.

### 0.5 Higiene de Terminal (OBRIGATÓRIO)
1. **Editor:** `core.editor` = nano; fallback único `zed --wait`.
   Vim é proibido como editor default de operações interativas.
2. **Saída longa:** todo comando de diagnóstico com saída potencialmente longa
   (reflog, log --all, ls-files, status --ignored) é redirecionado:
   `git reflog > reflog_snapshot.txt`. A IA nunca solicita dump integral no
   terminal; solicita o arquivo ou o trecho relevante.
3. **Proteção:** snapshots `.txt` na raiz são cobertos por `/*.txt` no
   .gitignore — jamais versionados.

## 1. 🔒 TRAVAS E LEIS ATIVAS (RELER ANTES DE QUALQUER AÇÃO)
[Reproduzir integralmente o bloco D do checklist, com os gates literais:]
```text
gate-raster:  Select-String -Path <arquivo>.svg -Pattern "<image|base64" | Measure-Object  → Count: 0
gate-rasters: git ls-files | Select-String "svg_base|\.png|\.jpg|\.jpeg|\.txt"             → VAZIO
gate-image:   git grep -c "data:image" $(git rev-list --all) -- "*.svg"                    → VAZIO
```

## 2. 🎯 SUMÁRIO EXECUTIVO DA SESSÃO
*Resumo de 2–3 linhas do objetivo narrativo/técnico alcançado.*

### Status de Entrega (Definition of Done):
- [x] [Entrega validada 1]
- [x] [Entrega validada 2]

---

## 3. 🏛️ REGISTRO DE DECISÕES CRIATIVAS E EPISTÊMICAS (CDRs)
| ID | Decisão / Conceito | Base Filosófica | Impacto na Trama/Pipeline |
|:---|:---|:---|:---|
| **CDR-XX** | [Decisão] | [Sagan/Popper/Kant/Rawls/Sandel/Outro] | [Impacto] |

---

## 4. 📂 MAPA DE ARQUIVOS MODIFICADOS E ENTREGUES
```text
a-vela-no-cerrado/
├── docs/bible/[arquivo.md] - [CRIADO/MODIFICADO] - [Resumo]
├── scripts/[name_XX.md] - [AÇÃO] - [Resumo]
└── assets/symbols/[simbolo.svg] - [AÇÃO] - [Resumo + gate de raster: OK]
```

---

## 5. 🛠️ RUNBOOK OPERACIONAL (CONTINUIDADE TÉCNICA)
```bash
# Pendências locais
git status --short

# Gates de segurança (devem retornar VAZIO)
git ls-files | Select-String "svg_base|\.png|\.jpg|\.jpeg|\.txt"
git grep -c "data:image" $(git rev-list --all) -- "*.svg"

# Commit convencional (padrão do projeto)
git add [arquivos]
git commit -m "docs(bible)|feat(script)|fix(asset)|chore(repo): [mensagem]"
git push origin main

# Versões do ambiente (preencher ou marcar NÃO VERIFICADO)
inkscape --version
scour --version
```

---

## 6. 🗺️ MANIFESTO DE ESTADO (RASTREAMENTO DE ATIVOS)
| ID do Ativo | Descrição | Status | Destino |
|:---|:---|:---|:---|
| [SYM-00X] | [Settei/Símbolo] | [VALIDADO/PENDENTE/EM EXECUÇÃO/RESERVA] | [assets/symbols/...] |
| [SCRIPT-EDXX] | [Name da Edição] | [STATUS] | [scripts/...] |

---

## 7. 📋 BACKLOG DE PRODUÇÃO (PRÓXIMAS FASES)
### 🟡 FASE [N]: [Nome da Tarefa]
- **Arquivos Alvo:** [caminhos]
- **Escopo:** [Descrição técnica/narrativa de como implementar]

## 8. ÂNCORAS DE VERIFICAÇÃO (MACHINE-READABLE)
*Bloco obrigatório. Sem ele, o Handover é inválido. Preencher com saída
literal dos comandos da Seção 3.F.*

**HEAD esperado:** [SHA curto] — [mensagem do commit]
**git log --oneline -6:**
```text
[SHA] [mensagem]
...
```
**git ls-files (resumo por diretório):**
```text
docs/bible/: [N] — [lista de nomes]
docs/referencias/: [N] — [lista]
scripts/: [lista]
assets/symbols/: [lista]
docs/ (raiz): [lista]
```
**Gates OpSec (saída literal):**
```text
gate-rasters: VAZIO
gate-image: VAZIO
```

---

## 9. DIRETRIZ DE ALÍVIO DE JANELA (ANTI-PESO)
1. Este arquivo permanece versionado como `docs/handover_<AAAA-MM-DD>.md`.
2. A nova sessão inicia lendo **apenas** três artefatos: o handover mais
   recente, `docs/framework_adversarial.md` e a Seção 1 (Travas).
3. Histórico profundo só via `git log > log_snapshot.txt`, nunca no terminal.

## 5. REGRAS DE FECHAMENTO (GERADOR)
1. Nenhum texto conversacional antes ou depois do template.
2. Se o working tree estiver DIRTY, o Status do Repositório lista os pendentes
   explicitamente — nunca omite.
3. O commit do handover ocorre após o arquivo ser salvo; o SHA ancorado é o do
   HEAD anterior ao commit do próprio handover (a tolerância de 0.2 cobre isso).
