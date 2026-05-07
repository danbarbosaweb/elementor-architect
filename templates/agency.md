# Template: Site de Agência

Estrutura para sites de agências de marketing, criação, desenvolvimento, branding e consultoria. Foco em demonstrar expertise criativa e técnica para gerar reuniões e orçamentos.

---

## Contexto de Uso

Use este template quando o cliente for:
- Agência de marketing digital
- Estúdio de design ou criação
- Agência de desenvolvimento web/apps
- Consultoria de branding ou estratégia
- Produtora de conteúdo ou vídeo

**Diferença do Institucional**: agências precisam **mostrar o trabalho**. Portfolio e resultados têm mais peso do que texto sobre a empresa.

---

## Princípios Específicos de Agência

1. **Show, don't tell**: o portfolio deve falar mais alto que qualquer copy
2. **Resultados com números**: resultados sem dados são promessas; com dados são prova
3. **Processo transparente**: mostrar como a agência trabalha cria confiança antes da reunião
4. **Personalidade de marca**: agências vendem ponto de vista — o site deve ter voz e estética próprias
5. **Fricção mínima para reunião**: o objetivo é uma reunião/briefing, não uma venda imediata

---

## Estrutura Completa

---

### Seção 1 — Hero

**Objetivo**: capturar atenção com impacto visual e comunicar o resultado que a agência entrega.

**Variante A — Hero com vídeo de fundo** (alta impacto):
```
[Flexbox — section-hero]
  direction: column, align: center, padding: 96px top/bottom
  background: vídeo (reel da agência) com overlay 50–70% escuro

  ├── [Heading — overline] texto: "[ESPECIALIDADE] · DESDE [ANO]"
  ├── [Heading H1] — resultado tangível, não descrição de serviço
  │   "Transformamos marcas que querem ser lembradas"
  │   "Resultados reais para empresas que querem crescer"
  ├── [Text-editor] — 1–2 linhas de suporte
  └── [Button] "Agendar reunião" / "Ver nosso trabalho"
```

**Variante B — Hero texto + imagem** (mais direto):
```
[Flexbox row, align: center, gap: 64px]
├── [Flexbox column] (flex: 1)
│   ├── [Heading — overline]
│   ├── [Heading H1]
│   ├── [Text-editor]
│   └── [Flexbox row]: [Button CTA] + [Button ghost "Ver portfólio"]
└── [Image] (flex: 1)
    Melhor projeto recente ou colagem de trabalhos
```

**Note sobre o H1 de agência**: nunca "Somos uma agência de marketing digital". Sempre o resultado para o cliente: "Transformamos [tipo de empresa] em marcas que vendem".

---

### Seção 2 — Clientes e Números

**Objetivo**: credibilidade imediata via nomes conhecidos e métricas de impacto.

**Widgets**:
```
[Flexbox — section-social-proof]
  direction: column, padding: 64px top/bottom, background: surface

  ├── [Text-editor] "Marcas que confiam no nosso trabalho"

  ├── [Flexbox row — logos]
  │   [Image × 6–10] — logos em grayscale
  │
  └── [Flexbox row — numbers] (opcional, abaixo dos logos)
      ├── [Counter] + [H4] — "projetos entregues"
      ├── [Counter] + [H4] — "anos de mercado"
      ├── [Counter] + [H4] — "clientes satisfeitos"
      └── [Counter] + [H4] — "países atendidos"
```

---

### Seção 3 — Portfolio

**Objetivo**: o coração do site de agência. Mostrar a qualidade e variedade do trabalho.

**Opção A — Grid de projetos** (visual, impactante):
```
[Flexbox — section-portfolio]
  direction: column, padding: 80px top/bottom

  ├── [Heading — overline] "PROJETOS SELECIONADOS"
  ├── [Heading H2]
  │
  └── [Gallery] ou [Loop-grid] — grade de projetos
      Layout: masonry ou grid uniforme
      Cada item: imagem do projeto + hover com nome + categoria
```

**Opção B — Casos em destaque** (narrativa, mais vendedor):
```
└── [Flexbox column, gap: 64px]
    └── [Flexbox row, align: center, gap: 48px] × 2–3 casos
        ├── [Image] (flex: 1) — imagem do projeto
        └── [Flexbox column] (flex: 1)
            ├── [Heading — overline] categoria do projeto
            ├── [Heading H3] nome do cliente / projeto
            ├── [Text-editor] desafio + solução em 2 parágrafos
            ├── [Icon-list] — 2–3 resultados com números
            └── [Button ghost] "Ver case completo"
```

**Regra do portfolio**: mostre apenas o melhor trabalho. 5 projetos excelentes > 20 projetos mediocres.

---

### Seção 4 — Serviços

**Objetivo**: clareza sobre o que a agência oferece e para qual resultado.

**Widgets**:
```
[Flexbox — section-services]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading H2]
  │
  └── [Tabs] — uma tab por área de serviço
      Tab 1 — Estratégia: [conteúdo + imagem]
      Tab 2 — Criação: [conteúdo + imagem]
      Tab 3 — Performance: [conteúdo + imagem]
      Tab 4 — Tecnologia: [conteúdo + imagem]
```

