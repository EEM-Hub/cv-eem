---
source: sources/wiki-Image_segmentation.md
source_url: https://en.wikipedia.org/wiki/Image_segmentation
chunk: 2/5
---

## Region-growing methods

 

[Region-growing](./Region-growing) methods rely mainly on the assumption that the neighboring pixels within one region have similar values. The common procedure is to compare one pixel with its neighbors. If a similarity criterion is satisfied, the pixel can be set to belong to the same cluster as one or more of its neighbors. The selection of the similarity criterion is significant and the results are influenced by noise in all instances.

 

The method of [Statistical Region Merging](./Statistical_region_merging)[[45]](./Image_segmentation#cite_note-SRM-45) (SRM) starts by building the graph of pixels using 4-connectedness with edges weighted by the absolute value of the intensity difference. Initially each pixel forms a single pixel region. SRM then sorts those edges in a [priority queue](./Priority_queue) and decides whether or not to merge the current regions belonging to the edge pixels using a statistical predicate.

 

One [region-growing](./Region-growing) method is the seeded region growing method. This method takes a set of seeds as input along with the image. The seeds mark each of the objects to be segmented. The regions are iteratively grown by comparison of all unallocated neighboring pixels to the regions. The difference between a pixel's intensity value and the region's mean,     δ δ    {\displaystyle \delta }  ![{\displaystyle \delta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/c5321cfa797202b3e1f8620663ff43c4660ea03a), is used as a [measure of similarity](./Similarity_measure). The pixel with the smallest difference measured in this way is assigned to the respective region. This process continues until all pixels are assigned to a region. Because seeded region growing requires seeds as additional input, the segmentation results are dependent on the choice of seeds, and noise in the image can cause the seeds to be poorly placed.

 

Another [region-growing](./Region-growing) method is the unseeded region growing method. It is a modified algorithm that does not require explicit seeds. It starts with a single region      A  1     {\displaystyle A_{1}}  ![{\displaystyle A_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6bc2435b217c1a0f46f8a517ffa225c6f9440e81)—the pixel chosen here does not markedly influence the final segmentation. At each iteration it considers the neighboring pixels in the same way as seeded region growing. It differs from seeded region growing in that if the minimum     δ δ    {\displaystyle \delta }  ![{\displaystyle \delta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/c5321cfa797202b3e1f8620663ff43c4660ea03a) is less than a predefined threshold     T   {\displaystyle T}  ![{\displaystyle T}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec7200acd984a1d3a3d7dc455e262fbe54f7f6e0) then it is added to the respective region      A  j     {\displaystyle A_{j}}  ![{\displaystyle A_{j}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6019bb70c912e59e9d5f442e9217517743ed4831). If not, then the pixel is considered different from all current regions      A  i     {\displaystyle A_{i}}  ![{\displaystyle A_{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1aed3b5def921afbe6cc48aaf8f9b11c6f1c1e2d) and a new region      A  n + 1     {\displaystyle A_{n+1}}  ![{\displaystyle A_{n+1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/012bd48813e2d8f450c3dcf728cf3747bbd27a7d) is created with this pixel.

 

One variant of this technique, proposed by [Haralick](./Haralick) and Shapiro (1985),[[1]](./Image_segmentation#cite_note-computervision-1) is based on pixel [intensities](./Brightness). The [mean](./Arithmetic_mean) and [scatter](./Statistical_dispersion) of the region and the intensity of the candidate pixel are used to compute a [test statistic](./Test_statistic). If the test statistic is sufficiently small, the pixel is added to the region, and the region's mean and scatter are recomputed. Otherwise, the pixel is rejected, and is used to form a new region.

 

A special region-growing method is called     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a)-connected segmentation (see also [lambda-connectedness](./Lambda-connectedness)). It is based on pixel [intensities](./Brightness) and neighborhood-linking paths. A degree of connectivity (connectedness) is calculated based on a path that is formed by pixels. For a certain value of     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a), two pixels are called     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a)-connected if there is a path linking those two pixels and the connectedness of this path is at least     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a).     λ λ    {\displaystyle \lambda }  ![{\displaystyle \lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b43d0ea3c9c025af1be9128e62a18fa74bedda2a)-connectedness is an [equivalence relation](./Equivalence_relation).[[46]](./Image_segmentation#cite_note-lambda-connectedness-46)

 

[Split-and-merge segmentation](./Split_and_merge_segmentation) is based on a [quadtree](./Quadtree) partition of an image. It is sometimes called quadtree segmentation.

 

This method starts at the root of the tree that represents the whole image. If it is found non-uniform (not homogeneous), then it is split into four child squares (the splitting process), and so on. If, in contrast, four child squares are homogeneous, they are merged as several connected components (the merging process). The node in the tree is a segmented node. This process continues recursively until no further splits or merges are possible.[[47]](./Image_segmentation#cite_note-split-and-merge1-47)[[48]](./Image_segmentation#cite_note-split-and-merge2-48) When a special data structure is involved in the implementation of the algorithm of the method, its time complexity can reach     O ( n log ⁡ ⁡  n )   {\displaystyle O(n\log n)}  ![{\displaystyle O(n\log n)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9d2320768fb54880ca4356e61f60eb02a3f9d9f1), an optimal algorithm of the method.[[49]](./Image_segmentation#cite_note-split-and-merge3-49)

 

## Partial differential equation-based methods

 

Using a [partial differential equation](./Partial_differential_equation) (PDE)-based method and solving the PDE equation by a numerical scheme, one can segment the image.[[50]](./Image_segmentation#cite_note-50) Curve propagation is a popular technique in this category, with numerous applications to object extraction, object tracking, stereo reconstruction, etc. The central idea is to evolve an initial curve towards the lowest potential of a cost function, where its definition reflects the task to be addressed. As for most [inverse problems](./Inverse_problems), the minimization of the cost functional is non-trivial and imposes certain smoothness constraints on the solution, which in the present case can be expressed as geometrical constraints on the evolving curve.

 

### Parametric methods

 

[Lagrangian](./Lagrangian_relaxation) techniques are based on parameterizing the contour according to some sampling strategy and then evolving each element according to image and internal terms. Such techniques are fast and efficient, however the original "purely parametric" formulation (due to Kass, [Witkin](./Andrew_Witkin) and [Terzopoulos](./Demetri_Terzopoulos) in 1987 and known as "[snakes](./Snake_(computer_vision))"), is generally criticized for its limitations regarding the choice of sampling strategy, the internal geometric properties of the curve, topology changes (curve splitting and merging), addressing problems in higher dimensions, etc.. Nowadays, efficient "discretized" formulations have been developed to address these limitations while maintaining high efficiency. In both cases, energy minimization is generally conducted using a steepest-gradient descent, whereby derivatives are computed using, e.g., finite differences.

 

### Level-set methods

 

The [level-set method](./Level-set_method) was initially proposed to track moving interfaces by Dervieux and Thomasset[[51]](./Image_segmentation#cite_note-51)[[52]](./Image_segmentation#cite_note-52) in 1979 and 1981 and was later reinvented by Osher and Sethian in 1988.[[53]](./Image_segmentation#cite_note-OsherSethian1988-53) This has spread across various imaging domains in the late 1990s. It can be used to efficiently address the problem of curve/surface/etc. propagation in an implicit manner. The central idea is to represent the evolving contour using a signed function whose zero corresponds to the actual contour. Then, according to the motion equation of the contour, one can easily derive a similar flow for the implicit surface that when applied to the zero level will reflect the propagation of the contour. The level-set method affords numerous advantages: it is implicit, is parameter-free, provides a direct way to estimate the geometric properties of the evolving structure, allows for change of topology, and is intrinsic. It can be used to define an optimization framework, as proposed by Zhao, Merriman and Osher in 1996. One can conclude that it is a very convenient framework for addressing numerous applications of computer vision and medical image analysis.[[54]](./Image_segmentation#cite_note-54) Research into various [level-set data structures](./Level-set_data_structures) has led to very efficient implementations of this method.

 

### Fast marching methods

 

The [fast marching method](./Fast_marching_method) has been used in image segmentation,[[55]](./Image_segmentation#cite_note-55) and this model has been improved (permitting both positive and negative propagation speeds) in an approach called the generalized fast marching method.[[56]](./Image_segmentation#cite_note-56)

 

## Variational methods

 

The goal of variational methods is to find a segmentation
which is optimal with respect to a specific energy functional. The functionals consist of a data fitting term and a regularizing terms. A classical representative is the [Potts model](./Potts_model) defined for an image     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) by

      argmin  u   ⁡ ⁡  γ γ  ‖ ‖  ∇ ∇  u  ‖ ‖   0   + ∫ ∫  ( u − −  f  )  2    d x .   {\displaystyle \operatorname {argmin} _{u}\gamma \|\nabla u\|_{0}+\int (u-f)^{2}\,dx.}  ![{\displaystyle \operatorname {argmin} _{u}\gamma \|\nabla u\|_{0}+\int (u-f)^{2}\,dx.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65aff33a382ba1b78b69a4b03e268af273bce25b) 

A minimizer      u  ∗ ∗      {\displaystyle u^{*}}  ![{\displaystyle u^{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cfeddccb8efb954b55c85480a6fe7d4e33b60ab4) is a piecewise constant image which has an optimal tradeoff between the squared L2 distance to the given image     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) and the total length of its jump set. The jump set of      u  ∗ ∗      {\displaystyle u^{*}}  ![{\displaystyle u^{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cfeddccb8efb954b55c85480a6fe7d4e33b60ab4) defines a segmentation. The relative weight of the energies is tuned by the parameter     γ γ  > 0   {\displaystyle \gamma >0}  ![{\displaystyle \gamma >0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/775a6435e4270cddf2cd7dcb486c20f7f4bb8cee). The binary variant of the Potts model, i.e., if the range of     u   {\displaystyle u}  ![{\displaystyle u}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3e6bb763d22c20916ed4f0bb6bd49d7470cffd8) is restricted to two values, is often called Chan-[Vese](./Luminița_Vese) model.[[57]](./Image_segmentation#cite_note-57) An important generalization is the [Mumford-Shah model](./Mumford–Shah_functional)[[58]](./Image_segmentation#cite_note-58) given by

      argmin  u , K   ⁡ ⁡  γ γ   |  K  |  + μ μ   ∫ ∫    K  C      |  ∇ ∇  u   |   2    d x + ∫ ∫  ( u − −  f  )  2    d x .   {\displaystyle \operatorname {argmin} _{u,K}\gamma |K|+\mu \int _{K^{C}}|\nabla u|^{2}\,dx+\int (u-f)^{2}\,dx.}  ![{\displaystyle \operatorname {argmin} _{u,K}\gamma |K|+\mu \int _{K^{C}}|\nabla u|^{2}\,dx+\int (u-f)^{2}\,dx.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c6dbbdac824117f3e0849b2b9501d9588a369f0c) 

The functional value is the sum of the total length of the segmentation curve     K   {\displaystyle K}  ![{\displaystyle K}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2b76fce82a62ed5461908f0dc8f037de4e3686b0), the smoothness of the approximation     u   {\displaystyle u}  ![{\displaystyle u}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3e6bb763d22c20916ed4f0bb6bd49d7470cffd8), and its distance to the original image     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61). The weight of the smoothness penalty is adjusted by     μ μ  > 0   {\displaystyle \mu >0}  ![{\displaystyle \mu >0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67319256f71b2ecddcb2a1f2a58bef0494135e62). The Potts model is often called piecewise constant Mumford-Shah model as it can be seen as the degenerate case     μ μ  → →  ∞ ∞    {\displaystyle \mu \to \infty }  ![{\displaystyle \mu \to \infty }](https://wikimedia.org/api/rest_v1/media/math/render/svg/77f79b0e55af5924f64f38f5fe8b0ce25aa4173c). The optimization problems are known to be NP-hard in general but near-minimizing strategies work well in practice. Classical algorithms are [graduated non-convexity](./Graduated_optimization) and [Ambrosio-Tortorelli approximation](./Mumford–Shah_functional).

 

## Graph partitioning methods

 

[Graph](./Graph_(data_structure)) partitioning methods are an effective tools for image segmentation since they model the impact of pixel neighborhoods on a given cluster of pixels or pixel, under the assumption of homogeneity in images. In these methods, the image is modeled as a weighted, [undirected graph](./Undirected_graph). Usually a pixel or a group of pixels are associated with [nodes](./Vertex_(graph_theory)) and [edge](./Glossary_of_graph_theory#Basics) weights define the (dis)similarity between the neighborhood pixels. The graph (image) is then partitioned according to a criterion designed to model "good" clusters. Each partition of the nodes (pixels) output from these algorithms are considered an object segment in the image; see [Segmentation-based object categorization](./Segmentation-based_object_categorization). Some popular algorithms of this category are normalized cuts,[[59]](./Image_segmentation#cite_note-59) [random walker](./Random_walker_(computer_vision)),[[60]](./Image_segmentation#cite_note-60) minimum cut,[[61]](./Image_segmentation#cite_note-61) isoperimetric partitioning,[[62]](./Image_segmentation#cite_note-62) [minimum spanning tree-based segmentation](./Minimum_spanning_tree-based_segmentation),[[63]](./Image_segmentation#cite_note-63) and [segmentation-based object categorization](./Segmentation-based_object_categorization).

 

### Markov random fields

 

The application of [Markov random fields](./Markov_random_field) (MRF) for images was suggested in early 1984 by Geman and Geman.[[64]](./Image_segmentation#cite_note-64) Their strong mathematical foundation and ability to provide a global optimum even when defined on local features proved to be the foundation for novel research in the domain of image analysis, de-noising and segmentation. MRFs are completely characterized by their prior probability distributions, marginal probability distributions, [cliques](./Clique_(graph_theory)), smoothing constraint as well as criterion for updating values. The criterion for image segmentation using MRFs is restated as finding the labelling scheme which has maximum probability for a given set of features. The broad categories of image segmentation using MRFs are supervised and unsupervised segmentation.

 

#### Supervised image segmentation using MRF and MAP

 

In terms of image segmentation, the function that MRFs seek to maximize is the probability of identifying a labelling scheme given a particular set of features are detected in the image. This is a restatement of the [maximum a posteriori estimation](./Maximum_a_posteriori_estimation) method.

 [![](//upload.wikimedia.org/wikipedia/commons/3/35/MRF_neighborhood.png)](./File:MRF_neighborhood.png)MRF neighborhood for a chosen pixel 

The generic algorithm for image segmentation using MAP is given below:

 
1. Define the neighborhood of each feature (random variable in MRF terms).

Generally this includes 1st-order or 2nd-order neighbors.
2. Set initial probabilities *P*(*fi*)> for each feature as 0 or
3. where *fi* ∈ Σ is the set containing features extracted

for pixel i and define an initial set of clusters.
4. Using the training data compute the mean (*μ**ℓ**i*) and variance (σ*ℓ**i*) for each label. This is termed as class statistics.
5. Compute the marginal distribution for the given labeling scheme *P*(*fi* | *ℓ**i*) using [Bayes' theorem](./Bayes'_theorem)
and the class statistics calculated earlier. A Gaussian model is used for the marginal distribution.
      1  σ σ  (  ℓ ℓ   i   )   2 π π        e  − −  (  f  i   − −  μ μ  (  ℓ ℓ   i   )  )  2    /  ( 2 σ σ  (  ℓ ℓ   i    )  2   )    d  ℓ ℓ   i     {\displaystyle {\frac {1}{\sigma (\ell _{i}){\sqrt {2\pi }}}}e^{-(f_{i}-\mu (\ell _{i}))^{2}/(2\sigma (\ell _{i})^{2})}\,d\ell _{i}}  ![{\displaystyle {\frac {1}{\sigma (\ell _{i}){\sqrt {2\pi }}}}e^{-(f_{i}-\mu (\ell _{i}))^{2}/(2\sigma (\ell _{i})^{2})}\,d\ell _{i}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/33c32b8e88e382070fcb5cadc88f3583f0eba561)
6. Calculate the probability of each class label given the neighborhood defined previously.

[Clique](./Clique_(graph_theory)) potentials are used to model the social impact in labeling.
7. Iterate over new prior probabilities and redefine clusters such that these probabilities are maximized.

This is done using a variety of optimization algorithms described below.
8. Stop when probability is maximized and labeling scheme does not change.

The calculations can be implemented in [log likelihood](./Log-likelihood) terms as well.

 

#### Optimization algorithms

 

Each optimization algorithm is an adaptation of models from a variety of fields and they are set apart by their unique cost functions. The common trait of cost functions is to penalize change in pixel value as well as difference in pixel label when compared to labels of neighboring pixels.

 

##### Iterated conditional modes/gradient descent

 

The [iterated conditional modes](./Iterated_conditional_modes) (ICM) algorithm tries to reconstruct the ideal labeling scheme by changing the values of each pixel over each iteration and evaluating the energy of the new labeling scheme using the cost function given below,

     α α  ( 1 − −  δ δ  (  ℓ ℓ   i   − −   ℓ ℓ    initial   i   ) + β β   Σ Σ   q ∈ ∈  N ( i )   ( 1 − −  δ δ  (  ℓ ℓ   i   ,  ℓ ℓ   q ( i )   ) ) .   {\displaystyle \alpha (1-\delta (\ell _{i}-\ell _{{\text{initial }}i})+\beta \Sigma _{q\in N(i)}(1-\delta (\ell _{i},\ell _{q(i)})).}  ![{\displaystyle \alpha (1-\delta (\ell _{i}-\ell _{{\text{initial }}i})+\beta \Sigma _{q\in N(i)}(1-\delta (\ell _{i},\ell _{q(i)})).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/46d29c8c62b05956217258f2d4f21b7cb97c893d) 

where α is the penalty for change in pixel label and β is the penalty for difference in label between
neighboring pixels and chosen pixel. Here     N ( i )   {\displaystyle N(i)}  ![{\displaystyle N(i)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fc61255f3ccbed0ca1ea0eec5a8459737f5931c6) is neighborhood of pixel i and δ is the Kronecker delta function. A major issue with ICM is that, similar to gradient descent, it has a tendency to rest over local maxima and thus not obtain a globally optimal labeling scheme.

 

##### Simulated annealing (SA)

 

Derived as an analogue of annealing in metallurgy, [simulated annealing](./Simulated_annealing) (SA) uses change in pixel label over iterations and estimates the difference in energy of each newly formed graph to the initial data. If the newly formed graph is more profitable, in terms of low energy cost, given by:

     Δ Δ  U =  U  new   − −   U  old     {\displaystyle \Delta U=U^{\text{new}}-U^{\text{old}}}  ![{\displaystyle \Delta U=U^{\text{new}}-U^{\text{old}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8ec373bc4947f826c0be2aebc33099b6edb1aa6f)      ℓ ℓ   i   =   {     ℓ ℓ   i   new   ,    if   Δ Δ  U ≤ ≤  0 ,      ℓ ℓ   i   new   ,    if   Δ Δ  U > 0   and   δ δ  <  e  − −  Δ Δ  U  /  T   ,  ℓ ℓ   i   old           {\displaystyle \ell _{i}={\begin{cases}\ell _{i}^{\text{new}},&{\text{if }}\Delta U\leq 0,\\\ell _{i}^{\text{new}},&{\text{if }}\Delta U>0{\text{ and }}\delta <e^{-\Delta U/T},\ell _{i}^{\text{old}}\end{cases}}}  ![{\displaystyle \ell _{i}={\begin{cases}\ell _{i}^{\text{new}},&{\text{if }}\Delta U\leq 0,\\\ell _{i}^{\text{new}},&{\text{if }}\Delta U>0{\text{ and }}\delta <e^{-\Delta U/T},\ell _{i}^{\text{old}}\end{cases}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f824e014b6c723bca20265eaa5c587888b92eee4) 

the algorithm selects the newly formed graph. Simulated annealing requires the input of temperature schedules which directly affects the speed of convergence of the system, as well as energy threshold for minimization to occur.

 

##### Alternative algorithms

 

A range of other methods exist for solving simple as well as higher order MRFs. They include Maximization of Posterior Marginal, Multi-scale MAP estimation,[[65]](./Image_segmentation#cite_note-65) Multiple Resolution segmentation[[66]](./Image_segmentation#cite_note-66) and more. Apart from likelihood estimates, graph-cut using maximum flow[[67]](./Image_segmentation#cite_note-67) and other highly constrained graph based methods[[68]](./Image_segmentation#cite_note-68)[[69]](./Image_segmentation#cite_note-69) exist for solving MRFs.

 

#### Image segmentation using MAP and expectation–maximization

 

The [expectation–maximization algorithm](./Expectation–maximization_algorithm) is utilized to iteratively estimate the a posterior probabilities and distributions of labeling when no training data is available and no estimate of segmentation model can be formed. A general approach is to use histograms to represent the features of an image and proceed as outlined briefly in this three-step algorithm:

 

1. A random estimate of the model parameters is utilized.

 

2. E step: Estimate class statistics based on the random segmentation model defined. Using these, compute the [conditional probability](./Conditional_probability) of belonging to a label given the feature set is calculated using naive [Bayes' theorem](./Bayes'_theorem).

     P ( λ λ  ∣ ∣   f  i   ) =    P (  f  i   ∣ ∣  λ λ  ) P ( λ λ  )    Σ Σ   λ λ  ∈ ∈  Λ Λ    P (  f  i   ∣ ∣  λ λ  ) P ( λ λ  )      {\displaystyle P(\lambda \mid f_{i})={\frac {P(f_{i}\mid \lambda )P(\lambda )}{\Sigma _{\lambda \in \Lambda }P(f_{i}\mid \lambda )P(\lambda )}}}  ![{\displaystyle P(\lambda \mid f_{i})={\frac {P(f_{i}\mid \lambda )P(\lambda )}{\Sigma _{\lambda \in \Lambda }P(f_{i}\mid \lambda )P(\lambda )}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/46448830777aeebb65d84ddac6a57f690f823484) 

Here     λ λ  ∈ ∈  Λ Λ    {\displaystyle \lambda \in \Lambda }  ![{\displaystyle \lambda \in \Lambda }](https://wikimedia.org/api/rest_v1/media/math/render/svg/7d1f14e3b08f79e38d62384eb90eff43a2fb587c), the set of all possible labels.

 

3. M step: The established relevance of a given feature set to a labeling scheme is now used to compute the a priori estimate of a given label in the second part of the algorithm. Since the actual number of total labels is unknown (from a training data set), a hidden estimate of the number of labels given by the user is utilized in computations.

     P ( λ λ  ) =     Σ Σ   λ λ  ∈ ∈  Λ Λ    P ( λ λ  ∣ ∣   f  i   )    |  Ω Ω   |       {\displaystyle P(\lambda )={\frac {\Sigma _{\lambda \in \Lambda }P(\lambda \mid f_{i})}{|\Omega |}}}  ![{\displaystyle P(\lambda )={\frac {\Sigma _{\lambda \in \Lambda }P(\lambda \mid f_{i})}{|\Omega |}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/469fbab67ed79e61e7e33d053116018849f9006e) 

where     Ω Ω    {\displaystyle \Omega }  ![{\displaystyle \Omega }](https://wikimedia.org/api/rest_v1/media/math/render/svg/24b0d5ca6f381068d756f6337c08e0af9d1eeb6f) is the set of all possible features.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/ef/Sample_segmentation_HMRF-EM.png/250px-Sample_segmentation_HMRF-EM.png)](./File:Sample_segmentation_HMRF-EM.png)Segmentation of color image using HMRF-EM model 

#### Disadvantages of MAP and EM based image segmentation

 
1. Exact MAP estimates cannot be easily computed.
2. Approximate MAP estimates are computationally expensive to calculate.
3. Extension to multi-class labeling degrades performance and increases storage required.
4. Reliable estimation of parameters for EM is required for global optima to be achieved.
5. Based on method of optimization, segmentation may cluster to local minima.

 

## Watershed transformation

 

The [watershed transformation](./Watershed_(algorithm)) considers the gradient magnitude of an image as a topographic surface. Pixels having the highest gradient magnitude intensities (GMIs) correspond to watershed lines, which represent the region boundaries. Water placed on any pixel enclosed by a common watershed line flows downhill to a common local intensity minimum (LIM). Pixels draining to a common minimum form a catch basin, which represents a segment.

 

## Model-based segmentation

 

The central assumption of model-based approaches is that the structures of interest have a tendency towards a particular shape. Therefore, one can seek a probabilistic model that characterizes the shape and its variation. When segmenting an image, constraints can be imposed using this model as a prior.[[70]](./Image_segmentation#cite_note-StaibDuncan1992-70) Such a task may involve (i) registration of the training examples to a common pose, (ii) probabilistic representation of the variation of the registered samples, and (iii) statistical inference between the model and the image. Other important methods in the literature for model-based segmentation include [active shape models](./Active_shape_model) and [active appearance models](./Active_appearance_model).

 


