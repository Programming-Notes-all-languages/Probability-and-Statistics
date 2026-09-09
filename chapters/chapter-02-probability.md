# Chapter 2 — Probability

**Course:** EGN 2440 — Probability & Statistics with Calculus (USF Fall 2026)
**Sections:** 2.1 Sample Spaces and Events (pp. 51–54), 2.2 Axioms, Interpretations, and Properties of Probability (pp. 55–62).

## Section 2.1 — Sample Spaces and Events

### Experiments and Sample Spaces

> **Definition (Experiment).** An experiment is any activity or process whose outcome is subject to uncertainty. The term is used in a wide sense — tossing a coin, selecting cards from a deck, weighing a loaf of bread, measuring the compressive strengths of steel beams — not just planned laboratory tests.

> **Definition (Sample space).** The *sample space* of an experiment, denoted $S$, is the set of all possible outcomes of that experiment.

$S$ may be finite or infinite: inspecting one fuse for defects gives $S = \lbrace N, D \rbrace$; inspecting three fuses in sequence gives the 8 sequences of N's and D's; compiling programs one by one until the first compiles on the first run gives the **infinite** space $S = \lbrace S, FS, FFS, \ldots \rbrace$, since any positive number of failures may precede the first success.

### Events

> **Definition (Event).** An *event* is any collection (subset) of outcomes contained in the sample space. An event is *simple* if it consists of exactly one outcome and *compound* if it consists of more than one.

When an experiment is performed, event $A$ **occurs** if the resulting experimental outcome is contained in $A$. Exactly one simple event always occurs, but many compound events can occur simultaneously: with three vehicles each turning left (L) or right (R), the outcome LLL makes the simple event $\lbrace LLL \rbrace$ occur together with "at most one turns right" and "all turn the same direction," while "exactly one turns right" does not.

### Relations from Set Theory

An event is just a set, so elementary set theory applies to events:

| Operation | Notation | Meaning |
|---|---|---|
| Complement | $A'$ | all outcomes in $S$ that are **not** in $A$ |
| Union | $A \cup B$, read "A or B" | outcomes in at least one of $A$, $B$ — includes those where both occur |
| Intersection | $A \cap B$, read "A and B" | outcomes in **both** $A$ and $B$ |

> **Definition (Mutually exclusive / disjoint).** If $A \cap B = \emptyset$, where $\emptyset$ is the *null event* (containing no outcomes), then $A$ and $B$ are said to be *mutually exclusive* or *disjoint*.

Union and intersection extend beyond two events: for three events, $A \cup B \cup C$ consists of the outcomes in at least one of them and $A \cap B \cap C$ of those in all three. Events $A_1, A_2, A_3, \ldots$ are *mutually exclusive* (pairwise disjoint) if no two have any outcomes in common.

### Venn Diagrams

Events can be represented pictorially: draw a rectangle whose interior is the sample space $S$, and represent each event as the interior of a closed curve (usually a circle) contained in it. Figure 2.1 shows $A \cup B$ shaded, $A \cap B$ shaded, $A'$ shaded, and mutually exclusive events as non-overlapping circles.

## Section 2.2 — Axioms, Interpretations, and Properties of Probability

### The Three Axioms

Given an experiment with sample space $S$, the objective of probability is to assign to each event $A$ a number $P(A)$, the **probability** of $A$, giving a precise measure of the chance that $A$ will occur. All consistent assignments satisfy three axioms:

> **Axiom 1.** For any event $A$, $\; P(A) \geq 0$.
>
> **Axiom 2.** $P(S) = 1$.
>
> **Axiom 3.** If $A_1, A_2, A_3, \ldots$ is an infinite collection of disjoint events, then
> $$ P(A_1 \cup A_2 \cup A_3 \cup \cdots) = \sum_{i=1}^{\infty} P(A_i) $$

