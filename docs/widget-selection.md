# Guia de Seleção de Widgets

Referência detalhada para decidir qual widget usar em cada situação, quando combiná-los e quando evitá-los. Este documento aprofunda a seção de Seleção de Widgets do SKILL.md.

---

## A Filosofia de Seleção

Antes de escolher um widget, responda:

> **Qual é o widget mais simples e previsível que resolve este problema?**

Simplicidade importa por três razões:

1. **Performance**: widgets simples carregam mais rápido
2. **Manutenção**: o cliente vai editar a página depois — widgets complexos criam confusão
3. **Previsibilidade**: widgets clássicos têm comportamento estável entre versões do Elementor

A tendência natural de quem conhece todos os widgets disponíveis é usar o widget "mais avançado" para cada situação. Resist. O heading clássico é melhor que o animated-heading para 90% dos títulos.

---

## Por que Evitar Atomic Widgets

Os widgets atômicos (add-atomic-*) do Elementor 4.0+ têm uma proposta interessante de arquitetura, mas apresentam problemas práticos:

**Problema 1 — Estilo imprevisível**
O mesmo valor de padding ou tamanho de fonte pode se comportar de forma diferente entre versões do Elementor. Atualizações mudam o comportamento sem aviso.

**Problema 2 — Curva de edição no Elementor Panel**
O cliente que vai editar a página após a entrega encontra uma interface diferente da que conhece. A experiência de edição é mais fragmentada.

**Problema 3 — Compatibilidade com temas**
Atomic widgets frequentemente conflitam com configurações globais de tema de forma menos previsível que os widgets clássicos.

**Quando usar atomic widgets:**
- Quando o cliente está num projeto novo que vai usar exclusivamente Elementor 4.0+
- Quando há razão técnica específica que os clássicos não resolvem
- Sempre com documentação do motivo da escolha

---

## Referência Completa por Categoria

### Containers e Layout

---

#### `add-flexbox` — Container Flexbox

**Prioridade**: Nível 1 — sempre preferido para layout.

**O que é**: container moderno baseado em CSS Flexbox. Controle total sobre direção, alinhamento, wrap e gap.

**Quando usar**: em todos os containers de seção e layout. É a estrutura base de toda a página.

**Configurações essenciais:**

| Configuração | Valor típico | Uso |
|-------------|-------------|-----|
| Direction | Row | Layout horizontal (cards lado a lado) |
| Direction | Column | Layout vertical (conteúdo empilhado) |
| Align items | Center | Centralizar verticalmente |
| Align items | Flex-start | Alinhar ao topo |
| Justify content | Center | Centralizar horizontalmente |
| Justify content | Space-between | Distribuir com espaço entre |
| Wrap | Wrap | Permite quebra de linha em múltiplos filhos |
| Gap | 24–32px | Espaçamento consistente entre filhos |

**Padrões comuns:**

```
Seção hero centralizada:
→ direction: column, align: center, justify: center
→ padding: 96px top/bottom
→ width: 1200px max-width

Grid de cards (3 colunas):
→ direction: row, wrap: wrap, gap: 24px
→ Cada card: flex: 1 1 calc(33% - 24px)

Seção com texto + imagem (50/50):
→ direction: row, align: center, gap: 64px
→ Filho texto: flex: 1
→ Filho imagem: flex: 1
```

---

#### `add-container` — Container Clássico

**Prioridade**: usar apenas por compatibilidade com projetos que já usam o sistema legado.

**Quando usar**: projetos em Elementor < 3.6 ou quando o cliente tem templates existentes no sistema legado.

**Nunca usar em**: projetos novos onde o flexbox está disponível.

---

#### `add-div-block` — Div Block

**Quando usar**: quando precisar de um container simples sem as opções de flexbox, para wrap semântico de conteúdo específico.

**Casos de uso reais**: raramente necessário. Na maioria dos casos, flexbox com direction column cumpre o mesmo papel.

---

### Conteúdo de Texto

---

#### `add-heading` — Heading

**Quando usar**: todos os títulos — H1, H2, H3, H4, e overlines.

**Configurações importantes:**

| Configuração | Recomendação |
|-------------|-------------|
| HTML Tag | Sempre selecionar o nível correto (H1 uma vez por página) |
| Tamanho | Configurar separado para desktop e mobile |
| Peso | 700–900 para H1/H2, 600 para H3/H4 |
| Line height | 1.05–1.15 para H1, 1.2–1.3 para H2 |

**Erros comuns:**
- Usar H2 onde deveria ser H3 por questão visual (use CSS para ajustar o tamanho sem mudar o nível)
- Copiar texto de heading para dentro de text-editor quando precisar de rich text

