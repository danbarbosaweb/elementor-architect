# Template: Site Institucional

Estrutura para sites institucionais — empresas, escritórios, organizações e marcas que precisam construir credibilidade e gerar contato qualificado.

---

## Contexto de Uso

Use este template quando o objetivo for:
- Estabelecer presença digital profissional de uma empresa
- Construir credibilidade e confiança de marca
- Apresentar serviços e gerar pedidos de contato/orçamento
- Criar um hub central para uma marca consolidada

**Diferença da Landing Page**: sites institucionais têm múltiplos objetivos secundários (apresentar a empresa, mostrar serviços, humanizar a equipe) além do objetivo primário de gerar contato.

---

## Princípios Específicos de Institucional

1. **Credibilidade primeiro**: quem somos e por que confiar antes de qualquer venda
2. **Humanização**: rostos reais, histórias reais, valores genuínos
3. **Clareza de serviços**: o visitante precisa entender em 10 segundos o que você oferece
4. **Prova de mercado**: clientes, parceiros, tempo de atuação
5. **Contato fácil**: múltiplos canais de contato, formulário acessível

---

## Estrutura Completa

---

### Seção 1 — Hero

**Objetivo**: comunicar a proposta de valor da empresa com clareza e confiança.

**Widgets**:
```
[Flexbox — section-hero]
  direction: column, align: center (ou row para versão com imagem lateral)
  padding: 96px top/bottom
  background: imagem da empresa, do escritório, ou gradiente da marca

  ├── [Heading — overline] texto: "[CIDADE/REGIÃO] · DESDE [ANO]"
  │
  ├── [Heading H1]
  │   "Ajudamos [tipo de cliente] a [resultado concreto]"
  │   max-width: 700px, text-align: center
  │
  ├── [Text-editor — subheadline]
  │   1–2 linhas: o como e o diferencial
  │   max-width: 560px
  │
  └── [Flexbox row — ctas]
      ├── [Button] "Solicitar proposta" / "Falar com especialista"
      └── [Button ghost] "Conhecer nosso trabalho" / "Ver portfólio"
```

**Variante com imagem lateral** (mais humanizado):
```
[Flexbox row, align: center, gap: 64px]
├── [Flexbox column — text] (flex: 1) — overline + H1 + subheadline + CTAs
└── [Image] (flex: 1) — foto da equipe, do escritório ou do produto principal
```

---

### Seção 2 — Números e Credenciais

**Objetivo**: provar o tamanho e a experiência da empresa de forma objetiva.

**Widgets**:
```
[Flexbox — section-stats]
  direction: column, align: center, padding: 64px top/bottom
  background: surface

  └── [Flexbox row, justify: space-around, wrap]
      ├── [Counter] + [Heading H4] — "anos de mercado"
      ├── [Counter] + [Heading H4] — "clientes atendidos"
      ├── [Counter] + [Heading H4] — "projetos entregues"
      └── [Counter] + [Heading H4] — "profissionais na equipe"
```

**Escolha apenas métricas reais e verificáveis**. Não infle números — se for descoberto, destrói a credibilidade que esta seção deveria construir.

---

### Seção 3 — Sobre a Empresa

**Objetivo**: humanizar a marca, contar a origem e comunicar os valores.

**Widgets**:
```
[Flexbox — section-about]
  direction: row, align: center, gap: 64px
  padding: 80px top/bottom

  ├── [Image] (flex: 1, max-width: 480px)
  │   Foto: equipe, fundador, escritório, ou momento representativo
  │
  └── [Flexbox column — text] (flex: 1)
      ├── [Heading — overline] texto: "NOSSA HISTÓRIA"
      ├── [Heading H2]
      ├── [Text-editor] — 2–3 parágrafos:
      │   1. A origem (quando, quem, por quê foi fundada)
      │   2. A proposta (o que nos move, qual o propósito)
      │   3. O hoje (onde estamos, para onde vamos)
      └── [Icon-list] — 3–4 valores da empresa
          com ícones representativos
```

**Nota**: o "sobre" deve contar uma história, não listar características. "Fundada em 2015, a [empresa] nasceu da frustração com..." é mais humano do que "Somos uma empresa especializada em...".

---

### Seção 4 — Serviços

**Objetivo**: deixar absolutamente claro o que a empresa oferece.

**Opção A — Grid de cards** (para 4–8 serviços):
```
[Flexbox — section-services]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading — overline] texto: "O QUE FAZEMOS"
  ├── [Heading H2]
  ├── [Text-editor] subtítulo opcional
  │
  └── [Flexbox row, wrap, gap: 24px]
      └── [Icon-box × N]
          ícone relevante + nome do serviço + descrição em 2–3 linhas
          background: white, padding: 28px, border-radius: 12px
```

**Opção B — Tabs** (para serviços com mais detalhe):
```
└── [Tabs]
    Tab 1 — Serviço A: [imagem + descrição + benefícios + CTA]
    Tab 2 — Serviço B: [imagem + descrição + benefícios + CTA]
    Tab 3 — Serviço C: [imagem + descrição + benefícios + CTA]
```

---

### Seção 5 — Diferenciais

**Objetivo**: responder "por que vocês ao invés da concorrência?".

**Widgets**:
```
[Flexbox — section-differentials]
  direction: column, padding: 80px top/bottom

  ├── [Heading H2] "Por que nos escolher"
  │
  └── [Flexbox row, align: stretch, gap: 32px, wrap]
      └── [Flip-box × 3–4]
          Frente: ícone + título do diferencial
          Verso: explicação detalhada do por quê importa
```

