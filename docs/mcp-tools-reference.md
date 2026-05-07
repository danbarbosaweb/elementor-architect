# Referência das Ferramentas Elementor MCP

Referência rápida de todas as ferramentas disponíveis, organizadas por categoria de uso. Para cada ferramenta, inclui propósito, quando usar, parâmetros principais e notas práticas.

---

## Sequência Recomendada de Uso

Antes de consultar a referência individual, internalize a sequência correta:

```
DIAGNÓSTICO PRIMEIRO
→ detect-elementor-version
→ get-global-settings

DESIGN SYSTEM ANTES DOS WIDGETS
→ update-global-colors
→ update-global-typography

PÁGINA
→ list-pages → create-page (se novo)
→ update-page-settings (se necessário)

CONSTRUÇÃO (por seção)
→ add-flexbox → add-[widget]...

OTIMIZAÇÃO
→ batch-update (≥3 elementos)
→ add-custom-css

VERIFICAÇÃO
→ get-page-structure
```

---

## Diagnóstico e Configuração Global

---

### `elementor-mcp-detect-elementor-version`

**Propósito**: identificar a versão do Elementor instalada e o modo de construção recomendado.

**Quando usar**: **sempre primeiro**, antes de qualquer outra operação.

**O que retorna**:
- Versão do Elementor instalada
- Modo recomendado (flexbox containers ou legacy containers)
- Funcionalidades disponíveis na versão detectada

**Por que importa**: Elementor 3.6+ introduziu os containers flexbox. Versões anteriores usam o sistema de seções/colunas legado. A abordagem de construção é diferente.

**Notas práticas**:
- Se detectar versão < 3.6: usar `add-container` ao invés de `add-flexbox`
- Se detectar versão 3.6+: usar `add-flexbox` para tudo
- Se detectar versão 4.0+: atomic widgets disponíveis (mas ainda não são prioridade)

---

### `elementor-mcp-get-global-settings`

**Propósito**: verificar as configurações globais atuais da instalação (design system, tipografia, cores).

**Quando usar**: antes de `update-global-colors` e `update-global-typography` para ver o que já existe.

**O que retorna**: configurações de cores globais, tipografia global, breakpoints, configurações de container.

**Por que importa**: evita sobrescrever configurações existentes de um projeto em andamento.

---

### `elementor-mcp-update-global-colors`

**Propósito**: definir a paleta de cores global que todos os widgets herdam.

**Quando usar**: antes de construir qualquer widget, em projetos novos ou ao estabelecer um design system.

**Parâmetros principais**:
```
colors: [
  { id: "primary",    title: "Primary",    value: "#7c3aed" },
  { id: "secondary",  title: "Secondary",  value: "#ede9fe" },
  { id: "accent",     title: "Accent",     value: "#a78bfa" },
  { id: "text-dark",  title: "Text Dark",  value: "#0f172a" },
  { id: "text-muted", title: "Text Muted", value: "#64748b" },
  { id: "background", title: "Background", value: "#f8fafc" },
  { id: "surface",    title: "Surface",    value: "#f1f5f9" }
]
```

**Notas práticas**:
- IDs devem ser semânticos (não "color1", "color2")
- Definir o conjunto completo de uma vez — não em chamadas separadas
- Após definir, os widgets herdam esses valores ao usar "Global Color" no painel

---

### `elementor-mcp-update-global-typography`

**Propósito**: definir a escala tipográfica global.

**Quando usar**: antes de construir qualquer widget com texto.

**Parâmetros principais**:
```
typography: [
  {
    id: "primary",
    title: "Primary",
    font_family: "Inter",
    font_weight: "700",
    font_size: { desktop: "56", tablet: "40", mobile: "36", unit: "px" },
    line_height: { size: "1.1", unit: "em" }
  },
  {
    id: "secondary",
    title: "Secondary",
    font_family: "Inter",
    font_weight: "400",
    font_size: { desktop: "17", tablet: "16", mobile: "15", unit: "px" },
    line_height: { size: "1.65", unit: "em" }
  },
  {
    id: "text",
    title: "Text",
    font_family: "Inter",
    font_weight: "400",
    font_size: { desktop: "15", tablet: "15", mobile: "14", unit: "px" },
    line_height: { size: "1.6", unit: "em" }
  }
]
```

**Notas práticas**:
- "Primary" é usado para headlines (H1, H2)
- "Secondary" é usado para body text
- "Text" é usado para elementos menores (captions, labels)
- Os três cobrem 90% dos casos — adicione mais apenas se necessário

---

### `elementor-mcp-list-dynamic-tags`

**Propósito**: listar as tags dinâmicas disponíveis na instalação (requer Elementor Pro).

