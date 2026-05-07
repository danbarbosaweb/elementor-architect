# Template: Landing Page

Estrutura completa para landing pages de alta conversão — captura de leads ou venda direta. Este template é um ponto de partida. Adapte conforme o objetivo, referências e identidade do projeto.

---

## Contexto de Uso

Use este template quando o objetivo for:
- Capturar leads (email, WhatsApp, formulário)
- Vender um produto digital (curso, e-book, programa)
- Vender um serviço com foco em conversão única
- Lançamentos com prazo definido

**Não use este template para**: sites institucionais (ver `institutional.md`), SaaS (ver `saas-page.md`), portfolios de agência (ver `agency.md`).

---

## Princípios Desta Estrutura

1. **Uma única ação**: toda a página aponta para um único objetivo
2. **Narrativa progressiva**: cada seção prepara o terreno para a próxima
3. **Prova social cedo**: credibilidade logo após o hero
4. **Objeções tratadas**: FAQ e garantias eliminam o último atrito
5. **CTAs estratégicos**: hero, meio e final — nunca competindo

---

## Estrutura Completa

---

### Seção 1 — Hero

**Objetivo**: responder em 3 segundos: *"Isso é para mim? Vale meu tempo?"*

**Widgets**:
```
[Flexbox — section-hero]
  direction: column, align: center, padding: 96px top/bottom
  background: imagem ou gradiente da marca

  ├── [Heading — overline]
  │   tag: p, style: overline, uppercase, letter-spacing: 0.1em
  │   texto: "CURSO ONLINE · TURMA JULHO 2026" (contextualizador)
  │
  ├── [Heading H1 — headline principal]
  │   tamanho: 56–72px desktop / 36–44px mobile, weight: 800
  │   max-width: 800px, text-align: center
  │   texto: [resultado concreto] + [para quem] + [sem/em X]
  │
  ├── [Text-editor — subheadline]
  │   tamanho: 18–20px, color: text-muted, max-width: 600px
  │   texto: elimina a principal dúvida ou objeção do visitante
  │
  ├── [Flexbox — wrapper-ctas]
  │   direction: row, justify: center, gap: 16px, wrap: wrap
  │   │
  │   ├── [Button — CTA primário]
  │   │   texto: "Quero [resultado]" / "Garantir minha vaga"
  │   │   cor: contraste máximo com o fundo do hero
  │   │   tamanho: padding 18px 40px, font-size: 18px, weight: 600
  │   │
  │   └── [Button — CTA secundário] (opcional)
  │       style: ghost/outline
  │       texto: "Ver como funciona" / "Assistir apresentação"
  │
  └── [Text-editor — trust signal]
      texto: "★★★★★ 4.9 · 2.847 alunos · Desde 2019"
      tamanho: 14px, color: text-muted
```

**Variações do trust signal**:
- `"★★★★★ 4.9 de 1.200 avaliações"` — para produtos com avaliações
- `"Mais de 3.000 profissionais formados"` — para cursos
- `"47 empresas confiam"` — para B2B
- `"Como visto em: [logos]"` — para autoridade de mídia

**Design notes**:
- Se o background for imagem: overlay escuro 40–60% para legibilidade
- Headline em branco sobre background escuro OR texto escuro sobre background claro
- CTA deve ser a cor que mais contrasta na página — não necessariamente a primária

---

### Seção 2 — Social Proof Imediata

**Objetivo**: credibilidade instantânea antes de qualquer benefício ou explicação.

**Widgets**:
```
[Flexbox — section-social-proof]
  direction: column, align: center, padding: 48px top/bottom
  background: surface (tom mais escuro que o fundo principal)

  ├── [Text-editor — label acima dos logos]
  │   texto: "Empresas onde nossos alunos trabalham" (para cursos)
  │         "Empresas que confiam" (para B2B)
  │   tamanho: 13px, color: text-muted, uppercase, letter-spacing: 0.08em
  │
  └── [Flexbox — logos-container]
      direction: row, justify: center, align: center
      gap: 48px, wrap: wrap
      └── [Image × N] — logos em escala de cinza, opacity: 0.5–0.7
```

**Variante com números** (quando não tem logos):
```
[Flexbox row, justify: space-around]
├── [Counter] + [Heading H4 label] — "Alunos formados"
├── [Counter] + [Heading H4 label] — "Avaliação média"
├── [Counter] + [Heading H4 label] — "Anos de mercado"
└── [Counter] + [Heading H4 label] — "Países alcançados"
```

