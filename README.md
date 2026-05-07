# elementor-architect

**Skill inteligente para Claude Code que projeta e constrói páginas Elementor de alta performance.**

Atua como UI Designer, UX Specialist, Conversion Specialist, Elementor Architect e Landing Page Strategist — tudo em um único comando.

---

## O Que É

`elementor-architect` é uma skill opinativa para [Claude Code](https://claude.ai/code) que trabalha junto ao [Elementor MCP](https://github.com/msrbuilds/elementor-mcp) para planejar, criticar e construir páginas no WordPress/Elementor.

**Não é apenas um executor de ferramentas.** A skill analisa referências, define hierarquia visual, estratégia de conversão, sistema de design e toma decisões arquiteturais embasadas. Quando você propõe algo que vai contra boas práticas, ela explica o problema e propõe uma alternativa melhor.

### O Que Ela Faz

| Capacidade | Descrição |
|-----------|-----------|
| Análise de referências | Interpreta links, screenshots, wireframes, HTML/CSS e descrições textuais |
| Arquitetura de páginas | Planeja estrutura de seções com justificativa estratégica |
| Sistema de design | Define paleta, tipografia e espaçamento consistentes |
| Hierarquia visual | Garante H1→H2→H3→body corretos em cada seção |
| Estratégia de conversão | CRO, posicionamento de CTAs, prova social, gatilhos |
| UX e mobile-first | Design parte de 375px, escala para desktop |
| Execução MCP | Constrói páginas completas via Elementor MCP |
| Revisão e crítica | Identifica e corrige problemas antes de implementar |

---

## Instalação

### Pré-requisitos

- [Claude Code](https://claude.ai/code) instalado e configurado
- [Elementor MCP](https://github.com/msrbuilds/elementor-mcp) configurado com sua instalação WordPress
- WordPress + Elementor (versão 3.x+)

### Instalar a Skill

Copie o arquivo da skill para o diretório de skills do Claude Code:

**macOS / Linux:**
```bash
mkdir -p ~/.claude/skills/elementor-architect
cp skill/SKILL.md ~/.claude/skills/elementor-architect/SKILL.md
```

**Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\elementor-architect"
Copy-Item "skill\SKILL.md" "$env:USERPROFILE\.claude\skills\elementor-architect\SKILL.md"
```

Pronto. A skill estará disponível imediatamente no Claude Code.

---

## Como Usar

### Ativação

No Claude Code, execute:

```
/elementor-architect
```

### Fluxo de Discovery

Após ativar, a skill fará perguntas antes de qualquer construção:

1. **Tipo de página** → Landing Page, SaaS, Institucional, Agência, Local, Personalizado
2. **Objetivo de conversão** → Leads, venda, agendamento, trial, branding
3. **Público-alvo** → Quem é, quais as dores, qual o tom de voz
4. **Referências** → Links, prints, wireframes, HTML ou descrição
5. **Confirmação** → A skill propõe arquitetura e aguarda aprovação

### Tipos de Página Suportados

| Tipo | Objetivo Principal |
|------|--------------------|
| **Landing Page** | Captura de leads ou venda direta com foco em conversão |
| **Página SaaS** | Trial, demo ou assinatura de software/plataforma |
| **Site Institucional** | Credibilidade de marca e geração de contato qualificado |
| **Site de Agência** | Demonstração de expertise e geração de reuniões |
| **Produto / Negócio Local** | Conversão de visitantes locais em clientes |

### Exemplos de Uso

**Construção do zero:**
```
/elementor-architect
→ Landing Page → Captura de leads → Curso de design
→ [enviar referência ou URL]
→ Skill analisa, propõe arquitetura, aguarda aprovação
→ Constrói seção por seção via MCP
```

**Análise de referência:**
```
/elementor-architect
→ Analise este site para mim: [URL]
→ Skill mapeia estrutura, hierarquia, CTAs e pontos de melhoria
```

**Revisão de página existente:**
```
/elementor-architect
→ Tenho uma página criada, quero revisar a UX e conversão
→ Skill lê a estrutura via get-page-structure e faz auditoria
```

---

## Prioridade de Widgets

A skill segue uma ordem clara de prioridade para seleção de widgets:

```
Nível 1 — Layout       → add-flexbox (todos os containers)
Nível 2 — Conteúdo     → heading, text-editor, button, image, icon-box
Nível 3 — Conversão    → call-to-action, counter, countdown, form, price-table
Nível 4 — Prova Social → testimonial-carousel, reviews, star-rating
Nível 5 — Interação    → tabs, accordion, toggle
Baixa prioridade       → atomic widgets (imprevisíveis, evitar)
```

---

## Princípios da Skill

### O que a skill sempre faz

- Define design system global antes de construir qualquer widget
- Propõe arquitetura e aguarda aprovação antes de executar
- Usa flexbox como container principal para todo layout
- Verifica a estrutura final com `get-page-structure`
- Questiona e corrige referências com problemas de UX

### O que a skill nunca faz

- Constrói sem entender o objetivo de conversão
- Usa atomic widgets como escolha padrão
- Coloca múltiplos CTAs primários na mesma seção
- Ignora mobile-first
- Implementa wireframes ruins sem propor melhorias
- Usa countdown falso como gatilho de urgência

---

## Estrutura do Repositório

```
elementor-architect/
├── CLAUDE.md                    ← Instruções para Claude Code neste projeto
├── README.md                    ← Esta documentação
│
├── skill/
│   └── SKILL.md                 ← Código-fonte da skill
│
├── docs/                        ← Documentação técnica aprofundada
│   ├── overview.md
│   ├── conversion-principles.md
│   ├── ux-principles.md
│   ├── widget-selection.md
│   └── mcp-tools-reference.md
│
└── templates/                   ← Estruturas de página prontas
    ├── landing-page.md
    ├── saas-page.md
    ├── institutional.md
    ├── agency.md
    └── local-business.md
```

---

## Dependências

| Dependência | Obrigatória | Link |
|------------|:-----------:|------|
| Claude Code | Sim | [claude.ai/code](https://claude.ai/code) |
| Elementor MCP | Sim | [github.com/msrbuilds/elementor-mcp](https://github.com/msrbuilds/elementor-mcp) |
| WordPress 6.x+ | Sim | [wordpress.org](https://wordpress.org) |
| Elementor 3.x+ | Sim | [elementor.com](https://elementor.com) |
| Elementor Pro | Não* | Necessário para form, loop-grid, nested-tabs |

*Elementor Pro amplifica significativamente as capacidades da skill.

---

## Roadmap

### Fase 1 — Fundação (atual)
- [x] SKILL.md principal com metodologia completa
- [x] CLAUDE.md e README.md
- [ ] Documentação de suporte (`docs/`)
- [ ] Templates de página (`templates/`)

### Fase 2 — Aprofundamento
- [ ] Guia de análise de referências com exemplos reais
- [ ] Biblioteca de padrões de seção documentados
- [ ] Casos de uso reais com screenshots
- [ ] Guia de integração com Elementor Pro

### Fase 3 — Expansão
- [ ] Suporte a e-commerce (WooCommerce)
- [ ] Templates para portais e blogs
- [ ] Integração com tokens de design (Figma → Elementor)
- [ ] Guia de otimização de performance

### Fase 4 — Comunidade
- [ ] Repositório público no GitHub
- [ ] Sistema de contribuição de templates
- [ ] Exemplos de páginas construídas com a skill
- [ ] Versão em inglês

---

## Contribuindo

Contribuições são bem-vindas. Antes de abrir um PR:

1. Leia o `CLAUDE.md` para entender as convenções do projeto
2. Mantenha o `skill/SKILL.md` e o arquivo instalado sempre em sincronia
3. Teste as mudanças com pelo menos 2 cenários diferentes
4. Descreva claramente o problema que a mudança resolve

---

## Licença

MIT — veja `LICENSE` quando disponível.

---

*Construído para funcionar com [Claude Code](https://claude.ai/code) e [Elementor MCP](https://github.com/msrbuilds/elementor-mcp).*