**Quando usar**: quando precisar de conteúdo dinâmico (CPT, ACF, meta fields).

---

### `elementor-mcp-set-dynamic-tag`

**Propósito**: vincular um elemento a uma tag dinâmica.

**Quando usar**: em projetos com Custom Post Types ou campos dinâmicos.

---

## Página e Estrutura

---

### `elementor-mcp-list-pages`

**Propósito**: listar todas as páginas/posts que têm o Elementor habilitado.

**Quando usar**: sempre antes de criar uma nova página — verificar se já existe.

**O que retorna**: lista de páginas com ID, título, slug, status.

---

### `elementor-mcp-create-page`

**Propósito**: criar uma nova página WordPress com o Elementor habilitado.

**Parâmetros principais**:
```
title: "Nome da Página"
slug: "nome-da-pagina"
status: "draft" | "publish"
template: "" (usar template do tema) | "elementor_canvas" (sem header/footer)
```

**Notas práticas**:
- Usar `elementor_canvas` para landing pages que não devem ter header/footer do tema
- Criar como "draft" primeiro, publicar após revisão
- O slug deve ser SEO-friendly (palavras-chave, sem caracteres especiais)

---

### `elementor-mcp-update-page-settings`

**Propósito**: atualizar configurações gerais da página (background, padding, layout).

**Parâmetros principais**:
```
page_id: [ID da página]
settings: {
  hide_title: true,            // esconder título do WordPress
  page_layout: "elementor_canvas",
  background_background: "classic",
  background_color: "#f8fafc",
  padding: { top: "0", right: "0", bottom: "0", left: "0" }
}
```

**Quando usar**: logo após criar a página, antes de adicionar conteúdo.

---

### `elementor-mcp-get-page-structure`

**Propósito**: retornar a árvore completa de elementos da página com IDs.

**Quando usar**:
- Antes de modificar uma página existente (para mapear os IDs)
- Após construir (verificação final)
- Quando precisar localizar um elemento específico

**O que retorna**: árvore aninhada de todos os elementos com ID, tipo, e filhos.

**Notas práticas**:
- Use para confirmar que a estrutura está correta antes de declarar conclusão
- Os IDs retornados são necessários para `update-element`, `move-element`, etc.

---

### `elementor-mcp-delete-page-content`

**Propósito**: apagar todo o conteúdo da página mantendo a página em si.

**Quando usar**: quando precisar reconstruir uma página do zero.

**Cuidado**: esta ação é irreversível. Confirmar com o usuário antes de executar.

---

### `elementor-mcp-export-page`

**Propósito**: exportar a página como template JSON.

**Quando usar**: antes de fazer alterações significativas em uma página existente (backup).

---

## Layout e Containers

---

### `elementor-mcp-add-flexbox`

**Propósito**: adicionar um container flexbox — a base de todo layout moderno.

**Parâmetros essenciais**:
```
page_id: [ID]
parent_id: null (para seção de primeiro nível) | [ID do pai]
settings: {
  // Layout
  flex_direction: "row" | "column",
  flex_wrap: "nowrap" | "wrap",
  align_items: "flex-start" | "center" | "flex-end" | "stretch",
  justify_content: "flex-start" | "center" | "flex-end" | "space-between",
  gap: { row: "24", column: "24", unit: "px" },

  // Dimensões
  content_width: "boxed",     // usa max-width
  width: { size: "1200", unit: "px" },  // max-width do conteúdo
  min_height: { size: "0", unit: "px" },

  // Espaçamento
  padding: {
    top: "80", right: "24", bottom: "80", left: "24",
    isLinked: false, unit: "px"
  },

  // Background
  background_background: "classic",
  background_color: "#ffffff",

  // CSS ID/Class (para manutenção)
  css_classes: "section-hero",
  _element_id: "section-hero"
}
```

**Padrões de uso frequente**:

```
Seção full-width:
→ parent_id: null
→ flex_direction: row, content_width: boxed, width: 1200px

Container interno de conteúdo:
→ parent_id: [ID da seção]
→ flex_direction: column, width: 100%

Grid de cards:
→ parent_id: [ID da seção]
→ flex_direction: row, flex_wrap: wrap, gap: 24px
```

---

### `elementor-mcp-update-container`

**Propósito**: atualizar configurações de um container existente.

**Parâmetros**: mesmos do add-flexbox, mais `element_id`.

---

### `elementor-mcp-get-container-schema`

**Propósito**: retornar todas as propriedades disponíveis para configurar um container.

**Quando usar**: quando precisar confirmar quais parâmetros estão disponíveis ou como são nomeados.

---

