# 🕯️ Karl Sagan: A Vela no Cerrado

[![Classificação Livre](https://img.shields.io/badge/Classificação-Livre_(All_Ages)-brightgreen.svg)](#-trava-0--diretriz-de-conteúdo)
[![Formato](https://img.shields.io/badge/Formato-SVG_Híbrido-orange.svg)](#-arquitetura-técnica-pipeline-svg-híbrido)
[![Licença](https://img.shields.io/badge/Licença-CC_BY--NC--SA_4.0-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Name_%231_Concluído-blueviolet.svg)](#-status-de-produção--roadmap)

> *"Onda é possibilidade. Bit é decisão. A vela acende onde a névoa fecha."*

Bem-vindo ao repositório oficial de **Karl Sagan: A Vela no Cerrado**, um projeto de mangá *shōnen* pedagógico e open-source que funde o método científico, filosofia epistêmica e ficção científica no bioma do Cerrado brasileiro (Porto Nacional e Miracema do Tocantins).

Este repositório atua como a **Ágora** do projeto: o local onde o código-fonte visual (arquivos SVG), os roteiros (*names*) e a documentação do universo são versionados e mantidos publicamente.

---

## 🔒 TRAVA 0 — Diretriz de Conteúdo (Permanente)

Este projeto opera sob a **Trava 0 de Classificação Indicativa Livre (All Ages)**:
*   **Zero conteúdo sexual ou adulto**, explícito ou implícito, em qualquer edição ou material derivado.
*   Conflito e intensidade restritos estritamente às esferas **intelectual, ética e emocional**.
*   Expressão de afeto limitada a conexões de companheirismo, respeito metodológico e cooperação.

---

## 📖 Sinopse

No interior do Tocantins, um adolescente afro-brasileiro herda um artefato analógico chamado **Kit Detector de Balelas** (a Vela). Para proteger a realidade de entidades conhecidas como **Pseudagens** — parasitas que se alimentam de crenças infalsificáveis e apagam evidências —, ele precisa atravessar as Doze Casas da Ágora. 

Ao seu lado está **Jehanne Ferrer**, portadora da lâmina da *Refutação*. Juntos, eles operam como um conversor de mão dupla: ela corta o que é falso (binário); ele mantém as hipóteses vivas até o teste empírico (analógico).

---

## 👥 Personagens Principais

| Personagem | Papel / Arquétipo | Registro / Elemento | Visual (Adequado ao Clima do Tocantins) |
| :--- | :--- | :--- | :--- |
| **Karl Sagan** (16 anos) | Protagonista. Porta o Kit Detector de Balelas. | **Vela** *(Analógico / Continuum)* | Camiseta de malha leve clara, bermuda de sarja/tactel, tênis de lona/chinelo. Lampião analógico a tiracolo. |
| **Jehanne Ferrer** (16 anos) | Cavaleira de Popper. Empunha a lâmina *Refutação*. | **Tocha** *(Binário / Falsificacionismo)* | Camiseta dry-fit UV clara, calça jeans leve ou shorts, tênis esportivo/sandália rasteira, trança longa. |

---

## 🧠 Sistema de Poder (Epistêmico)

Os combates neste universo são literais e intelectuais. A força de um personagem é medida em **Lúmen** (energia gerada quando uma proposição sobrevive a um teste empírico ou dedução axiomática).

*   **A Trava de Kant:** O limitador de dano universal. O Imperativo Categórico anula automaticamente qualquer técnica inimiga baseada em privilégio de exceção (*special pleading*).
*   **As Doze Casas da Ágora:** Progressão dos Cavaleiros do Método (*Euclides, Eratóstenes, Galileu, Occam, Popper, Kant, Noether, Heisenberg, Bohr, Schrödinger, Feynman e Sagan*).
*   **As Pseudagens (Inimigos):** Entidades como a *Névoa* (dúvida fabricada), *Terraplanor* (solipsismo), *Paleonauta* (apropriação histórica), *Diluidor* (falsa proporcionalidade) e *O Infalseável* (a certeza dogmática absoluta).

---

## ⚙️ Arquitetura Técnica: Pipeline SVG Híbrido

Este mangá não é desenhado em um fluxo raster tradicional (pixels). Ele é construído como código visual vetorial escalável:

1. **Modelagem de Ativos:** Geração de referências de pose/cenário e vetorização (*trace*) limpa em SVG.
2. **Reuso via Símbolos:** Personagens e objetos são instanciados via tags `<symbol>` e `<use>`, garantindo consistência absoluta de proporções.
3. **Composição Estruturada:** Montagem de painéis (*koma-wari*), balões (*fukidashi*) e onomatopeias (*kaki-moji*) em camadas estritas via **Inkscape**.

---

## 📂 Estrutura do Repositório

```text
📦 manga-a-vela-no-cerrado
 ┣ 📂 docs               # Bíblia do universo, regras e fichas de personagens (Settei)
 ┣ 📂 scripts            # Roteiros decupados em Full Script (Names) em Markdown
 ┣ 📂 assets
 ┃ ┣ 📂 symbols          # Biblioteca vetorial reutilizável (<symbol>: Karl, Jehanne, Itens)
 ┃ ┗ 📂 backgrounds      # Cenários vetorizados do Tocantins (Cerrado, Miracema)
 ┣ 📂 issues             # Edições compiladas em SVG e PDFs de leitura
 ┃ ┣ 📂 ed01_sinal_analogico
 ┃ ┗ 📂 ed02_a_estrada_que_mede
 ┗ 📜 README.md
```

---

## 📊 Status de Produção & Roadmap

- [x] **Concepção do Sistema Epistêmico & Bíblia Narrativa**
- [x] **Adequação Geoclimática do Design de Personagens (Tocantins)**
- [x] **Name #1: "Sinal Analógico"** (20 páginas decupadas em *Full Script*)
- [ ] **Settei Vetorial:** Fichas de proporção e símbolos base de Karl (#001) e Jehanne (#002)
- [ ] **Name #2: "A Estrada que Mede"** (A Casa I e a jornada a Miracema)
- [ ] **Renderização SVG da Edição #1**

---

## 📚 Matriz de Referências Bibliográficas

*   **Sagan, Carl (1995).** *The Demon-Haunted World: Science as a Candle in the Dark*. Random House.
*   **Popper, Karl (1959).** *The Logic of Scientific Discovery*. Hutchinson & Co.
*   **Kant, Immanuel (1785).** *Grundlegung zur Metaphysik der Sitten*.
*   **Euclides (c. 300 a.C.).** *Os Elementos* (Ed. T. L. Heath).
*   **Shannon, Claude E. (1948).** *A Mathematical Theory of Communication*. Bell System Technical Journal.
*   **Adams, Douglas (1979).** *The Hitchhiker's Guide to the Galaxy*. Pan Books.

---

## 📬 Contato e Comunicação

Projeto mantido por **Karl Sagan** (Autoficção / Pseudônimo).
*   **Discussões e Contribuições:** Utilize as [Issues do Repositório](https://github.com/karl-sagan/manga-a-vela-no-cerrado/issues) para sugerir melhorias ou apontar inconsistências metodológicas.
*   **E-mail de Contato:** `karl-sagan@tutamail.com`

---

## 📄 Licença

Todo o material literário, conceitual e vetorial deste repositório está protegido sob a licença **Creative Commons Atribuição-NãoComercial-CompartilhaIgual 4.0 Internacional (CC BY-NC-SA 4.0)**.
