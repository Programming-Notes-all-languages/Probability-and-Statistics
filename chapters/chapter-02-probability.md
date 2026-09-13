# Chapter 2 — Probability

**Course:** EGN 2440 — Probability & Statistics with Calculus (USF Fall 2026)
**Sections:** 2.1 Sample Spaces and Events (pp. 51–54), 2.2 Axioms, Interpretations, and Properties of Probability (pp. 55–62), 2.3 Counting Techniques (pp. 64–72), 2.4 Conditional Probability (pp. 73–80), 2.5 Independence (pp. 83–86).

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

$$ P(A_1 \cup A_2 \cup A_3 \cup \cdots) = \sum_{i=1}^{\infty} P(A_i) $$

Axiom 1 formalizes that chances are nonnegative; Axiom 2 assigns the maximum probability to $S$, which by definition must occur; Axiom 3 says the chance that at least one of several disjoint events occurs is the sum of their individual chances. The finite version of Axiom 3 is *derived* from it (append empty sets to a finite disjoint collection), so the axiom list stays minimal — no axiom may be derivable from the others.

Two immediate consequences:

> **Proposition.** For any event $A$, $\; P(\emptyset) = 0$.
>
> **Proposition.** If $A_1, \ldots, A_k$ are disjoint events, then $\sum_{i=1}^{k} P(A_i) = P\left( \bigcup_{i=1}^{k} A_i \right)$ — the finite additivity rule.

### Interpreting Probability

The axioms do **not** completely determine a probability assignment; they only rule out assignments inconsistent with intuition (e.g., for a thumbtack toss, $P(U) = p$, $P(D) = 1 - p$ is consistent for *any* $p \in [0,1]$). Which value of $p$ is "correct" depends on the experiment and on one's interpretation:

> **Definition (Objective / relative-frequency interpretation).** For an experiment that can be repeated identically and independently, let $n(A)$ be the number of times event $A$ occurs in $n$ replications. The ratio

$$ \frac{n(A)}{n} $$

> is the *relative frequency* of occurrence of $A$. As $n$ grows large this fluctuating ratio **stabilizes** to a limiting (long-run) relative frequency, and the objective interpretation identifies that limit with $P(A)$.

So "$P(B) = .1$" for an appliance needing warranty service means roughly 10% will need it *in the long run* — not exactly 1 of every 10 or 10 of every 100, since those are not the long run. The interpretation is "objective" because it rests on a property of the experiment, not on any particular observer (two observers of the same coin-toss sequence must agree). Its limitation: it applies only to **repeatable** experiments.

> **Definition (Subjective interpretation).** For inherently unrepeatable situations ("we will win the contract," "a peace agreement will be signed"), probabilities are assigned from an individual's beliefs and prior information, so different observers may legitimately assign different values.

### More Probability Properties

All derived from the axioms:

> **Proposition.** For any event $A$, $\; P(A) \leq 1$.
> (Since $P(A') \geq 0$ and $1 = P(A) + P(A') \geq P(A)$.)

> **Proposition (Complement rule).** For any event $A$,

$$ P(A) + P(A') = 1 \qquad\Longleftrightarrow\qquad P(A) = 1 - P(A') $$

> because $A$ and $A'$ are disjoint with union $S$.