## Gerenciamento de Elementos

---

### `elementor-mcp-find-element`

**Propósito**: localizar um elemento por tipo ou ID sem percorrer toda a árvore manualmente.

**Parâmetros**:
```
page_id: [ID]
type: "heading" | "button" | etc.  // busca por tipo
element_id: "abc123"               // busca por ID específico
```

---

### `elementor-mcp-get-element-settings`

**Propósito**: retornar todas as configurações atuais de um elemento específico.

**Quando usar**: antes de `update-element` para ver as configurações atuais e modificar apenas o necessário.

---

### `elementor-mcp-update-element`

**Propósito**: atualizar qualquer propriedade de um elemento existente.

**Parâmetros**:
```
page_id: [ID]
element_id: [ID do elemento]
settings: {
  // apenas as propriedades que devem mudar
  title: "Novo título",
  font_size: { size: "48", unit: "px" }
}
```

**Notas práticas**:
- Só passar as propriedades que precisam mudar (não o objeto completo)
- Para 3+ elementos, usar `batch-update` ao invés de chamadas individuais

---

### `elementor-mcp-batch-update`

**Propósito**: atualizar múltiplos elementos em uma única chamada API.

**Quando usar**: sempre que houver 3 ou mais elementos a atualizar.

**Parâmetros**:
```
page_id: [ID]
updates: [
  {
    element_id: "id1",
    settings: { title: "Novo título" }
  },
  {
    element_id: "id2",
    settings: { background_color: "#7c3aed" }
  },
  {
    element_id: "id3",
    settings: { font_size: { size: "48", unit: "px" } }
  }
]
```

**Por que importa**: cada chamada individual ao MCP tem overhead. O batch-update reduz o número de chamadas e é mais eficiente.

---

### `elementor-mcp-move-element`

**Propósito**: mover um elemento de um container para outro.

**Parâmetros**:
```
page_id: [ID]
element_id: [ID do elemento a mover]
target_parent_id: [ID do novo container pai]
position: 0 | 1 | 2...  // posição dentro do pai
```

---

### `elementor-mcp-remove-element`

**Propósito**: remover um elemento da página.

**Cuidado**: verificar que o elemento correto está sendo removido antes de executar.

---

### `elementor-mcp-duplicate-element`

**Propósito**: duplicar um elemento existente com todas as suas configurações.

**Quando usar**: quando precisar de múltiplos elementos similares — duplicar e editar é mais rápido que criar do zero.

---

### `elementor-mcp-reorder-elements`

**Propósito**: reordenar os filhos dentro de um container.

**Parâmetros**:
```
page_id: [ID]
parent_id: [ID do container]
order: ["id1", "id2", "id3"]  // nova ordem dos IDs filhos
```

---

## Adição de Widgets

A lista completa de widgets disponíveis. Para cada um, o uso principal.

### Texto e Conteúdo

| Tool | Uso principal |
|------|--------------|
| `add-heading` | Todos os títulos H1–H4 e overlines |
| `add-text-editor` | Parágrafos, rich text, listas formatadas |
| `add-button` | CTAs isolados |
| `add-icon` | Ícone decorativo isolado (sem texto) |
| `add-icon-box` | Card com ícone + título + texto |
| `add-icon-list` | Lista com ícones (benefícios, features) |
| `add-image-box` | Card com imagem + título + texto |
| `add-alert` | Caixas de aviso ou destaque |
| `add-blockquote` | Citações destacadas |
| `add-text-path` | Texto em caminho SVG (decorativo) |
| `add-html` | HTML customizado, embeds |
| `add-shortcode` | Shortcodes WordPress |
| `add-spacer` | Ajuste fino de espaçamento |
| `add-divider` | Separadores visuais sutis |

### Mídia

| Tool | Uso principal |
|------|--------------|
| `add-image` | Imagens, fotos, ilustrações |
| `add-video` | Vídeos incorporados (YouTube, Vimeo, self-hosted) |
| `add-gallery` | Galerias de imagens |
| `add-image-carousel` | Carrossel de imagens |
| `add-media-carousel` | Carrossel de mídia mista |
| `add-lottie` | Animações Lottie JSON |
| `add-slides` | ~~Deprecated~~ — usar media-carousel |
| `add-google-maps` | Mapa do Google incorporado |
| `add-stock-image` | Imagens de banco gratuito |
| `add-search-images` | Busca de imagens na biblioteca |
| `add-sideload-image` | Carregar imagem externa para a biblioteca |
| `add-upload-svg-icon` | Upload de ícone SVG customizado |

### Conversão e Marketing