---

#### `add-text-editor` — Editor de Texto

**Quando usar**: parágrafos, listas formatadas, conteúdo com negrito/itálico, links no corpo do texto.

**Não usar quando**: é um título simples sem formatação especial (use heading).

**Configurações importantes:**

| Configuração | Recomendação |
|-------------|-------------|
| Font size | 16–18px desktop, 15–16px mobile |
| Line height | 1.6–1.7 |
| Max width | Configurar via CSS: max-width: 720px para textos longos |
| Color | Nunca #000000 puro |

**Dica de formatação:**
Parágrafos curtos (2–4 linhas) são mais escaneáveis. Separe ideias em parágrafos distintos. Use negrito com moderação — para o que realmente importa.

---

#### `add-button` — Botão

**Quando usar**: todos os CTAs isolados na página.

**Não usar quando**: o botão está dentro de um bloco call-to-action com background próprio (use o CTA widget).

**Configurações de CTA de alta conversão:**

| Configuração | Recomendação |
|-------------|-------------|
| Texto | Verbo de ação + contexto |
| Tipo | Filled para primário, outline para secundário |
| Cor | Contraste com o fundo da seção — não necessariamente a cor primária |
| Tamanho | Padding mínimo: 14px vertical, 28px horizontal (desktop) |
| Border radius | Consistente com o estilo do projeto (flat: 0–4px, arredondado: 8–12px, pill: 50px) |
| Mobile | Full-width em mobile para facilitar toque |

**Hover state essencial:** adicionar via Custom CSS:
```css
.elementor-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.15);
  transition: all 0.2s ease;
}
```

---

#### `add-icon-box` — Caixa de Ícone

**Quando usar**: cards de feature com ícone + título + texto. O widget mais versátil para seções de benefícios e serviços.

**Estrutura ideal de card:**
```
[Ícone — relevante ao conteúdo, não apenas decorativo]
[Título — o benefício em 3–6 palavras]
[Texto — explicação em 1–3 linhas, máximo]
```

**Configurações:**

| Configuração | Recomendação |
|-------------|-------------|
| Posição do ícone | Topo ou esquerda (nunca direita) |
| Tamanho do ícone | 40–56px |
| Cor do ícone | Cor primária ou accent |
| Background do card | Surface (fundo levemente diferente do fundo da seção) |
| Border radius do card | Consistente com o projeto |
| Padding interno | 24–32px |

**Em grade de 3 colunas**: configurar min-height igual para todos os cards via CSS para alinhar os bottoms.

---

#### `add-icon-list` — Lista com Ícones

**Quando usar**: listas de benefícios, features, itens incluídos, comparações.

**Vantagem sobre text-editor com lista**: cada item tem ícone configurável (checkmark, X, seta, etc.) e espaçamento independente.

**Configurações:**

| Configuração | Recomendação |
|-------------|-------------|
| Ícone | Check para benefícios, X para o que não inclui |
| Espaçamento entre itens | 12–16px |
| Tamanho do texto | 15–16px |
| Cor do ícone | Verde para check, vermelho para X |

---

#### `add-image-box` — Caixa de Imagem

**Quando usar**: cards que têm imagem como elemento principal + título + texto. Ideal para equipe, portfolio simples, serviços com imagem.

**Diferença do icon-box**: a imagem ocupa mais espaço e tem mais impacto visual. Use quando a foto/imagem é o elemento mais importante do card.

---

#### `add-html` — HTML Customizado

**Quando usar**: quando nenhum widget nativo consegue o resultado desejado. Embed de terceiros (Typeform, Calendly, etc.), componentes customizados.

**Cuidados:**
- Sempre escapar input de usuário se houver
- Verificar comportamento mobile
- Documentar o que o HTML faz (para quem vai manter)

---

### Widgets de Conversão

---

#### `add-call-to-action` — Call to Action

**Quando usar**: blocos CTA completos com background próprio (imagem ou cor), título e botão.

**Diferença do button**: o CTA widget é um bloco visual completo, não apenas um botão. Ideal para seções de CTA entre o meio e o final da página.

**Configurações típicas:**
- Background: imagem de alta qualidade ou gradiente da cor primária
- Overlay: 40–60% de opacidade escura sobre a imagem
- Título: cor branca, H2 size
- Botão: cor contrastante (ex: branco se fundo escuro)

---

#### `add-animated-headline` — Headline Animada

**Quando usar**: hero headlines onde há variações do produto/serviço que o visitante pode se identificar.

