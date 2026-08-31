# Respostas — Lista 1 (Aulas 01 e 02)

## Linguagens Formais, Alfabeto, Linguagens e Gramáticas

**Aluno:** Luís Filipe Silva Santos
**Disciplina:** Linguagens Formais e Autômatos

---

## Exercício 1 — Alfabeto

Considere $\Sigma = \{a, b, c\}$.

1. **Quantos símbolos existem no alfabeto?** → 3 símbolos.
2. **Quais são os símbolos?** → $a$, $b$ e $c$.
3. **O símbolo `a` pertence ao alfabeto?** → Sim: $a \in \Sigma$.
4. **O símbolo `d` pertence ao alfabeto?** → Não: $d \notin \Sigma$.
5. **Uma palavra formada por símbolos desse alfabeto:** → `abc` (também valem `a`, `bca`, `cab`, etc.).

---

## Exercício 2 — Palavras sobre um alfabeto

Considere $\Sigma = \{0, 1\}$.

| Sequência | Válida?      | Justificativa                              |
| --------- | ------------ | ------------------------------------------ |
| `0101`    | Válida       | Todos os símbolos são `0` ou `1`.          |
| `00110`   | Válida       | Todos os símbolos são `0` ou `1`.          |
| `012`     | Não válida   | O símbolo `2` não pertence ao alfabeto.    |
| `111`     | Válida       | Todos os símbolos pertencem ao alfabeto.   |
| `10a`     | Não válida   | O símbolo `a` não pertence ao alfabeto.    |

---

## Exercício 3 — Pertinência de símbolos e palavras

Considere $\Sigma = \{0, 1\}$.

1. $0 \in \Sigma$ → **Verdadeiro** (é um símbolo do alfabeto).
2. $1 \in \Sigma$ → **Verdadeiro** (é um símbolo do alfabeto).
3. $01 \in \Sigma$ → **Falso** (`01` é uma palavra com dois símbolos, não um símbolo individual).
4. $01 \in \Sigma^*$ → **Verdadeiro** (é uma palavra formada por símbolos do alfabeto).
5. $2 \in \Sigma$ → **Falso** (`2` não pertence ao alfabeto).
6. $101 \in \Sigma^*$ → **Verdadeiro** (todos os símbolos de `101` pertencem ao alfabeto).

---

## Exercício 4 — Linguagem

Considere $L = \{0, 01, 011, 0111\}$.

1. $0 \in L$ → **Sim** (está no conjunto).
2. $01 \in L$ → **Sim** (está no conjunto).
3. $0111 \in L$ → **Sim** (está no conjunto).
4. $10 \in L$ → **Não** (não é um dos elementos do conjunto).
5. $111 \in L$ → **Não** (não é um dos elementos do conjunto).
6. $011 \in L$ → **Sim** (está no conjunto).

---

## Exercício 5 — Descrevendo uma linguagem por padrão

Considere $L = \{b^n \mid n \geq 1\}$.

1. **Cinco primeiras palavras:**

```text
b
bb
bbb
bbbb
bbbbb
```

2. **Significado de $b^n$:** representa `n` ocorrências do símbolo `b` (ex.: $b^3 = bbb$).

3. **A palavra `bbbbbb` pertence à linguagem?** → **Sim.** Ela é $b^6$, e como $6 \geq 1$, temos $bbbbbb \in L$.

4. **A palavra vazia ($\varepsilon$) pertence à linguagem?** → **Não.** A condição exige $n \geq 1$, e a palavra vazia teria $n = 0$. Logo, $\varepsilon \notin L$.

---

## Exercício 6 — Linguagem vazia e palavra vazia

**Diferença entre $L = \emptyset$ e $L = \{\varepsilon\}$:**

- $L = \emptyset$ é uma linguagem **sem nenhuma palavra** — o conjunto é totalmente vazio.
- $L = \{\varepsilon\}$ é uma linguagem que **possui uma palavra**: a palavra vazia. Ela tem uma palavra, só que essa palavra não tem nenhum símbolo (comprimento zero).

Portanto, são coisas diferentes: $\emptyset \neq \{\varepsilon\}$.

1. **Qual delas possui uma palavra?** → $L = \{\varepsilon\}$.
2. **Qual delas não possui nenhuma palavra?** → $L = \emptyset$.
3. **Qual é o comprimento da palavra $\varepsilon$?** → Zero: $|\varepsilon| = 0$.

---

## Exercício 7 — Estrutura de uma gramática

Considere $G = (\{S, A\}, \{0, 1\}, P, S)$ com $P = \{S \rightarrow 0A,\ A \rightarrow 1\}$.

1. **Conjunto de variáveis:** $V = \{S, A\}$.
2. **Conjunto de terminais:** $T = \{0, 1\}$.
3. **Conjunto de produções:** $P = \{S \rightarrow 0A,\ A \rightarrow 1\}$.
4. **Símbolo inicial:** $S$.
5. **Palavra que pode ser gerada:**

$$
S \Rightarrow 0A \Rightarrow 01
$$

A gramática gera a palavra **`01`**.

---

## Exercício 8 — Como ler e aplicar uma produção

Considere $S \rightarrow 0S$, começando com $S$.

1. **Aplicando uma vez:** $S \Rightarrow 0S$
2. **Aplicando duas vezes:** $S \Rightarrow 0S \Rightarrow 00S$
3. **Aplicando três vezes:** $S \Rightarrow 0S \Rightarrow 00S \Rightarrow 000S$
4. **Sequência completa de derivação:**

