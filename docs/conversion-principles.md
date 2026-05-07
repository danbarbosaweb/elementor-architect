# Princípios de Conversão (CRO)

Playbook completo de otimização para conversão aplicado a páginas Elementor. Este documento aprofunda a seção CRO do SKILL.md com frameworks, princípios e táticas específicas.

---

## A Mentalidade de Conversão

Conversão não é sobre truques ou manipulação — é sobre **reduzir o atrito entre a intenção do visitante e a ação que você quer que ele tome**.

Um visitante que chega em sua página já tem uma dor ou desejo. Seu trabalho é:
1. Provar que você entende esse problema
2. Demonstrar que sua solução funciona
3. Eliminar os riscos percebidos de agir
4. Tornar a ação o caminho de menor resistência

Se qualquer uma dessas etapas falhar, o visitante sai.

---

## Frameworks de Narrativa

### AIDA — Para páginas de persuasão gradual

```
A — Atenção    → Hero: capturar atenção com headline impactante
I — Interesse  → Problema + Solução: despertar curiosidade
D — Desejo     → Benefícios + Prova social: criar querer
A — Ação       → CTA: remover o último obstáculo
```

Use AIDA quando o produto precisa de explicação. O visitante chega sem conhecer a solução — você precisa educá-lo enquanto persuade.

### PAS — Para páginas com dor latente

```
P — Problema   → Nomear a dor do visitante com precisão cirúrgica
A — Agitação   → Amplificar as consequências de não resolver
S — Solução    → Apresentar o produto como saída inevitável
```

Use PAS quando o visitante já sabe que tem um problema mas não encontrou a solução certa. A agitação é poderosa — mas use com responsabilidade. Nunca invente dores que o público não tem.

### PASTOR — Para páginas de venda de alta fricção

```
P — Problema   → Identificar a dor
A — Amplificar → Agitar as consequências
S — Story      → Contar a história de transformação
T — Testemony  → Prova de que funciona para outros
O — Offer      → A proposta com tudo que está incluído
R — Response   → CTA com eliminação de risco
```

Use PASTOR para produtos de alto ticket ou alto comprometimento onde o visitante precisa de mais persuasão antes de converter.

---

## Anatomia Detalhada das Seções

### Hero

O hero é a seção mais importante da página. É a única que **todos os visitantes veem**. Tudo após o hero é visto por uma fração menor.

**Elementos obrigatórios:**

| Elemento | Função | Onde posicionar |
|---------|--------|----------------|
| Overline | Contextualizador — "você está no lugar certo" | Acima do H1 |
| H1 (Headline) | Proposta de valor principal | Topo da seção |
| Subheadline | Elimina a principal dúvida do visitante | Imediatamente abaixo do H1 |
| CTA Primário | A única ação que o visitante deve tomar | Abaixo do subheadline |
| Trust signal | Prova imediata de credibilidade | Abaixo do CTA |

**O que a headline deve comunicar:**

A headline ideal responde a uma pergunta que todo visitante faz em 3 segundos: *"Isso é para mim e vale meu tempo?"*

Para responder isso, ela deve conter alguma combinação de:
- O **resultado** que o visitante vai obter
- **Para quem** é (persona)
- O **diferencial** ou a **barreira eliminada**

Exemplos comparativos:

| Fraca | Forte | Por quê |
|-------|-------|---------|
| "Bem-vindo ao nosso curso" | "Aprenda UX Design em 12 semanas" | Resultado específico |
| "Software de gestão" | "Reduza 3h de trabalho manual por dia" | Benefício concreto |
| "Consultoria empresarial" | "Para PMEs que querem crescer sem contratar gerente" | Persona + barreira |
| "Clínica de estética" | "Procedimentos a laser sem tempo de recuperação" | Diferencial |

**O trust signal no hero:**

O trust signal deve aparecer **dentro do hero**, logo abaixo do CTA. Não em uma seção separada — no próprio hero. Exemplos efetivos:

