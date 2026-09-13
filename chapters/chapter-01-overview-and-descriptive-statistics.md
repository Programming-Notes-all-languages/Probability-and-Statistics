# Chapter 1 — Overview and Descriptive Statistics

**Course:** EGN 2440 — Probability & Statistics with Calculus (USF Fall 2026)
**Sections:** 1.3 Measures of Location (pp. 28–33), 1.4 Measures of Variability (pp. 35–43).

Visual summaries give preliminary impressions; formal analysis needs numerical summary measures that characterize a data set and convey its salient features. Section 1.3 covers **location** — where the data is centered; Section 1.4 covers **variability** — how far observations spread around that center.

---

## Section 1.3 — Measures of Location

### The Mean

> **Definition (Sample mean).** For observations $x_1, x_2, \ldots, x_n$, the *sample mean* (arithmetic average) is

$$\bar{x} = \frac{x_1 + x_2 + \cdots + x_n}{n} = \frac{\sum_{i=1}^{n} x_i}{n}.$$

**Reporting convention.** Report $\bar{x}$ with one more decimal place than the observations.

**Physical interpretation: balance point.** Draw and scale a horizontal measurement axis, and represent each observation by a 1-lb weight placed at its value on the axis. The only point at which a fulcrum balances the system of weights is $\bar{x}$ (Figure 1.15) — the mean is literally the center of mass of the sample.

> **Definition (Population mean).** For a finite population with $N$ values,

$$\mu = \frac{\text{sum of the } N \text{ population values}}{N}.$$

Chapters 3–4 give a more general definition covering infinite populations. Just as $\bar{x}$ summarizes a sample, $\mu$ is often the most important characteristic of a population — and inference methods use $\bar{x}$ as a **point estimate** of $\mu$.

**Sensitivity to outliers.** The mean's key weakness is that even one outlier (an unusually large or small observation) can greatly affect it. The mean remains widely used because for many populations — bell-shaped (normal) ones above all — extreme sample outliers are highly unlikely and $\bar{x}$ is stable and representative.

### The Median

> **Definition (Sample median).** Order the $n$ observations from smallest to largest (repeated values included, so every observation appears). Then
> - if $n$ is odd: $\tilde{x} = $ the single middle value — the $(n+1)/2$-th ordered value;
> - if $n$ is even: $\tilde{x} = $ the average of the two middle values — the $n/2$-th and $(n/2 + 1)$-st ordered values.

**Insensitivity to outliers; population median and skewness.** The median is very insensitive to outliers. In handling outlying values, $\bar{x}$ and $\tilde{x}$ sit at opposite ends of a spectrum — both describe where the data is centered, but they focus on different aspects of the sample and are not generally equal.

> **Definition (Population median).** The middle value in the population, denoted $\tilde{\mu}$. As with $\bar{x}$ vs. $\mu$, use $\tilde{x}$ to make inferences about $\tilde{\mu}$.

A median is often used for income or salary data because it is not greatly influenced by a few large salaries.

**Skewness.** $\mu$ and $\tilde{\mu}$ are not generally identical (Figure 1.17):

| Shape | Relationship |
|---|---|
| Symmetric | mean ≈ median at the center |
| Positive skew (long right tail) | $\mu > \tilde{\mu}$ |
| Negative skew (long left tail) | $\mu < \tilde{\mu}$ |

When inferring about a skewed population, first decide which of the two characteristics is of greater interest, then proceed accordingly.

### Quartiles, Percentiles, and Trimmed Means

The median divides the data into two equal parts; finer location measures divide it further:

| Measure | Divides the data... |
|---|---|
| **Median** ($Q_2$) | into two equal halves |
| **Quartiles** $Q_1, Q_2, Q_3$ | into four roughly equal parts — $Q_3$ separates the upper quarter, $Q_1$ the lower quarter from the upper three-quarters, and $Q_2 = \tilde{x}$ |
| **Percentiles** | into 100 parts — the 99th percentile separates the highest 1% from the bottom 99% |