**Exemplo de uso efetivo:**
```
"A plataforma que [Rotação: aumenta suas vendas / automatiza seu marketing / reduz seus custos]"
```

**Quando não usar:**
- Apenas para efeito visual sem conteúdo diferente
- Quando a mensagem principal é única e clara (use heading simples)
- Em seções fora do hero (distrativo)

**Efeitos disponíveis**: typing, rotate, fade, slide, flip, zoom. O "rotate" (troca suave) é o mais legível.

---

#### `add-counter` — Contador

**Quando usar**: números de prova social que devem ser impactantes — alunos, clientes, anos, projetos, avaliações.

**Configurações de impacto:**

| Configuração | Recomendação |
|-------------|-------------|
| Número final | O número real, não exagerado |
| Prefixo/sufixo | "+" para "mais de X", "%" para percentuais |
| Duração da animação | 2–3 segundos |
| Tamanho do número | 48–72px, bold |
| Label abaixo | 14–16px, muted color |

**Estrutura recomendada para seção de counters:**
```
[Flexbox row, justify: space-around]
├── Counter 1: 2.847 / Alunos formados
├── Counter 2: 97% / Taxa de satisfação
├── Counter 3: 43 / Países alcançados
└── Counter 4: 8 anos / De experiência
```

---

#### `add-countdown` — Contagem Regressiva

**Quando usar**: apenas com data real de término da oferta.

**Configurações:**

| Configuração | Recomendação |
|-------------|-------------|
| Data | Data real absoluta |
| Labels | "Dias", "Horas", "Minutos", "Segundos" em português |
| Exibição | Compacto (sem moldura excessiva) |
| Ação ao terminar | Redirecionar ou esconder a seção |

**Nunca usar countdown "evergreen"** (que reinicia para cada visitante). A credibilidade vale mais do que a urgência falsa.

---

#### `add-price-table` — Tabela de Preços

**Quando usar**: seções de pricing com 2–4 planos comparáveis.

**Estrutura de pricing de alta conversão:**

```
[Plano Básico]     [PLANO PRO ★ Recomendado]     [Plano Enterprise]
R$97/mês           R$197/mês                       R$497/mês
[features]         [features + mais]               [features + tudo]
[CTA secundário]   [CTA primário destacado]        [CTA secundário]
```

**Regras:**
- Sempre ter um plano visualmente destacado (borda colorida, badge "recomendado")
- O plano destacado deve ser o que você quer vender — geralmente o intermediário
- Price anchoring: mostrar o plano mais caro primeiro (da esquerda para direita) para fazer o intermediário parecer razoável

---

#### `add-form` — Formulário

**Quando usar**: capturas de lead, formulários de contato, inscrições.

**Configurações críticas:**

| Configuração | Recomendação |
|-------------|-------------|
| Campos | Mínimo necessário — ver docs/conversion-principles.md |
| Placeholder | Explicativo, não apenas "Nome" |
| Botão submit | CTA de ação, não "Enviar" |
| Mensagem de sucesso | Clara sobre o próximo passo ("Enviamos um e-mail de confirmação") |
| Redirect após submit | Página de obrigado para rastrear conversão no Google Analytics |

---

### Prova Social

---

#### `add-testimonial-carousel` — Carrossel de Depoimentos

**Quando usar**: 3 ou mais depoimentos em sequência. O widget mais efetivo para prova social qualitativa.

**Configurações:**

| Configuração | Recomendação |
|-------------|-------------|
| Autoplay | Ligado, velocidade 5–6 segundos |
| Navigation arrows | Sempre visíveis |
| Slides visíveis | 1 centralizado (desktop), 1 (mobile) |
| Imagem | Foto real da pessoa, não avatar |

**Estrutura de depoimento forte:**
```
Foto real + Nome completo + Cargo/Cidade
"[Resultado específico. Antes eu [situação]. Depois [transformação concreta].]"
★★★★★
```

---

#### `add-reviews` — Grade de Avaliações

**Quando usar**: mostrar avaliações de plataforma (Google, produto) em formato de grade.

**Melhor para**: e-commerce, serviços locais, cursos com plataforma de review.

---

#### `add-star-rating` — Avaliação em Estrelas

**Quando usar**: rating isolado de produto ou serviço, geralmente próximo ao hero ou ao produto.

**Combinação efetiva:**
```
[star-rating: 4.9] + [text-editor: "1.247 avaliações"]
```

---

### Navegação e Interação

---

#### `add-tabs` e `add-nested-tabs` — Abas

**Quando usar tabs simples**: organizar features, serviços, ou categorias de conteúdo onde o visitante quer navegar entre opções paralelas.

