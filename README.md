# Code for the "Reformulations for Solving Robust Contract Pricing with Dual-Source Data"
We consider a contract pricing problem in a two-tier supply chain with information asymmetry. To ensure decision reliability in small data, we develop a Wasserstein-based data-driven distributionally robust pricing model using a dual-source data set to maximize the supplier’s worst-case profit. Different from the classical Wasserstein ambiguity set, we combine two types of data to construct a more appropriate ambiguity set. Specifically, we develop an equivalent linear programming reformulation based on Lagrange duality and set partition to solve an augmented center distribution. Furthermore, we incorporate additional quantile constraints into the uncertain set, based on the retailer’s first-order conditions, which avoids overly conservative decisions. Given the complexity of solving Wasserstein-based DRO model, we devise a partition-based cutting-plane approach to determine the supplier’s worst-case profit. Furthermore, when all products are mutually independent, an equivalent second-order cone programming model can be formulated to solve for the supplier’s worst-case profit. Numerical experimental results demonstrate that our solution methods have higher computational efficiency compared to traditional methods, and our optimal decision exhibits superior out-of-sample performance compared to classical data-driven decisions. The code of this study is open accessible in GitHub repository.
## Computational efficiency center.py and n=3 center.py
These two files solve the center of the Wasserstein ball ambiguity set by calling the Gurobi solver. Specifically, we consider two solving methods: the LD method (benchmark) and the LRDS method proposed in this paper. The solution results and solution times are recorded to illustrate the computational effectiveness of the LRDS method.
## minimax_tilting_sampler.py 
As an external package, this file is imported into other xxx.py files and used to generate historical demand realization data under multivariate truncated normal distribution.
## value of order data and robust n=1.py
This file is a complete code used to solve the optimal decision for a single product. The output of this file includes: out-of-sample performance under the empirical distribution, out-of-sample performance under the augmented center distribution, and out-of-sample performance under the classic Wasserstein ambiguity set, and out-of-sample performance under our proposed improved Wasserstein ambiguity sets. These results are used to demonstrate the value of historical contract data and the effectiveness of our proposed model. Meanwhile, the solution time of the model is used to illustrate the computational effectiveness of our proposed reformulations and solution methods.
## value of order data n=2 indep.py 
This file plays a similar role to file "value of order data and robust n=1.py", except that the code is run in an independent multi-product context.
## value of order data and robust n=2 dep.py
This file plays a similar role to file "value of order data and robust n=1.py", except that the code is run in an dependent multi-product context.
## retailer incomplete knowledge.py and retailer complete knowledge.py
In our experiment, we numerically analyze the impact of the retailer’s incomplete knowledge of the true distribution on supplier decisions. Specifically, we consider the case where the retailer only has partial historical demand realization data, and makes order decisions based
on the empirical distribution. This file is used to output the decision results and out-of-sample performance for this particular case.
## ACD  vs ED wasserstein.py
This file is used to calculate the Wasserstein distance from the empirical distribution to the true distribution and the Wasserstein distance from the augmented center distribution to the true distribution. The results are used to illustrate that our proposed augmented center provides better predictions of the true distribution.
## results.xlsx
This file is a summary (part) of the output results in the above xxx.py files. It contains the solution results under different data settings and different model settings. They are used to form the tabular results and picture results in the experimental chapter of our article. For more intuitive results, see our paper.