Unless $n$ is a multiple of 100, care must be exercised in obtaining percentiles; that discussion is postponed to Chapter 4.

> **Definition ($a\%$ trimmed mean).** Eliminate the smallest $a\%$ and largest $a\%$ of the sample, then average what remains; written $\bar{x}_{tr}(a)$.

The mean and median are opposite extremes of one family: the mean averages **all** the data (trims 0% from each end), while the median trims as much as possible, keeping only the middle one or two values. A trimmed mean is a compromise between them — a moderate trimming percentage, somewhere between 5% and 25%, yields a center neither as sensitive to outliers as the mean nor as insensitive as the median. When $na$ is not an integer, interpolation may be used.

### Categorical Data and Sample Proportions

For categorical data, a frequency or relative frequency distribution is an effective tabular summary; the natural numerical summaries are the individual frequencies and relative frequencies (e.g., counting Canon vs. Sony vs. Kodak owners in a brand-preference survey).

**Dichotomous populations.** When there are exactly two categories, let $x$ = number of sample observations falling in category 1; then $n - x$ fall in category 2:

- Sample proportion in category 1: $x/n$
- Sample proportion in category 2: $(n-x)/n$

**Coding as 0s and 1s.** Code a response in the category of interest as 1 and every other response as 0. The sample proportion in a category is exactly the sample mean of its 1/0 coding, so a sample mean can summarize categorical samples.

> **Definition (Population proportion).** $p$ = the proportion of the entire population falling in the category; a number between 0 and 1 that is a characteristic of the population. The relationship parallels $\bar{x}$ to $\mu$ (and $\tilde{x}$ to $\tilde{\mu}$): use $x/n$ as a point estimate of $p$.

With $k \geq 2$ categories, the $k$ sample proportions estimate the population proportions $p_1, \ldots, p_k$.

---

## Section 1.4 — Measures of Variability

Reporting a measure of center gives only partial information about a data set or distribution. Different samples may have identical measures of center yet differ from one another in other important ways: Figure 1.19 shows dotplots of three samples with the **same mean and median**, yet different amounts of spread about the center — sample 1 has the most variability, sample 3 the least, and sample 2 is intermediate.

### Range

> **Definition (Range).** The difference between the largest and smallest sample values: $\text{range} = \max x_i - \min x_i$.

The simplest measure of variability. Sample 1's range in Figure 1.19 is much larger than sample 3's, reflecting more variability. But a defect of the range is that it depends on only the two most extreme observations and disregards the positions of all the rest — samples 1 and 2 have **identical ranges**, yet when the observations between the extremes are taken into account there is far less dispersion in sample 2 than in sample 1.

### Sample Variance and Standard Deviation

The primary measures of variability involve the **deviations from the mean**, $x_1 - \bar{x}, x_2 - \bar{x}, \ldots, x_n - \bar{x}$: positive if the observation lies to the right of $\bar{x}$ on the measurement axis, negative if to the left. If all deviations are small in magnitude, all $x_i$'s are close to the mean and there is little variability; if some are large, some observations lie far from $\bar{x}$.

Averaging the deviations directly is a bad idea — they always cancel:

$$\sum_{i=1}^{n} (x_i - \bar{x}) = \sum x_i - n\bar{x} = \sum x_i - n\left(\frac{\sum x_i}{n}\right) = 0,$$

so the average deviation is always zero. One could instead average the absolute deviations, $\sum |x_i - \bar{x}|/n$, but the absolute value operation leads to theoretical difficulties; consider instead the **squared deviations** $(x_1 - \bar{x})^2, \ldots, (x_n - \bar{x})^2$.

> **Definition (Sample variance and standard deviation).** The *sample variance*, denoted $s^2$, is

$$s^2 = \frac{\sum_{i=1}^{n}(x_i - \bar{x})^2}{n - 1} = \frac{S_{xx}}{n-1},$$

> where $S_{xx} = \sum (x_i - \bar{x})^2$ is the sum of squared deviations. The *sample standard deviation* is the positive square root: $s = \sqrt{s^2}$.

