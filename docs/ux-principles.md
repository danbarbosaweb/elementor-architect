# Princípios de UX

Fundamentos de experiência do usuário aplicados à construção de páginas no Elementor. Este documento aprofunda a seção UX + Mobile-First do SKILL.md.

---

## O que UX significa neste contexto

UX (User Experience) em landing pages e sites não é sobre fazer interfaces bonitas — é sobre **remover obstáculos entre a intenção do visitante e a ação desejada**.

Uma boa UX não é percebida. Quando a experiência é boa, o visitante simplesmente navega, encontra o que precisa e age. Quando é ruim, o visitante sente confusão, frustração ou desconfiança — mesmo sem conseguir nomear o motivo.

O trabalho de UX no Elementor Architect se divide em quatro camadas:

```
Arquitetura de Informação → O que existe e em que ordem
Hierarquia Visual         → O que o olho vê primeiro
Fluxo de Leitura          → Como o visitante percorre o conteúdo
Micro-interações          → Como os elementos respondem a ações
```

---

## Arquitetura de Informação

### Princípio da Pirâmide Invertida

Informação mais importante primeiro, detalhes depois. O visitante decide se vai continuar lendo nas primeiras 3 segundos. Tudo que ele precisa para tomar essa decisão deve estar above the fold.

```
MAIS IMPORTANTE → Valor, para quem é, o que deve fazer
MÉDIO           → Como funciona, benefícios, prova social
MENOS URGENTE   → Detalhes técnicos, FAQ, informações complementares
```

### A Regra das Seções Necessárias

Cada seção deve justificar sua existência respondendo a uma pergunta do visitante. Antes de construir qualquer seção, defina:

> **Qual pergunta do visitante esta seção responde?**

Se não houver resposta clara, a seção provavelmente não deveria existir.

Perguntas que as seções típicas respondem:

| Seção | Pergunta respondida |
|-------|---------------------|
| Hero | "Isso é para mim? Vale meu tempo?" |
| Prova social | "Outras pessoas usaram e funcionou?" |
| Problema | "Eles entendem minha situação?" |
| Solução | "Como exatamente isso vai me ajudar?" |
| Como funciona | "É complicado de usar/implementar?" |
| Depoimentos | "Tem resultados reais, não só promessas?" |
| FAQ | "E se eu tiver dúvida X ou medo Y?" |
| CTA final | "Tenho segurança para agir agora?" |

### Densidade de Informação

Páginas muito densas cansam. Páginas muito vazias parecem sem substância. O equilíbrio está em:

- **Parágrafos curtos**: máximo 3–4 linhas por parágrafo
- **Listas quando possível**: listas são mais escaneáveis que parágrafos
- **Um ponto por seção**: cada seção tem uma ideia central clara
- **Respiro entre elementos**: espaçamento é parte do conteúdo

---

## Hierarquia Visual

### Por que a hierarquia importa

O olho humano não lê — ele escaneia. Em 3 segundos, um visitante captura a impressão geral de uma página. A hierarquia visual determina o que é capturado nessa varredura inicial.

Se a hierarquia for confusa, o visitante não sabe onde olhar. Se a hierarquia for clara, o olho vai naturalmente do mais importante ao menos importante.

### Os 5 níveis aplicados ao Elementor

```
Nível 1 — Focal primário
→ H1, headline hero, imagem hero de alto impacto
→ Deve ser o primeiro elemento que o olho encontra
→ Tamanho, peso e contraste máximos da página

Nível 2 — Contexto imediato
→ H2, subheadline, imagem de suporte
→ Complementa o focal, não compete com ele
→ Segundo em tamanho e contraste

Nível 3 — Detalhamento
→ H3, body text, listas, ícones
→ Responde "e daí?" ao focal e contexto
→ Legível mas subordinado visualmente

Nível 4 — Ação
→ CTA button, formulário, link de ação
→ Deve se destacar pelo contraste de cor, não pelo tamanho
→ Claramente diferente do texto ao redor

Nível 5 — Complemento
→ Labels, captions, links secundários, informações legais
→ Presente mas não competitivo
→ Cor mais suave, tamanho menor
```

### Mecanismos práticos no Elementor

**Tamanho tipográfico:**
Diferença mínima de 8px entre níveis adjacentes. Se H2 está em 36px, H3 deve ser no máximo 28px. Tamanhos muito próximos criam ambiguidade sobre a hierarquia.