```
★★★★★ 4.9 de média · 847 avaliações
→ "2.847 alunos desde 2019"
→ "Como visto em: [logos de mídia]"
→ "Aprovado por [número] [profissionais/empresas]"
```

---

### Prova Social Imediata (Logos Strip)

A seção imediatamente após o hero deve ser dedicada a prova social — antes de qualquer benefício, feature ou explicação.

**Por que antes dos benefícios?**

O visitante que acabou de ler o hero está em modo de avaliação: *"Será que isso funciona?"*. Mostrar que outros (especialmente reconhecíveis) confiam interrompe o ceticismo antes que ele se instale.

**Variantes por tipo de negócio:**

| Tipo de negócio | Tipo de prova ideal |
|----------------|---------------------|
| B2B / SaaS | Logos de empresas clientes |
| Curso / Infoproduto | Contador de alunos + avaliação média |
| Serviço local | Estrelas Google + número de avaliações |
| Agência | Logos de clientes + números de resultados |
| Produto físico | Avaliações + número de compradores |

---

### Seção de Problema

Muitos construtores de páginas pulam esta seção. É um erro.

A seção de problema faz o visitante sentir que **você o entende**. Quando alguém lê a descrição exata de sua dor nas palavras certas, a resposta psicológica é: *"Essas pessoas entendem minha situação — talvez tenham a solução"*.

**Como escrever a seção de problema:**

1. Nome o problema sem julgamento ("Você já se sentiu...")
2. Descreva as consequências práticas (tempo perdido, dinheiro desperdiçado, frustração)
3. Valide que é um problema real, não uma falha pessoal ("Não é sua culpa. O sistema foi construído assim...")
4. Crie a transição natural para a solução

**Widget recomendado:** `heading` + `text-editor` com formatação em parágrafos curtos, 2–3 linhas máximo cada.

---

### Seção de Benefícios

A diferença entre features e benefícios é fundamental para conversão:

| Feature (o que é) | Benefício (o que faz por você) |
|-------------------|-------------------------------|
| "Aulas em vídeo HD" | "Aprenda no seu ritmo, quando quiser" |
| "Suporte 24/7" | "Nunca fica preso num problema por mais de algumas horas" |
| "Dashboard em tempo real" | "Veja exatamente o que está acontecendo antes que vire problema" |
| "3 anos de garantia" | "Compre sem medo — se quebrar, resolvemos" |

**Regra de ouro**: para cada feature, pergunte "e daí?" até chegar no benefício real para o usuário.

**Estrutura recomendada para seção de benefícios:**

```
[Overline: SEUS RESULTADOS / POR QUE FUNCIONA]
[H2: headline da seção]
[Grid de icon-boxes 3 colunas desktop / 1 coluna mobile]

Cada card:
- Ícone relevante (não decorativo)
- Título: o benefício em 3-5 palavras
- Texto: explicação em 1-3 linhas
```

---

### Como Funciona

Esta seção existe para reduzir a **fricção cognitiva** — a resistência que acontece quando o visitante não entende como funciona e sente que pode fazer errado ou perder tempo.

**Estrutura em 3 passos** (quase universal):

```
Passo 1: [Ação simples] → "Crie sua conta em 2 minutos"
Passo 2: [Configuração] → "Configure seu perfil"
Passo 3: [Resultado]   → "Comece a ver resultados"
```

Máximo 3 passos. Se precisar de mais, agrupe.

**Widget recomendado:** `icon-list` numerado ou `tabs` para processos mais complexos.

---

### Depoimentos

Depoimentos são o elemento de prova social mais poderoso após o vídeo. Mas depoimentos mal escritos ou mal apresentados não convencem ninguém.

**Anatomia de um depoimento eficaz:**

```
[FOTO REAL da pessoa — não avatar, não silhueta]

"[Citar o resultado específico, não a satisfação geral]
 Antes eu [situação anterior]. Depois de [produto/serviço],
 eu [resultado concreto em dados ou descrição vivida]."

NOME COMPLETO
Cargo, Empresa (para B2B) ou Cidade, Estado (para B2C)
```