---

### Seção 3 — Problema

**Objetivo**: provar que você entende a dor do visitante. Criar identificação emocional.

**Widgets**:
```
[Flexbox — section-problem]
  direction: row, align: center, gap: 64px
  padding: 80px top/bottom
  (ou direction: column para versão mais simples)

  ├── [Flexbox column — text-side] (flex: 1)
  │   ├── [Heading — overline] texto: "VOCÊ JÁ SE SENTIU ASSIM?"
  │   ├── [Heading H2] texto: headline que nomeia a dor
  │   └── [Text-editor] — 3–4 parágrafos curtos descrevendo:
  │       1. A situação atual frustrante
  │       2. As tentativas que não funcionaram
  │       3. O custo de continuar assim
  │       4. A promessa de que existe uma saída
  │
  └── [Image] (flex: 1) — imagem que representa a frustração
      (opcional — pode ser seção apenas de texto)
```

**Nota**: a seção de problema pode usar formato de lista com `icon-list` (ícones de X vermelho) para itens de dor.

---

### Seção 4 — Solução

**Objetivo**: apresentar o produto/serviço como a resposta natural ao problema anterior.

**Widgets**:
```
[Flexbox — section-solution]
  direction: row, align: center, gap: 64px
  padding: 80px top/bottom
  background: surface

  ├── [Image] (flex: 1) — mockup, foto do produto, screenshot
  │
  └── [Flexbox column — text-side] (flex: 1)
      ├── [Heading — overline] texto: "A SOLUÇÃO"
      ├── [Heading H2] texto: nome do produto + promessa
      ├── [Text-editor] — explicação da proposta de valor em 2–3 parágrafos
      └── [Icon-list] — 3–5 pontos principais da solução
          com ícones de check verde
```

---

### Seção 5 — Benefícios

**Objetivo**: detalhar os resultados que o visitante vai obter. Features → Benefícios.

**Widgets**:
```
[Flexbox — section-benefits]
  direction: column, align: center, padding: 80px top/bottom

  ├── [Heading — overline] texto: "O QUE VOCÊ VAI CONQUISTAR"
  ├── [Heading H2] texto: título da seção orientado a resultado
  ├── [Text-editor] — subtítulo opcional (max-width: 600px)
  │
  └── [Flexbox — cards-grid]
      direction: row, wrap: wrap, gap: 24px, justify: center
      └── [Icon-box × 3–6] — um por benefício
          ícone + título (o benefício) + texto (como funciona)
          background: surface, border-radius: 12px, padding: 28px
```

**Nota sobre os cards**: cada card deve comunicar **um benefício**, não uma feature. Substituir "Aulas em vídeo HD" por "Aprenda no seu ritmo, de qualquer lugar".

---

### Seção 6 — Como Funciona

**Objetivo**: reduzir a fricção cognitiva mostrando que é simples começar.

**Opção A — Passos numerados** (para processos lineares):
```
[Flexbox — section-how-it-works]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading H2] texto: "Como funciona"
  │
  └── [Icon-list numerado × 3 passos]
      Passo 1: ação simples de início
      Passo 2: configuração ou onboarding
      Passo 3: resultado esperado
```

**Opção B — Tabs** (para produtos com múltiplos aspectos):
```
[Flexbox — section-how-it-works]
  └── [Tabs]
      Tab 1: Para iniciantes
      Tab 2: Para intermediários
      Tab 3: Para avançados
```

---

### Seção 7 — Resultados / Cases

**Objetivo**: prova quantitativa de que a solução funciona.

**Widgets**:
```
[Flexbox — section-results]
  direction: column, padding: 80px top/bottom

  ├── [Heading H2] texto: "Resultados reais"
  │
  ├── [Flexbox row — counters] (para números de impacto)
  │   [Counter] × 3–4: métricas com contexto
  │
  └── [Flexbox row — cases] (para casos de estudo)
      [Image-box × 2–3]: foto + nome + resultado
```

---

### Seção 8 — Depoimentos

**Objetivo**: prova social qualitativa. Histórias de transformação que o visitante se identifica.

**Widgets**:
```
[Flexbox — section-testimonials]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading — overline] texto: "O QUE NOSSOS ALUNOS DIZEM"
  ├── [Heading H2]
  │
  └── [Testimonial-carousel]
      Cada item: foto real + nome completo + cargo/cidade + depoimento com resultado
      Autoplay: 5s, navigation: visible
```

