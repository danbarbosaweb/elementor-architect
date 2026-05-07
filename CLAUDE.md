# elementor-architect

## O Que É Este Projeto

`elementor-architect` é uma skill para Claude Code que funciona como um arquiteto inteligente de páginas Elementor. Ela combina UI Design, UX, CRO, estratégia e execução técnica em um único comando: `/elementor-architect`.

A skill não apenas executa ferramentas do Elementor MCP — ela planeja estruturas, analisa referências, define hierarquia visual, estratégia de conversão, sistema de design e toma decisões arquiteturais embasadas. É **opinativa** por design: questiona soluções ruins e propõe alternativas melhores.

---

## Estrutura do Projeto

```
elementor-architect/
│
├── CLAUDE.md                    ← Este arquivo (instruções para Claude)
├── README.md                    ← Documentação pública (GitHub)
│
├── skill/
│   └── SKILL.md                 ← Fonte da skill (cópia do arquivo instalado)
│
├── docs/                        ← Documentação técnica de suporte
│   ├── overview.md              ← Como a skill funciona internamente
│   ├── conversion-principles.md ← Playbook de CRO completo
│   ├── ux-principles.md         ← Princípios UX aplicados ao Elementor
│   ├── widget-selection.md      ← Guia detalhado de seleção de widgets
│   └── mcp-tools-reference.md  ← Referência rápida das ferramentas MCP
│
└── templates/                   ← Estruturas de página prontas para uso
    ├── landing-page.md          ← Template de Landing Page
    ├── saas-page.md             ← Template de página SaaS
    ├── institutional.md         ← Template de site institucional
    ├── agency.md                ← Template de site de agência
    └── local-business.md       ← Template de produto/negócio local
```

---

## Dois Destinos do SKILL.md

O arquivo principal da skill existe em **dois lugares** com conteúdo idêntico:

| Local | Propósito |
|-------|-----------|
| `skill/SKILL.md` | Fonte versionada no repositório (editável aqui) |
| `C:\Users\Pc\.claude\skills\elementor-architect\SKILL.md` | Skill instalada e ativa no Claude Code |

**Regra importante:** sempre que `skill/SKILL.md` for modificado neste repositório, copie o conteúdo atualizado para o arquivo instalado em `~/.claude/skills/elementor-architect/SKILL.md`. Os dois arquivos devem estar sempre em sincronia.

---

## Como Testar a Skill

### Ativação básica

1. Abra o Claude Code em qualquer diretório
2. Digite: `/elementor-architect`
3. A skill deve se apresentar e iniciar o fluxo de discovery

### Testes recomendados por cenário

| Cenário | O que validar |
|---------|--------------|
| Landing Page simples | Discovery completo + proposta de arquitetura |
| Análise de referência (URL) | Análise crítica de estrutura, hierarquia e conversão |
| Análise de screenshot | Identificação de paleta, tipografia e problemas |
| Construção com MCP | Sequência correta de chamadas, design system antes dos widgets |
| Página já existente | Uso de get-page-structure antes de qualquer modificação |

### Verificações de qualidade pós-build

Após uma construção, verifique:
- `elementor-mcp-get-page-structure` retorna estrutura correta
- Todos os containers são flexbox
- Design system global foi configurado antes dos widgets
- Custom CSS foi adicionado onde necessário

---

## Como Contribuir com a Skill

### Tipos de melhoria aceitos

- **Novos tipos de página**: adicionar estratégia para e-commerce, portal, blog, etc.
- **Novos princípios**: CRO, acessibilidade, performance, internacionalização
- **Exemplos reais**: casos de uso documentados e testados
- **Refinamento de anti-padrões**: novos padrões a evitar identificados em uso real
- **Templates**: novas estruturas de página em `templates/`

### Processo de atualização da skill

1. Edite `skill/SKILL.md` neste repositório
2. Teste as mudanças copiando para `~/.claude/skills/elementor-architect/SKILL.md`
3. Valide com pelo menos 2 cenários diferentes
4. Documente a mudança no commit com contexto claro

### Padrões de escrita para arquivos `.md` deste projeto

- **Seções**: usar `##` para seções principais, `###` para subseções
- **Tabelas**: preferir tabelas para comparações e referências rápidas
- **Blocos de código**: usar ` ``` ` para exemplos de estrutura ou sequências
- **Tom**: direto, técnico, sem enrolação — cada frase deve acrescentar algo
- **Listas**: preferir tabelas quando há mais de 2 colunas de informação

---

## Dependências

### Obrigatórias

| Dependência | Versão | Propósito |
|------------|--------|-----------|
| Claude Code | 2.x+ | Runtime da skill |
| Elementor MCP | Qualquer | Ferramentas de construção no WordPress |
| WordPress | 6.x+ | CMS onde o Elementor opera |
| Elementor | 3.x+ | Page builder |

### Opcionais

| Dependência | Propósito |
|------------|-----------|
| Elementor Pro | Widgets avançados: form, loop-grid, nested-tabs |
| ACF / MetaBox | Necessário para loop-grid com CPT |

---

## Convenções de Nomenclatura

### Arquivos

- Snake case para todos os arquivos: `landing-page.md`, `widget-selection.md`
- Nomes descritivos e sem abreviações: `conversion-principles.md` não `conv-princ.md`
- Templates sempre no plural do tipo: `landing-page.md`, não `lp.md`

### CSS Classes nos Containers Elementor

Use nomenclatura semântica e descritiva ao nomear containers via CSS class:

```
.section-hero
.section-social-proof
.section-features
.section-testimonials
.section-faq
.section-cta-final

.container-hero-content
.grid-feature-cards
.wrapper-testimonial
```

---

## Roadmap

Veja o README.md para o roadmap público do projeto.

Para contribuições internas, priorize nesta ordem:
1. Qualidade e precisão do SKILL.md existente
2. Criação dos docs de suporte (`docs/`)
3. Criação dos templates (`templates/`)
4. Novos tipos de página e cenários
5. Integrações futuras (Figma, design tokens, etc.)