**Quando usar nested-tabs**: quando as tabs têm subcategorias com conteúdo próprio. Use com moderação — aumenta complexidade cognitiva.

**Não usar quando**: o conteúdo seria melhor em uma lista ou accordion. Tabs esconderem conteúdo — se o visitante não clicar, não vê.

**Configurações:**

| Configuração | Recomendação |
|-------------|-------------|
| Posição das tabs | Topo (padrão) ou esquerda para listas longas |
| Tab ativa | Estilo claro — cor primária ou borda inferior |
| Mobile | Verificar que as tabs têm scroll horizontal ou são empilhadas |

---

#### `add-accordion` e `add-toggle` — FAQ

**accordion**: múltiplas abas podem estar abertas simultaneamente.

**toggle**: apenas uma resposta aberta por vez (mais simples cognitivamente para FAQ).

**Quando usar accordion**: quando as respostas são longas e o visitante pode querer comparar duas abertas ao mesmo tempo.

**Quando usar toggle**: para FAQ padrão onde o visitante vai ler uma resposta por vez.

**Configurações:**

| Configuração | Recomendação |
|-------------|-------------|
| Ícone | Seta ou + / − |
| Primeiro item | Aberto por padrão (a pergunta mais comum) |
| Espaçamento | 8–12px entre itens |
| Border | Apenas borda inferior sutil, não contorno completo |

---

## Combinações de Widgets por Objetivo

### Hero de alta conversão

```
[Flexbox column, centralizado, padding 96px]
├── [Heading — overline em uppercase]
├── [Heading H1 — headline principal]
├── [Text-editor — subheadline]
├── [Flexbox row — wrapper dos botões]
│   ├── [Button — CTA primário]
│   └── [Button — CTA secundário ghost]
└── [Text-editor — trust signal: ★★★★★ 4.9 · 2.847 usuários]
```

### Seção de features (3 colunas)

```
[Flexbox column, centralizado]
├── [Heading — overline]
├── [Heading H2 — título da seção]
├── [Text-editor — subtítulo opcional]
└── [Flexbox row, wrap, gap 24px]
    ├── [Icon-box — feature 1]
    ├── [Icon-box — feature 2]
    └── [Icon-box — feature 3]
```

### Seção de depoimentos

```
[Flexbox column]
├── [Heading H2 — título da seção]
└── [Testimonial-carousel]
    └── [Star-rating por item — se relevante]
```

### Seção de prova social numérica

```
[Flexbox row, justify space-around, wrap]
├── [Flexbox column, align center] → [Counter] + [Heading H4 label]
├── [Flexbox column, align center] → [Counter] + [Heading H4 label]
├── [Flexbox column, align center] → [Counter] + [Heading H4 label]
└── [Flexbox column, align center] → [Counter] + [Heading H4 label]
```

### CTA final com formulário

```
[Flexbox column, centralizado, background primário]
├── [Heading H2 — headline de fechamento]
├── [Text-editor — eliminar objeção final]
├── [Form — campos mínimos + CTA no submit]
└── [Icon-list — garantias e trust signals]
    ├── [✓ 30 dias de garantia]
    ├── [✓ Sem taxa de cancelamento]
    └── [✓ Suporte incluso]
```

---

## Impacto de Performance por Widget

| Widget | Impacto de carregamento | Observação |
|--------|------------------------|------------|
| `add-flexbox` | Mínimo | Apenas CSS nativo |
| `add-heading` | Mínimo | Apenas texto |
| `add-text-editor` | Mínimo | Apenas texto |
| `add-button` | Mínimo | CSS simples |
| `add-image` | Médio | Depende do tamanho da imagem |
| `add-icon-box` | Mínimo | Ícone SVG + texto |
| `add-counter` | Mínimo | Pequeno script de animação |
| `add-form` | Médio | Scripts de validação |
| `add-testimonial-carousel` | Médio | Script de carousel |
| `add-video` | Alto | Embed de vídeo (defer quando possível) |
| `add-google-maps` | Alto | API do Google Maps |
| `add-animated-headline` | Médio | Script de rotação |
| `add-countdown` | Médio | Script de contagem |
| `add-loop-grid` | Alto | Queries de banco de dados |
| `add-lottie` | Alto | Animação JSON pesada |

**Dica de performance**: widgets de mídia pesada (`add-video`, `add-google-maps`, `add-lottie`) devem ter lazy loading ativado. Para Google Maps, considere usar uma imagem estática do mapa com link para o Google Maps — carrega 100x mais rápido.
