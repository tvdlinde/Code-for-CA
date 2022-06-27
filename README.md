# Code for Cosmash Associativity

This repository contains the code that was used by the authors to obtain part of the results in the article  

> Ülo Reimaa, Tim Van der Linden and Corentin Vienne, _Associativity and the cosmash product in operadic varieties of algebras_, [preprint arXiv:2206.12096](https://arxiv.org/abs/2206.12096), 2022.

All mathematical explanations are in the article; use of the code is explained in the file `how_to.txt` and in the code files themselves. Briefly:

The files `generate_equations.singular` and `solve_equations_*.singular` contain code which can be run in the software package [Singular](https://www.singular.uni-kl.de/). The file `version.txt` shows which is the precise version we used. First run

```
Singular -q generate_equations.singular
```

to generate the file `equations.txt` which contains the equations. Then run

```
Singular -q solve_equations_m.singular
```

to check that the number _m_ in the article is indeed a linear combination of the _f[i]_. The number _m'_ and proof that the system is inconsistent in characteristic 2 are obtained by applying the same process to `solve_equations_mprime.singular` and `solve_equations_m2.singular`. In each case a new file is created which can be opened inside Mathematica to check the outcome: the coefficients obtained by Singular are multiplied with the corresponding equations, the results are added, and what we get is the same number _m_ or _m' = mprime_ or _1_. Once inside Mathematica, run the file in question by entering

```
ToExpression[Import["output-m.mathematica", "Text"]]
% == m
```

and the likes. Further information can be found in the article. Please contact us by email with any questions you may have.
## Authors 

Ülo Reimaa, Tim Van der Linden and Corentin Vienne

## Acknowledgements
Research of the first author was supported by the Estonian Research Council grant PUTJD948. The second author is a Senior Research Associate of the Fonds de la Recherche Scientifique-FNRS. Research of the third author was supported by the Fonds Thelam of the Fondation Roi Baudouin. Computational resources have been provided by the Consortium des Équipements de Calcul Intensif (CÉCI), funded by the Fonds de la Recherche Scientifique de Belgique (F.R.S.-FNRS) under Grant No. 2.5020.11 and by the Walloon Region.