The complement rule is the workhorse of "at least one" problems: when $P(A)$ is hard to compute directly, compute $P(A')$ instead. A series system of five components fails if *any* component fails (31 outcomes), but works only for the single outcome SSSSS — so $P(\text{fail}) = 1 - P(SSSSS)$.

> **Proposition (Addition rule, disjoint).** If events $A$ and $B$ are mutually exclusive, then

$$ P(A \cup B) = P(A) + P(B) $$

For events that are *not* mutually exclusive, adding $P(A)$ and $P(B)$ double-counts the outcomes in $A \cap B$:

> **Proposition (General addition rule).** For any two events $A$ and $B$,

$$ P(A \cup B) = P(A) + P(B) - P(A \cap B) $$

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

## Section 2.3 — Counting Techniques

### Why Counting

When all outcomes of an experiment are equally likely, $P(A) = N(A)/N$ (Eq. 2.1), so computing probabilities reduces to counting favorable and total outcomes. If the sample space is small enough to list, no general rules are needed; for large spaces listing is prohibitive, and counting rules give $N$ and $N(A)$ directly. The rules also apply when outcomes are *not* equally likely, and several of them reappear in Chapter 3's probability distributions.

### The Product Rule for Ordered Pairs

An **ordered pair** $(O_1, O_2)$ is different from $(O_2, O_1)$.

> **Proposition (Product rule).** If the first element of a pair can be selected in $n_1$ ways and, for each such choice, the second element can be selected in $n_2$ ways, then there are $n_1 n_2$ ordered pairs.

Equivalent interpretation: an operation carried out in **two stages** — if stage 1 has $n_1$ possible performances and, for each way of performing stage 1, stage 2 has $n_2$ ways, then the two-stage sequence can be performed in $n_1 n_2$ ways. The rule stays valid even when the *set* of possible second elements depends on which first element was chosen, as long as there are exactly $n_2$ choices for each first choice (e.g., choosing an obstetrician and a pediatrician from the same clinic: 4 obstetricians with 3 pediatricians per clinic gives $(4)(3) = 12$ pairs).

### Tree Diagrams

A **tree diagram** represents all possibilities pictorially: from a starting point, one *first-generation branch* for each possible first element; from the tip of each first branch, one *second-generation branch* for each possible second element. The tips of the $n_1 n_2$ second-generation branches correspond one-to-one with the ordered pairs — this verifies the product rule. Unlike the product rule, a tree diagram does **not** require equal numbers of branches at each level (e.g., clinics with different numbers of pediatricians), so it can represent experiments to which the product rule does not apply.

### The General Product Rule for k-Tuples

An ordered collection of $k$ objects is called a **k-tuple** (a pair = 2-tuple, a triple = 3-tuple).

> **Proposition (Product rule for k-tuples).** If the first element has $n_1$ possible choices; for each choice of the first element, the second has $n_2$ possible choices; …; and for each possible choice of the first $k-1$ elements, the $k$th element has $n_k$ choices, then there are

$$ n_1 n_2 \cdots n_k $$

> k-tuples.

Equivalent interpretation: an operation in **$k$ stages**, where stage $i$ can be performed in $n_i$ ways for each way of performing the earlier stages. Visualized by adding generations to a tree diagram — each possible k-tuple corresponds to the tip of exactly one $k$th-generation branch.

### Permutations and Combinations

From a group of $n$ **distinct** objects, the number of ways to select $k$ objects depends on whether order matters. These formulas assume selection **without replacement**, so $0 \leq k \leq n$.

> **Definition.** An *ordered* subset is called a **permutation**; the number of permutations of size $k$ that can be formed from $n$ objects is denoted $P_{k,n}$. An *unordered* subset is called a **combination**, and its count is written $\binom{n}{k}$, read "n choose k."

For a positive integer $m$, factorial notation is

$$
m! = m(m-1)(m-2)\cdots(2)(1),
$$

with $0! = 1$.

#### Permutations: Order Matters

The first selected position has $n$ choices, the second has $n-1$, and this continues until $k$ positions are filled. By the product rule,

> **Proposition.**

$$
P_{k,n} = n(n-1)\cdots(n-k+1) = \frac{n!}{(n-k)!}.
$$

When all $n$ objects are arranged, $k=n$, so the number of complete orderings is $n!$.

#### Combinations: Order Does Not Matter

Each combination of $k$ objects can be arranged in $k!$ different orders. Permutations count all of those orders separately, so dividing by $k!$ removes the duplicate orderings:

> **Proposition.**

$$
\binom{n}{k} = \frac{P_{k,n}}{k!} = \frac{n!}{k!(n-k)!}.
$$

Boundary values: $\binom{n}{0} = 1$ and $\binom{n}{n} = 1$ (only one way to choose none or all), and $\binom{n}{1} = n$.

| Selection question | Use | Count |
|---|---|---|
| Does changing the order produce a different outcome? | Permutation | $P_{k,n} = \dfrac{n!}{(n-k)!}$ |
| Does only the selected group matter? | Combination | $\binom{n}{k} = \dfrac{n!}{k!(n-k)!}$ |

The relationship $P_{k,n} = k!\binom{n}{k}$ expresses the difference directly: every unordered group corresponds to $k!$ ordered arrangements.

### Counting in Two-Group Sampling

When a sample of $k$ items is drawn without replacement from a population of $N = N_1 + N_2$ split into two groups, the number of samples containing exactly $j$ items from group 1 (hence $k-j$ from group 2) is $\binom{N_1}{j}\binom{N_2}{k-j}$ — a product-rule argument over the two independent choices — while the total number of possible samples is $\binom{N}{k}$. Under equally likely sampling,
$$ P(\text{exactly } j \text{ from group 1}) = \frac{\binom{N_1}{j}\binom{N_2}{k-j}}{\binom{N}{k}} $$
This is the counting pattern behind the hypergeometric distribution (Chapter 3). For compound events like "at least $j$ from group 1," decompose into disjoint exact-count events and sum their probabilities.

## Section 2.4 — Conditional Probability

### Conditioning on Information

The probability assigned to an event depends on what is known about the experimental situation when the assignment is made, so $P(A)$ is now regarded as the **unconditional** (original) probability of $A$. When partial information becomes available — specifically that another event $B$ has occurred — the probability of $A$ may need revision:

> **Definition (Conditional probability).** For any two events $A$ and $B$ with $P(B) > 0$, the *conditional probability* of $A$ given that $B$ has occurred is

$$ P(A \mid B) = \frac{P(A \cap B)}{P(B)} $$

> where $B$ is called the **conditioning event**.

When outcomes are equally likely, this reduces to counting within a shrunken sample space: after $B$ occurs, only the $N(B)$ outcomes in $B$ remain possible, and $A$ occurs exactly when one of the $N(A \cap B)$ intersection outcomes occurs — so $P(A \mid B) = N(A \cap B)/N(B)$. The Venn diagram (Figure 2.8) shows why: given $B$, the relevant sample space is no longer $S$ but $B$ itself, and the factor $1/P(B)$ normalizes so that this new "sample space" has probability 1 ($P(B \mid B) = 1$).

In general $P(A \mid B) \neq P(B \mid A)$, and both can differ from $P(A)$ — conditioning changes the reference class. (A negative blood test lowers but does not zero out the probability of disease, since tests are not infallible.)

### The Multiplication Rule

Multiplying the definition by $P(B)$ gives its most useful form:

> **Proposition (Multiplication rule).**

$$ P(A \cap B) = P(A \mid B)\,P(B) $$

This is important because often it is $P(A \cap B)$ that is desired, while both $P(B)$ and $P(A \mid B)$ are specified directly by the problem. The rule shines when the experiment consists of several stages in succession: if $B$ describes the outcome of stage 1 and $A$ that of stage 2, then $P(A \mid B)$ — conditioning on what occurs first — is often known. It extends to more than two stages; for three events occurring in order,

$$ P(A_1 \cap A_2 \cap A_3) = P(A_3 \mid A_1 \cap A_2)\,P(A_2 \mid A_1)\,P(A_1) $$

### Tree Diagrams and Prior/Posterior Probabilities

For a multi-stage experiment, draw a **tree diagram**: one branch per possible outcome at each stage. The initial branches carry $P(A_i)$; the second-generation branches carry conditional probabilities such as $P(B \mid A_i)$; and next to each tip is written the product of the probabilities along the path — just the multiplication rule in action, giving the joint probability of the full sequence.

The tree also makes explicit the distinction between **prior** and **posterior** probabilities: $P(A_i)$ is the *prior* (before observing the second-stage outcome), while $P(A_i \mid B)$ is the *posterior* — the revised probability after learning that $B$ occurred. The posterior moves in the direction of the evidence: a partition event that makes $B$ more likely gains share, one that makes it less likely loses share (e.g., a product line with a higher repair rate gets its brand share increased when a returned unit needs repair).

### The Law of Total Probability

> **Definition (Mutually exclusive and exhaustive).** Events $A_1, \ldots, A_k$ are *mutually exclusive* if no two have common outcomes, and *exhaustive* if one must occur: $A_1 \cup \cdots \cup A_k = S$. Together they form a **partition** of the sample space.

> **Proposition (Law of total probability).** Let $A_1, \ldots, A_k$ be mutually exclusive and exhaustive events. Then for any other event $B$,

$$ P(B) = \sum_{i=1}^{k} P(B \mid A_i)\,P(A_i) $$

Proof idea: if $B$ occurs it must occur in conjunction with exactly one of the $A_i$'s, so $B = (A_1 \cap B) \cup \cdots \cup (A_k \cap B)$ is a union of mutually exclusive pieces (Figure 2.11). Finite additivity plus the multiplication rule gives the result: each path through the partition contributes its joint probability.

### Bayes' Theorem

> **Theorem (Bayes).** Let $A_1, \ldots, A_k$ be a collection of mutually exclusive and exhaustive events with prior probabilities $P(A_i)$. For any event $B$ with $P(B) > 0$, the *posterior probability* of $A_j$ given that $B$ has occurred is

$$ P(A_j \mid B) = \frac{P(B \mid A_j)\,P(A_j)}{\sum_{i=1}^{k} P(B \mid A_i)\,P(A_i)}, \qquad j = 1, \ldots, k $$

The numerator is the multiplication rule; the denominator is the law of total probability. Bayes' theorem formalizes the prior → posterior update: evidence $B$ reweights each partition event in proportion to how likely it makes that evidence. When there are only a few partition events, a tree diagram computes posteriors directly (path product divided by the sum of all path products) without ever writing the formula explicitly.

A counterintuitive consequence: when an event is rare, even very accurate evidence can leave its posterior probability low. For a disease affecting 1 in 1000 adults, a test that is positive on 99% of diseased individuals but also on 2% of healthy ones yields $P(\text{disease} \mid \text{positive}) \approx .047$ — the posterior rises by a factor of about 47 over the prior, yet most positive results still come from healthy people. Pushing the posterior much higher requires a test with far smaller error rates.

## Section 2.5 — Independence

### Independent Events

Conditional probability measures how knowledge that $B$ occurred changes the probability of $A$. If that knowledge produces no change, the events are independent.

> **Definition (Independence).** For $P(B) > 0$, two events $A$ and $B$ are **independent** if $P(A \mid B) = P(A)$ and are **dependent** otherwise.

Although the definition is written using $P(A \mid B)$, independence is symmetric. When $P(A) > 0$, conditional probability and the multiplication rule give

$$
P(B \mid A)
= \frac{P(A \cap B)}{P(A)}
= \frac{P(A \mid B)P(B)}{P(A)}.
$$

Thus, when $P(A \mid B) = P(A)$, it follows that $P(B \mid A) = P(B)$. The occurrence or nonoccurrence of either event has no bearing on the probability of the other.

If $A$ and $B$ are independent, then each of the following pairs is also independent:

- $A'$ and $B$
- $A$ and $B'$
- $A'$ and $B'$

Mutually exclusive events with positive probabilities cannot be independent. If $A \cap B = \emptyset$ and $P(A) > 0$, $P(B) > 0$, then $P(A \mid B) = 0 \ne P(A)$.

### Multiplication Criterion

> **Proposition.** Events $A$ and $B$ are independent if and only if

$$
P(A \cap B) = P(A)P(B).
$$

This follows from the multiplication rule:

$$
P(A \cap B) = P(A \mid B)P(B) = P(A)P(B).
$$

The product criterion is often the most convenient way to verify independence or calculate the probability that independent events occur together. Independence may be specified by the experimental situation rather than derived from numerical probabilities.

### Independence of More Than Two Events

> **Definition (Mutual independence).** Events $A_1, \ldots, A_n$ are **mutually independent** if the probability of the intersection of every subset of two or more events equals the product of their individual probabilities. For every $k = 2, 3, \ldots, n$ and every subset of indices $i_1, i_2, \ldots, i_k$,

$$
P(A_{i_1} \cap A_{i_2} \cap \cdots \cap A_{i_k})
= P(A_{i_1})P(A_{i_2}) \cdots P(A_{i_k}).
$$

Mutual independence requires the product rule for **every** subset, not only for the intersection of all $n$ events. When events are mutually independent, any of them may be replaced by its complement while preserving independence, so intersection probabilities involving events and complements can also be found by multiplication.

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
| Ordered pair / k-tuple | $(O_1, O_2) \ne (O_2, O_1)$; an ordered collection of $k$ objects is a k-tuple (pair = 2-tuple, triple = 3-tuple) |
| Product rule (pairs) | first element in $n_1$ ways, second in $n_2$ for each → $n_1 n_2$ pairs; equivalently a two-stage operation with $n_1$, then $n_2$, ways |
| Tree diagram | one branch per choice at each generation; tips of the last generation ↔ outcomes (verifies product rule); works even when branch counts vary, where the product rule does not |
| Product rule (k-tuples) | $k$-stage operation with $n_i$ ways at stage $i$ → $n_1 n_2 \cdots n_k$ k-tuples |
| Permutation $P_{k,n}$ | ordered subset of size $k$ from $n$: $\frac{n!}{(n-k)!}$ — order matters (lineups, officer selections) |
| Combination $\binom{n}{k}$ | unordered subset: $\frac{n!}{k!(n-k)!} = P_{k,n}/k!$; $\binom{n}{0} = \binom{n}{n} = 1$, $\binom{n}{1} = n$ — order does not matter (samples, committees) |
| Two-group sampling | exactly $j$ of group 1 in a sample of $k$: $\frac{\binom{N_1}{j}\binom{N_2}{k-j}}{\binom{N}{k}}$ — the hypergeometric counting pattern (Ch. 3) |
| $P(A \mid B)$ | conditional probability of $A$ given that $B$ has occurred ($B$ = conditioning event); equally likely outcomes: $N(A\cap B)/N(B)$ — sample space shrinks to $B$, normalized by $1/P(B)$ (Figure 2.8) |
| Definition of conditional probability | for $P(B) > 0$: $P(A \mid B) = P(A \cap B)/P(B)$; in general $P(A \mid B) \neq P(B \mid A)$, and both can differ from $P(A)$ |
| Multiplication rule | $P(A \cap B) = P(A \mid B)\,P(B)$ — use when the intersection is wanted but only conditioning probabilities are given; three stages: $P(A_1\cap A_2\cap A_3) = P(A_3 \mid A_1\cap A_2)\,P(A_2 \mid A_1)\,P(A_1)$ |
| Tree diagram (probability) | one branch per outcome at each stage; initial branches $P(A_i)$, second generation $P(B \mid A_i)$; product along a path = joint probability of the sequence |
| Prior vs. posterior | prior = $P(A_i)$ before observing evidence; posterior = $P(A_i \mid B)$ after — moves in the direction of the evidence (partition events that make $B$ more likely gain share) |
| Mutually exclusive and exhaustive | no two $A_i$'s share an outcome, and one must occur: $A_1 \cup \cdots \cup A_k = S$ — a partition of $S$ |
| Law of total probability | for a partition $A_1,\ldots,A_k$: $P(B) = \sum_{i=1}^{k} P(B \mid A_i)\,P(A_i)$ — partitions $B$ into disjoint pieces (Figure 2.11) |
| Bayes' theorem | $P(A_j \mid B) = \frac{P(B \mid A_j)\,P(A_j)}{\sum_{i=1}^{k} P(B \mid A_i)\,P(A_i)}$ — numerator is the multiplication rule, denominator total probability; prior → posterior update |
| Rare-event phenomenon | with low prevalence, even an accurate test leaves most positives as false alarms: 99% sensitivity, 2% false-positive rate, prevalence 1/1000 → $P(\text{disease} \mid +) \approx .047$ (≈47× the prior) |
| Independent events | $P(A \mid B) = P(A)$; equivalently $P(B \mid A) = P(B)$ — learning that one occurred does not change the probability of the other |
| Product criterion | $A$ and $B$ are independent iff $P(A \cap B) = P(A)P(B)$ |
| Complements | if $A$ and $B$ are independent, so are $(A',B)$, $(A,B')$, and $(A',B')$ |
| Mutual exclusivity vs. independence | mutually exclusive events with positive probability cannot be independent |
| Mutual independence | every intersection of two or more selected events has probability equal to the product of the selected events' probabilities |