**Alternativa sem flip-box** (mais conservador):
```
└── [Flexbox row, wrap, gap: 24px]
    └── [Icon-box × 4–6]
        Diferencial como título + explicação
```

---

### Seção 6 — Processo / Metodologia

**Objetivo**: reduzir incerteza mostrando como a empresa trabalha.

**Widgets**:
```
[Flexbox — section-process]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading H2] "Como trabalhamos"
  │
  └── [Icon-list numerado × 4–5 etapas]
      Cada etapa: número + nome da etapa + descrição em 1–2 linhas
```

**Alternativa visual** (para agências e consultorias):
```
[Flexbox row, gap: 0]
└── [Icon-box × N] com linha conectora via CSS
    cada box: número + etapa + descrição
```

---

### Seção 7 — Equipe

**Objetivo**: humanizar a empresa mostrando as pessoas por trás.

**Widgets**:
```
[Flexbox — section-team]
  direction: column, align: center, padding: 80px top/bottom

  ├── [Heading H2] "Nossa equipe"
  ├── [Text-editor] subtítulo humanizado
  │
  └── [Flexbox row, wrap, justify: center, gap: 32px]
      └── [Image-box × N]
          Foto profissional + Nome + Cargo
          max-width por card: 220px
          estilo: foto quadrada ou circular + overlay sutil
```

**Nota**: fotos profissionais reais são imprescindíveis. Fotos de celular com fundo bagunçado destroem a credibilidade que esta seção deveria construir. Se as fotos não estiverem prontas, omitir a seção temporariamente.

---

### Seção 8 — Clientes e Parceiros

**Objetivo**: prova social de autoridade por associação.

**Widgets**:
```
[Flexbox — section-clients]
  direction: column, align: center, padding: 64px top/bottom, background: surface

  ├── [Text-editor] "Empresas que confiam em nosso trabalho"
  │   13px, uppercase, letter-spacing, color: text-muted
  │
  └── [Flexbox row, justify: center, align: center, gap: 48px, wrap]
      └── [Image × N] — logos em grayscale, opacity: 0.6
```

**Se tiver depoimentos**: adicionar `testimonial-carousel` abaixo dos logos.

---

### Seção 9 — Contato

**Objetivo**: converter a visita em contato qualificado.

**Widgets**:
```
[Flexbox — section-contact]
  direction: row, align: flex-start, gap: 64px
  padding: 80px top/bottom

  ├── [Flexbox column — contact-info] (flex: 1)
  │   ├── [Heading H2] "Entre em contato"
  │   ├── [Text-editor] — 1–2 parágrafos sobre o próximo passo
  │   │
  │   ├── [Icon-list] — canais de contato
  │   │   ├── 📍 Endereço completo
  │   │   ├── 📞 Telefone / WhatsApp
  │   │   ├── 📧 E-mail
  │   │   └── 🕐 Horário de atendimento
  │   │
  │   └── [Google-maps]
  │       altura: 300px, coordenadas do endereço
  │
  └── [Flexbox column — form-side] (flex: 1)
      └── [Form]
          Campos: Nome + E-mail + Telefone + Assunto + Mensagem
          Submit: "Enviar mensagem" / "Solicitar contato"
```

---

## Notas de Design

### Paleta recomendada para institucional

| Perfil | Paleta |
|--------|--------|
| Corporativo/Financeiro | Azul marinho, cinza, branco |
| Saúde/Clínica | Verde-água, branco, cinza claro |
| Jurídico | Dourado, cinza escuro, branco |
| Criativo/Agência | Cores vibrantes, preto, branco |
| Tech/Consultoria | Azul, roxo, cinza |
| Educação | Azul, laranja ou verde, branco |

### Tipografia para institucional

Preferir famílias com boa legibilidade e credibilidade:
- Inter, Lato, Open Sans (moderno e limpo)
- Playfair Display + Inter (premium e editorial)
- Raleway, Poppins (profissional e atual)

### Sequência de cores de seção

```
Hero          → imagem ou gradient da marca
Stats         → surface
Sobre         → white/light
Serviços      → surface
Diferenciais  → white/light
Processo      → surface
Equipe        → white/light
Clientes      → surface
Contato       → white/light
```

---

## Sequência de Construção MCP

```
1. detect-elementor-version
2. update-global-colors  (paleta da identidade da empresa)
3. update-global-typography  (2 fontes escolhidas)
4. create-page  (com header/footer do tema, não elementor_canvas)

Seção 1: add-flexbox → add-heading × 2 → add-text-editor → add-button × 2
Seção 2: add-flexbox → add-counter × 4
Seção 3: add-flexbox → add-image + add-heading × 2 + add-text-editor + add-icon-list
Seção 4: add-flexbox → add-icon-box × N  (ou add-tabs)
Seção 5: add-flexbox → add-flip-box × 4  (ou add-icon-box × 4)
Seção 6: add-flexbox → add-icon-list × 4
Seção 7: add-flexbox → add-image-box × N
Seção 8: add-flexbox → add-image × N
Seção 9: add-flexbox → add-icon-list + add-google-maps + add-form

batch-update  (ajustes de cores, padding, tipografia)
add-custom-css  (hover states, imagens de equipe circular, etc.)
get-page-structure  (verificação)
```
