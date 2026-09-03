# Chapter 1 — Overview and Descriptive Statistics

**Course:** EGN 2440 — Probability & Statistics with Calculus (USF Fall 2026)
**Sections:** 1.3 Measures of Location (pp. 28–33).

Visual summaries give preliminary impressions; formal analysis needs numerical summary measures that characterize the data set and convey its salient features. This section describes **location** — where a data set is centered. Section 1.4 turns to variability.

---

## 1. The Mean

### 1.1 Definition

> **Definition (Sample mean).** For observations $x_1, x_2, \ldots, x_n$, the *sample mean* (arithmetic average) is
> $$\bar{x} = \frac{x_1 + x_2 + \cdots + x_n}{n} = \frac{\sum_{i=1}^{n} x_i}{n}.$$

**Reporting convention.** Report $\bar{x}$ with one more decimal place than the observations. If stopping distances are $x_1 = 125$ ft and $x_2 = 131$ ft, report $\bar{x} = 127.3$ ft — not 128 or 127.

### 1.2 Worked Example — Crack Lengths (Example 1.14)

Caustic stress corrosion cracking of iron and steel is studied because of failures around rivets in steel boilers and steam rotors. Constant-load stress-corrosion tests on smooth bar tensile specimens give crack lengths $x$ (mm), $n = 21$, listed here in increasing order:

8.9, 9.6, 10.3, 11.8, 12.7, 14.0, 14.6, 16.1, 18.5, 20.4, 21.2, 23.3, 24.2, 24.9, 25.3, 25.8, 27.1, 28.5, 30.2, 32.4, 45.0

**Solution.** $\sum x_i = 444.8$, so

$$\bar{x} = \frac{444.8}{21} = 21.18.$$

A value consistent with the stem-and-leaf display of the data (Figure 1.14), where a crack length in the low 20s appears "typical."

### 1.3 Physical Interpretation: Balance Point

Draw and scale a horizontal measurement axis, and represent each observation by a 1-lb weight placed at its value on the axis. The only point at which a fulcrum balances the system of weights is $\bar{x}$ (Figure 1.15) — the mean is literally the center of mass of the sample.

### 1.4 Population Mean

> **Definition (Population mean).** For a finite population with $N$ values,
> $$\mu = \frac{\text{sum of the } N \text{ population values}}{N}.$$

Chapters 3–4 give a more general definition covering infinite populations. Just as $\bar{x}$ summarizes a sample, $\mu$ is often the most important characteristic of a population — and inference methods (later chapters) use $\bar{x}$ to draw conclusions about $\mu$. In Example 1.14, $\bar{x} = 21.18$ mm serves as a **point estimate** (a single "best guess") of $\mu$, the true average crack length for all specimens treated that way.

### 1.5 Sensitivity to Outliers

The mean's key weakness: even one outlier (an unusually large or small observation) can greatly affect it. In Example 1.14, $x_{14} = 45.0$ is an obvious outlier:

- Without it: $\bar{x} = 399.8/20 = 19.99$. The single outlier raises the mean by more than 1 mm.
- If replaced with a catastrophic $295.0$: $\bar{x} = 694.8/21 = 33.09$ — larger than all but one of the observations!

Sample incomes often produce such outliers (a few astronomical salaries), making "average income" misleading as a measure of location. Yet the mean remains the most widely used measure of center, because for many populations — bell-shaped (normal) ones above all — extreme sample outliers are highly unlikely and $\bar{x}$ is stable and representative.

---

## 2. The Median

### 2.1 Definition

> **Definition (Sample median).** Order the $n$ observations from smallest to largest (repeated values included, so every observation appears). Then
> - if $n$ is odd: $\tilde{x} = $ the single middle value — the $(n+1)/2$-th ordered value;
> - if $n$ is even: $\tilde{x} = $ the average of the two middle values — the $n/2$-th and $(n/2 + 1)$-st ordered values.

### 2.2 Worked Example — Beethoven's Ninth (Example 1.15)

Durations (min) of a sample of 12 recordings of Symphony No. 9, in increasing order:

