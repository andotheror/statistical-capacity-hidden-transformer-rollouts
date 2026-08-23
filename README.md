# The Statistical Capacity of Hidden Transformer Rollouts

## Abstract

A Transformer with $W$ parameters is reused at every autoregressive step. Can $M$ hidden steps make its final-answer class statistically more complex than one forward pass? Generic autoregressive learning theory permits a linear factor in $M$, but it was unknown whether a fixed Transformer architecture attains this factor. We give a sharp answer. Every depth-$L$ hard-attention Transformer has final-token VC dimension at most 

$$O\\!\left(MWL\log(MT_{\rm ctx}WLK)\right),$$

 where $K$ is vocabulary size. Conversely, for every $W$ and $M$, one three-block decoder with constant hidden dimension and constant vocabulary has VC dimension $\Omega(WM)$. Its prompt has length $O(\log W+\log M)$. The construction stores a binary tape in each trainable scalar, emits the tape one bit at a time, then retrieves a prompt-selected bit. It works with ordinary softmax attention after finite logit scaling. This capacity has a sharp trainable-precision cutoff. If every trainable scalar has at most $b$ bits of choice, cardinality gives VC dimension at most $bW$, while the construction gives $\Omega(W\min\\{M,b\\})$. Hence hidden rollouts unlock one selectable label bit per parameter per step until trainable precision is exhausted. Finally, for the same fixed Transformer subclass and the same prompt distribution, final-answer supervision has realizable sample complexity $\Theta(WM/\epsilon)$ at constant confidence, while full-trace supervision needs only $\Theta(W/\epsilon)$. This is a factor-$\Theta(M)$ supervision gap, not a comparison between different architectures. The results resolve the end-to-end Transformer question left open by the sharp single-pass and full-trace theory, and separate the computational power of longer reasoning from the statistical information stored in its parameters.

## Contributions

- an end-to-end upper bound $O(MWL\log(MT_{\rm ctx}WLK))$ for every fixed
 hard-attention Transformer architecture
- an explicit three-block lower bound $\Omega(WM)$, including a constant-alphabet version
 and a softmax compilation
- a matching trainable-precision cutoff $\Omega(W\min\\{M,b\\})\leq
 \mathrm{VCdim}\leq bW$
- a factor-$\Theta(M)$ sample-complexity gap between final-answer and full-trace supervision
 for the same Transformer subclass.

All scalar identities and attention competitions are independently executable in the supplement.

## Keywords

transformers, chain-of-thought, statistical capacity, sample complexity, autoregressive models, hidden rollouts

## Files

- `main_2026-08-12.pdf`, the paper as first published, with its OpenTimestamps proof `main_2026-08-12.pdf.ots`.
- source: `appendix.tex`, `iclr2027_conference.bst`, `iclr2027_conference.sty`, `main_2026-08-12.tex`, `references.bib`.
- also: `main_2026-08-12.bbl`.
