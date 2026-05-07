# Template: Produto / Negócio Local

Estrutura para negócios locais — clínicas, restaurantes, lojas, prestadores de serviço, academias, salões, pet shops, e qualquer negócio com presença física ou atendimento local.

---

## Contexto de Uso

Use este template quando o negócio for:
- Clínica (médica, odontológica, estética, fisioterapia)
- Restaurante, cafeteria, bar
- Loja física (moda, eletrônicos, artesanato)
- Serviço doméstico (encanador, eletricista, diarista)
- Academia, estúdio de pilates, yoga
- Salão de beleza, barbearia, nail art
- Imobiliária, construtora local
- Qualquer negócio com endereço físico

**Objetivo primário**: converter visitantes locais em clientes — agendamento, visita à loja, pedido ou contato.

---

## Princípios Específicos de Negócio Local

1. **Localização visível**: endereço, bairro ou cidade devem aparecer no hero
2. **Prova social local**: avaliações do Google são mais valiosas que depoimentos genéricos
3. **Galeria real**: fotos do espaço, produto ou serviço (não stock photos)
4. **CTA direto**: WhatsApp, agendamento online ou telefone — máxima facilidade
5. **Google Maps obrigatório**: facilitar a chegada física é parte da conversão

---

## Estrutura Completa

---

### Seção 1 — Hero

**Objetivo**: comunicar claramente o que é, onde fica e por que visitar.

**Widgets**:
```
[Flexbox — section-hero]
  direction: column, align: center (ou row para versão com foto)
  padding: 80–96px top/bottom
  background: foto real do espaço/produto com overlay

  ├── [Heading — overline]
  │   "[BAIRRO/CIDADE] · [TIPO DE NEGÓCIO]"
  │   ex: "VILA MADALENA · CLÍNICA DE ESTÉTICA"
  │
  ├── [Heading H1]
  │   "[O que você oferece] + [para quem / benefício]"
  │   ex: "Procedimentos a laser sem tempo de recuperação"
  │       "O melhor hambúrguer artesanal de Campinas"
  │       "Cortes e colorações premiadas em São Paulo"
  │
  ├── [Text-editor — subheadline]
  │   1–2 linhas com detalhe ou diferencial
  │
  ├── [Flexbox row — ctas]
  │   ├── [Button] "Agendar agora" / "Pedir pelo WhatsApp" / "Ver cardápio"
  │   └── [Button ghost] "Ver nossos serviços" / "Conhecer o espaço"
  │
  └── [Flexbox row — trust signals]
      ├── [Star-rating]
      └── [Text-editor] "★ 4.9 · 847 avaliações no Google"
```

**Variante com imagem lateral** (clínicas, serviços profissionais):
```
[Flexbox row, align: center]
├── [Flexbox column] (flex: 1) — copy + CTAs
└── [Image] (flex: 1) — foto do profissional ou do espaço
```

---

### Seção 2 — Avaliações do Google

**Objetivo**: prova social local imediata — avaliações reais do Google têm alto peso de confiança.

**Widgets**:
```
[Flexbox — section-ratings]
  direction: column, align: center, padding: 48px top/bottom
  background: surface

  ├── [Flexbox row, justify: center, align: center, gap: 48px]
  │   ├── [Flexbox column, align: center]
  │   │   ├── [Counter] — nota média (ex: 4.9)
  │   │   ├── [Star-rating]
  │   │   └── [Text-editor] "847 avaliações no Google"
  │   │
  │   └── [Flexbox column, align: center]
  │       ├── [Counter] — anos de mercado ou clientes atendidos
  │       └── [Text-editor] label contextual
  │
  └── [Testimonial-carousel] (opcional)
      Com avaliações reais do Google copie/coladas
```

---

### Seção 3 — Serviços / Produtos

**Objetivo**: clareza sobre o que está disponível e o que diferencia.

**Para clínicas e serviços** (com descrição):
```
[Flexbox — section-services]
  direction: column, padding: 80px top/bottom

  ├── [Heading H2] "Nossos serviços"
  │
  └── [Flexbox row, wrap, gap: 24px]
      └── [Icon-box × N]
          ícone + nome do serviço + descrição 1–2 linhas
          background: surface, padding: 24px, border-radius: 10px
```