Axiom 1 formalizes that chances are nonnegative; Axiom 2 assigns the maximum probability to $S$, which by definition must occur; Axiom 3 says the chance that at least one of several disjoint events occurs is the sum of their individual chances. The finite version of Axiom 3 is *derived* from it (append empty sets to a finite disjoint collection), so the axiom list stays minimal — no axiom may be derivable from the others.

Two immediate consequences:

> **Proposition.** For any event $A$, $\; P(\emptyset) = 0$.
>
> **Proposition.** If $A_1, \ldots, A_k$ are disjoint events, then $\sum_{i=1}^{k} P(A_i) = P\left( \bigcup_{i=1}^{k} A_i \right)$ — the finite additivity rule.

### Interpreting Probability

The axioms do **not** completely determine a probability assignment; they only rule out assignments inconsistent with intuition (e.g., for a thumbtack toss, $P(U) = p$, $P(D) = 1 - p$ is consistent for *any* $p \in [0,1]$). Which value of $p$ is "correct" depends on the experiment and on one's interpretation:

> **Definition (Objective / relative-frequency interpretation).** For an experiment that can be repeated identically and independently, let $n(A)$ be the number of times event $A$ occurs in $n$ replications. The ratio
> $$ \frac{n(A)}{n} $$
> is the *relative frequency* of occurrence of $A$. As $n$ grows large this fluctuating ratio **stabilizes** to a limiting (long-run) relative frequency, and the objective interpretation identifies that limit with $P(A)$.

So "$P(B) = .1$" for an appliance needing warranty service means roughly 10% will need it *in the long run* — not exactly 1 of every 10 or 10 of every 100, since those are not the long run. The interpretation is "objective" because it rests on a property of the experiment, not on any particular observer (two observers of the same coin-toss sequence must agree). Its limitation: it applies only to **repeatable** experiments.

> **Definition (Subjective interpretation).** For inherently unrepeatable situations ("we will win the contract," "a peace agreement will be signed"), probabilities are assigned from an individual's beliefs and prior information, so different observers may legitimately assign different values.

### More Probability Properties

All derived from the axioms:

> **Proposition.** For any event $A$, $\; P(A) \leq 1$.
> (Since $P(A') \geq 0$ and $1 = P(A) + P(A') \geq P(A)$.)

> **Proposition (Complement rule).** For any event $A$,
> $$ P(A) + P(A') = 1 \qquad\Longleftrightarrow\qquad P(A) = 1 - P(A') $$
> because $A$ and $A'$ are disjoint with union $S$.