**Peso tipográfico:**
- Títulos principais: 700–900 (bold a black)
- Subtítulos: 600 (semibold)
- Body: 400 (regular)
- Captions/labels: 400 ou 600 dependendo do contexto

**Contraste de cor:**
- Texto principal: mínimo 4.5:1 contra o fundo (WCAG AA)
- Texto grande (>18px bold ou >24px regular): mínimo 3:1
- Texto muted: 55–65% de opacidade do texto principal
- Nunca abaixo de 3:1 para qualquer texto funcional

**Espaçamento como hierarquia:**
Mais espaço ao redor de um elemento = mais importância percebida. O padding generoso do hero comunica que aquele conteúdo merece atenção.

---

## Padrões de Leitura

### F-Pattern

Como usuários leem conteúdo com muita informação textual:

```
→ → → → → → → → (varredura horizontal completa no topo)
→ → → → (varredura horizontal mais curta no meio)
↓
↓ (varredura vertical pela borda esquerda)
↓
```

**Implicações para o Elementor:**
- Informações críticas à **esquerda e no topo**
- CTAs no lado esquerdo têm mais visibilidade que à direita em conteúdo denso
- As primeiras 2–3 palavras de cada linha são as mais lidas
- Listas com marcadores são mais efetivas que parágrafos (cada linha começa "fresh")

### Z-Pattern

Como usuários percorrem páginas com pouco texto e muitos elementos visuais:

```
← → (diagonal da esquerda para direita no topo)
  ↘
← → (diagonal da esquerda para direita no fundo)
```

**Implicações para o Elementor:**
- Logo no canto **superior esquerdo**
- CTA no canto **superior direito** (nav)
- Diagonal serve para imagens e elementos visuais
- CTA final no **inferior direito** ou centrado

### Golden Path (Caminho Dourado)

Em landing pages de conversão com foco único, o visitante deve seguir um caminho linear de cima para baixo sem desvios:

```
↓ Hero
↓ Prova Social
↓ Benefícios
↓ Como Funciona
↓ Depoimentos
↓ FAQ
↓ CTA Final
```

**Implicações para o Elementor:**
- Hierarquia vertical clara — cada seção "entrega" para a próxima
- Seções bem separadas visualmente (80–120px de padding)
- CTAs inline reforçam o destino sem criar desvios
- Menus de navegação em landing pages são prejudiciais (levam para fora do funil)

---

## White Space (Espaço em Branco)

White space não é espaço vazio — é um **elemento de design ativo**. Ele:
- Guia o olho para onde olhar
- Reduz carga cognitiva
- Comunica qualidade e sofisticação
- Melhora a legibilidade

### Tipos de white space

**Macro white space:** espaço entre seções principais (80–120px). Separa claramente uma seção da outra.

**Micro white space:** espaço entre elementos dentro de uma seção (8–32px). Cria grupos visuais e ritmo interno.

**Line height:** espaço entre linhas de texto (1.6–1.7 para body). Torna o texto respirável.

**Letter spacing:** espaço entre letras. Ligeiramente positivo em overlines (0.05–0.15em) para legibilidade de uppercase.

### Erros comuns de white space

**Excesso de conteúdo por seção**: quando há muita informação em uma área, aumentar o padding ajuda mais do que reduzir o conteúdo.

**Seções coladas**: menos de 60px entre seções faz a página parecer uma parede de texto.

**Cards sem respiração interna**: padding interno de cards abaixo de 20px parece sufocante.

**Gap insuficiente entre colunas**: menos de 24px entre colunas em grid de cards cria colisão visual.

---

## Psicologia das Cores

### Princípio de uso

A cor tem três funções em landing pages:
1. **Identidade**: comunicar a marca
2. **Hierarquia**: destacar o que importa
3. **Ação**: sinalizar onde clicar

O erro mais comum é usar cor para decoração sem função. Cada cor deve ter um papel claro.

### Paleta funcional mínima

