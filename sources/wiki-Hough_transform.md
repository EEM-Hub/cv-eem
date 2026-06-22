---
source: https://en.wikipedia.org/wiki/Hough_transform
fetched: 2026-06-21
---

Method of detecting shapes within images 
| Feature detection |
| --- |
| Edge detection |
| CannyDericheDifferentialSobelPrewittRobinsonRoberts cross |
| Corner detection |
| Harris operatorShi and TomasiLevel curve curvatureHessian feature strength measuresSUSANFAST |
| Blob detection |
| Laplacian of Gaussian (LoG)Difference of Gaussians (DoG)Determinant of Hessian  (DoH)Maximally stable extremal regionsPCBR |
| Ridge detection |
| Hough transform |
| Hough transformGeneralized Hough transform |
| Structure tensor |
| Structure tensorGeneralized structure tensor |
| Affine invariant feature detection |
| Affine shape adaptationHarris affineHessian affine |
| Feature description |
| SIFTSURFGLOHHOG |
| Scale space |
| Scale-space axiomsImplementation detailsPyramids |
| vte |

 

The **Hough transform** ([/hʌf/](./Help:IPA/English)) is a [feature extraction](./Feature_extraction) technique used in [image analysis](./Image_analysis), [computer vision](./Computer_vision), [pattern recognition](./Pattern_recognition), and [digital image processing](./Digital_image_processing).[[1]](./Hough_transform#cite_note-1)[[2]](./Hough_transform#cite_note-2) The purpose of the technique is to find imperfect instances of objects within a certain class of shapes by a voting procedure. This voting procedure is carried out in a [parameter space](./Parameter_space), from which object candidates are obtained as local maxima in a so-called accumulator space that is explicitly constructed by the algorithm for computing the Hough transform.  Mathematically it is simply the  [Radon transform](./Radon_transform) in the plane, known since at least 1917, but the Hough transform refers to its use in image analysis. 

 

The classical Hough transform was concerned with the identification of [lines](./Line_(mathematics)) in the image, but later the Hough transform has been extended to identifying positions of arbitrary shapes, most commonly [circles](./Circle) or [ellipses](./Ellipse). The Hough transform as it is universally used today was invented by [Richard Duda](./Richard_Duda) and [Peter Hart](./Peter_E._Hart) in 1972, who called it a "generalized Hough transform"[[3]](./Hough_transform#cite_note-3) after the related 1962 patent of Paul Hough.[[4]](./Hough_transform#cite_note-4)[[5]](./Hough_transform#cite_note-5) The transform was popularized in the [computer vision](./Computer_vision) community by [Dana H. Ballard](./Dana_H._Ballard) through a 1981 journal article titled "[Generalizing the Hough transform to detect arbitrary shapes](./Generalised_Hough_transform)".

 

## History

 

It was initially invented for machine analysis of [bubble chamber](./Bubble_chamber) photographs (Hough, 1959).

 

The Hough transform was patented as [U.S. patent 3,069,654](https://patents.google.com/patent/US3069654) in 1962 and assigned to the U.S. Atomic Energy Commission with the name "Method and Means for Recognizing Complex Patterns". This patent uses a slope-intercept parametrization for straight lines, which awkwardly leads to an unbounded transform space, since the slope can go to infinity.

 

The rho–theta parametrization universally used today was [first described](./Species_description) in

 Duda, R.O.; Hart, P. E. (January 1972). ["Use of the Hough Transformation to Detect Lines and Curves in Pictures"](https://doi.org/10.1145%2F361237.361242). *Comm. ACM*. **15**: 11–15. [doi](./Doi_(identifier)):[10.1145/361237.361242](https://doi.org/10.1145%2F361237.361242). [S2CID](./S2CID_(identifier)) [1105637](https://api.semanticscholar.org/CorpusID:1105637). 

although it was already standard for the [Radon transform](./Radon_transform) since at least the 1930s.

 

O'Gorman and Clowes' variation is described in

 O'Gorman, Frank; Clowes, MB (1976). "Finding Picture Edges Through Collinearity of Feature Points". *IEEE Trans. Comput*. **25** (4): 449–456. [Bibcode](./Bibcode_(identifier)):[1976ITCmp.100..449O](https://ui.adsabs.harvard.edu/abs/1976ITCmp.100..449O). [doi](./Doi_(identifier)):[10.1109/TC.1976.1674627](https://doi.org/10.1109%2FTC.1976.1674627). [S2CID](./S2CID_(identifier)) [10851078](https://api.semanticscholar.org/CorpusID:10851078). 

The story of how the modern form of the Hough transform was invented is given in

 Hart, P. E. (November 2009). ["How the Hough Transform was Invented"](https://web.archive.org/web/20180516103712/https://pdfs.semanticscholar.org/f7e8/cbca97de34fd3695e538e164a1b40d27b04e.pdf) (PDF). *IEEE Signal Processing Magazine*. **26** (6): 18–22. [Bibcode](./Bibcode_(identifier)):[2009ISPM...26...18H](https://ui.adsabs.harvard.edu/abs/2009ISPM...26...18H). [doi](./Doi_(identifier)):[10.1109/msp.2009.934181](https://doi.org/10.1109%2Fmsp.2009.934181). [S2CID](./S2CID_(identifier)) [16245096](https://api.semanticscholar.org/CorpusID:16245096). Archived from [the original](https://pdfs.semanticscholar.org/f7e8/cbca97de34fd3695e538e164a1b40d27b04e.pdf) (PDF) on 2018-05-16. 

## Theory

 

In automated analysis of [digital images](./Digital_image), a subproblem often arises of detecting simple shapes, such as straight lines, circles or ellipses. In many cases an [edge detector](./Edge_detection) can be used as a pre-processing stage to obtain image points or image pixels that are on the desired curve in the image space. Due to imperfections in either the image data or the edge detector, however, there may be missing points or pixels on the desired curves as well as spatial deviations between the ideal line/circle/ellipse and the noisy edge points as they are obtained from the edge detector. For these reasons, it is often non-trivial to group the extracted edge features to an appropriate set of lines, circles or ellipses. The purpose of the Hough transform is to address this problem by making it possible to perform groupings of edge points into object candidates by performing an explicit voting procedure over a set of parameterized image objects (Shapiro and Stockman, 304).

 

### Detecting lines

 

The simplest case of Hough transform is detecting straight lines. In general, the straight line *y* = *mx* + *b* can be represented as a point (*b*, *m*) in the parameter space. However, vertical lines pose a problem. They would give rise to unbounded values of the slope parameter *m*. Thus, for computational reasons, Duda and Hart[[6]](./Hough_transform#cite_note-6) proposed the use of the [Hesse normal form](./Hesse_normal_form)

     r = x cos ⁡ ⁡  θ θ  + y sin ⁡ ⁡  θ θ  ,   {\displaystyle r=x\cos \theta +y\sin \theta ,}  ![{\displaystyle r=x\cos \theta +y\sin \theta ,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/66a82759b07aafbe9d00aa827d07608312fbe698) 

where     r   {\displaystyle r}  ![{\displaystyle r}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d1ecb613aa2984f0576f70f86650b7c2a132538) is the distance from the [origin](./Origin_(mathematics)) to the closest point on the straight line, and     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af) is the angle between the     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) axis and the line connecting the origin with that closest point.

 

The intuition for this form, similarly to the plane equation, is that every vector on the line must be perpendicular (orthogonal) to the line segment of length     r   {\displaystyle r}  ![{\displaystyle r}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d1ecb613aa2984f0576f70f86650b7c2a132538) that comes from the origin. The intersection point of the function line and the perpendicular line that comes from the origin is at      P  0   = ( r cos ⁡ ⁡  θ θ  , r sin ⁡ ⁡  θ θ  )   {\displaystyle P_{0}=(r\cos \theta ,r\sin \theta )}  ![{\displaystyle P_{0}=(r\cos \theta ,r\sin \theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1a2085c03a99d17e42be6042956e57c58e291287). So, for any point     P = ( x , y )   {\displaystyle P=(x,y)}  ![{\displaystyle P=(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/099c643e67f1973c546d7e001eae4ab0ec7b2415) on the line, the vector     P − −   P  0     {\displaystyle P-P_{0}}  ![{\displaystyle P-P_{0}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7a7ab711724f8beac13df1229d6e0764a4a31c42) must be orthogonal to the vector      P  0   − −  0 =  P  0     {\displaystyle P_{0}-0=P_{0}}  ![{\displaystyle P_{0}-0=P_{0}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c49c636b872aef07ed3a8b3a93f1baadc6cbbe5d). This enforces     ( P − −   P  0   ) ⋅ ⋅   P  0   = 0   {\displaystyle (P-P_{0})\cdot P_{0}=0}  ![{\displaystyle (P-P_{0})\cdot P_{0}=0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9ff6c8641f46e7da3ebb68781ad8a43ad487c958). Therefore,     P ⋅ ⋅   P  0   =  P  0   ⋅ ⋅   P  0     {\displaystyle P\cdot P_{0}=P_{0}\cdot P_{0}}  ![{\displaystyle P\cdot P_{0}=P_{0}\cdot P_{0}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/49129225c89fcdafc84f2106f64966d948416389). So, we get     r ( x cos ⁡ ⁡  θ θ  + y sin ⁡ ⁡  θ θ  ) =  r  2   (  cos  2   ⁡ ⁡  θ θ  +  sin  2   ⁡ ⁡  θ θ  )   {\displaystyle r(x\cos \theta +y\sin \theta )=r^{2}(\cos ^{2}\theta +\sin ^{2}\theta )}  ![{\displaystyle r(x\cos \theta +y\sin \theta )=r^{2}(\cos ^{2}\theta +\sin ^{2}\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ad397228af0230b05f3035c42c912b609d0de20d). Yet, as      cos  2   ⁡ ⁡  θ θ  +  sin  2   ⁡ ⁡  θ θ  = 1   {\displaystyle \cos ^{2}\theta +\sin ^{2}\theta =1}  ![{\displaystyle \cos ^{2}\theta +\sin ^{2}\theta =1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9333418071b0b0662ba53f8983fe1cbb613ad005), we get the final form of     x cos ⁡ ⁡  θ θ  + y sin ⁡ ⁡  θ θ  = r   {\displaystyle x\cos \theta +y\sin \theta =r}  ![{\displaystyle x\cos \theta +y\sin \theta =r}](https://wikimedia.org/api/rest_v1/media/math/render/svg/02fa06f4f34aeb2b5cbd7b6bd4218c699672e68d).

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e6/R_theta_line.GIF/250px-R_theta_line.GIF)](./File:R_theta_line.GIF) 

It is therefore possible to associate with each line of the image a pair     ( r , θ θ  )   {\displaystyle (r,\theta )}  ![{\displaystyle (r,\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed8396fdc359fb06c93722137c959e7496e47ed6). The     ( r , θ θ  )   {\displaystyle (r,\theta )}  ![{\displaystyle (r,\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed8396fdc359fb06c93722137c959e7496e47ed6) plane is sometimes referred to as *Hough space* for the set of straight lines in two dimensions. This representation makes the Hough transform conceptually very close to the two-dimensional [Radon transform](./Radon_transform). In fact, the Hough transform is mathematically equivalent to the Radon transform, but the two transformations have different computational interpretations traditionally associated with them.[[7]](./Hough_transform#cite_note-7)

 

Given a *single point* in the plane, the set of *all* straight lines going through that point corresponds to a [sinusoidal curve](./Sine_wave) in the (*r*, *θ*) plane, which is unique to that point. A set of two or more points that form a straight line will produce sinusoids crossing at the (*r*, *θ*) for that line. Thus, the problem of detecting [collinear points](./Line_(geometry)#Collinear_points) can be converted to the problem of finding [concurrent curves](./Concurrent_lines).

 

### Probabilistic interpretation

 

Given a shape parametrized by     (  a  1   , . . . ,  a  t   )   {\displaystyle (a_{1},...,a_{t})}  ![{\displaystyle (a_{1},...,a_{t})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a22aa2ef404c23cb81a23a6629c191f6af3a84eb), taking values in the set     S   {\displaystyle S}  ![{\displaystyle S}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4611d85173cd3b508e67077d4a1252c9c05abca2) called the shape space, one can interpret the Hough transform as the inverse transform of a [probability distribution](./Probability_distribution) on the image space to the shape space     S   {\displaystyle S}  ![{\displaystyle S}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4611d85173cd3b508e67077d4a1252c9c05abca2), and interpret shape detection as [maximum likelihood estimation](./Maximum_likelihood_estimation).

 

Explicitly, the Hough transform performs an approximate [naive Bayes](./Naive_Bayes_classifier) inference. We start with a uniform prior on the shape space. We consider only the positive evidence, and ignore all negative evidence, so that we can detect partially occluded shapes. 

 

We add up the [log-likelihood](./Log-likelihood) in the shape space up to an additive constant. The assumption of *naive Bayes* means that all pixels in the image space provide independent evidence, so that their likelihoods multiply, that is, their log-likelihoods add. The freedom in additive constant allows us to perform no operation on the "background pixels" in shape space.

 

Finally, we perform maximum likelihood estimation by picking out the peaks in the log-likelihood on the shape space.[[8]](./Hough_transform#cite_note-8)

 

## Implementation

 

The linear Hough transform [algorithm](./Algorithm) estimates the two parameters that define a straight line. The transform space has two dimensions, and every point in the transform space is used as an accumulator to detect or identify a line described by     r = x cos ⁡ ⁡  θ θ  + y sin ⁡ ⁡  θ θ    {\displaystyle r=x\cos \theta +y\sin \theta }  ![{\displaystyle r=x\cos \theta +y\sin \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/22a90ffe4dc97e5d76230b29c99febac9df6d53e). Every point in the detected edges in the image contributes to the accumulators.

 

The [dimension](./Dimension) of the accumulator equals the number of unknown parameters, i.e., two, considering quantized values of     r   {\displaystyle r}  ![{\displaystyle r}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d1ecb613aa2984f0576f70f86650b7c2a132538) and     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af) in the pair     ( r , θ θ  )   {\displaystyle (r,\theta )}  ![{\displaystyle (r,\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed8396fdc359fb06c93722137c959e7496e47ed6). For each pixel at     ( x , y )   {\displaystyle (x,y)}  ![{\displaystyle (x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/41cf50e4a314ca8e2c30964baa8d26e5be7a9386) and its neighborhood, the Hough transform algorithm determines whether there is enough evidence of a straight line at that pixel. If so, it will calculate the parameters     ( r , θ θ  )   {\displaystyle (r,\theta )}  ![{\displaystyle (r,\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed8396fdc359fb06c93722137c959e7496e47ed6) of that line, then look for the accumulator's bin that the parameters fall into, and increment the value of that bin.

 

By finding the bins with the highest values, typically by looking for local maxima in the accumulator space, the most likely lines can be extracted, and their (approximate) geometric definitions read off (Shapiro and Stockman, 304). The simplest way of finding these *peaks* is by applying some form of threshold, but other techniques may yield better results in different circumstances – determining which lines are found, as well as how many. Since the lines returned do not contain any length information, it is often necessary, in the next step, to find which parts of the image match up with which lines. Moreover, due to imperfection errors in the edge-detection step, there will usually be errors in the accumulator space, which may make it non-trivial to find the appropriate peaks, and thus the appropriate lines.

 

The final result of the linear Hough transform is a two-dimensional array (matrix) similar to the accumulator—one dimension of this matrix is the quantized angle     θ θ    {\displaystyle \theta }  ![{\displaystyle \theta }](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ab2664b422d53eb0c7df3b87e1360d75ad9af), and the other dimension is the quantized distance     r   {\displaystyle r}  ![{\displaystyle r}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d1ecb613aa2984f0576f70f86650b7c2a132538). Each element of the matrix has a value equal to the sum of the points or pixels that are positioned on the line represented by quantized parameters     ( r , θ θ  )   {\displaystyle (r,\theta )}  ![{\displaystyle (r,\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed8396fdc359fb06c93722137c959e7496e47ed6). So the element with the highest value indicates the straight line that is most represented in the input image.[[9]](./Hough_transform#cite_note-Jeppe_Jensen_2007-9)

 

## Examples

 

### Example 1

 

Consider three data points, shown here as black dots.

 [![Three graphs that show steps of the Hough transformation process](//upload.wikimedia.org/wikipedia/commons/thumb/2/28/Hough_transform_diagram.svg/960px-Hough_transform_diagram.svg.png)](./File:Hough_transform_diagram.svg)Example 1 
- For each data point, a number of lines are plotted going through it, all at different angles. These are shown here in different colours.
- The Hough transform accumulates contributions from all pixels in the detected edge. To each line, a support line exists which is [perpendicular](./Perpendicular) to it and which intersects the [origin](./Origin_(mathematics)). In each case, one of these is shown as an arrow.
- The length (i.e. perpendicular distance to the origin) and angle of each support line is calculated. Lengths and angles are tabulated below the diagrams.

 

From the calculations, it can be seen that in either case the support line at 60° has a similar length.
Hence, it is understood that the corresponding lines (the blue ones in the above picture) are very similar.
One can thus assume that all points lie close to the blue line.

 

### Example 2

 

The following is a different example showing the results of a Hough transform on a raster image containing two thick lines.

 

[![](//upload.wikimedia.org/wikipedia/commons/thumb/1/1c/Hough-example-result-en.png/960px-Hough-example-result-en.png)](./File:Hough-example-result-en.png)

 

The results of this transform were stored in a matrix. Cell value represents the number of curves through any point. Higher cell values are rendered brighter. The two distinctly bright spots are the Hough parameters of the two lines. From these spots' positions, angle and distance from image center of the two lines in the input image can be determined.

 

## Variations and extensions

 

### Using the gradient direction to reduce the number of votes

 

An improvement suggested by O'Gorman and Clowes can be used to detect lines if one takes into account that the local [gradient](./Gradient) of the image intensity will necessarily be orthogonal to the edge. Since [edge detection](./Edge_detection) generally involves computing the intensity gradient magnitude, the gradient direction is often found as a side effect. If a given point of coordinates (*x,y*) happens to indeed be on a line, then the local direction of the gradient gives the *θ* parameter corresponding to said line, and the *r* parameter is then immediately obtained. (Shapiro and Stockman, 305) The gradient direction can be estimated to within 20°, which shortens the sinusoid trace from the full 180° to roughly 45°. This reduces the computation time and has the interesting effect of reducing the number of useless votes, thus enhancing the visibility of the spikes corresponding to real lines in the image.

 

### Kernel-based Hough transform (KHT)

 

Fernandes and Oliveira [[10]](./Hough_transform#cite_note-10) suggested an improved voting scheme for the Hough transform that allows a software implementation to achieve real-time performance even on relatively large images (e.g., 1280×960). The Kernel-based Hough transform uses the same     ( r , θ θ  )   {\displaystyle (r,\theta )}  ![{\displaystyle (r,\theta )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed8396fdc359fb06c93722137c959e7496e47ed6) parameterization proposed by Duda and Hart but operates on clusters of approximately collinear pixels. For each cluster, votes are cast using an oriented elliptical-Gaussian kernel that models the uncertainty associated with the best-fitting line with respect to the corresponding cluster. The approach not only significantly improves the performance of the voting scheme, but also produces a much cleaner accumulator and makes the transform more robust to the detection of spurious lines.

 

### 3-D kernel-based Hough transform for plane detection (3DKHT)

 

Limberger and Oliveira[[11]](./Hough_transform#cite_note-11) suggested a deterministic technique for plane detection in unorganized point clouds whose cost is     n log ⁡ ⁡  ( n )   {\displaystyle n\log(n)}  ![{\displaystyle n\log(n)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/aca080dee55ba2825a2d955bd6ca43c0e7ed04db) in the number of samples, achieving real-time performance for relatively large datasets (up to      10  5     {\displaystyle 10^{5}}  ![{\displaystyle 10^{5}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7310d2ac4ddefd259b8a2c7c8fb89c6a9ea11a8) points on a 3.4 GHz CPU). It is based on a fast Hough-transform voting strategy for planar regions, inspired by the Kernel-based Hough transform (KHT). This 3D kernel-based Hough transform (3DKHT) uses a fast and robust algorithm to segment clusters of approximately co-planar samples, and casts votes for individual clusters (instead of for individual samples) on a (    θ θ  , ϕ ϕ  , ρ ρ    {\displaystyle \theta ,\phi ,\rho }  ![{\displaystyle \theta ,\phi ,\rho }](https://wikimedia.org/api/rest_v1/media/math/render/svg/fb8958539904f4bd42205602efbb0d2cd4cd6ee9)) spherical accumulator using a trivariate Gaussian kernel. The approach is several orders of magnitude faster than existing (non-deterministic) techniques for plane detection in point clouds, such as [RHT](./Randomized_Hough_transform) and [RANSAC](./RANSAC), and scales better with the size of the datasets. It can be used with any application that requires fast detection of planar features on large datasets.

 

### Hough transform of curves, and its generalization for analytical and non-analytical shapes

 

Although the version of the transform described above applies only to finding straight lines, a similar transform can be used for finding any shape which can be represented by a set of parameters. A circle, for instance, can be transformed into a set of three parameters, representing its center and radius, so that the Hough space becomes three dimensional. Arbitrary ellipses and curves can also be found this way, as can any shape easily expressed as a set of parameters.

 

The generalization of the Hough transform for detecting analytical shapes in spaces having any dimensionality was proposed by Fernandes and Oliveira.[[12]](./Hough_transform#cite_note-12) In contrast to other Hough transform-based approaches for analytical shapes, Fernandes' technique does not depend on the shape one wants to detect nor on the input [data type](./Data_type). The detection can be driven to a type of analytical shape by changing the assumed model of geometry where data have been encoded (e.g., [euclidean space](./Euclidean_space), [projective space](./Projective_space), [conformal geometry](./Conformal_geometry), and so on), while the proposed formulation remains unchanged. Also, it guarantees that the intended shapes are represented with the smallest possible number of parameters, and it allows the concurrent detection of different kinds of shapes that best fit an input set of entries with different dimensionalities and different geometric definitions (e.g., the concurrent detection of planes and spheres that best fit a set of points, straight lines and circles).

 

For more complicated shapes in the plane (i.e., shapes that cannot be represented analytically in some 2D space), the [Generalised Hough transform](./Generalised_Hough_transform)[[13]](./Hough_transform#cite_note-13) is used, which allows a [feature](./Feature_(computer_vision)) to vote for a particular position, orientation and/or scaling of the shape using a predefined look-up table.The Hough transform accumulates contributions from all pixels in the detected edge.

 

### Circle detection process

 Main article: [Circle Hough Transform](./Circle_Hough_Transform) 

Altering the algorithm to detect circular shapes instead of lines is relatively straightforward.

 
- First, we create the accumulator space, which is made up of a cell for each pixel. Initially each cell is set to 0.
- For each edge point (i, j) in the image, increment all cells which according to the equation of a circle     ( i − −  a  )  2   + ( j − −  b  )  2   =  r  2     {\displaystyle (i-a)^{2}+(j-b)^{2}=r^{2}}  ![{\displaystyle (i-a)^{2}+(j-b)^{2}=r^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/570e10b74db7456ed15cbdac08eda013f0f37223) could be the center of a circle. These cells are represented by the letter     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc) in the equation.
- For each possible value of     a   {\displaystyle a}  ![{\displaystyle a}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ffd2487510aa438433a2579450ab2b3d557e5edc) found in the previous step, find all possible values of     b   {\displaystyle b}  ![{\displaystyle b}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f11423fbb2e967f986e36804a8ae4271734917c3) which satisfy the equation.
- Search for local maxima in the accumulator space. These cells represent circles that were detected by the algorithm.

 

If we do not know the radius of the circle we are trying to locate beforehand, we can use a three-dimensional accumulator space to search for circles with an arbitrary radius. Naturally, this is more computationally expensive.

 

This method can also detect circles that are partially outside of the accumulator space, as long as enough of the circle's area is still present within it.

 

### Detection of 3D objects (planes and cylinders)

 

Hough transform can also be used for the detection of 3D objects in [range data](./Range_imaging) or 3D [point clouds](./Point_cloud). The extension of classical Hough transform for plane detection is quite straightforward. A plane is represented by its explicit equation     z =  a  x   x +  a  y   y + d   {\displaystyle z=a_{x}x+a_{y}y+d}  ![{\displaystyle z=a_{x}x+a_{y}y+d}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c892123f5baf89334e5e534934c499faef6002fa) for which we can use a 3D Hough space corresponding to      a  x     {\displaystyle a_{x}}  ![{\displaystyle a_{x}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/339ff13ca52000e5467b829dfd008f6846820b57),      a  y     {\displaystyle a_{y}}  ![{\displaystyle a_{y}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4332752b07ec00b533637753ef567a2730cf335f) and     d   {\displaystyle d}  ![{\displaystyle d}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e85ff03cbe0c7341af6b982e47e9f90d235c66ab). This extension suffers from the same problems as its 2D counterpart i.e., near horizontal planes can be reliably detected, while the performance deteriorates as planar direction becomes vertical (big values of      a  x     {\displaystyle a_{x}}  ![{\displaystyle a_{x}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/339ff13ca52000e5467b829dfd008f6846820b57) and      a  y     {\displaystyle a_{y}}  ![{\displaystyle a_{y}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4332752b07ec00b533637753ef567a2730cf335f) amplify the noise in the data). This formulation of the plane has been used for the detection of planes in the point clouds acquired from airborne laser scanning [[14]](./Hough_transform#cite_note-14) and works very well because in that domain all planes are nearly horizontal.

 

For generalized plane detection using Hough transform, the plane can be parametrized by its normal vector     n   {\displaystyle n}  ![{\displaystyle n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a601995d55609f2d9f5e233e36fbe9ea26011b3b) (using spherical coordinates) and its distance from the origin     ρ ρ    {\displaystyle \rho }  ![{\displaystyle \rho }](https://wikimedia.org/api/rest_v1/media/math/render/svg/1f7d439671d1289b6a816e6af7a304be40608d64) resulting in a three dimensional Hough space. This results in each point in the input data voting for a sinusoidal surface in the Hough space. The intersection of these sinusoidal surfaces indicates presence of a plane.[[15]](./Hough_transform#cite_note-15) A more general approach for more than 3 dimensions requires search heuristics to remain feasible.[[16]](./Hough_transform#cite_note-16)

 

Hough transform has also been used to find cylindrical objects in point clouds using a two step approach. The first step finds the orientation of the cylinder and the second step finds the position and radius.[[17]](./Hough_transform#cite_note-17)

 

### Using weighted features

 

One common variation detail. That is, finding the bins with the highest count in one stage can be used to constrain the range of values searched in the next.

 

### Carefully chosen parameter space

 

A high-dimensional parameter space for the Hough transform is not only slow, but if implemented without forethought can easily overrun the available memory. Even if the programming environment allows the allocation of an array larger than the available memory space through [virtual memory](./Virtual_memory), the number of [page swaps](./Page_swapping) required for this will be very demanding because the accumulator array is used in a randomly accessed fashion, rarely stopping in contiguous memory as it skips from index to index.

 

Consider the task of finding ellipses in an 800x600 image. Assuming that the radii of the ellipses are oriented along principal axes, the parameter space is four-dimensional. (*x*, *y*) defines the center of the ellipse, and *a* and *b* denote the two radii. Allowing the center to be anywhere in the image, adds the constraint 0<x<800 and 0<y<600. If the radii are given the same values as constraints, what is left is a sparsely filled accumulator array of more than 230 billion values.

 

A program thus conceived is unlikely to be allowed to allocate sufficient memory. This doesn't mean that the problem can't be solved, but only that new ways to constrain the size of the accumulator array are to be found, which makes it feasible. For instance:

 
1. If it is reasonable to assume that the ellipses are each contained entirely within the image, the range of the radii can be reduced. The largest the radii can be is if the center of the ellipse is in the center of the image, allowing the edges of the ellipse to stretch to the edges. In this extreme case, the radii can only each be half the magnitude of the image size oriented in the same direction. Reducing the range of a and b in this fashion reduces the accumulator array to 57 billion values.
2. Trade accuracy for space in the estimation of the center: If the center is predicted to be off by 3 on both the x and y axis this reduces the size of the accumulator array to about 6 billion values.
3. Trade accuracy for space in the estimation of the radii: If the radii are estimated to each be off by 5 further reduction of the size of the accumulator array occurs, by about 256 million values.
4. Crop the image to areas of interest. This is image dependent, and therefore unpredictable, but imagine a case where all of the edges of interest in an image are in the upper left quadrant of that image. The accumulator array can be reduced even further in this case by constraining all 4 parameters by a factor of 2, for a total reduction factor of 16.

 

By applying just the first three of these constraints to the example stated about, the size of the accumulator array is reduced by almost a factor of 1000, bringing it down to a size that is much more likely to fit within a modern computer's memory.

 

#### Efficient ellipse detection algorithm

 

Yonghong Xie and Qiang Ji give an efficient way of implementing the Hough transform for ellipse detection by overcoming the memory issues.[[18]](./Hough_transform#cite_note-XieJi2002-18) As discussed in the algorithm (on page 2 of the paper), this approach uses only a one-dimensional accumulator (for the minor axis) in order to detect ellipses in the image. The complexity is O(N3) in the number of non-zero points in the image.

 

## Limitations

 

The Hough transform is only efficient if a high number of votes fall in the right bin, so that the bin can be easily detected amid the background noise. This means that the bin must not be too small, or else some votes will fall in the neighboring bins, thus reducing the visibility of the main bin.[[19]](./Hough_transform#cite_note-19)

 

Also, when the number of parameters is large (that is, when we are using the Hough transform with typically more than three parameters), the average number of votes cast in a single bin is very low, and those bins corresponding to a real figure in the image do not necessarily appear to have a much higher number of votes than their neighbors. The complexity increases at a rate of Big&#x2D;O(A<sup&#x3E;m &#x2D; 2</sup&#x3E;)      O    (   A  m − −  2    )    {\displaystyle {\mathcal {O}}\left({A^{m-2}}\right)}  ![{\displaystyle {\mathcal {O}}\left({A^{m-2}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/040b6ef3507faabf1df20fcc4206395dec508452) with each additional parameter, where     A   {\displaystyle A}  ![{\displaystyle A}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7daff47fa58cdfd29dc333def748ff5fa4c923e3) is the size of the image space and     m   {\displaystyle m}  ![{\displaystyle m}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0a07d98bb302f3856cbabc47b2b9016692e3f7bc) is the number of parameters. (Shapiro and Stockman, 310) Thus, the Hough transform must be used with great care to detect anything other than lines or circles.

 

Finally, much of the efficiency of the Hough transform is dependent on the quality of the input data: the edges must be detected well for the Hough transform to be efficient. Use of the Hough transform on noisy images is a very delicate matter and generally, a denoising stage must be used before. In the case where the image is corrupted by speckle, as is the case in radar images, the [Radon transform](./Radon_transform) is sometimes preferred to detect lines, because it attenuates the noise through summation.

 

## See also

 
- [Generalised Hough transform](./Generalised_Hough_transform)
- [Randomized Hough transform](./Randomized_Hough_transform)
- [Radon transform](./Radon_transform)
- [Fourier transform](./Fourier_transform)

 

## References

  
1. [↑](./Hough_transform#cite_ref-1) [Shapiro, Linda](./Linda_Shapiro) and Stockman, George. "Computer Vision", Prentice-Hall, Inc. 2001
2. [↑](./Hough_transform#cite_ref-2) Romanengo, Chiara; Falcidieno, Bianca; Biasotti, Silvia (2024-09-01). ["Extending the Hough transform to recognize and approximate space curves in 3D models"](https://doi.org/10.1016%2Fj.cagd.2024.102377). *Computer Aided Geometric Design*. **113** 102377. [doi](./Doi_(identifier)):[10.1016/j.cagd.2024.102377](https://doi.org/10.1016%2Fj.cagd.2024.102377). [ISSN](./ISSN_(identifier)) [0167-8396](https://search.worldcat.org/issn/0167-8396).
3. [↑](./Hough_transform#cite_ref-3) Duda, R. O. and P. E. Hart, "Use of the Hough Transformation to Detect Lines and Curves in Pictures", *Comm. ACM*, vol. 15, pp. 11–15 (January, 1972).
4. [↑](./Hough_transform#cite_ref-4) Hough, P. V. C. *Method and means for recognizing complex patterns*, U.S. Patent 3,069,654, Dec. 18, 1962.
5. [↑](./Hough_transform#cite_ref-5) P. V. C. Hough, *[Machine Analysis of Bubble Chamber Pictures](http://inspirehep.net/record/919922/files/HEACC59_598-602.pdf)*, Proc. Int. Conf. High Energy Accelerators and Instrumentation, 1959.
6. [↑](./Hough_transform#cite_ref-6) [Richard O. Duda](./Richard_O._Duda); [Peter E. Hart](./Peter_E._Hart) (April 1971). ["Use of the Hough Transformation to Detect Lines and Curves in Pictures"](http://www.ai.sri.com/pubs/files/tn036-duda71.pdf) (PDF). [Artificial Intelligence Center](./Artificial_Intelligence_Center).
7. [↑](./Hough_transform#cite_ref-7) [A short introduction to the Radon and Hough transforms and how they relate to each other Bot generated title ](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.2.9419). CiteSeerX.
8. [↑](./Hough_transform#cite_ref-8) Stephens, R. S. (1990). ["A probabilistic approach to the Hough Transform"](https://dx.doi.org/10.5244/c.4.12). *Proceedings of the British Machine Vision Conference 1990*. British Machine Vision Association. pp. 12.1 – 12.6. [doi](./Doi_(identifier)):[10.5244/c.4.12](https://doi.org/10.5244%2Fc.4.12).
9. [↑](./Hough_transform#cite_ref-Jeppe_Jensen_2007_9-0) Jensen, Jeppe. ["Hough Transform for Straight Lines"](https://web.archive.org/web/20120426054222/http://www.cvmt.dk/education/teaching/e07/MED3/IP/hough_lines.pdf) (PDF). Archived from [the original](http://www.cvmt.dk/education/teaching/e07/MED3/IP/hough_lines.pdf) (PDF) on 26 April 2012. Retrieved 16 December 2011.
10. [↑](./Hough_transform#cite_ref-10) Fernandes, L.A.F.; Oliveira, M.M. (2008). "Real-time line detection through an improved Hough transform voting scheme". *Pattern Recognition*. **41** (1): 299–314. [Bibcode](./Bibcode_(identifier)):[2008PatRe..41..299F](https://ui.adsabs.harvard.edu/abs/2008PatRe..41..299F). [doi](./Doi_(identifier)):[10.1016/j.patcog.2007.04.003](https://doi.org/10.1016%2Fj.patcog.2007.04.003). [S2CID](./S2CID_(identifier)) [5996185](https://api.semanticscholar.org/CorpusID:5996185).
11. [↑](./Hough_transform#cite_ref-11) Limberger, F. A.; Oliveira, M. M. (2015). ["Real-Time Detection of Planar Regions in Unorganized Point Clouds"](https://lume.ufrgs.br/bitstream/10183/97001/1/000919556.pdf) (PDF). *Pattern Recognition*. **48** (6): 2043–2053. [Bibcode](./Bibcode_(identifier)):[2015PatRe..48.2043L](https://ui.adsabs.harvard.edu/abs/2015PatRe..48.2043L). [doi](./Doi_(identifier)):[10.1016/j.patcog.2014.12.020](https://doi.org/10.1016%2Fj.patcog.2014.12.020). [hdl](./Hdl_(identifier)):[10183/97001](https://hdl.handle.net/10183%2F97001).
12. [↑](./Hough_transform#cite_ref-12) Fernandes, L.A.F.; Oliveira, M.M. (2012). "A general framework for subspace detection in unordered multidimensional data". *Pattern Recognition*. **45** (9): 3566–3579. [Bibcode](./Bibcode_(identifier)):[2012PatRe..45.3566F](https://ui.adsabs.harvard.edu/abs/2012PatRe..45.3566F). [doi](./Doi_(identifier)):[10.1016/j.patcog.2012.02.033](https://doi.org/10.1016%2Fj.patcog.2012.02.033).
13. [↑](./Hough_transform#cite_ref-13) Ballard, D.H. (1981). "Generalizing the Hough transform to detect arbitrary shapes". *Pattern Recognition*. **13** (2): 111–122. [Bibcode](./Bibcode_(identifier)):[1981PatRe..13..111B](https://ui.adsabs.harvard.edu/abs/1981PatRe..13..111B). [doi](./Doi_(identifier)):[10.1016/0031-3203(81)90009-1](https://doi.org/10.1016%2F0031-3203%2881%2990009-1). [hdl](./Hdl_(identifier)):[1802/13802](https://hdl.handle.net/1802%2F13802).
14. [↑](./Hough_transform#cite_ref-14) Vosselman, G., Dijkman, S: "[3D Building Model Reconstruction from Point Clouds and Ground Plans](https://pdfs.semanticscholar.org/bb77/54f8e928bd79baf56a1da501484a4567d8ab.pdf)", International Archives of the Photogrammetry, Remote Sensing and Spatial Information Sciences, vol 34, part 3/W4, October 22–24, 2001, Annapolis, MA, USA, pp. 37–44.
15. [↑](./Hough_transform#cite_ref-15) Tahir Rabbani: ["Automatic reconstruction of industrial installations – Using point clouds and images"](http://www.ncg.knaw.nl/Publicaties/Geodesy/62Rabbani.html) [Archived](https://web.archive.org/web/20081201052227/http://www.ncg.knaw.nl/Publicaties/Geodesy/62Rabbani.html) 2008-12-01 at the [Wayback Machine](./Wayback_Machine), pages 43–44, Publications on Geodesy 62, Delft, 2006. [ISBN](./ISBN_(identifier)) [978-90-6132-297-9](./Special:BookSources/978-90-6132-297-9).
16. [↑](./Hough_transform#cite_ref-16) Achtert, Elke; Böhm, Christian; David, Jörn; Kröger, Peer; [Zimek, Arthur](./Arthur_Zimek) (2008). "Global Correlation Clustering Based on the Hough Transform". *Statistical Analysis and Data Mining*. **1** (3): 111–127. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.716.6006](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.716.6006). [doi](./Doi_(identifier)):[10.1002/sam.10012](https://doi.org/10.1002%2Fsam.10012). [S2CID](./S2CID_(identifier)) [5111283](https://api.semanticscholar.org/CorpusID:5111283).
17. [↑](./Hough_transform#cite_ref-17) Tahir Rabbani and Frank van den Heuvel, "[Efficient hough transform for automatic detection of cylinders in point clouds](https://pdfs.semanticscholar.org/d205/b6e6f743bc62e31257b47d18b36ada95f4f1.pdf)" in Proceedings of the 11th Annual Conference of the Advanced School for Computing and Imaging (ASCI '05), The Netherlands, June 2005.
18. [↑](./Hough_transform#cite_ref-XieJi2002_18-0) Yonghong Xie; Qiang Ji (2002). "A new efficient ellipse detection method". *Object recognition supported by user interaction for service robots*. Vol. 2. pp. 957–960. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.1.8792](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.1.8792). [doi](./Doi_(identifier)):[10.1109/ICPR.2002.1048464](https://doi.org/10.1109%2FICPR.2002.1048464). [ISBN](./ISBN_(identifier)) [978-0-7695-1695-0](./Special:BookSources/978-0-7695-1695-0). [S2CID](./S2CID_(identifier)) [9276255](https://api.semanticscholar.org/CorpusID:9276255).
19. [↑](./Hough_transform#cite_ref-19) ["Image Transforms - Hough Transform"](http://homepages.inf.ed.ac.uk/rbf/HIPR2/hough.htm). Homepages.inf.ed.ac.uk. Retrieved 2009-08-17.

 

## External links

 
- [hough_transform.cpp](https://web.archive.org/web/20150503173405/http://cimg.sourceforge.net/screenshots.shtml) – C++ code – example of CImg library ([open source](./Open_source_software) library, [C++](./C++) source code, [Grayscale](./Grayscale) images)
- [Interactive Demonstration on the Basics of the Hough Transform](https://web.archive.org/web/20200430031840/http://matlabtricks.com/post-39/understanding-the-hough-transform)
- [https://web.archive.org/web/20070827233423/http://www.rob.cs.tu-bs.de/content/04-teaching/06-interactive/Hough.html](https://web.archive.org/web/20070827233423/http://www.rob.cs.tu-bs.de/content/04-teaching/06-interactive/Hough.html) – [Java Applet](./Java_Applet) + Source for learning the Hough transformation in slope-intercept form
- [https://web.archive.org/web/20070827191440/http://www.rob.cs.tu-bs.de/content/04-teaching/06-interactive/HNF.html](https://web.archive.org/web/20070827191440/http://www.rob.cs.tu-bs.de/content/04-teaching/06-interactive/HNF.html) – [Java Applet](./Java_Applet) + Source for learning the Hough-Transformation in normal form
- [http://www.sydlogan.com/deskew.html](http://www.sydlogan.com/deskew.html) [Archived](https://web.archive.org/web/20100209090834/http://www.sydlogan.com/deskew.html) 2010-02-09 at the [Wayback Machine](./Wayback_Machine) – Deskew images using Hough transform ([Grayscale](./Grayscale) images, [C++](./C++) source code)
- [https://web.archive.org/web/20070922090216/http://imaging.gmse.net/articledeskew.html](https://web.archive.org/web/20070922090216/http://imaging.gmse.net/articledeskew.html) – Deskew images using Hough transform ([Visual Basic](./Visual_Basic) source code)
- [http://www.mitov.com/products/visionlab](http://www.mitov.com/products/visionlab) – [Delphi](./Embarcadero_Delphi), [C++](./C++) and [.NET](./.NET_Framework) free for educational purposes library containing Line, Circle and Line segment Hough transform components.
- [Tarsha-Kurdi, F., Landes, T., Grussenmeyer, P., 2007a. Hough-transform and extended RANSAC algorithms for automatic detection of 3d building roof planes from Lidar data.](http://www.isprs.org/proceedings/XXXVI/3-W52/final_papers/Tarsha-Kurdi_2007.pdf) ISPRS Proceedings. Workshop Laser scanning. Espoo, Finland, September 12–14, 2007.
- [Into](https://web.archive.org/web/20100709025652/http://intopii.com/into/) contains open source implementations of linear and circular Hough transform in C++
- [http://www.vision.ime.usp.br/~edelgado/defesa/code/hough.html](http://www.vision.ime.usp.br/~edelgado/defesa/code/hough.html) [Deprecated link](./Wikipedia:Archive.today_guidance) archived 2012-12-05 at [archive.today](./Archive.today) Hough-transform for Ellipse detection, implemented in [C](./C_(programming_language)).
- [scikit-image](http://scikit-image.org/docs/dev/api/skimage.transform.html) Hough-transform for line, circle and ellipse, implemented in [Python](./Python_(programming_language)).
- [](http://www.mathworks.com/matlabcentral/fileexchange/40537-wavelet-based-circular-hough-transform) Hough transform based on wavelet filtering, to detect a circle of a particular radius. ([Matlab](./Matlab) code.)
- [Hough transform for lines using MATLAB](http://www.mathworks.com/help/images/detect-lines-in-images.html) [Archived](https://web.archive.org/web/20140413140540/http://www.mathworks.com/help/images/detect-lines-in-images.html) 2014-04-13 at the [Wayback Machine](./Wayback_Machine)
- [Hough transform for circles in MATLAB](http://www.mathworks.com/help/images/ref/imfindcircles.html)
- [KHT](http://www2.ic.uff.br/~laffernandes/projects/kht/) – C++ source code.
- [3DKHT](http://www.inf.ufrgs.br/~oliveira/pubs_files/HT3D/HT3D_page.html) – C++ source code and datasets.
- [Straight line Hough transform in Python](https://www.luigiselmi.eu/dip/hough_transform.html)