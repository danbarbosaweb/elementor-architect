# Template: Página SaaS

Estrutura para páginas de produtos SaaS, aplicativos e ferramentas digitais. Foco em demonstrar valor, reduzir fricção de adoção e converter em trial ou demo.

---

## Contexto de Uso

Use este template quando o produto for:
- Software como serviço (SaaS)
- Aplicativo web ou mobile
- Ferramenta digital com plano de assinatura
- Plataforma com modelo freemium ou trial

**Diferença da Landing Page**: SaaS pages precisam **mostrar o produto** — não apenas descrever. O visitante precisa ver antes de decidir.

---

## Princípios Específicos de SaaS

1. **Demo is king**: mostrar o produto em ação vale mais do que qualquer copy
2. **Features por resultado**: organizar features pelo que o usuário conquista, não pelo que a ferramenta faz
3. **Segmentação por persona**: benefícios diferentes para perfis diferentes
4. **Pricing claro**: não esconder preços cria desconfiança em SaaS
5. **Redução de risco máxima**: trial gratuito, sem cartão de crédito, cancelamento fácil

---

## Estrutura Completa

---

### Seção 1 — Hero

**Objetivo**: comunicar o outcome do produto e capturar o interesse em 5 segundos.

**Widgets**:
```
[Flexbox — section-hero]
  direction: column, align: center, padding: 96px top/bottom
  background: gradiente tech ou imagem de produto com overlay

  ├── [Heading — overline] texto: "PARA [SEGMENTO/PERSONA]"
  │
  ├── [Animated-headline H1]
  │   texto fixo: "O software que "
  │   rotação: ["aumenta suas vendas", "automatiza sua operação",
  │             "reduz seu churn"]
  │   (ou use Heading H1 simples com uma mensagem forte)
  │
  ├── [Text-editor — subheadline]
  │   Descreve como o produto entrega o outcome
  │   Máximo 2 linhas. Max-width: 580px
  │
  ├── [Flexbox row — ctas-wrapper]
  │   ├── [Button] "Começar grátis" / "Testar por 14 dias"
  │   └── [Button ghost] "Ver demonstração" / "Assistir em 2 min"
  │
  ├── [Text-editor — friction reducer]
  │   "Sem cartão de crédito · Cancele quando quiser · 5 min para configurar"
  │   tamanho: 13px, color: text-muted
  │
  └── [Image] — screenshot ou mockup do produto
      Posição: logo abaixo dos CTAs, em destaque
      Estilo: browser frame, device mockup, ou print limpo
```

**Nota importante**: o mockup/screenshot do produto é **obrigatório** no hero de SaaS. Se não há imagem do produto, a página não converte.

---

### Seção 2 — Logos de Clientes

**Objetivo**: social proof B2B imediato — mostrar que empresas reconhecidas confiam.

**Widgets**:
```
[Flexbox — section-logos]
  direction: column, align: center, padding: 40px top/bottom
  background: surface

  ├── [Text-editor] texto: "Mais de 3.000 empresas confiam no [Produto]"
  │   tamanho: 14px, color: text-muted, text-align: center
  │
  └── [Flexbox row — logos-wrapper]
      justify: center, align: center, gap: 48px, wrap: wrap
      └── [Image × 6–8] — logos em grayscale, opacity: 0.6
```

**Se não tiver logos de empresas conhecidas**: use contador de usuários/empresas:
```
"2.847 equipes em 43 países usam [Produto]"
```

---

### Seção 3 — Features Principais

**Objetivo**: mostrar as capacidades do produto organizadas por resultado para o usuário.

**Opção A — Tabs por categoria** (para produtos com múltiplas áreas):
```
[Flexbox — section-features]
  direction: column, padding: 80px top/bottom

  ├── [Heading — overline] texto: "TUDO QUE VOCÊ PRECISA"
  ├── [Heading H2]
  │
  └── [Nested-tabs]
      Tab 1 — "Automatização"
        └── [Flexbox row]: [Text-content] + [Screenshot]
      Tab 2 — "Relatórios"
        └── [Flexbox row]: [Screenshot] + [Text-content]
      Tab 3 — "Integrações"
        └── [Flexbox row]: [Text-content] + [Screenshot]
```