**O que não funciona:**
- "Ótimo atendimento!" — genérico, sem credibilidade
- Foto de stock ou silhueta — parece fabricado
- Sem nome completo — anônimo não convence
- Sem contexto (cargo, empresa, cidade) — abstrato

**O que funciona:**
- Resultado específico e mensurável quando possível
- Situação anterior + transformação (narrativa de antes/depois)
- Pessoa real com foto real e identificação completa
- Linguagem natural, não marketeira

---

### FAQ — Tratamento de Objeções

O FAQ não é uma seção de dúvidas técnicas. É uma **seção de demolição de objeções de venda**.

As perguntas do FAQ devem ser as reais razões pelas quais as pessoas não compram — não as mais fáceis de responder.

**Perguntas de alta conversão por tipo:**

| Tipo | Perguntas de alta conversão |
|------|-----------------------------|
| Curso | "E se eu não tiver tempo?" / "Funciona para iniciantes?" / "Quanto tempo leva para ver resultados?" |
| SaaS | "Preciso de equipe técnica?" / "Como faço a migração dos dados?" / "E se eu quiser cancelar?" |
| Serviço | "Quanto tempo leva?" / "Funciona para o meu caso?" / "O que acontece se eu não ficar satisfeito?" |
| Produto físico | "E se não servir?" / "Qual o prazo de entrega?" / "É seguro comprar online?" |

**Como descobrir as objeções reais:**
- Perguntas que chegam por e-mail ou WhatsApp antes da compra
- Comentários em redes sociais sobre o produto
- Feedbacks de vendas perdidas
- Perguntas de suporte recorrentes

**Widget recomendado:** `accordion` (múltiplas abertas) ou `toggle` (apenas uma aberta por vez).

---

### CTA Final

O CTA final é diferente do CTA do hero. O visitante que chegou até aqui já leu a página. Ele está mais informado — e ainda assim não converteu. Isso significa que há uma objeção final que precisa ser tratada.

**Elementos do CTA final de alta conversão:**

```
[H2: reforça o resultado, não repete o headline do hero]
[Subheadline: elimina o risco final]
[CTA principal]
[Prova social resumida: "Junte-se a X pessoas"]
[Garantia ou eliminação de risco]
[CTA secundário para quem ainda não está pronto]
```

**O papel da garantia:**

A garantia não é apenas um benefício — é uma **inversão de risco**. Em vez de o visitante arriscar seu dinheiro ou tempo, você assume o risco. Isso reduz o custo psicológico de decidir.

Exemplos efetivos:
- "30 dias de garantia total — se não gostar, devolvemos 100%"
- "Primeira sessão grátis — só paga se quiser continuar"
- "Cancele quando quiser, sem multa"

---

## Posicionamento de CTAs na Página

### Mapa de CTAs por scroll

```
0–25% da página (Hero)
→ CTA primário obrigatório
→ Muitos visitantes convertem aqui sem ler mais

25–75% da página (Meio)
→ CTAs inline opcionais em seções de alta intensidade
→ Exemplo: CTA após seção "Como funciona" ou "Resultados"
→ Não competem — são o mesmo CTA primário

75–100% da página (Fundo)
→ CTA final obrigatório
→ Mais elaborado que o do hero (garantia, contexto)
→ Para quem precisou ler tudo para decidir
```

### Regras de CTAs inline (meio da página)

- Mesmo copy e destino do CTA principal (não crie CTAs alternativos)
- Aparecem naturalmente após seções de alto valor persuasivo
- Nunca forçados — só se a seção encerrar com uma "promessa" cumprida

---

## Gatilhos Psicológicos — Uso Responsável

Os gatilhos psicológicos são ferramentas. Usados com honestidade, reduzem o atrito para boas decisões. Usados de forma manipulativa, destroem credibilidade.

### Urgência