**Para restaurantes e lojas** (com imagem):
```
└── [Flexbox row, wrap, gap: 24px]
    └── [Image-box × N]
        Foto do prato/produto + Nome + Preço (opcional)
```

**Para serviços com tabs** (academia, salão):
```
└── [Tabs]
    Tab 1 — Serviços Capilares
    Tab 2 — Coloração
    Tab 3 — Tratamentos
```

---

### Seção 4 — Benefícios / Diferenciais

**Objetivo**: responder "por que vocês ao invés do concorrente ao lado?".

**Widgets**:
```
[Flexbox — section-benefits]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading H2] "Por que nos escolher"
  │
  └── [Flexbox row, wrap, gap: 24px]
      └── [Icon-box × 4–6]
          Diferencial como título + explicação em 1–2 linhas

Exemplos de diferenciais por tipo:
Clínica:     "Profissionais certificados", "Equipamentos de última geração"
Restaurante: "Ingredientes frescos diariamente", "Sem conservantes"
Academia:    "Professores especializados", "Turmas reduzidas"
Salão:       "Produtos veganos e cruelty-free", "Agendamento online 24h"
```

---

### Seção 5 — Galeria

**Objetivo**: mostrar o espaço, produto ou resultado de forma visual e honesta.

**Widgets**:
```
[Flexbox — section-gallery]
  direction: column, padding: 80px top/bottom

  ├── [Heading H2] "Conheça nosso espaço" / "Nossos trabalhos" / "Nossos pratos"
  │
  └── [Gallery] — grade com 6–12 fotos reais
      Layout: justified ou masonry
      Hover: zoom sutil + ícone de lupa
      Lightbox: ativado
```

**Tipos de foto por negócio**:
- Clínica: ambiente, equipamentos, equipe, antes e depois
- Restaurante: pratos, ambiente interno, cozinha, eventos
- Salão: trabalhos realizados (cabelos, unhas, etc.), ambiente, equipe
- Academia: equipamentos, aulas, alunos, resultados

**Nota crítica**: fotos de stock genérico destroem credibilidade. Fotos reais, mesmo com celular, são sempre superiores.

---

### Seção 6 — Avaliações Textuais

**Objetivo**: prova social qualitativa com histórias reais de clientes locais.

**Widgets**:
```
[Flexbox — section-reviews]
  direction: column, padding: 80px top/bottom, background: surface

  ├── [Heading H2] "O que nossos clientes dizem"
  │
  └── [Testimonial-carousel]
      Cada item:
      - Foto real ou inicial do nome
      - Nome e bairro/cidade
      - Avaliação em estrelas
      - Depoimento com experiência específica
```

**Para negócios com muitas avaliações**: usar `add-reviews` para mostrar formato de grade, mais próximo do visual do Google.

---

### Seção 7 — Equipe / Profissionais

**Objetivo**: humanizar e construir confiança nos profissionais que vão atender.

**(Mais crítico para clínicas, salões, academias — menos necessário para restaurantes e lojas)**

**Widgets**:
```
[Flexbox — section-team]
  direction: column, align: center, padding: 80px top/bottom

  ├── [Heading H2] "Nossa equipe"
  │
  └── [Flexbox row, wrap, justify: center, gap: 32px]
      └── [Image-box × N]
          Foto profissional + Nome + Especialidade/Cargo
          Subtexto opcional: formação, certificações
```

---

### Seção 8 — Localização e Horários

**Objetivo**: facilitar ao máximo a chegada ao local.

**Widgets**:
```
[Flexbox — section-location]
  direction: row, align: flex-start, gap: 48px
  padding: 80px top/bottom

  ├── [Flexbox column — info] (flex: 1)
  │   ├── [Heading H2] "Como nos encontrar"
  │   │
  │   ├── [Icon-list]
  │   │   ├── 📍 Endereço completo com referência
  │   │   ├── 🕐 Horário de funcionamento por dia
  │   │   ├── 📞 Telefone / WhatsApp com link clicável
  │   │   └── 🅿️ Informação sobre estacionamento (se houver)
  │   │
  │   └── [Button] "Como chegar" (link Google Maps)
  │       ou [Button WhatsApp] "Falar pelo WhatsApp"
  │
  └── [Google-maps] (flex: 1)
      altura: 400px
      coordenadas do endereço exato
      tipo: roadmap
      zoom: 15
```