**Opção B — Grid de icon-boxes** (para lista de features key):
```
└── [Flexbox row, wrap, gap 24px]
    └── [Icon-box × 6–9] — ícone + feature como resultado + 1 linha de descrição
```

**Estrutura de cada feature em Opção A**:
```
[Flexbox row, align: center, gap: 64px]
├── [Flexbox column — text] (flex: 1)
│   ├── [Heading H3]
│   ├── [Text-editor — 2–3 parágrafos]
│   └── [Icon-list] — 3–4 sub-features desta área
└── [Image] (flex: 1) — screenshot da feature em uso
```

---

### Seção 4 — Demo Visual

**Objetivo**: tornar o produto concreto. Mostrar funcionando é mais persuasivo que descrever.

**Opção A — Vídeo de demo**:
```
[Flexbox — section-demo]
  direction: column, align: center, padding: 80px top/bottom
  background: dark/surface

  ├── [Heading H2] "Veja [Produto] em ação"
  ├── [Text-editor] subtítulo curto
  └── [Video]
      Tipo: YouTube ou self-hosted
      Tamanho: máximo 960px de largura, aspect-ratio: 16:9
      Autoplay: off, controls: on
```

**Opção B — Screenshots animados ou em sequência**:
```
[Flexbox — section-demo]
  └── [Image-carousel] ou [Media-carousel]
      Cada frame: screenshot de uma etapa do produto
      Legenda: o que o usuário está vendo
```

**Opção C — Screenshot com hotspots**:
```
[Flexbox — section-demo]
  └── [Hotspot]
      Imagem de fundo: screenshot principal do produto
      Pontos: clicáveis, cada um abre um tooltip explicando o elemento
```

---

### Seção 5 — Benefícios por Persona

**Objetivo**: mostrar que o produto serve diferentes perfis de usuário.

**Widgets**:
```
[Flexbox — section-personas]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading H2] "Para cada tipo de equipe"
  │
  └── [Tabs]
      Tab 1 — "Para gestores"
        └── [Flexbox row]: benefícios específicos para gestores
      Tab 2 — "Para vendedores"
        └── [Flexbox row]: benefícios para vendedores
      Tab 3 — "Para operações"
        └── [Flexbox row]: benefícios para ops
```

**Estrutura de cada tab de persona**:
```
[Flexbox row, align: center, gap: 48px]
├── [Image] — persona usando o produto ou resultado visual
└── [Flexbox column]
    ├── [Heading H3] "Para [Cargo/Persona]"
    ├── [Text-editor] — 1 parágrafo sobre o problema desta persona
    └── [Icon-list]  — 4–5 benefícios específicos para esta persona
```

---

### Seção 6 — Pricing

**Objetivo**: clareza total sobre o custo. Pricing oculto gera desconfiança em SaaS.

**Widgets**:
```
[Flexbox — section-pricing]
  direction: column, align: center, padding: 80px top/bottom

  ├── [Heading H2] "Planos e preços"
  ├── [Text-editor] "Sem taxa de setup · Cancele quando quiser"
  │
  ├── [Toggle billing] (opcional — mensal/anual)
  │   Implementar via custom JS ou plugin
  │
  └── [Flexbox row — pricing-cards]
      gap: 24px, align: stretch
      ├── [Price-table — Básico]    (menor destaque)
      ├── [Price-table — Pro ★]    (MAIOR destaque — recomendado)
      └── [Price-table — Enterprise] (menor destaque)
```

**Estrutura de cada Price-table**:
```
[Price-table]
├── Nome do plano
├── Preço mensal/anual
├── Descrição curta da persona ideal
├── Lista de features incluídas (icon-list interno)
├── CTA button
└── Link "Ver comparação completa" (opcional)
```

**Regras do pricing**:
- Plano do meio sempre visualmente destacado (borda colorida, badge "Mais popular")
- Mostrar preço mensal E anual com desconto anual claramente indicado
- Incluir "Grátis por 14 dias" no plano Pro se houver trial
- Nota de sem cartão de crédito abaixo dos planos