**Urgência legítima**: prazo real, oferta com data de término, vagas realmente limitadas.

**Urgência falsa**: countdown perpétuo que reinicia, "oferta termina em breve" sem data real.

A diferença entre os dois é a credibilidade de longo prazo. Quem comprou em 2023 com countdown "urgente" e ainda vê o mesmo countdown em 2025 nunca mais confia na sua comunicação.

**Implementação**: `add-countdown` com data real definida. Se a oferta acabou, remove o countdown — não inventa uma nova data.

### Escassez

**Escassez legítima**: número real de vagas em curso presencial, estoque real de produto físico, capacidade real de atendimento.

**Escassez falsa**: "apenas 3 vagas restantes" em produto digital infinitamente escalável.

**Implementação**: `add-text-editor` com copy claro sobre a limitação real.

### Autoridade

Diferentes de escassez e urgência, autoridade pode sempre ser usada com honestidade — porque ela é baseada em fatos verificáveis.

Tipos de autoridade:
- Anos de experiência
- Número de clientes / projetos
- Certificações e prêmios
- Aparições em mídia
- Formação acadêmica
- Casos de sucesso documentados

**Implementação**: `add-counter` para números, `add-image` para logos de mídia, `add-image-box` para certificações.

### Reciprocidade

Dar valor antes de pedir algo em troca cria uma obrigação psicológica de retribuir. Isso funciona quando o valor dado é genuíno.

Exemplos de reciprocidade efetiva:
- Conteúdo gratuito de verdade (e-book, mini-curso, checklist)
- Diagnóstico ou consultoria inicial gratuita
- Trial com acesso real ao produto

Exemplos de reciprocidade que não funcionam:
- "E-book" com 5 páginas de conteúdo genérico
- "Consultoria" que é apenas um pitch de vendas
- Trial com funcionalidades bloqueadas

---

## Otimização de Formulários

### Princípios

**Cada campo adicional reduz a taxa de conversão.** Pesquisas da Formstack indicam que remover um campo de formulário pode aumentar conversões em 25–50%.

**Regra da justificativa**: só inclua um campo se conseguir justificar por que você **precisa** dessa informação neste momento.

| Campo | Quando incluir |
|-------|---------------|
| Nome | Sempre (personalização e humanização) |
| E-mail | Sempre (canal primário de contato) |
| WhatsApp/Telefone | Apenas se o próximo passo for contato direto |
| Empresa | Apenas em contexto B2B com razão clara |
| Cargo | Apenas se segmentar a comunicação por cargo |
| Como nos conheceu | Apenas se tiver processo de análise de canal |

### Multi-step forms

Para formulários com muitos campos necessários, use abordagem em etapas:

```
Etapa 1 (baixa barreira):  Nome + E-mail
Etapa 2 (comprometido):    Telefone + Empresa
Etapa 3 (quase lá):        Informações complementares
```

Mesmo que o visitante abandone na etapa 2, você capturou o contato da etapa 1.

### Copy dos campos

| Evitar | Preferir |
|--------|---------|
| "Nome" | "Como posso te chamar?" |
| "E-mail" | "Seu melhor e-mail" |
| "Enviar" | "Quero meu acesso grátis" |
| "Cadastrar" | "Garantir minha vaga" |

O botão de submit é o CTA do formulário — ele merece a mesma atenção que qualquer outro CTA da página.

---

## Métricas de Referência

Use estes benchmarks para avaliar performance de páginas construídas:

| Tipo de página | Taxa de conversão típica | Taxa boa |
|----------------|-------------------------|----------|
| Landing Page (lead gen) | 2–5% | > 10% |
| Landing Page (vendas) | 1–3% | > 5% |
| Trial SaaS | 2–5% | > 8% |
| E-commerce (produto) | 1–3% | > 5% |
| Institucional (contato) | 0,5–2% | > 3% |

Esses números variam muito por setor, ticket e qualidade do tráfego. Use como referência, não como verdade absoluta.
