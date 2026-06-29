# ⚽ Matemática da Copa do Mundo 2026
### Caderno Temático — NotebookLM

> Explorando as propriedades matemáticas da fase de grupos com 48 times, 12 grupos e 4 equipes por grupo.

---

## 📌 Contexto e Objetivos

A Copa do Mundo FIFA 2026 representa a maior reestruturação da história do torneio: de 32 para **48 seleções**, organizadas em **12 grupos de 4 times** cada. Essa mudança cria um novo universo matemático — novas combinações de jogos, novas probabilidades de classificação e novos critérios de desempate.

### Objetivos de Estudo

- Derivar e aplicar equações de pontuação para a fase de grupos
- Calcular combinações de jogos e pontuações máximas por equipe
- Analisar probabilidades de classificação em função de pontos e saldo de gols
- Compreender metodologias estatísticas avançadas (SDR, Monte Carlo) aplicadas ao futebol
- Explorar como o novo formato altera a estratégia matemática das seleções

---

## 📚 Curadoria de Fontes

| # | Fonte | Tipo | Link |
|---|-------|------|------|
| 1 | Tabela de Classificação Oficial — FIFA 2026 | Dados Oficiais | [fifa.com](https://www.fifa.com/pt/tournaments/mens/worldcup/canadamexicousa2026/standings) |
| 2 | *Predicting the 2026 FIFA World Cup with Sufficient Dimension Reduction of Elo Rating Histories* | Artigo Científico (arXiv) | [Rezaei & Samadi] | (https://arxiv.org/abs/2606.24171)
| 3 | Regulamento de Classificação FIFA 2026 | Documento Oficial | [FIFA.com] | (https://www.fifa.com/en/tournaments/mens/worldcup/canadamexicousa2026/articles/groups-how-teams-qualify-tie-breakers)
| 4 | Análises de probabilidade de classificação | Portal esportivo | Lance! / Football Meets Data |

> **Nota:** As fontes 1 e 2 foram carregadas diretamente no NotebookLM como base para as análises.

---

## 🧠 Engenharia de Prompts e Cicatrizes de Aprendizado

### Prompt Base — Definição do Escopo

**Prompt:**
```
Estou fazendo um estudo sobre a matemática da classificação da copa do mundo de 2026.
E para isso eu vou contar com a sua ajuda em:
- Manipulação de equações
- Determinação de probabilidades
- Estatísticas simples
```

**Resposta obtida:**
O NotebookLM contextualizou o formato de 48 seleções e solicitou o upload das fontes (regulamento, tabelas de resultados e dados históricos) para iniciar as análises com precisão.

**Dificuldade:** Nenhuma — resposta objetiva e bem direcionada.

---

### Prompt 1 — Equação de Pontuação

**Prompt:**
```
Vamos começar de forma simples:

Tomando:
  e: Número de empates (valem 1 ponto)
  v: Número de vitórias (valem 3 pontos)
  d: Número de derrotas (valem 0 pontos)

Qual a expressão que determina o número de pontos p após n jogos p(n)?
```

**Resposta obtida:**

A IA derivou corretamente a equação fundamental:

$$p = 3v + e$$

Com a restrição: $n = v + e + d$

As derrotas ($d$) não somam pontos, mas compõem o total de jogos disputados.

**Dificuldade:** Nenhuma.

---

### Prompt 2 — Combinações e Pontuação Máxima

**Prompt:**
```
- Se são 4 equipes que jogam entre si 1 única vez (Combinação), então quantos jogos
  são no total do grupo e para cada equipe?
- Com o número obtido acima, qual o máximo de pontos possíveis de serem feitos
  por cada equipe?
```

**Resposta obtida:**

- **Total de jogos por grupo:** $C(4,2) = \frac{4!}{2! \cdot 2!} = 6$ jogos
- **Jogos por equipe:** 3 partidas (enfrenta cada um dos 3 adversários)
- **Pontuação máxima por equipe:** $3 \times 3 = 9$ pontos (3 vitórias)

> Com um líder em 9 pontos, a disputa pelas vagas restantes torna-se matematicamente apertada.

**⚠️ Dificuldade encontrada (cicatriz):** A IA gerou confusão inicial entre *pontos totais do grupo* (soma de todos os pontos distribuídos em 6 jogos) e *pontos por equipe* (máximo individual de 9). Foi necessário reformular a pergunta para separar os dois conceitos. **Lição:** especificar o sujeito da pergunta ("por equipe" vs. "no grupo total") evita ambiguidades.

---

### Prompt 3 — Relatório de Probabilidades (Studio)

**Prompt:**
```
Crie um relatório sobre a probabilidade de classificação da Copa do Mundo de 2026:
  - Tabela Central: Pontuação vs. Probabilidade de Classificação
  - O Papel Crítico do Saldo de Gols (Tiebreakers)
  - Metodologia de Previsão de Elite: O Estudo arXiv
  - Projeções de Desempenho por Seleção
```

**Resposta obtida (via Studio):** Relatório completo — consolidado na seção Miniguia abaixo.

**Dificuldade:** Nenhuma — o uso do Studio com estrutura de tópicos bem definida produziu resultado direto e organizado.

---

## 📖 Miniguia de Estudo — Entrega Final

### 1. Resumos Estruturados

#### 1.1 O Novo Formato da Copa 2026

- **48 seleções** → **12 grupos** de **4 times**
- Total de jogos na fase de grupos: $12 \times 6 = 72$ partidas
- Total do torneio: **104 jogos** (vs. 64 no Catar 2022)
- **66,7% das equipes avançam**: os 2 primeiros de cada grupo + os 8 melhores terceiros colocados
- Novidade: introdução do **Round of 32** (16-avos de final)

#### 1.2 Matemática da Pontuação

| Resultado | Pontos |
|-----------|--------|
| Vitória   | 3      |
| Empate    | 1      |
| Derrota   | 0      |

**Equação geral:** $p = 3v + e$, com $n = v + e + d$

**Máximo por equipe em 3 jogos:** $p_{max} = 9$ pontos

#### 1.3 Probabilidades de Classificação (Round of 32)

| Pontos | Saldo de Gols (GD) | Prob. de Avanço |
|--------|-------------------|-----------------|
| 6 ou 5 | Qualquer          | **100%**        |
| 4      | GD ≥ 0            | **100%**        |
| 4      | GD até −3         | 99,7%           |
| 3      | GD = 0            | 99,1%           |
| 3      | GD até −5         | > 50%           |
| 2      | GD ≥ −1           | ~16,6%          |
| 1      | Qualquer          | Remota          |

> **Porto seguro estatístico:** 4 pontos garantem classificação em quase todos os cenários.

#### 1.4 O Papel Crítico do Saldo de Gols

No sistema com 8 vagas para melhores terceiros, o saldo de gols deixa de ser critério secundário e passa a ser **variável crítica de sobrevivência**. A hierarquia de desempate da FIFA é:

1. Pontos
2. Saldo de gols
3. Gols marcados
4. Fair-play (cartões)
5. Ranking FIFA

**Implicação estratégica:** Times com 2 pontos devem priorizar fechamento defensivo na 3ª rodada — manter GD ≥ −1 preserva 16,6% de chance de classificação histórica.

#### 1.5 Metodologia de Previsão Avançada (Estudo arXiv)

O modelo de **Redução de Dimensão Suficiente (SDR)** — aplicado por Rezaei & Samadi — supera regressões de Poisson tradicionais:

- Técnicas utilizadas: **SIR** e **SAVE** sobre histórico do Elo Rating
- **Ranked Probability Score (RPS):** caiu de 0,219 → **0,127** com SDR
- O modelo SAVE (d=2) introduz uma "segunda direção" que refina probabilidades de empate
- Após **5.000 simulações de Monte Carlo**:

| Seleção   | Prob. de Título | Prob. Oitavas (Round of 16) |
|-----------|----------------|------------------------------|
| Espanha   | 16,6%          | 74,9%                        |
| Argentina | 16,1%          | 73,5%                        |
| França    | 13,7%          | 71,5%                        |

---

### 2. Glossário de Conceitos-Chave

| Termo | Definição |
|-------|-----------|
| **Combinação C(n,k)** | Número de formas de escolher k elementos de n sem repetição e sem ordem: $C(n,k) = \frac{n!}{k!(n-k)!}$ |
| **Saldo de Gols (GD)** | Diferença entre gols marcados e sofridos. Critério de desempate após pontos. |
| **Round of 32** | Nova fase de 16-avos de final introduzida em 2026, com 32 equipes. |
| **Elo Rating** | Sistema de pontuação que estima a força relativa de seleções com base em resultados históricos. |
| **SDR (Sufficient Dimension Reduction)** | Técnica estatística que reduz a dimensionalidade de séries históricas mantendo informações preditivas. |
| **RPS (Ranked Probability Score)** | Métrica de avaliação de modelos probabilísticos; quanto menor, mais preciso o modelo. |
| **Monte Carlo** | Método de simulação que usa aleatoriedade repetida (aqui, 5.000 vezes) para estimar probabilidades. |
| **Melhores Terceiros** | Os 8 melhores terceiros colocados entre os 12 grupos, que garantem vaga no Round of 32. |
| **Fair-Play** | Critério de desempate baseado em cartões amarelos e vermelhos recebidos. |

---

### 3. Prompts Reutilizáveis para Revisão Futura

```
📌 PROMPT A — Pontuação e Equações
"Dado que uma seleção fez [V] vitórias, [E] empates e [D] derrotas,
 qual sua pontuação total, aproveitamento percentual e posição estimada no grupo?"
```

```
📌 PROMPT B — Cenários de Classificação
"Com [X] pontos e saldo de gols de [Y], qual a probabilidade estimada de
 uma equipe avançar como melhor terceira colocada na Copa 2026?"
```

```
📌 PROMPT C — Análise Combinatória
"Em um grupo de [N] equipes onde cada dupla joga [K] vez(es),
 quantos jogos acontecem no total e quantos cada equipe disputa?"
```

```
📌 PROMPT D — Comparativo de Modelos Preditivos
"Compare o desempenho do modelo de regressão de Poisson com o SDR (SIR/SAVE)
 para prever resultados de futebol. Quais as limitações de cada abordagem?"
```

```
📌 PROMPT E — Estratégia de Saldo de Gols
"Dado que [SELEÇÃO] tem [P] pontos na 3ª rodada e enfrenta um adversário com [P2] pontos,
 qual estratégia (ofensiva ou defensiva) maximiza suas chances de classificação?"
```

---

*Caderno desenvolvido com NotebookLM | Copa do Mundo FIFA 2026 — Canadá, México e EUA*