The complement rule is the workhorse of "at least one" problems: when $P(A)$ is hard to compute directly, compute $P(A')$ instead. A series system of five components fails if *any* component fails (31 outcomes), but works only for the single outcome SSSSS — so $P(\text{fail}) = 1 - P(SSSSS)$.

> **Proposition (Addition rule, disjoint).** If events $A$ and $B$ are mutually exclusive, then
> $$ P(A \cup B) = P(A) + P(B) $$

For events that are *not* mutually exclusive, adding $P(A)$ and $P(B)$ double-counts the outcomes in $A \cap B$:

> **Proposition (General addition rule).** For any two events $A$ and $B$,
> $$ P(A \cup B) = P(A) + P(B) - P(A \cap B) $$

Proof idea: decompose $A \cup B$ into the disjoint pieces $A$ and $(B \cap A')$, where $B \cap A'$ is the part of $B$ outside $A$ (Figure 2.4); since $P(B) = P(A \cap B) + P(A' \cap B)$, substituting gives the rule.

The union of three events extends analogously:

$$ P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C) $$

Adding the three single probabilities counts pairwise intersections twice (hence subtracted), but this subtracts $P(A \cap B \cap C)$ one time too often, so it is added back. Verify with a Venn diagram (Figure 2.6).

### Determining Probabilities Systematically

For a sample space that is finite or **countably infinite** (outcomes listable in an infinite sequence — first, second, third, …), let $E_1, E_2, E_3, \ldots$ be the simple events. The sensible strategy:

1. Assign each simple event probability $P(E_i)$ subject to $\sum P(E_i) = 1$.
2. For any compound event $A$, add the simple-event probabilities inside it:
$$ P(A) = \sum_{E_i \in A} P(E_i) $$

### Equally Likely Outcomes

In many experiments (fair coin, fair die, well-shuffled deck) it is reasonable to assign equal probability $p$ to all $N$ simple events. Since $\sum_{i=1}^{N} p = 1$, we get $p = 1/N$: **each outcome has probability $1/N$.**

With $N(A)$ denoting the number of outcomes in event $A$:

$$ P(A) = \frac{N(A)}{N} $$

When outcomes are equally likely, computing probabilities reduces to **counting**: count the favorable outcomes and divide by the total.

## Quick Reference

| Symbol / concept | Meaning |
|---|---|
| Experiment | any activity or process with an uncertain outcome — wide sense, not just lab tests |
| $S$ | sample space — set of all possible outcomes; finite ($\lbrace N, D \rbrace$, 8 fuse sequences) or infinite ($\lbrace S, FS, FFS, \ldots \rbrace$) |
| Event | any subset of $S$; *simple* = exactly one outcome, *compound* = more than one |
| Occurrence | $A$ occurs when the experimental outcome lies in $A$; exactly one simple event always occurs, many compound events can occur at once |
| $A'$ | complement — outcomes in $S$ not in $A$ |
| $A \cup B$ | union ("A or B") — outcomes in at least one of the two, including both |
| $A \cap B$ | intersection ("A and B") — outcomes in both |
| $\emptyset$ | null event (no outcomes); $A \cap B = \emptyset \Rightarrow A$, $B$ mutually exclusive / disjoint |
| Pairwise disjoint | events $A_1, A_2, \ldots$ with no two sharing an outcome |
| Venn diagram | rectangle = $S$, closed curve = event; depicts unions, intersections, complements, disjointness (Figure 2.1) |
| $P(A)$ | probability of $A$ — number measuring the chance $A$ occurs; assignments must satisfy the three axioms |
| Axiom 1 / 2 / 3 | $P(A) \geq 0$; $\; P(S) = 1$; disjoint $A_i$: $P\left( \bigcup_{i=1}^{\infty} A_i \right) = \sum_{i=1}^{\infty} P(A_i)$ |
| Derived: null + finite additivity | $P(\emptyset) = 0$; disjoint $A_1, \ldots, A_k$: $\sum_{i=1}^{k} P(A_i) = P\left( \bigcup_{i=1}^{k} A_i \right)$ |
| Objective interpretation | repeatable experiments: relative frequency $n(A)/n$ stabilizes as $n \to \infty$; its limit is $P(A)$ (long-run, not exact short-run counts) |
| Subjective interpretation | unrepeatable situations: probabilities from beliefs/prior information — may differ between observers |
| Complement rule | $P(A) + P(A') = 1$, i.e. $P(A) = 1 - P(A')$; also gives $P(A) \leq 1$. Use for "at least one" problems: compute the complement instead |
| Addition rule (disjoint) | $A \cap B = \emptyset \Rightarrow P(A \cup B) = P(A) + P(B)$ |
| General addition rule | $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ — subtracts the double-counted intersection (Figure 2.4) |
| Three-event union | $P(A \cup B \cup C) = P(A)+P(B)+P(C) - P(A\cap B) - P(A\cap C) - P(B\cap C) + P(A\cap B\cap C)$ (Figure 2.6) |
| Systematic assignment | finite/countably infinite $S$: assign simple-event probabilities with $\sum P(E_i) = 1$, then $P(A) = \sum_{E_i \in A} P(E_i)$ |
| Equally likely outcomes | each of the $N$ outcomes has probability $1/N$, so $P(A) = N(A)/N$ — probability reduces to counting favorable vs. total outcomes |
