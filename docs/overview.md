# Overview — Como o Elementor Architect Funciona

Este documento descreve a arquitetura interna da skill, o fluxo de decisão em cada etapa e a relação entre os arquivos do projeto.

---

## A Filosofia da Skill

O Elementor Architect parte de uma premissa central: **construir uma boa página é primeiro um problema de estratégia, depois de execução**.

A maioria das ferramentas de automação se preocupa com o "como" — quais ferramentas usar, qual a sintaxe correta, como encadear chamadas. O Elementor Architect começa um passo antes: **por que** essa estrutura, **para quem** essa página existe, e **qual o único objetivo** que ela deve alcançar.

Só depois que essas perguntas estão respondidas, a skill toca nas ferramentas MCP.

---

## Estrutura da Skill

```
SKILL.md
├── Identidade          → Quem é a skill e o que ela prioriza
├── Discovery           → Coleta de contexto antes de qualquer ação
├── Análise de Refs     → Como interpretar diferentes tipos de input
├── Metodologia         → 5 etapas de arquitetura antes do MCP
├── Estratégia por Tipo → Estruturas base por tipo de página
├── Sistema de Design   → Tipografia, cores, espaçamento
├── Hierarquia Visual   → Como guiar o olho do visitante
├── CRO                 → Princípios de conversão aplicados
├── UX + Mobile-First   → Responsividade e acessibilidade
├── Widgets             → Seleção e prioridade
├── Sequência MCP       → Como e quando usar cada ferramenta
├── Anti-Padrões        → O que nunca implementar
└── Checklist           → Verificação antes de declarar conclusão
```

A documentação de suporte aprofunda cada uma dessas áreas:

```
docs/
├── overview.md              ← Este arquivo
├── conversion-principles.md ← Aprofunda a seção CRO
├── ux-principles.md         ← Aprofunda a seção UX
├── widget-selection.md      ← Aprofunda a seleção de widgets
└── mcp-tools-reference.md  ← Referência completa das ferramentas

templates/
└── [tipo].md                ← Estruturas prontas por tipo de página
```

---

## O Fluxo Completo

### Fase 1 — Discovery

**Objetivo**: entender o contexto antes de planejar qualquer coisa.

A skill coleta cinco tipos de informação:

| Informação | Por que importa |
|-----------|-----------------|
| Tipo de página | Define a estrutura base e os widgets prioritários |
| Objetivo de conversão | Define o CTA principal e a sequência de seções |
| Público-alvo | Define o tom, a linguagem e as objeções a tratar |
| Referências | Define o estilo visual e o que replicar ou evitar |
| Identidade visual | Define o design system a aplicar |

O discovery termina com uma **proposta de arquitetura** que aguarda aprovação explícita do usuário antes de qualquer execução.

**Regra**: a skill nunca começa a construir sem aprovação. Essa etapa existe para alinhar expectativas e evitar retrabalho.

---

### Fase 2 — Análise de Referências

**Objetivo**: extrair insights acionáveis de qualquer tipo de input.

A skill adapta sua análise ao tipo de referência recebida:

```
URL recebida:
→ Estrutura de seções em ordem
→ Hierarquia visual (H1/H2/H3)
→ Posicionamento e linguagem de CTAs
→ Tipos e posição da prova social
→ O que funciona bem + o que pode melhorar

Screenshot/imagem recebida:
→ Layout e distribuição de colunas
→ Paleta de cores extraída
→ Tipografia identificada (famílias, pesos, tamanhos)
→ Componentes reutilizáveis
→ Problemas de hierarquia ou consistência

Wireframe recebido:
→ Intenção de cada elemento
→ Gaps de UX e conversão
→ Proposta de melhoria antes de implementar

HTML/CSS recebido:
→ Sistema de design implícito
→ Padrões e componentes reutilizáveis
→ Problemas estruturais a não replicar

Descrição textual:
→ Perguntas de clarificação se necessário
→ Inferência de estrutura ideal
→ Proposta baseada em benchmarks do setor
```

---

### Fase 3 — Arquitetura

**Objetivo**: planejar a estrutura completa antes de tocar em qualquer ferramenta.

A metodologia de 5 etapas:

```
Etapa 1 → Objetivo único de conversão
           Uma ação. Toda a página serve a ela.

Etapa 2 → Jornada do visitante
           TOPO: "Isso é para mim?"
           MEIO: "Posso confiar?"
           FUNDO: "Devo agir agora?"

Etapa 3 → Sequência de seções
           Cada seção responde a uma pergunta do visitante.
           Se não responde, não existe.

Etapa 4 → Hierarquia visual por seção
           Focal → Suporte → CTA → Prova

Etapa 5 → Sistema de design
           Paleta, tipografia, espaçamento — antes da primeira chamada MCP.
```

A saída desta fase é um documento de arquitetura que lista:
- Todas as seções em ordem
- Widget principal de cada seção
- Objetivo estratégico de cada seção
- Ferramentas MCP que serão utilizadas