---

### Seção 7 — Integrações (quando relevante)

**Objetivo**: mostrar que o produto funciona com as ferramentas que o visitante já usa.

**Widgets**:
```
[Flexbox — section-integrations]
  direction: column, align: center, padding: 64px top/bottom
  background: surface

  ├── [Heading H2] "Integra com suas ferramentas favoritas"
  │
  └── [Flexbox row, wrap, justify: center, gap: 24px]
      └── [Icon-box × N] — logo da integração + nome
          ou [Image × N] — logos em grade
```

---

### Seção 8 — Depoimentos

**Widgets**:
```
[Flexbox — section-testimonials]
  direction: column, align: center, padding: 80px top/bottom

  ├── [Heading H2]
  └── [Testimonial-carousel]
      Foco: depoimentos com métricas e resultados de negócio
      ("Reduzimos 3h de trabalho manual por dia")
```

---

### Seção 9 — FAQ

**Widgets**:
```
[Flexbox — section-faq]
  direction: column, align: center, padding: 80px top/bottom, background: surface

  ├── [Heading H2]
  └── [Toggle × 6–8]
```

**Perguntas de alta conversão para SaaS**:
- "Preciso de equipe técnica para implementar?"
- "Como funciona o trial gratuito?"
- "O que acontece quando o trial termina?"
- "Como faço para migrar meus dados atuais?"
- "Vocês oferecem suporte durante a implementação?"
- "Posso cancelar a qualquer momento?"
- "Existe contrato de fidelidade?"
- "Quais integrações estão disponíveis?"

---

### Seção 10 — CTA Final

**Widgets**:
```
[Flexbox — section-cta-final]
  direction: column, align: center, padding: 96px top/bottom
  background: gradiente primary

  ├── [Heading H2] "Comece seu trial gratuito agora"
  ├── [Text-editor] "14 dias grátis. Sem cartão de crédito."
  │
  ├── [Flexbox row — ctas]
  │   ├── [Button] "Começar grátis" (primário, branco)
  │   └── [Button ghost] "Falar com vendas" (para enterprise)
  │
  └── [Icon-list horizontal]
      ✓ Setup em 5 minutos · ✓ Sem cartão · ✓ Cancele quando quiser
```

---

## Notas de Design

### Identidade visual de SaaS

| Elemento | Recomendação |
|---------|-------------|
| Fontes | Inter, DM Sans, Sora (clean e técnico) |
| Cores | Azul, roxo ou teal (confiança e tecnologia) |
| Estilo | Flat, espaçoso, screenshots clean |
| Background | Dark hero, transições para light/surface |
| Imagens | Screenshots reais do produto, não ilustrações genéricas |

### Screenshots do produto

- Sempre mostrar o produto em uso real, não telas vazias
- Usar device frames (browser, laptop) para contextualizar
- Se o produto estiver em beta, preparar mockups de alta fidelidade

---

## Sequência de Construção MCP

```
1. detect-elementor-version
2. update-global-colors  (tech palette)
3. update-global-typography  (Inter ou DM Sans)
4. create-page  (elementor_canvas)

Seção 1: add-flexbox → add-animated-headline → add-text-editor
         → add-button × 2 → add-image (mockup)

Seção 2: add-flexbox → add-text-editor → add-image × N (logos)

Seção 3: add-flexbox → add-nested-tabs
         (dentro de cada tab: add-flexbox → add-heading + add-text-editor + add-icon-list + add-image)

Seção 4: add-flexbox → add-video (ou add-hotspot)

Seção 5: add-flexbox → add-tabs
         (dentro de cada tab: add-flexbox → add-image + add-icon-list)

Seção 6: add-flexbox → add-price-table × 3

Seção 7: add-flexbox → add-icon-box × N (integrações)

Seção 8: add-flexbox → add-testimonial-carousel

Seção 9: add-flexbox → add-toggle × 8

Seção 10: add-flexbox → add-heading → add-text-editor
          → add-button × 2 → add-icon-list

batch-update  (ajustes finais)
add-custom-css  (hover states, max-widths, mockup frames)
get-page-structure  (verificação)
```