62.3, 62.8, 63.6, 65.2, 65.7, 66.4, 67.4, 68.4, 68.8, 70.8, 75.7, 79.0

**Solution.** $n = 12$ is even, so the median averages the $n/2 = 6$-th and $(n/2 + 1) = 7$-th ordered values:

$$\tilde{x} = \frac{66.4 + 67.4}{2} = 66.90.$$

If the largest observation (79.0) had not been included, $n = 11$ and the median would be the single middle value — the $(11+1)/2 = 6$-th ordered value: $\tilde{x} = 66.4$. The sample mean is

$$\bar{x} = \frac{816.1}{12} = 68.01,$$

a bit more than a full minute larger than the median — pulled out relative to it because the data stretches out somewhat more on the upper end than the lower.

### 2.3 Insensitivity to Outliers; Population Median and Skewness

The median is very insensitive to outliers: increasing the two largest durations from 75.7, 79.0 to 85.7, 89.0 leaves $\tilde{x}$ unaffected. In handling outlying values, $\bar{x}$ and $\tilde{x}$ sit at opposite ends of a spectrum — both describe where the data is centered, but they focus on different aspects of the sample and are not generally equal.

> **Definition (Population median).** The middle value in the population, denoted $\tilde{\mu}$. As with $\bar{x}$ vs. $\mu$, use $\tilde{x}$ to make inferences about $\tilde{\mu}$.

A median is often used for income or salary data precisely because it is not greatly influenced by a few large salaries: if the median salary of a sample of engineers were $66,416, that supports concluding the population median exceeds $60,000.

**Skewness.** $\mu$ and $\tilde{\mu}$ are not generally identical (Figure 1.17):

| Shape | Relationship |
|---|---|
| Symmetric | mean ≈ median at the center |
| Positive skew (long right tail) | $\mu > \tilde{\mu}$ |
| Negative skew (long left tail) | $\mu < \tilde{\mu}$ |

When inferring about a skewed population, first decide which of the two characteristics is of greater interest, then proceed accordingly.

---

## 3. Quartiles, Percentiles, and Trimmed Means

### 3.1 Quartiles and Percentiles

The median divides the data into two equal parts; finer location measures divide it further:

| Measure | Divides the data... |
|---|---|
| **Median** ($Q_2$) | into two equal halves |
| **Quartiles** $Q_1, Q_2, Q_3$ | into four roughly equal parts — $Q_3$ separates the upper quarter, $Q_1$ the lower quarter from the upper three-quarters, and $Q_2 = \tilde{x}$ |
| **Percentiles** | into 100 parts — the 99th percentile separates the highest 1% from the bottom 99% |

Unless $n$ is a multiple of 100, care must be exercised in obtaining percentiles; that discussion is postponed to Chapter 4.

### 3.2 Trimmed Means

The mean and median are opposite extremes of one family: the mean averages **all** the data (trims 0% from each end), while the median trims as much as possible, keeping only the middle one or two values. A trimmed mean is a compromise between them:

> **Definition ($a\%$ trimmed mean).** Eliminate the smallest $a\%$ and largest $a\%$ of the sample, then average what remains; written $\bar{x}_{tr}(a)$.

A moderate trimming percentage — somewhere between 5% and 25% — yields a center neither as sensitive to outliers as the mean nor as insensitive as the median. If $na$ is not an integer, interpolate: for example with $n = 26$, $\bar{x}_{tr}(10)$ would be a weighted average of the 7.7% trimmed mean (trim two from each end) and the 11.5% trimmed mean (trim three from each end).

### 3.3 Worked Example — Bidri Copper Content (Example 1.16)

Bidri wares are cast in India from an alloy of primarily zinc with some copper. Copper content (%) for a sample of 26 artifacts, in increasing order:

2.0, 2.4, 2.5, 2.6, 2.6, 2.7, 2.7, 2.8, 3.0, 3.1, 3.2, 3.3, 3.3, 3.4, 3.4, 3.6, 3.6, 3.6, 3.6, 3.7, 4.4, 4.6, 4.7, 4.8, 5.3, 10.1

