Dear Reviewer hFUg,

Thanks for your insightful comments and time again. We also appreciate that you give us the chance to clarify our work further. Here are some supplementary experimental results and clarification of our rebuttal:

> Con1: Difference with other methods.

Except for the contents mentioned in the rebuttal, we'd like to facilitate a better understanding of **our unique design and why it works** through the 'Interdisciplinary Teaching', which is a cutting-edge approach in the field of education:

'Interdisciplinary Teaching' aims to **enhance the comprehensiveness and depth of learning by integrating knowledge and methods from 👉different subjects (w.r.t diverse graph datasets)👈**. It addresses the complexity of real-world problems (w.r.t diverse and complex structures, attributes, structure and attribute patterns) requiring a multidisciplinary perspective for solutions and encouraging students to apply cross-domain knowledge. This approach leads to a more thorough understanding and higher-level thinking skills (w.r.t transferrable pretrained graph representations). The teaching strategy highlights **👉the connections between subjects (implemented by learnable graph coordinators)👈**, asking teachers to design courses that reflect core concepts of the disciplines while fostering interaction among them. This helps students see the bridges between subjects, nurturing flexible and innovative thinking (w.r.t. transferring to new downstream datasets, especially the few-shot scenarios).

> Con3: Comparision with cross-domain graph dataset pretraining and transferring achieved by All-in-one and projection.

We compare our method with it here:

|Dataset/FAGCN|Supervised|IP + ProG|GCOPE + ProG|
|---|---|---|---|
|Cora| 0.3819 ± 0.03 | 0.3312 ± 0.02 ↓|0.4283 ± 0.03 ↑ |
|Citeseer| 0.5219 ± 0.08 | 0.4896 ± 0.02 ↓|0.5251 ± 0.01 ↑ |
|Wisconsin| 0.5222 ± 0.05 | 0.4814 ± 0.05 ↓|0.6208 ± 0.04 ↑ |
|Texas|0.6900 ± 0.06| 0.5187 ± 0.04 ↓|0.7438 ± 0.01 ↑ |

As observed, our method consistently outperforms All-in-one adapted to an isolated-pretrained GNN, proving our effectiveness.

> Revision for Equation 2.

We will re-write Equation 2 as:

$$
\tilde A= \begin{bmatrix}
A_{\mathrm{diag}} & R_A^T \\
R_A & R_R
\end{bmatrix}
$$

where $A_{\mathrm{diag}} = \mathrm{Diag}(A^{(1)},A^{(2)},\cdots,A^{(M)})$, $R_A=\mathrm{Stack}(R_A^{(1)},R_A^{(2)},\cdots,R_A^{(M)})$, $R_R=\mathbb{1}^{M\times M}$. $\mathrm{Diag}$ means concatenating matrices diagonally, and $\mathrm{Stack}$ means stacking row-vectors into a matrix. Specifically, $R_A^{(i)}\in \mathbb{R}^{\sum_k^M|\mathcal{V}^{(k)}|}$ and we have the $j-th$ value of $R_A^{(i)}$ as 

$$
R_{A}^{(i)}(j) = 
\begin{cases}
1 & \sum_1^i|\mathcal{V}^{(k)}| \le j < \sum_1^{i+1}|\mathcal{V}^{(k)}| \\
0 & \mathrm{otherwise}.
\end{cases}
$$

We genuinely thank you for your time and efforts again!

Sincerely,

Authors