Note that $s^2$ and $s$ are both nonnegative, and the unit for $s$ is the same as the unit for each $x_i$ (if observations are fuel efficiencies in mpg, then perhaps $s = 2.0$ mpg). A rough interpretation: **$s$ is the size of a typical or representative deviation from the sample mean** — if $s = 2.0$ mpg, some $x_i$'s are closer than 2.0 to $\bar{x}$ and others farther away; 2.0 is a "standard" deviation from the mean. If a second sample has $s = 3.0$, its typical deviation is roughly 1.5 times as large — an indication of more variability.

**Why divide by $n-1$ and not $n$?** There is also a measure of variability for the population, the **population variance**: when the population is finite and consists of $N$ values,

$$\sigma^2 = \frac{\sum_{i=1}^{N}(x_i - \mu)^2}{N},$$

the average of all squared deviations from the population mean (for the population, the divisor is $N$, not $n-1$); $\sigma = \sqrt{\sigma^2}$ is the **population standard deviation**. More general definitions appear in Chapters 3 and 4. Just as $\bar{x}$ will be used to make inferences about $\mu$, we want $s^2$ usable for inferences about $\sigma^2$. But $\sigma^2$ involves squared deviations about $\mu$, which is almost never known — so the sum of squared deviations about $\bar{x}$ must be used. The catch: the sample $x_i$'s tend to be **closer to their own average** $\bar{x}$ than to the population average $\mu$, so dividing by $n$ would make the resulting quantity tend to **underestimate** $\sigma^2$ (produce values too small on average). Dividing by the slightly smaller $n-1$ corrects this underestimating.

It is customary to refer to $s^2$ as being based on $n - 1$ **degrees of freedom (df)**. Although $s^2$ is built from the $n$ quantities $x_1 - \bar{x}, \ldots, x_n - \bar{x}$, these sum to 0, so specifying any $n-1$ of them determines the remaining one.

**Computing formula.** Best to obtain $s^2$ from statistical software or a calculator that stores data and returns it with one keystroke. If not, an alternative expression for the numerator avoids calculating the deviations:

$$S_{xx} = \sum (x_i - \bar{x})^2 = \sum x_i^2 - \frac{(\sum x_i)^2}{n},$$

involving $\sum x_i$ (summing then squaring) and $\sum x_i^2$ (squaring then summing). The identity follows by expanding: since $\bar{x} = \sum x_i / n$,

$$\sum (x_i - \bar{x})^2 = \sum (x_i^2 - 2\bar{x}\,x_i + \bar{x}^2) = \sum x_i^2 - 2\bar{x}\sum x_i + n\bar{x}^2 = \sum x_i^2 - n\bar{x}^2 = \sum x_i^2 - \frac{(\sum x_i)^2}{n}.$$

Both the defining formula and the computational formula can be sensitive to rounding, so as much decimal accuracy as possible should be used in intermediate calculations.

### Properties of $s^2$ Under Shifts and Scaling

> **Proposition.** Let $x_1, x_2, \ldots, x_n$ be a sample and let $c$ be any nonzero constant.
> 1. If $y_i = x_i + c$ for all $i$, then $s_y^2 = s_x^2$.
> 2. If $y_i = cx_i$ for all $i$, then $s_y^2 = c^2 s_x^2$, so $s_y = |c|\,s_x$.

Result 1: adding (or subtracting) a constant shifts the location of the data set but leaves distances between values unchanged — variance is unaffected. Result 2: multiplying every observation by $c$ multiplies all deviations by $c$, hence the variance by $c^2$. Both follow immediately from the definition, since $(y_i - \bar{y}) = (x_i + c) - (\bar{x} + c) = x_i - \bar{x}$ in Result 1 and $(y_i - \bar{y}) = c(x_i - \bar{x})$ in Result 2.

### Boxplots