**Para 1–2 depoimentos em destaque**: usar `add-testimonial` individual ao invés do carousel.

---

### Seção 9 — FAQ

**Objetivo**: destruir as últimas objeções que impedem a conversão.

**Widgets**:
```
[Flexbox — section-faq]
  direction: column, align: center, padding: 80px top/bottom

  ├── [Heading H2] texto: "Perguntas frequentes"
  ├── [Text-editor] texto: "Ainda tem dúvidas? Fale conosco."
  │
  └── [Toggle × 6–10] — objeções reais do público
      Cada item: pergunta como título, resposta honesta e completa
```

**Perguntas de alta conversão para cursos/infoprodutos**:
- "E se eu não tiver tempo para as aulas?"
- "Isso funciona para iniciantes?"
- "Por quanto tempo tenho acesso?"
- "E se eu não ficar satisfeito?"
- "Preciso de algum equipamento ou software?"
- "Quando começa? Posso fazer no meu ritmo?"
- "Qual o suporte disponível?"
- "Vale a pena para minha área de atuação?"

---

### Seção 10 — CTA Final

**Objetivo**: fechar a conversão com eliminação de risco e reforço do resultado.

**Widgets**:
```
[Flexbox — section-cta-final]
  direction: column, align: center, padding: 96px top/bottom
  background: primária da marca (ou imagem com overlay)

  ├── [Heading — overline] texto: "COMECE HOJE"
  ├── [Heading H2] — reforça o resultado (diferente do headline do hero)
  ├── [Text-editor] — elimina o risco final: garantia, sem compromisso, etc.
  │
  ├── [Form] — campos mínimos + botão de submit como CTA
  │   (ou [Button] se o CTA é para outra página/checkout)
  │
  └── [Icon-list] — 3 trust signals
      ├── ✓ [Garantia de satisfação]
      ├── ✓ [Segurança de pagamento ou privacidade]
      └── ✓ [Facilidade de cancelamento ou acesso]
```

**Variante com urgência legítima**:
```
Adicionar entre o Text-editor e o Form:
└── [Countdown] — data real de encerramento da oferta
    texto abaixo: "Após essa data, o preço volta ao normal"
```

---

## Notas de Design para toda a Página

### Cores alternadas de seção

```
Seção 1 (Hero)          → background: imagem ou gradiente dark
Seção 2 (Social Proof)  → background: surface
Seção 3 (Problema)      → background: white/light
Seção 4 (Solução)       → background: surface
Seção 5 (Benefícios)    → background: white/light
Seção 6 (Como Funciona) → background: surface
Seção 7 (Resultados)    → background: white/light
Seção 8 (Depoimentos)   → background: surface
Seção 9 (FAQ)           → background: white/light
Seção 10 (CTA Final)    → background: primária (dark)
```

### Tipografia por elemento

| Elemento | Tamanho Desktop | Mobile | Weight |
|---------|----------------|--------|--------|
| H1 Hero | 60–72px | 38–44px | 800 |
| H2 Seção | 36–44px | 28–34px | 700 |
| Overline | 12–13px | 11–12px | 600, uppercase |
| Body | 17–18px | 15–16px | 400 |
| CTA button | 16–18px | 16px | 600 |

### CSS Custom Recomendado

```css
/* Separação visual entre seções */
.section-hero + .section-social-proof {
  border-top: 1px solid rgba(0,0,0,0.06);
}

/* Máx width para texto corrido */
.section-problem .elementor-text-editor,
.section-solution .elementor-text-editor {
  max-width: 600px;
}

/* Hover em botões CTA */
.elementor-button {
  transition: all 0.2s ease;
}
.elementor-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.15);
}

/* Cards de benefício com altura igual */
.section-benefits .elementor-icon-box-wrapper {
  height: 100%;
}
```

---

## Sequência de Construção MCP

```
1. detect-elementor-version
2. get-global-settings
3. update-global-colors  (paleta completa)
4. update-global-typography  (primária + secondary + text)
5. create-page  (template: elementor_canvas, status: draft)
6. update-page-settings  (padding: 0, hide title: true)

Para cada seção (1–10):
7. add-flexbox  (section container)
8. add-flexbox  (inner container se necessário)
9. add-heading  (overline)
10. add-heading (H1/H2 principal)
11. add-[widget]  (conteúdo específico)
...

12. batch-update  (ajustes de espaçamento e cores)
13. add-custom-css  (hover states, max-widths, detalhes)
14. get-page-structure  (verificação final)
```