---

### Seção 9 — CTA Final / Agendamento

**Objetivo**: facilitar ao máximo o início do relacionamento.

**Para negócios com agendamento**:
```
[Flexbox — section-booking]
  direction: column, align: center, padding: 80px top/bottom
  background: primária da marca

  ├── [Heading H2] "Agende sua consulta" / "Reserve sua mesa" / "Marque seu horário"
  ├── [Text-editor] — 1 linha: facilidade e próximo passo
  │
  ├── [Button] "Agendar pelo WhatsApp"
  │   link: https://wa.me/55[numero]?text=[mensagem pré-preenchida]
  │
  └── [Text-editor] — "Ou ligue: (11) 9xxxx-xxxx"
```

**Para negócios com formulário de contato**:
```
[Flexbox row]
├── [Flexbox column — texto] (info + ícones de contato)
└── [Form] — Nome + Telefone + [campo específico] + Submit
```

**Para restaurantes**:
```
├── [Button] "Reservar mesa" — link para sistema de reserva
├── [Button] "Pedir pelo WhatsApp" — link WA
└── [Button] "Ver cardápio completo" — link para PDF ou página
```

---

## Notas de Design para Negócio Local

### Paletas por tipo de negócio

| Tipo | Tom | Paleta sugerida |
|------|-----|----------------|
| Clínica médica | Confiança, limpeza | Azul suave, branco, cinza claro |
| Clínica estética | Premium, elegância | Dourado, nude, branco |
| Restaurante/café | Calor, apetite | Terracota, caramelo, branco cru |
| Academia | Energia, força | Laranja/vermelho, preto, cinza |
| Salão de beleza | Sofisticação | Rosa, preto, dourado |
| Loja de moda | Estilo | Preto, branco, accent colorido |
| Pet shop | Diversão, cuidado | Verde, amarelo, azul |

### WhatsApp como CTA principal

Para negócios locais, WhatsApp frequentemente converte melhor que formulários. Use links diretos:

```
https://wa.me/5511999999999?text=Olá!%20Gostaria%20de%20agendar%20um%20horário.
```

O texto pré-preenchido reduz a fricção — o cliente só precisa clicar em enviar.

### Horários de funcionamento

Sempre visíveis — no footer e na seção de localização. Incluir:
- Dias da semana com horário
- Feriados (se diferente)
- "Atendimento por agendamento" quando aplicável

---

## Sequência de Construção MCP

```
1. detect-elementor-version
2. update-global-colors  (paleta do negócio)
3. update-global-typography  (legível, amigável)
4. create-page  (com header/footer ou elementor_canvas)

Seção 1: add-flexbox → add-heading × 2 + add-text-editor + add-button × 2 + add-star-rating
Seção 2: add-flexbox → add-counter × 2 + add-star-rating + add-testimonial-carousel
Seção 3: add-flexbox → add-icon-box × N  (ou add-image-box × N para comida/moda)
Seção 4: add-flexbox → add-icon-box × 4
Seção 5: add-flexbox → add-gallery
Seção 6: add-flexbox → add-testimonial-carousel  (ou add-reviews)
Seção 7: add-flexbox → add-image-box × N  (equipe — se relevante)
Seção 8: add-flexbox → add-icon-list + add-google-maps
Seção 9: add-flexbox → add-heading + add-text-editor + add-button

batch-update  (ajustes finais de cores, espaçamento, responsividade)
add-custom-css  (hover em galeria, estilo de botão WhatsApp, etc.)
get-page-structure  (verificação final)
```

---

## CSS de Botão WhatsApp

```css
.btn-whatsapp {
  background: #25D366;
  color: #ffffff;
  border-radius: 50px;
  padding: 14px 32px;
  font-weight: 600;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  transition: all 0.2s ease;
}

.btn-whatsapp:hover {
  background: #20b958;
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(37, 211, 102, 0.35);
}
```
