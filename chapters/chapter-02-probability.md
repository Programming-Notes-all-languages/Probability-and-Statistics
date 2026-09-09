# Chapter 2 — Probability

**Course:** EGN 2440 — Probability & Statistics with Calculus (USF Fall 2026)
**Sections:** 2.1 Sample Spaces and Events (pp. 51–54).

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