| Papel | Função | Como usar |
|-------|--------|-----------|
| Primary | A cor da marca — CTAs, links, destaques | Usada com parcimônia para manter impacto |
| Secondary | Backgrounds alternativos, suporte | Seções alternadas, fundos de cards |
| Accent | Badges, highlights, micro-detalhes | Sparingly — perde impacto se overused |
| Text Dark | Texto principal | Consistente em toda a página |
| Text Muted | Texto secundário | 55–65% opacity do Text Dark |
| Background | Fundo de página | Quase sempre neutro |

### Temperatura emocional das cores

| Cor | Associação | Bom para |
|-----|-----------|---------|
| Azul | Confiança, tecnologia, profissionalismo | SaaS, fintech, saúde, serviços |
| Verde | Crescimento, saúde, natureza, aprovação | Saúde, finanças, sustentabilidade |
| Roxo | Criatividade, luxo, espiritualidade | Criativos, bem-estar, premium |
| Laranja | Energia, entusiasmo, acessibilidade | Varejo, educação, food |
| Vermelho | Urgência, paixão, atenção | CTAs, alertas, promoções |
| Cinza | Sofisticação, neutralidade | Fundos, textos secundários, bordas |

### Contraste e acessibilidade

**WCAG AA** (mínimo obrigatório):
- Texto normal (< 18px ou < 14px bold): contraste 4.5:1
- Texto grande (≥ 18px ou ≥ 14px bold): contraste 3:1
- Componentes de UI (bordas de input, ícones ativos): contraste 3:1

**WCAG AAA** (ideal):
- Texto normal: contraste 7:1
- Texto grande: contraste 4.5:1

Ferramenta de verificação: [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)

---

## Tipografia para Legibilidade

### Comprimento de linha (measure)

Linhas muito longas forçam o olho a voltar para o início da próxima — e é fácil se perder.

| Largura | Número de caracteres | Legibilidade |
|---------|---------------------|-------------|
| < 45 chars | Muito curto | Leitura entrecortada |
| 45–75 chars | Ideal | Leitura fluida |
| 75–90 chars | Aceitável | Ligeiramente cansativo |
| > 90 chars | Longo demais | Ilegível em textos longos |

**Implementação no Elementor:** max-width de 720px para `text-editor` com body text. Custom CSS se necessário.

### Line height

```
Títulos (H1–H2): 1.05–1.25
Subtítulos (H3–H4): 1.3–1.4
Body text: 1.6–1.7
Captions/labels: 1.4
```

Line height abaixo de 1.5 para body text dificulta a leitura de textos longos.

### Texto e alinhamento

**Alinhamento à esquerda**: padrão para qualquer texto com mais de 1 linha. O olho sempre sabe onde a próxima linha começa.

**Alinhamento centralizado**: aceitável apenas para títulos curtos (1–2 linhas), CTAs, e textos com até 3 linhas em contextos específicos.

**Alinhamento justificado**: nunca. Cria rios de espaço brancos irregulares em textos com palavras compridas. Especialmente ruim em mobile.

**Alinhamento à direita**: apenas para elementos de UI específicos (valores monetários em tabelas, timestamps).

---

## Mobile-First na Prática

### Por que mobile-first (de verdade)

"Mobile-first" não significa "design para desktop e depois adapte para mobile". Significa **começar pelo mobile como ponto de partida do design**.

Razões técnicas:
- Mais de 60% do tráfego web é mobile (fonte: StatCounter, 2024)
- Google usa mobile-first indexing — o mobile é a versão indexada
- Layout mobile ≠ layout desktop comprimido — são estruturas diferentes

Razões de design:
- Restrições de mobile forçam priorização — você é obrigado a manter apenas o essencial
- Um design mobile forte quase sempre escala bem para desktop
- Um design desktop forte raramente escala bem para mobile

### O processo correto no Elementor

```
1. Construir a estrutura mobile primeiro
   → Coluna única
   → Fonte base (15–16px body)
   → Padding lateral 16px
   → Botões full-width ou mínimo 200px

2. Verificar no breakpoint tablet (768px)
   → 2 colunas onde faz sentido (cards, features)
   → Ajustar gaps e padding
   → Verificar imagens

3. Expandir para desktop (1024px+)
   → Layout completo
   → Aumentar padding e fontes
   → Adicionar elementos que só fazem sentido em desktop
```

### Checklist mobile por tipo de elemento

**Tipografia:**
- [ ] H1: máximo 48px mobile (preferível 36–42px)
- [ ] Body: mínimo 15px mobile
- [ ] Nunca abaixo de 14px em qualquer elemento
- [ ] Line height adequado (1.5+ para body)