$$
S \Rightarrow 0S \Rightarrow 00S \Rightarrow 000S
$$

**Observação:** a derivação ainda não terminou, pois ainda existe o não terminal $S$.

---

## Exercício 9 — Derivação completa de uma palavra

Usando $G: \{S \rightarrow aS,\ S \rightarrow b\}$, gerar `aaab`:

$$
S \Rightarrow aS \Rightarrow aaS \Rightarrow aaaS \Rightarrow aaab
$$

Cada aplicação de $S \rightarrow aS$ adiciona um `a`. Quando já temos os três `a`, usamos $S \rightarrow b$ para finalizar. Portanto, $aaab \in L(G)$.

---

## Exercício 10 — Identificando palavras geradas por uma gramática

Gramática $G: \{S \rightarrow 0S,\ S \rightarrow 1\}$.

1. **`1`** → **Sim.** $S \Rightarrow 1$
2. **`01`** → **Sim.** $S \Rightarrow 0S \Rightarrow 01$
3. **`001`** → **Sim.** $S \Rightarrow 0S \Rightarrow 00S \Rightarrow 001$
4. **`0001`** → **Sim.** $S \Rightarrow 0S \Rightarrow 00S \Rightarrow 000S \Rightarrow 0001$
5. **`101`** → **Não.** Depois de aplicar $S \rightarrow 1$ a derivação termina; não é possível produzir mais símbolos. Como `101` tem símbolos após o `1`, não pode ser gerada.
6. **`1001`** → **Não.** As palavras válidas têm o formato "zero ou mais `0`, seguido de um único `1` no final" (`00...01`). `1001` começa com `1` e ainda tem símbolos depois, o que não é permitido.

---

# Checklist de estudo

- **Explicar o que é um alfabeto:** é um conjunto finito de símbolos usados para formar palavras (ex.: $\Sigma = \{0, 1\}$).
- **Identificar os símbolos de um alfabeto:** são os elementos individuais do conjunto $\Sigma$; em $\{a, b, c\}$ os símbolos são $a$, $b$ e $c$.
- **Diferenciar símbolo de palavra:** símbolo é um elemento único do alfabeto (`a`); palavra é uma sequência de símbolos (`ab`).
- **Explicar o que é uma linguagem:** é um conjunto de palavras formadas sobre um alfabeto.
- **Verificar se uma palavra pertence a uma linguagem:** basta checar se ela é um dos elementos do conjunto que define a linguagem.
- **Interpretar $\Sigma^*$:** é o conjunto de todas as palavras possíveis sobre $\Sigma$, incluindo a palavra vazia $\varepsilon$.
- **Diferenciar $\emptyset$ de $\varepsilon$:** $\emptyset$ é uma linguagem sem nenhuma palavra; $\varepsilon$ é uma palavra de comprimento zero (a linguagem $\{\varepsilon\}$ tem uma palavra).
- **Interpretar $w \in L$:** significa que a palavra $w$ pertence à linguagem $L$.
- **Identificar os componentes de uma gramática:** $G = (V, T, P, S)$ — variáveis, terminais, produções e símbolo inicial.
- **Ler uma regra como $S \rightarrow aS$:** lê-se "S produz aS", ou seja, $S$ pode ser substituído por $aS$.
- **Realizar uma derivação passo a passo:** aplicar as produções uma a uma, substituindo os não terminais até chegar à palavra final (ex.: $S \Rightarrow aS \Rightarrow ab$).
- **Identificar quando uma derivação termina:** termina quando não há mais nenhum não terminal na sequência, só terminais.
- **Determinar se uma palavra pode ser gerada por uma gramática:** tentar derivá-la aplicando as produções; se existe uma sequência de derivação que a produz, ela pertence a $L(G)$.

---

# Desafio final

Gramática: $G: \{S \rightarrow aS,\ S \rightarrow b\}$

**1. A palavra `b` pode ser gerada?**
Sim. Aplicando direto $S \rightarrow b$:

$$
S \Rightarrow b
$$

**2. A palavra `ab` pode ser gerada?**
Sim.

$$
S \Rightarrow aS \Rightarrow ab
$$

**3. A palavra `aab` pode ser gerada?**
Sim.

$$
S \Rightarrow aS \Rightarrow aaS \Rightarrow aab
$$

**4. A palavra `aaab` pode ser gerada?**
Sim.

$$
S \Rightarrow aS \Rightarrow aaS \Rightarrow aaaS \Rightarrow aaab
$$

**5. A palavra `aba` pode ser gerada?**
**Não.** A única regra que encerra a derivação é $S \rightarrow b$, que coloca um `b` no final. Depois disso não há mais não terminal para produzir o `a` final. Como `aba` termina em `a`, ela não pode ser gerada.

**6. Derivação completa de `aaaab`:**

$$
S \Rightarrow aS \Rightarrow aaS \Rightarrow aaaS \Rightarrow aaaaS \Rightarrow aaaab
$$

**7. Padrão das palavras geradas por essa gramática:**
A gramática gera palavras com **zero ou mais `a` seguidos de um único `b` no final**. Ou seja, todas as palavras têm a forma $a^n b$ com $n \geq 0$:

$$
L(G) = \{a^n b \mid n \geq 0\}
$$

Cada aplicação de $S \rightarrow aS$ acrescenta um `a`, e a derivação sempre termina com $S \rightarrow b$, garantindo exatamente um `b` no fim.