**Estrutura de cada tab de serviço**:
```
[Flexbox row, align: center, gap: 48px]
├── [Flexbox column] (flex: 1)
│   ├── [Heading H3] nome do serviço
│   ├── [Text-editor] o que inclui e para quem é
│   ├── [Icon-list] — entregas específicas
│   └── [Button ghost] "Saber mais" (link para página de serviço)
└── [Image] (flex: 1) — exemplo visual ou mockup do serviço
```

---

### Seção 5 — Resultados

**Objetivo**: prova quantitativa de que a agência gera resultado real, não apenas entregáveis.

**Widgets**:
```
[Flexbox — section-results]
  direction: column, padding: 80px top/bottom

  ├── [Heading H2] "Resultados que valem a conversa"
  │
  └── [Flexbox row, wrap, gap: 32px]
      └── [Image-box × 2–3] — mini cases
          Imagem do projeto + cliente + métrica principal
          ex: "300% de aumento em tráfego orgânico em 6 meses"
```

**Formato alternativo — Counters contextuais**:
```
[Flexbox row, justify: space-around]
├── Counter "847" + label "Posts publicados"
├── Counter "3.2M" + label "Impressões geradas"
├── Counter "127%" + label "Crescimento médio de leads"
└── Counter "98%" + label "Taxa de retenção de clientes"
```

---

### Seção 6 — Processo

**Objetivo**: reduzir a ansiedade do prospect mostrando como é trabalhar com a agência.

**Widgets**:
```
[Flexbox — section-process]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading H2] "Como trabalhamos"
  ├── [Text-editor] — 1 parágrafo sobre a metodologia
  │
  └── [Flexbox row, gap: 0, align: flex-start]
      └── [Flexbox column × 4–5 etapas] com linha conectora via CSS
          Cada etapa: número em destaque + nome + descrição em 2 linhas
```

**Etapas típicas de agência criativa**:
1. **Briefing** — entender o desafio e os objetivos
2. **Imersão** — pesquisa de mercado, concorrência e público
3. **Estratégia** — proposta de posicionamento e abordagem
4. **Criação** — desenvolvimento das peças e soluções
5. **Entrega e análise** — implementação e medição de resultados

---

### Seção 7 — Depoimentos

**Widgets**:
```
[Flexbox — section-testimonials]
  direction: column, padding: 80px top/bottom

  ├── [Heading H2]
  └── [Testimonial-carousel]
      Foco em: ROI, transformação de marca, facilidade de trabalhar com a agência
```

---

### Seção 8 — CTA — Agendar Reunião

**Objetivo**: converter interesse em ação concreta — uma reunião, não uma venda.

**Widgets**:
```
[Flexbox — section-cta]
  direction: column (ou row em desktop), align: center
  padding: 80px top/bottom
  background: primária da marca

  ├── [Heading H2] "Pronto para transformar sua marca?"
  │   (ou: "Vamos conversar sobre seu projeto?")
  ├── [Text-editor] — 1–2 linhas sobre como funciona a reunião inicial
  │   "Uma conversa de 30 minutos. Sem compromisso. Sem script de vendas."
  │
  └── [Button] "Agendar reunião gratuita"
      Pode linkar para Calendly, formulário ou WhatsApp
```

**Variante com formulário**:
```
[Flexbox row, align: flex-start, gap: 64px]
├── [Flexbox column] (texto + bullet points do que vai acontecer)
└── [Form] — Nome + E-mail + Empresa + "Me conte seu desafio" + Submit
```

---

## Notas de Design para Agências

### Identidade visual de agência

O site da agência é a própria vitrine do trabalho criativo. Deve ter:

| Aspecto | Orientação |
|---------|-----------|
| Personalidade | Forte e distinta — evitar genérico |
| Cor | Paleta própria e reconhecível |
| Tipografia | Escolha curatorial, não padrão |
| Imagens | Qualidade máxima, sem stock genérico |
| Espaçamento | Generoso — comunica sofisticação |
| Hover | Efeitos sutis de hover em imagens de portfolio |

### Hover em imagens de portfolio

```css
.portfolio-item {
  overflow: hidden;
  border-radius: 12px;
}

.portfolio-item img {
  transition: transform 0.4s ease;
}

.portfolio-item:hover img {
  transform: scale(1.04);
}

.portfolio-item .overlay {
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.6);
  opacity: 0;
  transition: opacity 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.portfolio-item:hover .overlay {
  opacity: 1;
}
```

---

## Sequência de Construção MCP

```
1. detect-elementor-version
2. update-global-colors  (paleta forte da agência)
3. update-global-typography  (escolha curatorial — 2 fontes)
4. create-page  (geralmente com header/footer customizado)

Seção 1: add-flexbox → add-video (reel) + add-heading × 2 + add-text-editor + add-button
Seção 2: add-flexbox → add-image × N (logos) + add-counter × 4
Seção 3: add-flexbox → add-gallery  (ou add-loop-grid se CPT)
Seção 4: add-flexbox → add-tabs
Seção 5: add-flexbox → add-image-box × 3 (mini cases)
Seção 6: add-flexbox → add-icon-list numerado × 5
Seção 7: add-flexbox → add-testimonial-carousel
Seção 8: add-flexbox → add-heading + add-text-editor + add-button

batch-update
add-custom-css  (hover em portfolio, animações, efeitos)
get-page-structure
```