---

### Fase 4 — Execução com MCP

**Objetivo**: construir a página de forma eficiente e sem retrabalho.

A sequência de execução sempre segue esta ordem:

```
1. detect-elementor-version     → diagnóstico da instalação
2. get-global-settings          → verificar design system existente
3. update-global-colors         → definir paleta ANTES dos widgets
4. update-global-typography     → definir tipografia ANTES dos widgets
5. list-pages / create-page     → selecionar ou criar a página
6. [construção seção por seção] → flexbox + widgets por nível
7. batch-update                 → atualizações em lote (≥3 elementos)
8. add-custom-css               → ajustes finos não cobertos pelos widgets
9. get-page-structure           → verificação final da estrutura
```

**Por que design system antes dos widgets?**

Se você define as cores e tipografia globais depois de construir os widgets, precisa atualizar cada widget individualmente. Definir antes significa que todos os widgets já herdam os valores corretos do sistema global.

---

### Fase 5 — Verificação

**Objetivo**: garantir que nada foi esquecido antes de declarar a página concluída.

A verificação percorre o checklist de qualidade em 4 dimensões:

| Dimensão | O que verifica |
|----------|---------------|
| Conversão e estratégia | Hero, prova social, CTAs, formulário, sequência |
| Design e consistência | Tipografia, cores, espaçamento, hierarquia |
| Estrutura técnica | Flexbox, nomenclatura, custom CSS, estrutura final |
| Mobile-first | Breakpoints, fontes, touch targets, layout responsivo |

Nenhum item do checklist é opcional.

---

## Como a Skill Toma Decisões

### Seleção de Widget

A skill sempre pergunta: qual é o widget mais simples e previsível que resolve este problema?

```
Preciso de texto? → heading ou text-editor (nunca atomic)
Preciso de layout? → flexbox (sempre)
Preciso de CTA? → button ou call-to-action
Preciso de prova social? → counter, testimonial-carousel, reviews
```

Atomic widgets são evitados por padrão porque seu comportamento de estilização no editor é imprevisível — o mesmo valor CSS pode se comportar de forma diferente dependendo da versão do Elementor. Widgets clássicos são mais estáveis e têm melhor suporte histórico.

### Quando Questionar o Usuário

A skill questiona ativamente quando:

- O wireframe proposto tem problemas de UX claros
- A referência enviada tem anti-padrões de conversão
- O usuário pede múltiplos CTAs primários concorrentes
- A estrutura proposta ignora mobile-first
- O objetivo de conversão não está claro

Questionar não é resistência — é parte do trabalho de arquitetura. Uma pergunta certa antes de construir economiza horas de retrabalho.

### Quando Propor Alternativas

Sempre que houver uma solução melhor do que a solicitada, a skill:

1. Explica o problema da solução original com justificativa técnica
2. Propõe a alternativa com justificativa estratégica
3. Pergunta antes de implementar

Exemplo:
> "Você pediu um carrossel no hero, mas carrosséis como hero têm alta taxa de bounce porque os CTAs ficam invisíveis enquanto o usuário não interage. Posso construir um hero estático com a mesma mensagem e um carrossel separado na seção de galeria. Faz sentido?"

---

## A Relação Entre os Arquivos

```
SKILL.md
→ É a skill em si. Contém tudo que Claude precisa saber para executar.
→ Deve ser suficiente sozinho para um caso de uso completo.
→ Referencia os docs/ para aprofundamento mas não depende deles.

docs/
→ Aprofundamento de cada área da skill.
→ Útil quando a skill precisa de mais detalhes sobre um tópico específico.
→ Útil para quem quer entender os princípios por trás das decisões.
→ Nunca contém instruções que contradizem o SKILL.md.

templates/
→ Estruturas prontas para os tipos de página mais comuns.
→ A skill pode referenciar os templates quando constrói.
→ Cada template é uma instância concreta da metodologia do SKILL.md.
→ Templates são ponto de partida, não regras rígidas.
```

**Regra de consistência**: qualquer princípio nos docs/ ou templates/ deve estar alinhado com o SKILL.md. Se houver conflito, o SKILL.md prevalece — ele é a fonte da verdade.

---

## Atualizando a Skill

### Quando atualizar

- Novos anti-padrões identificados em uso real
- Novos tipos de página que precisam de estratégia própria
- Mudanças no Elementor que afetam a seleção de widgets
- Refinamentos em princípios de CRO ou UX baseados em dados

### Como atualizar

1. Edite `skill/SKILL.md` no repositório
2. Copie o conteúdo atualizado para `~/.claude/skills/elementor-architect/SKILL.md`
3. Atualize o doc relevante em `docs/` se necessário
4. Teste com pelo menos 2 cenários antes de commitar

**Os dois arquivos SKILL.md devem estar sempre em sincronia.**
