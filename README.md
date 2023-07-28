# Key_Ranking

to 
markdown_github
 Standalone
 Embed resources
 Citeproc
 TOC
 Number sections


**Evaluation Metric.** We utilize ***key rank*** (a.k.a. *guessing
entropy* ) as the metric to measure the attack performance of
side-channel attacks. Specifically, given a power trace
*t*′<sub>*i*</sub>, classifier *F* outputs a *HW score vector*
(*s*<sub>*i*</sub>\[0\],...,*s*<sub>*i*</sub>\[8\]), where
*s*<sub>*i*</sub>\[*j*\] is the score for Hamming weight *j*. Next, an
attacker obtains a *key score vector*
(*r*<sub>*i*</sub>\[*k*<sub>1</sub><sup>\*</sup>\],...,*r*<sub>*i*</sub>\[*k*<sub>256</sub><sup>\*</sup>\])
by calculating
$$r\_{i}\[k^{\*}\_{g}\] = s\_{i}\[j\], \quad \textnormal{ if } \quad \mathtt{HW}(\varphi(m'\_{i}, k^{\*}\_{g})) == j$$
*for* 1 ≤ *g* ≤ 256, where
*r*<sub>*i*</sub>\[*k*<sub>*g*</sub><sup>\*</sup>\] is the score of
possible key *k*<sub>*g*</sub><sup>\*</sup> according to trace
*t*′<sub>*i*</sub> and plaintext *m*′. The *aggregated key score vector*
(*r*\[*k*<sub>1</sub><sup>\*</sup>\],...,*r*\[*k*<sub>256</sub><sup>\*</sup>\])
over *N*′ power traces are computed as
$$r\[k^{\*}\_{j}\] = \sum\_{i=1}^{N'} r\_{i}\[k^{\*}\_{j}\], \textnormal{   \textit{for} $1\leq{j}\leq256$}$$
The aggregated key scores
(*r*\[*k*<sub>1</sub><sup>\*</sup>\],...,*r*\[*k*<sub>256</sub><sup>\*</sup>\])
are further sorted in descending order based on the scores.

*Key rank* is denoted as *w*, where *w* ∈ \[0,255\], if correct key *k*′
is ranked as the (*w*+1)-th key among all the possible keys
*k*<sub>1</sub><sup>\*</sup>, ..., *k*<sub>256</sub><sup>\*</sup> based
on the aggregated key scores. A key rank of 0 over *N*′ traces suggests
that an attacker can recover key *k*′ with *N*′ traces. We use ***KRC***
to indicate the number of test traces that an attacker needs for key
rank to converge to 0. If key rank converges to 0 with a lower number of
traces, it indicates that an attack is more effective.
