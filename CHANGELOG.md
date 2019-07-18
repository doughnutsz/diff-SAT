0.4.1

- Support for weighted clauses annotated with probabilities in DIMACS CNF (Probabilistic CNF). See [Usage](#usage) for details.
- `_eval_("term", "?")` meta-predicate for ad hoc querying of probabilities and other statistics (e.g., remaining loss) over sampled models. 
An example can be found under [Performing ad hoc queries](#Performing-ad-hoc-queries). 
- Argument `-s` k (k>1) for sampling k models _uniformly_ from the multimodel cost solution.
- Argument `-n` -k (k>1) for sampling k models such that k-m of these models are sampled _uniformly_ from the sample (with size m) for which the cost threshold was initially reached.
- Improved finite differences approach to the case where not all parameter atoms are measured (i.e., occur in costs), automatically activated when needed. Switch `useNumFiniteDiff` is
not required anymore, however, purely numerical differentiation approach can still be enforced with `--solverarg mixedScenario false` (in rare cases this is more efficient). 
- Typically higher solution entropy for the same sample size (`-n`), compared to previous versions. For how to increase the entropy further see `README.md`
- Support for non-quoted `_cost_` and `_eval_` terms using plain logic programming term notation (e.g., `_cost_(pow(subtr(div(77,100),f(coin(1,heads))),2))` instead of `_cost_("(0.77-f(coin(1,heads)))^2")`).
- Several minor improvements and bug fixes
- Enhanced documentation (this file)

0.4.0  

- Simplified usage; support for parameter atom and cost function specification using special logical predicates
- Support for distinct sets of parameter atoms and measured atoms, enabling preliminary support for inductive/abductive inference.