| Tool | Uso principal |
|------|--------------|
| `add-call-to-action` | Bloco CTA completo com background |
| `add-counter` | Números de impacto animados |
| `add-countdown` | Contagem regressiva (apenas datas reais) |
| `add-progress` | Barras de progresso |
| `add-progress-tracker` | Tracker de progresso multi-etapa |
| `add-animated-headline` | Headline com rotação de texto |
| `add-flip-box` | Card com frente/verso ao hover |
| `add-hotspot` | Pontos interativos em imagem |
| `add-price-list` | Lista de preços simples |
| `add-price-table` | Tabela de planos comparáveis |
| `add-form` | Formulários de captura (Elementor Pro) |
| `add-login` | Formulário de login (Elementor Pro) |

### Prova Social

| Tool | Uso principal |
|------|--------------|
| `add-testimonial` | 1–2 depoimentos individuais |
| `add-testimonial-carousel` | 3+ depoimentos em carrossel |
| `add-reviews` | Grade de avaliações |
| `add-star-rating` | Rating em estrelas isolado |
| `add-rating` | Widget de rating com votos |
| `add-social-icons` | Ícones de redes sociais |
| `add-share-buttons` | Botões de compartilhamento |

### Navegação e Interação

| Tool | Uso principal |
|------|--------------|
| `add-tabs` | Abas de conteúdo paralelo |
| `add-nested-tabs` | Abas com subcategorias |
| `add-accordion` | Conteúdo colapsável (múltiplos abertos) |
| `add-nested-accordion` | Accordion com subcategorias |
| `add-toggle` | FAQ (apenas um aberto por vez) |
| `add-nav-menu` | Menu de navegação |
| `add-menu-anchor` | Âncora de navegação interna |
| `add-table-of-contents` | Índice de conteúdo |
| `add-off-canvas` | Menu ou conteúdo off-canvas |
| `add-search` | Campo de busca |

### Blog e Conteúdo Dinâmico

| Tool | Uso principal |
|------|--------------|
| `add-posts-grid` | Grade de posts/CPT |
| `add-loop-grid` | Grade dinâmica com Loop (Elementor Pro) |
| `add-loop-carousel` | Carrossel dinâmico com Loop |
| `add-portfolio` | Grade de portfolio |
| `add-author-box` | Box de informações do autor |

### Templates

| Tool | Uso principal |
|------|--------------|
| `list-templates` | Listar templates salvos |
| `apply-template` | Aplicar template a uma página |
| `save-as-template` | Salvar seção/página como template |
| `import-template` | Importar template JSON |
| `create-theme-template` | Criar template de tema (header, footer) |
| `create-popup` | Criar popup Elementor (Pro) |
| `set-popup-settings` | Configurar comportamento do popup |
| `set-template-conditions` | Definir onde o template se aplica |

### Código e Customização

| Tool | Uso principal |
|------|--------------|
| `add-custom-css` | CSS global ou de elemento específico |
| `add-custom-js` | JavaScript customizado |
| `add-code-snippet` | Snippet de código (WP Code) |
| `add-code-highlight` | Bloco de código com highlight |
| `list-code-snippets` | Listar snippets cadastrados |

### Utilitários

| Tool | Uso principal |
|------|--------------|
| `add-widget` | Adicionar widget genérico por tipo |
| `update-widget` | Atualizar widget por tipo |
| `list-widgets` | Listar todos os widgets disponíveis |
| `get-widget-schema` | Ver schema de um widget específico |

---

## Padrões de Eficiência

### Regra do batch-update

Sempre que houver 3 ou mais atualizações:

```
❌ update-element (id1)
❌ update-element (id2)
❌ update-element (id3)

✅ batch-update ([id1, id2, id3])
```

### Sequência de diagnóstico antes de modificar

Antes de editar qualquer página existente:

```
1. get-page-structure → mapear toda a estrutura e IDs
2. find-element       → localizar o elemento específico
3. get-element-settings → ver configurações atuais
4. update-element    → modificar apenas o necessário
5. get-page-structure → confirmar o resultado
```

### Custom CSS: quando e como

O `add-custom-css` deve ser usado para:
- Hover states e transições
- Pseudo-elementos (::before, ::after)
- Ajustes de responsividade muito específicos
- Propriedades não disponíveis no painel do Elementor
- Animações CSS

**Não usar** para substituir configurações que o painel cobre — isso cria conflitos de manutenção.

```css
/* Exemplo: hover em botão */
.section-hero .elementor-button {
  transition: all 0.2s ease;
}
.section-hero .elementor-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(124, 58, 237, 0.3);
}

/* Exemplo: max-width em texto */
.section-features .elementor-text-editor {
  max-width: 720px;
  margin: 0 auto;
}
```
