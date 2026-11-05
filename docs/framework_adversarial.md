# ⚙️ Framework Adversarial de Produção Vetorial (Mapa e Trilhos)

> **Base Teórica:** Adaptado do modelo de governança de IA "Mapa e Trilhos" (Daniel Dines) e metodologias de *Red Teaming*.
> **Objetivo:** Mitigar falhas cumulativas, perda de memória de sessão e alucinações em um projeto de mangá de longo prazo, utilizando um pipeline SVG Híbrido e versionamento Git.

---

## A DINÂMICA ADVERSARIAL (Os Atores)
O projeto opera sob uma triagem estrita para cada entrega:
1.  **IA Geradora (ex: Gemini):** Produz o código SVG bruto, os roteiros (*Names*) e as expansões de mundo.
2.  **IA Crítica (ex: Qwen / Auditoria de Prompt):** Ataca o artefato gerado buscando furos lógicos, violações da Trava 0, lixo XML e inconsistências com a Bíblia.
3.  **Humano (Karl Sagan / Autor):** Arbitra o debate, executa o traçado manual no Inkscape (garantindo o *Air-Gap* artístico) e assina o commit no GitHub.

---

## AS 5 FASES DE PRODUÇÃO SEQUENCIAL

### FASE 0: MAPA FUNDACIONAL (A Bíblia do Mangá)
*   **Objetivo:** Estabelecer a memória persistente (O "Mapa").
*   **Artefatos Determinísticos:** `README.md`, `docs/bible/` (Trava 0, Botânica do Cerrado, Resistência Cognitiva, Personagens Cinzas).
*   **Processo:** A IA Crítica testa se há contradições entre a filosofia (Sagan/Popper/Kant) e as mecânicas de mundo.
*   **Status Atual:** **[CONCLUÍDO E BLOQUEADO]**. Qualquer alteração aqui exige um commit `docs(bible):` com justificativa severa.

### FASE 1: ARQUITETURA DE ARCO (As Doze Casas)
*   **Objetivo:** Estruturar o embate epistêmico do capítulo.
*   **Processo Adversarial:**
    *   *Gerador:* Propõe qual *Pseudagem* será enfrentada e qual *Postura* será usada.
    *   *Crítico:* Testa contra a **Lei do Esforço Produtivo** (O protagonista pensou por si mesmo ou a IA facilitou?).
*   **Artefato:** Resumo do arco adicionado ao planejamento (`issues/`).

### FASE 2: ROTEIRO DECUPADO (*Name / Full Script*)
*   **Objetivo:** Escrever a planta arquitetônica da edição em Markdown.
*   **Processo Adversarial:**
    *   *Gerador:* Escreve o script página a página (Koma-wari, Fukidashi, Kaki-moji).
    *   *Crítico:* Ataca exposição excessiva, verifica se o cenário respeita o bioma (Cerrado) e audita a **Trava 0** (Zero conteúdo adulto/sexual).
*   **Artefato:** Arquivo `.md` na pasta `scripts/` (Ex: `name_01_sinal_analogico.md`).

### FASE 3: ENGENHARIA DE ATIVOS VISUAIS (*Settei* e Símbolos)
*   **Objetivo:** Criar os componentes vetoriais reutilizáveis.
*   **Processo Híbrido:**
    *   *Gerador:* Fornece referências raster ou código SVG estrutural.
    *   *Humano:* Realiza o traçado Bézier manual no Inkscape sobre fotos de referência (Opacidade 30%) para garantir fenótipos reais e limpos.
    *   *Crítico (Linter):* Verifica se o arquivo contém lixo proprietário (`inkscape:`, `sodipodi:`).
*   **Artefato:** Arquivos `<symbol>` salvos como **SVG Otimizado (Scour)** na pasta `assets/symbols/`.

### FASE 4: MONTAGEM E PUBLICAÇÃO (O *Trilho* do Git)
*   **Objetivo:** Consolidar a página, registrar a autoria e publicar.
*   **Processo:**
    *   *Humano:* Monta as páginas instanciando os símbolos (`<use>`) no Inkscape.
    *   *Consolidação:* O Humano executa o bloco de **Commit Automatizado** (Conventional Commits).
*   **Artefatos:** 
    *   Páginas finais em `issues/edXX/`.
    *   O `git log` atua como o **Log de Decisões Criativas** inalterável.
    *   Atualização do *Manifesto de Estado* no prompt da IA.

---

## PROTOCOLO DE MITIGAÇÃO DAS LIMITAÇÕES DA IA

| Limitação da IA | Mitigação no Framework (Os "Trilhos") |
| :--- | :--- |
| **Amnésia de Sessão** | Leitura obrigatória do `Manifesto de Estado` e da pasta `docs/bible/` no início de cada prompt. |
| **Falta de Accountability** | O Humano é o único com a chave SSH (`id_ed25519`) para assinar o `git push`. A IA sugere, o Humano commita. |
| **Alucinação Visual** | Proibição de geração raster direta para a obra final. Uso estrito de SVG modular (`<symbol>`) higienizado pelo Scour. |
| **Falha Cumulativa** | Separação estrita de pastas (`scripts/` vs `assets/`). Um erro no roteiro não corrompe o código vetorial. |