A prominent feature is the single outlier (10.1) at the upper end; the data is sparser in the region of larger values than smaller ones.

**Solution.**

$$\bar{x} = \frac{95.0}{26} = 3.65, \qquad \tilde{x} = \frac{3.3 + 3.4}{2} = 3.35.$$

A trimming percentage of $100(2/26) = 7.7\%$ eliminates the two smallest (2.0, 2.4) and two largest (5.3, 10.1) observations; averaging the remaining 22:

$$\bar{x}_{tr}(7.7) = \frac{95.0 - 2.0 - 2.4 - 5.3 - 10.1}{22} = \frac{75.2}{22} = 3.42.$$

Trimming here eliminates the larger outlier and pulls the trimmed mean toward the median — landing between $\bar{x}$ and $\tilde{x}$, as designed.

---

## 4. Categorical Data and Sample Proportions

For categorical data, a frequency or relative frequency distribution is an effective tabular summary; the natural numerical summaries are the individual frequencies and relative frequencies (e.g., counting Canon vs. Sony vs. Kodak owners in a brand-preference survey).

**Dichotomous populations.** When there are exactly two categories, let $x$ = number of sample observations falling in category 1; then $n - x$ fall in category 2:

- Sample proportion in category 1: $x/n$
- Sample proportion in category 2: $(n-x)/n$

**Coding as 0s and 1s.** Code a response in the category of interest as 1 and every other response as 0. A sample of size 10 might yield 1, 1, 0, 1, 1, 1, 0, 0, 1, 1 — seven 1s, so

$$\bar{x} = \frac{7}{10} = \frac{x}{n}.$$

The sample proportion in a category is exactly the sample mean of its 1/0 coding, so a sample mean can summarize categorical samples. The same applies to categories formed by grouping numerical values (e.g., "owned current car at least 5 years" vs. not, rather than exact ownership length).

> **Definition (Population proportion).** $p$ = the proportion of the entire population falling in the category; a number between 0 and 1 that is a characteristic of the population. The relationship parallels $\bar{x}$ to $\mu$ (and $\tilde{x}$ to $\tilde{\mu}$): use $x/n$ as a point estimate of $p$.

If a sample of 100 car owners reveals that 22 owned their car at least 5 years, then $22/100 = .22$ is the point estimate of the proportion of all owners in that category. With $k \geq 2$ categories, the $k$ sample proportions answer questions about the population proportions $p_1, \ldots, p_k$.

---

## Quick Reference

| Symbol | Meaning |
|---|---|
| $\bar{x} = \sum x_i / n$ | sample mean; report one more decimal place than the data |
| Balance point | each observation as a 1-lb weight on an axis — the fulcrum that balances them is at $\bar{x}$ |
| $\mu$ | population mean (finite: sum of $N$ values / $N$); estimated by $\bar{x}$ |
| Outlier sensitivity | one extreme value can move $\bar{x}$ dramatically; median unaffected — prefer median for skewed or outlier-prone data such as incomes |
| $\tilde{x}$ | sample median: middle ordered value ($n$ odd) or average of the two middle values ($n$ even); insensitive to outliers |
| $\tilde{\mu}$ | population median; estimated by $\tilde{x}$ |
| Skewness | symmetric: $\mu \approx \tilde{\mu}$ · positive skew (right tail): $\mu > \tilde{\mu}$ · negative skew (left tail): $\mu < \tilde{\mu}$ |
| $Q_1, Q_2, Q_3$ | quartiles — four roughly equal parts; $Q_2 = \tilde{x}$ |
| Percentile | the 99th separates the top 1% from the bottom 99%; computation deferred to Ch. 4 |
| $\bar{x}_{tr}(a)$ | $a\%$ trimmed mean: drop smallest and largest $a\%$, average the rest; 5–25% typical; interpolate when $na$ is not an integer |
| $x/n$ | sample proportion in a category = sample mean of its 1/0 coding |
| $p$ | population proportion in a category (between 0 and 1); estimated by $x/n$ |