Stem-and-leaf displays and histograms convey general impressions; a single summary such as the mean or standard deviation focuses on just one aspect of the data. A **boxplot** describes several prominent features at once: (1) center, (2) spread, (3) the extent and nature of any departure from symmetry, and (4) identification of **"outliers,"** observations that lie unusually far from the main body of the data. Because even a single outlier can drastically affect $\bar{x}$ and $s$, the boxplot is based on measures that are **resistant** to a few outliers — the median and a measure of variability called the fourth spread.

> **Definition (Fourths and fourth spread).** Order the $n$ observations from smallest to largest and separate the smallest half from the largest half; the median $\tilde{x}$ is included in both halves if $n$ is odd. The *lower fourth* is the median of the smallest half, and the *upper fourth* is the median of the largest half. The **fourth spread** is

$$f_s = \text{upper fourth} - \text{lower fourth}.$$

Roughly speaking, $f_s$ is unaffected by the positions of observations in the smallest 25% or largest 25% of the data — hence resistant to outliers.

The simplest boxplot is based on the **five-number summary**: smallest $x_i$, lower fourth, median, upper fourth, largest $x_i$. Construction: draw a horizontal measurement scale; place a rectangle above it with left edge at the lower fourth and right edge at the upper fourth (so box width = $f_s$); mark the median inside the rectangle — its position relative to the two edges conveys skewness in the middle 50% of the data; finally draw "whiskers" out from either end of the box to the smallest and largest observations. A vertical orientation is drawn by obvious modifications.

**Boxplots that show outliers.** Many inferential procedures assume the population distribution is normal (a bell curve). Even a single extreme outlier warns that such procedures may be unreliable; several mild outliers convey the same message.

> **Definition (Outlier).** Any observation farther than $1.5\,f_s$ from the closest fourth is an **outlier**. An outlier is **extreme** if it is more than $3\,f_s$ from the nearest fourth, and **mild** otherwise.

The construction is modified: whiskers extend out from each end of the box to the smallest and largest observations that are **not** outliers; each mild outlier is drawn as a closed circle and each extreme outlier as an open circle (some software packages do not distinguish between the two).

**Comparative boxplots.** A comparative or side-by-side boxplot is a very effective way of revealing similarities and differences between two or more data sets consisting of observations on the same variable — fuel efficiency for four types of automobiles, crop yields for three varieties, and so on.

---

## Quick Reference

| Symbol / concept | Meaning |
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
| Range | $\max x_i - \min x_i$; uses only the two extreme observations — ignores internal dispersion |
| Deviations | $x_i - \bar{x}$ sum to exactly 0, so their average is always 0 — cannot measure spread directly |
| $s^2 = S_{xx}/(n-1)$ | sample variance, with $S_{xx} = \sum (x_i - \bar{x})^2$; divisor $n-1$ (not $n$) because dividing by $n$ would underestimate $\sigma^2$ — based on $n-1$ df since the deviations sum to 0 |
| $s = \sqrt{s^2}$ | sample standard deviation — size of a typical deviation from the mean; same units as the data |
| Computational formula | $S_{xx} = \sum x_i^2 - (\sum x_i)^2/n$; both formulas sensitive to rounding — keep full precision in intermediate steps |
| Shift / scale | $y_i = x_i + c \Rightarrow s_y^2 = s_x^2$ · $y_i = cx_i \Rightarrow s_y^2 = c^2 s_x^2$, $s_y = \|c\|\,s_x$ |
| $\sigma^2$, $\sigma$ | population variance / standard deviation (finite: divisor $N$); estimated by $s^2$, $s$ |
| Fourth spread $f_s$ | upper fourth − lower fourth; fourths are the medians of the two halves (median in both halves when $n$ odd) — resistant to outliers |
| Five-number summary | smallest, lower fourth, median, upper fourth, largest → boxplot: box from L4 to U4, line at median, whiskers to extremes |
| Outlier fences | farther than $1.5\,f_s$ from nearest fourth = outlier; more than $3\,f_s$ = extreme (open circle), otherwise mild (closed circle); modified whiskers stop at the largest non-outlier |
| SE Mean $= s/\sqrt{n}$ | standard error of the mean — key quantity for inferences about $\mu$ in later chapters |