**Espaçamento:**
- [ ] Padding lateral de seção: mínimo 16px
- [ ] Padding vertical de seção: mínimo 48px
- [ ] Gap entre cards: mínimo 16px
- [ ] Padding interno de botões: mínimo 12px vertical

**Interação:**
- [ ] Botões: altura mínima 44px
- [ ] Links: área de toque mínima 44×44px
- [ ] Inputs de formulário: altura mínima 44px
- [ ] Menus mobile: itens com 44px de altura

**Layout:**
- [ ] Máximo 1 coluna para texto em mobile
- [ ] Cards empilhados verticalmente
- [ ] Tabelas com scroll horizontal ou reformatadas
- [ ] Imagens não excedem a largura da tela

### Erros mobile frequentes no Elementor

**Esconder conteúdo com display:none:**
Ruim para SEO (Google indexa o mobile), ruim para UX (visitantes mobile merecem o mesmo conteúdo), e cria manutenção duplicada.

**Copiar layout desktop para mobile:**
Duas colunas de texto em mobile = linhas com 15 caracteres = ilegível.

**Imagens com dimensões fixas:**
Uma imagem com width:600px em mobile de 375px vai criar scroll horizontal.

**Animações pesadas em mobile:**
Animar propriedades como box-shadow, filter, ou opacity em muitos elementos ao mesmo tempo consome bateria e causa jank. No mobile, prefira transições simples.

---

## Micro-Interações

Micro-interações são os pequenos feedbacks visuais que confirmam que algo funcionou ou que um elemento é interativo.

### Hover states

Elementos interativos (botões, links, cards clicáveis) devem ter hover state visível:

```css
/* Botão padrão */
.button {
  background: #7c3aed;
  transition: background 0.2s ease, transform 0.1s ease;
}

.button:hover {
  background: #6d28d9; /* 10% mais escuro */
  transform: translateY(-1px); /* elevação sutil */
}

.button:active {
  transform: translateY(0); /* retorna ao lugar */
}
```

### Focus states

Elementos focáveis via teclado devem ter focus state visível — isso é acessibilidade, não estética:

```css
.button:focus-visible {
  outline: 2px solid #7c3aed;
  outline-offset: 3px;
}
```

### Link states

Links no body text devem ser claramente identificáveis — não apenas pela cor:

```css
a {
  color: #7c3aed;
  text-decoration: underline; /* visível sem depender de cor */
}
```

### Animações de entrada

Animações de entrada (fade in, slide up) criam percepção de qualidade quando bem executadas:

- **Duração**: 300–500ms para a maioria dos elementos
- **Easing**: ease-out (começa rápido, desacelera) para elementos que entram
- **Distância de translação**: máximo 20–30px para slide-up
- **Não animar tudo**: elementos focais ganham mais impacto com animação quando os demais não animam

**No Elementor**: preferir Entrance Animations nativas do widget quando disponível. Para controle fino, usar custom CSS.

---

## Acessibilidade Aplicada

### Mínimo aceitável (WCAG 2.1 AA)

| Critério | Padrão |
|----------|--------|
| Contraste de texto | 4.5:1 (normal), 3:1 (grande) |
| Tamanho de fonte | Reescalável pelo usuário (não use px absolutas para configuração de browser) |
| Teclado | Todos os elementos interativos acessíveis via Tab |
| Focus visible | Indicador de foco sempre visível |
| Alt text | Todas as imagens funcionais com descrição |
| Formulários | Labels associados a inputs |
| Erro de formulário | Identificado por texto, não apenas por cor |

### Erros de acessibilidade mais comuns no Elementor

**Imagens sem alt text**: o campo existe no widget de imagem — sempre preencher para imagens funcionais. Para imagens decorativas, alt="" (vazio intencional).

**Contraste insuficiente em botões ghost**: botão com borda transparente e texto da cor primária sobre fundo branco frequentemente falha no contraste.

**Placeholder como label**: o placeholder desaparece quando o usuário começa a digitar. Sempre incluir um label visível.

**Links "Clique aqui"**: leitores de tela leem os links fora de contexto. "Clique aqui" não comunica destino. Use "Ver planos de preço" ou "Baixar e-book gratuito".
