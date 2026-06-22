---
source: https://en.wikipedia.org/wiki/Edge_detection
fetched: 2026-06-21
---

Image processing method 
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

 

**Edge detection** includes a variety of [mathematical](./Mathematical) methods that aim at identifying ***edges***, defined as [curves](./Curve) in a [digital image](./Digital_image) at which the [image brightness](./Luminous_intensity) changes sharply or, more formally, has [discontinuities](./Discontinuity_(mathematics)). The same problem of finding discontinuities in one-dimensional signals is known as *[step detection](./Step_detection)* and the problem of finding signal discontinuities over time is known as *[change detection](./Change_detection)*. Edge detection is a fundamental tool in [image processing](./Image_processing), [machine vision](./Machine_vision) and [computer vision](./Computer_vision), particularly in the areas of [feature detection](./Feature_detection_(computer_vision)) and [feature extraction](./Feature_extraction).[[1]](./Edge_detection#cite_note-1)

 

## Motivations

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/20/%C3%84%C3%A4retuvastuse_n%C3%A4ide.png/500px-%C3%84%C3%A4retuvastuse_n%C3%A4ide.png)](./File:Ääretuvastuse_näide.png)[Canny edge detection](./Canny_edge_detection) applied to a photograph 

The purpose of detecting sharp changes in image brightness is to capture important events and changes in properties of the world.
It can be shown that under rather general assumptions for an image formation model, discontinuities in image brightness are likely to correspond to:[[2]](./Edge_detection#cite_note-2)[[3]](./Edge_detection#cite_note-lin95-3)

 
- discontinuities in depth,
- discontinuities in surface orientation,
- changes in material properties and
- variations in scene illumination.

 

In the ideal case, the result of applying an edge detector to an image may lead to a set of connected curves that indicate the boundaries of objects, the boundaries of surface markings as well as curves that correspond to discontinuities in surface orientation.
Thus, applying an edge detection algorithm to an image may significantly reduce the amount of data to be processed and may therefore filter out information that may be regarded as less relevant, while preserving the important structural properties of an image.
If the edge detection step is successful, the subsequent task of interpreting the information contents in the original image may therefore be substantially simplified.
However, it is not always possible to obtain such ideal edges from real life images of moderate complexity.

 

Edges extracted from non-trivial images are often hampered by *fragmentation*, meaning that the edge curves are not connected, missing edge segments as well as *false edges* not corresponding to interesting phenomena in the image – thus complicating the subsequent task of interpreting the image data.[[4]](./Edge_detection#cite_note-lin98-4)

 

Edge detection is one of the fundamental steps in image processing, [image analysis](./Image_analysis), image pattern recognition, and computer vision techniques.

 

## Edge properties

 

The edges extracted from a two-dimensional image of a three-dimensional scene can be classified as either viewpoint dependent or viewpoint independent.
A *viewpoint independent edge* typically reflects inherent properties of the three-dimensional objects, such as surface markings and surface shape.
A *viewpoint dependent edge* may change as the viewpoint changes, and typically reflects the geometry of the scene, such as objects occluding one another.

 

A typical edge might for instance be the border between a block of red color and a block of yellow. In contrast a **[line](./Line_(mathematics))** (as can be extracted by a [ridge detector](./Ridge_detection)) can be a small number of [pixels](./Pixel) of a different color on an otherwise unchanging background. For a line, there may therefore usually be one edge on each side of the line.

 

## A simple edge model

 

Although certain literature has considered the detection of ideal step edges, the edges obtained from natural images are usually not at all ideal step edges. Instead they are normally affected by one or several of the following effects:

 
- focal blur caused by a finite [depth-of-field](./Depth-of-field) and finite [point spread function](./Point_spread_function).
- [penumbral blur](./Penumbra) caused by shadows created by light sources of non-zero radius.
- [shading](./Shading) at a smooth object

 

A number of researchers have used a Gaussian smoothed step edge (an [error function](./Error_function)) as the simplest extension of the ideal step edge model for modeling the effects of edge blur in practical applications.[[4]](./Edge_detection#cite_note-lin98-4)[[5]](./Edge_detection#cite_note-5)
Thus, a one-dimensional image     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) that has exactly one edge placed at     x = 0   {\displaystyle x=0}  ![{\displaystyle x=0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/953917eaf52f2e1baad54c8c9e3d6f9bb3710cdc) may be modeled as:

     f ( x ) =     I  r   − −   I  ℓ ℓ     2    (  erf ⁡ ⁡   (   x    2   σ σ     )  + 1  )  +  I  ℓ ℓ    .   {\displaystyle f(x)={\frac {I_{r}-I_{\ell }}{2}}\left(\operatorname {erf} \left({\frac {x}{{\sqrt {2}}\sigma }}\right)+1\right)+I_{\ell }.}  ![{\displaystyle f(x)={\frac {I_{r}-I_{\ell }}{2}}\left(\operatorname {erf} \left({\frac {x}{{\sqrt {2}}\sigma }}\right)+1\right)+I_{\ell }.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cbd244b4c0a95f097d652707aef9a3233b274c3e) 

At the left side of the edge, the intensity is      I  ℓ ℓ    =  lim  x → →  − −  ∞ ∞    f ( x )   {\displaystyle I_{\ell }=\lim _{x\rightarrow -\infty }f(x)}  ![{\displaystyle I_{\ell }=\lim _{x\rightarrow -\infty }f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7c5edfeb7641930325fbc7081b9a7b0c18422b55), and right of the edge it is
     I  r   =  lim  x → →  ∞ ∞    f ( x )   {\displaystyle I_{r}=\lim _{x\rightarrow \infty }f(x)}  ![{\displaystyle I_{r}=\lim _{x\rightarrow \infty }f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/70afa613f3d3a9f46ed205d9d75db2100aab75ad). The scale parameter     σ σ    {\displaystyle \sigma }  ![{\displaystyle \sigma }](https://wikimedia.org/api/rest_v1/media/math/render/svg/59f59b7c3e6fdb1d0365a494b81fb9a696138c36) is called the blur scale of the edge. Ideally this scale parameter should be adjusted based on the quality of image to avoid destroying true edges of the image.[*[citation needed](./Wikipedia:Citation_needed)*]

 

## Difficulty

 

Outside of images with simple objects or featuring well-controlled lighting, edge detection is not a trivial task, since it can be difficult to determine what threshold should be used to define an edge between two pixels.[[4]](./Edge_detection#cite_note-lin98-4) For example, in the following one-dimensional signal, most would intuitively say there is an edge between the 4th and 5th pixels:

 
| 5 | 7 | 6 | 4 | 152 | 148 | 149 |
| --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |

 

However, if the intensity difference between the 4th and the 5th pixels were smaller, it would not be as easy to say that there should be an edge in the corresponding region. Similarly, if the intensity differences between the adjacent neighboring pixels were higher, one could argue that more than one edge should be considered to exist, or even none at all.

 
| 5 | 7 | 6 | 61 | 113 | 148 | 149 |
| --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |

 

## Approaches

 

There are many methods for edge detection, but most of them can be grouped into two categories, search-based and [zero-crossing](./Zero_crossing) based.
The search-based methods detect edges by first computing a measure of edge strength, usually a [first-order derivative expression](./First-order_derivative_expression) such as the gradient magnitude, and then searching for local directional maxima of the gradient magnitude using a computed estimate of the local orientation of the edge, usually the gradient direction.
The zero-crossing based methods search for zero crossings in a [second-order derivative expression](./Second-order_derivative_expression) computed from the image in order to find edges, usually the zero-crossings of the [Laplacian](./Laplacian) or the zero-crossings of a non-linear differential expression. As a pre-processing step to edge detection, a smoothing stage, typically [Gaussian smoothing](./Gaussian_smoothing), is almost always applied (see also [noise reduction](./Noise_reduction)).

 

The edge detection methods that have been published mainly differ in the types of smoothing filters that are applied and the way the measures of edge strength are computed. As many edge detection methods rely on the computation of image gradients, they also differ in the types of filters used for computing gradient estimates in the *x*- and *y*-directions.

 

A survey of a number of different edge detection methods can be found in (Ziou and Tabbone 1998);[[6]](./Edge_detection#cite_note-6) see also the encyclopedia articles on edge detection in *Encyclopedia of Mathematics*[[3]](./Edge_detection#cite_note-lin95-3) and Encyclopedia of Computer Science and Engineering.[[7]](./Edge_detection#cite_note-7)

 

### Canny

 Main article: [Canny edge detector](./Canny_edge_detector) 

[John Canny](./John_Canny) considered the mathematical problem of deriving an optimal smoothing filter, given the criteria of detection, localization and minimizing multiple responses to a single edge.[[8]](./Edge_detection#cite_note-8) He showed that the optimal filter, given these assumptions, is a sum of four exponential terms. He also showed that this filter can be well approximated by first-order derivatives of Gaussians.
Canny also introduced the notion of non-maximum suppression, which means that, given the presmoothing filters, edge points are defined as points where the gradient magnitude assumes a local maximum in the gradient direction.
Looking for the zero crossing of the 2nd derivative along the gradient direction was first proposed by [Haralick](./Haralick).[[9]](./Edge_detection#cite_note-9)
It took less than two decades to find a modern geometric variational meaning for that operator, that links it to the [Marr–Hildreth](./Marr–Hildreth_algorithm) (zero crossing of the Laplacian) edge detector.
That observation was presented by [Ron Kimmel](./Ron_Kimmel) and [Alfred Bruckstein](./Alfred_Bruckstein?action=edit&redlink=1).[[10]](./Edge_detection#cite_note-10)

 

Although his work was done in the early days of computer vision, the [Canny edge detector](./Canny_edge_detector) (including its variations) is still a state-of-the-art edge detector.[[11]](./Edge_detection#cite_note-11) Edge detectors that perform better than the Canny usually require longer computation times or a greater number of parameters.

 

### Kovalevsky

 

[Vladimir A. Kovalevsky](./Vladimir_Antonovich_Kovalevsky)[[12]](./Edge_detection#cite_note-12) has suggested a quite different approach. He uses a preprocessing of the image with the Sigma filter[[13]](./Edge_detection#cite_note-13) and with a special filter for the dilution of the ramps. This method uses no brightness of the image but only the intensities of the color channels which is important for detecting an edge between two adjacent pixels of equal brightness but different colors. The method scans the image two times: first along the horizontal lines and second along the vertical columns. In each horizontal line six consequent adjacent pixels are considered and five color difference between each two adjacent pixels are calculated. Each color difference is the sum of absolute differences of the intensities of the color channels Red, Green, and Blue of the corresponding adjacent pixels. If this sum is greater than a given threshold, then the sign of the color difference is set equal to the sign of the difference of the green intensities. If the green difference is zero, then the sign of the color difference is set equal to the sign of the difference of the red intensities. If, however, both the green and the red differences are zero, then the sign of the color difference is set equal to the sign of the blue difference which in this case cannot be zero since the sum is greater than the threshold. 
Certain conditions for the values and signs of the five color differences are specified in such way that if the conditions are fulfilled, then a short vertical stroke is put between the third and the fourth of the six pixels as the label of the edge.
Similar calculations are performed for the vertical columns. In this case a short horizontal stroke is put between the third and the fourth of the six subsequent pixels. The vertical and horizontal strokes (being the one-dimensional cells of an abstract cell complex corresponding to the image) mostly compose a connected sequence representing the edge.
This method is robust and very fast and, what is more important, it can detect edges between adjacent pixels of equal brightness’s if the color difference between these pixels is greater than the threshold.

 

The Canny–Deriche detector was derived from similar mathematical criteria as the Canny edge detector, although starting from a discrete viewpoint and then leading to a set of recursive filters for image smoothing instead of [exponential filters](./Exponential_filter?action=edit&redlink=1) or Gaussian filters.[[14]](./Edge_detection#cite_note-14)

 

The [differential edge detector](./Edge_detection#Differential) described below can be seen as a reformulation of Canny's method from the viewpoint of differential invariants computed from a [scale space representation](./Scale_space_representation) leading to a number of advantages in terms of both theoretical analysis and sub-pixel implementation. In that aspect, [Log Gabor filter](./Log_Gabor_filter) have been shown to be a good choice to extract boundaries in natural scenes.[[15]](./Edge_detection#cite_note-15)

 

### Other first-order methods

 

Different gradient operators can be applied to estimate image gradients from the input image or a smoothed version of it. The simplest approach is to use central differences:

          L  x   ( x , y )    = − −    1 2   L ( x − −  1 , y ) + 0 ⋅ ⋅  L ( x , y ) +   1 2   ⋅ ⋅  L ( x + 1 , y )      L  y   ( x , y )    = − −    1 2   L ( x , y − −  1 ) + 0 ⋅ ⋅  L ( x , y ) +   1 2   ⋅ ⋅  L ( x , y + 1 ) ,       {\displaystyle {\begin{aligned}L_{x}(x,y)&=-{\frac {1}{2}}L(x-1,y)+0\cdot L(x,y)+{\frac {1}{2}}\cdot L(x+1,y)\\[8pt]L_{y}(x,y)&=-{\frac {1}{2}}L(x,y-1)+0\cdot L(x,y)+{\frac {1}{2}}\cdot L(x,y+1),\end{aligned}}}  ![{\displaystyle {\begin{aligned}L_{x}(x,y)&=-{\frac {1}{2}}L(x-1,y)+0\cdot L(x,y)+{\frac {1}{2}}\cdot L(x+1,y)\\[8pt]L_{y}(x,y)&=-{\frac {1}{2}}L(x,y-1)+0\cdot L(x,y)+{\frac {1}{2}}\cdot L(x,y+1),\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ce95f816cf5a777f8b452869882df46357957b07) 

corresponding to the application of the following filter masks to the image data:

      L  y   =   [    + 1  /  2   0   − −  1  /  2    ]   L   and    L  x   =   [    + 1  /  2     0     − −  1  /  2    ]   L .   {\displaystyle L_{y}={\begin{bmatrix}+1/2&0&-1/2\end{bmatrix}}L\quad {\text{and}}\quad L_{x}={\begin{bmatrix}+1/2\\0\\-1/2\end{bmatrix}}L.}  ![{\displaystyle L_{y}={\begin{bmatrix}+1/2&0&-1/2\end{bmatrix}}L\quad {\text{and}}\quad L_{x}={\begin{bmatrix}+1/2\\0\\-1/2\end{bmatrix}}L.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/31dd261fdb32d938fbb615557413aba0116c4f68) 

The well-known and earlier [Sobel operator](./Sobel_operator) is based on the following filters:

      L  y   =   [    + 1   0   − −  1     + 2   0   − −  2     + 1   0   − −  1    ]   L   and    L  x   =   [    + 1   + 2   + 1     0   0   0     − −  1   − −  2   − −  1    ]   L .   {\displaystyle L_{y}={\begin{bmatrix}+1&0&-1\\+2&0&-2\\+1&0&-1\end{bmatrix}}L\quad {\text{and}}\quad L_{x}={\begin{bmatrix}+1&+2&+1\\0&0&0\\-1&-2&-1\end{bmatrix}}L.}  ![{\displaystyle L_{y}={\begin{bmatrix}+1&0&-1\\+2&0&-2\\+1&0&-1\end{bmatrix}}L\quad {\text{and}}\quad L_{x}={\begin{bmatrix}+1&+2&+1\\0&0&0\\-1&-2&-1\end{bmatrix}}L.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2395a5ff6a54838086ad44626be7726504f37c99) 

Given such estimates of first-order [image derivatives](./Image_derivative), the gradient magnitude is then computed as:

      |  ∇ ∇  L  |  =    L  x   2   +  L  y   2       {\displaystyle |\nabla L|={\sqrt {L_{x}^{2}+L_{y}^{2}}}}  ![{\displaystyle |\nabla L|={\sqrt {L_{x}^{2}+L_{y}^{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6005db585533cb3c450a113ae7302c49fa247f6a) 

while the gradient orientation can be estimated as

     θ θ  = atan2 ⁡ ⁡  (  L  y   ,  L  x   ) .   {\displaystyle \theta =\operatorname {atan2} (L_{y},L_{x}).}  ![{\displaystyle \theta =\operatorname {atan2} (L_{y},L_{x}).}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5333772540dd1030c910aef9c366273d71bce7c8) 

Other first-order difference operators for estimating [image gradient](./Image_gradient) have been proposed in the [Prewitt operator](./Prewitt_operator), [Roberts cross](./Roberts_cross), Kayyali[[16]](./Edge_detection#cite_note-16) operator and [Frei–Chen operator](./Frei–Chen_operator?action=edit&redlink=1).

 

It is possible to extend filters dimension to avoid the issue of recognizing edge in low [SNR](./Signal-to-noise_ratio) image. The cost of this operation is loss in terms of resolution. Examples are Extended Prewitt 7×7.

 

### Thresholding and linking

 

Once we have computed a measure of edge strength (typically the gradient magnitude), the next stage is to apply a threshold, to decide whether edges are present or not at an image point. The lower the threshold, the more edges will be detected, and the result will be increasingly susceptible to [noise](./Image_noise) and detecting edges of irrelevant features in the image.  Conversely a high threshold may miss subtle edges, or result in fragmented edges.

 

If the edge is applied to just the gradient magnitude image, the resulting edges will in general be thick and some type of edge thinning post-processing is necessary. For edges detected with non-maximum suppression however, the edge curves are thin by definition and the edge pixels can be linked into edge polygon by an edge linking (edge tracking) procedure. On a discrete grid, the non-maximum suppression stage can be implemented by estimating the gradient direction using first-order derivatives, then rounding off the gradient direction to multiples of 45 degrees, and finally comparing the values of the gradient magnitude in the estimated gradient direction.

 

A commonly used approach to handle the problem of appropriate thresholds for thresholding is by using [thresholding](./Adaptive_thresholding) with [hysteresis](./Hysteresis).  This method uses multiple thresholds to find edges. We begin by using the upper threshold to find the start of an edge. Once we have a start point, we then trace the path of the edge through the image pixel by pixel, marking an edge whenever we are above the lower threshold.  We stop marking our edge only when the value falls below our lower threshold. This approach makes the assumption that edges are likely to be in continuous curves, and allows us to follow a faint section of an edge we have previously seen, without meaning that every noisy pixel in the image is marked down as an edge. Still, however, we have the problem of choosing appropriate thresholding parameters, and suitable thresholding values may vary over the image.

 

### Connectivity of gradients without using (high) magnitude thresholds

 

This method finds connected set of pixels having a [directional derivative](./Directional_derivative) magnitude larger than a fairly small threshold.[[17]](./Edge_detection#cite_note-17) It considers only presence of gradients instead of strength of gradients. After applying a dramatically small threshold (i.e. 5), a binary image is obtained. The morphological opening operation and the morphological closing operation are applied to the binary image to close gaps. Then, the distance transform operation is applied to the binary image to clear the pixels far from the background, so blob-like shapes or other false labeled regions are deleted from the edge map. 

 

### Edge thinning

 

Edge thinning is a technique used to remove the unwanted spurious points on the edges in an image. This technique is employed after the image has been filtered for noise (using median, Gaussian filter etc.), the edge operator has been applied (like the ones described above, Canny or Sobel) to detect the edges and after the edges have been smoothed using an appropriate threshold value.
This removes all the unwanted points, and if applied carefully, results in one pixel thick edge elements.

 

Advantages:

 
1. Sharp and thin edges lead to greater efficiency in [object recognition](./Object_recognition).
2. If [Hough transforms](./Hough_transform) are used to detect lines and ellipses, then thinning could give much better results.
3. If the edge happens to be the boundary of a region, then thinning could easily give the image parameters like perimeter without much algebra.

 

There are many popular algorithms used to do this, one such is described below:

 
1. Choose a type of [connectivity](./Pixel_connectivity#2-dimensional), like 8, 6 or 4.
2. [8 connectivity](./Moore_neighborhood) is preferred, where all the immediate pixels surrounding a particular pixel are considered.
3. Remove points from North, south, east and west.
4. Do this in multiple passes, i.e. after the north pass, use the same semi processed image in the other passes and so on.
5. Remove a point if:
The point has no neighbors in the North (if you are in the north pass, and respective directions for other passes).
The point is not the end of a line.
The point is isolated.
Removing the points will not cause to disconnect its neighbors in any way.
6. Otherwise, keep the point.

 

The number of passes across direction should be chosen according to the level of accuracy desired.

 

### Second-order approaches

 

Some edge-detection operators are instead based upon second-order derivatives of the intensity.  This essentially captures the [rate of change](./Derivative) in the intensity gradient. Thus, in the ideal continuous case, detection of zero-crossings in the second derivative captures local maxima in the gradient.

 

The early [Marr–Hildreth](./Marr–Hildreth_algorithm) operator is based on the detection of zero-crossings of the Laplacian operator applied to a Gaussian-smoothed image. It can be shown, however, that this operator will also return false edges corresponding to local minima of the gradient magnitude. Moreover, this operator will give poor localization at curved edges. Hence, this operator is today mainly of historical interest.

 

#### Differential

 

A more refined second-order edge detection approach which automatically detects edges with sub-pixel accuracy, uses the following *differential approach* of detecting zero-crossings of the second-order directional derivative in the gradient direction:

 

Following the differential geometric way of expressing the requirement of non-maximum suppression proposed by Lindeberg,[[4]](./Edge_detection#cite_note-lin98-4)[[18]](./Edge_detection#cite_note-lin93-18) let us introduce at every image point a local coordinate system     ( u , v )   {\displaystyle (u,v)}  ![{\displaystyle (u,v)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eadf12294edccd7a29c99cfc1765e4a14bf47e58), with the     v   {\displaystyle v}  ![{\displaystyle v}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e07b00e7fc0847fbd16391c778d65bc25c452597)-direction parallel to the gradient direction. Assuming that the image has been pre-smoothed by Gaussian smoothing and a [scale space representation](./Scale_space_representation)     L ( x , y ; t )   {\displaystyle L(x,y;t)}  ![{\displaystyle L(x,y;t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cd93798265e95026b9118bb0ff6b4e26aada38e4) at scale     t   {\displaystyle t}  ![{\displaystyle t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65658b7b223af9e1acc877d848888ecdb4466560) has been computed, we can require that the gradient magnitude of the [scale space representation](./Scale_space_representation), which is equal to the first-order directional derivative in the     v   {\displaystyle v}  ![{\displaystyle v}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e07b00e7fc0847fbd16391c778d65bc25c452597)-direction      L  v     {\displaystyle L_{v}}  ![{\displaystyle L_{v}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d3252ec5dbd18467fc109498966e5abb43123b), should have its first order directional derivative in the     v   {\displaystyle v}  ![{\displaystyle v}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e07b00e7fc0847fbd16391c778d65bc25c452597)-direction equal to zero

      ∂ ∂   v   (  L  v   ) = 0   {\displaystyle \partial _{v}(L_{v})=0}  ![{\displaystyle \partial _{v}(L_{v})=0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d86dabbe79664cd18f59ee98cdb8913dc26fd2b4) 

while the second-order directional derivative in the     v   {\displaystyle v}  ![{\displaystyle v}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e07b00e7fc0847fbd16391c778d65bc25c452597)-direction of      L  v     {\displaystyle L_{v}}  ![{\displaystyle L_{v}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/67d3252ec5dbd18467fc109498966e5abb43123b) should be negative, i.e.,

      ∂ ∂   v v   (  L  v   ) ≤ ≤  0.   {\displaystyle \partial _{vv}(L_{v})\leq 0.}  ![{\displaystyle \partial _{vv}(L_{v})\leq 0.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4b21d86531f5454c7a17fa701109946b33dd4db2) 

Written out as an explicit expression in terms of local partial derivatives      L  x   ,  L  y   , … …  ,  L  y y y     {\displaystyle L_{x},L_{y},\ldots ,L_{yyy}}  ![{\displaystyle L_{x},L_{y},\ldots ,L_{yyy}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7fbe82ff5e62bcf94ce03fc0943c1b9a4b64b075), this edge definition can be expressed as the zero-crossing curves of the differential invariant

      L  v   2    L  v v   =  L  x   2     L  x x   + 2   L  x     L  y     L  x y   +  L  y   2     L  y y   = 0 ,   {\displaystyle L_{v}^{2}L_{vv}=L_{x}^{2}\,L_{xx}+2\,L_{x}\,L_{y}\,L_{xy}+L_{y}^{2}\,L_{yy}=0,}  ![{\displaystyle L_{v}^{2}L_{vv}=L_{x}^{2}\,L_{xx}+2\,L_{x}\,L_{y}\,L_{xy}+L_{y}^{2}\,L_{yy}=0,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fd5edf5a9c08ea58345c08bc3ec3715ad5a835a7) 

that satisfies a sign-condition on the following differential invariant

      L  v   3    L  v v v   =  L  x   3     L  x x x   + 3   L  x   2     L  y     L  x x y   + 3   L  x     L  y   2     L  x y y   +  L  y   3     L  y y y   ≤ ≤  0   {\displaystyle L_{v}^{3}L_{vvv}=L_{x}^{3}\,L_{xxx}+3\,L_{x}^{2}\,L_{y}\,L_{xxy}+3\,L_{x}\,L_{y}^{2}\,L_{xyy}+L_{y}^{3}\,L_{yyy}\leq 0}  ![{\displaystyle L_{v}^{3}L_{vvv}=L_{x}^{3}\,L_{xxx}+3\,L_{x}^{2}\,L_{y}\,L_{xxy}+3\,L_{x}\,L_{y}^{2}\,L_{xyy}+L_{y}^{3}\,L_{yyy}\leq 0}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e5ddaee9d8e0d7138e8613f75c1f14316bcde3a) 

where      L  x   ,  L  y   , … …  ,  L  y y y     {\displaystyle L_{x},L_{y},\ldots ,L_{yyy}}  ![{\displaystyle L_{x},L_{y},\ldots ,L_{yyy}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7fbe82ff5e62bcf94ce03fc0943c1b9a4b64b075) denote partial derivatives computed from a [scale space representation](./Scale_space_representation)     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8) obtained by smoothing the original image with a [Gaussian kernel](./Gaussian_kernel). In this way, the edges will be automatically obtained as continuous curves with sub-pixel accuracy. Hysteresis thresholding can also be applied to these differential and subpixel edge segments.

 

In practice, first-order derivative approximations can be computed by central differences as described above, while second-order derivatives can be computed from the [scale space representation](./Scale_space_representation)     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8) according to:

          L  x x   ( x , y )    = L ( x − −  1 , y ) − −  2 L ( x , y ) + L ( x + 1 , y ) ,      L  x y   ( x , y )    =   1 4   ( L ( x − −  1 , y − −  1 ) − −  L ( x − −  1 , y + 1 ) − −  L ( x + 1 , y − −  1 ) + L ( x + 1 , y + 1 ) ) ,      L  y y   ( x , y )    = L ( x , y − −  1 ) − −  2 L ( x , y ) + L ( x , y + 1 ) .       {\displaystyle {\begin{aligned}L_{xx}(x,y)&=L(x-1,y)-2L(x,y)+L(x+1,y),\\[6pt]L_{xy}(x,y)&={\frac {1}{4}}(L(x-1,y-1)-L(x-1,y+1)-L(x+1,y-1)+L(x+1,y+1)),\\[6pt]L_{yy}(x,y)&=L(x,y-1)-2L(x,y)+L(x,y+1).\end{aligned}}}  ![{\displaystyle {\begin{aligned}L_{xx}(x,y)&=L(x-1,y)-2L(x,y)+L(x+1,y),\\[6pt]L_{xy}(x,y)&={\frac {1}{4}}(L(x-1,y-1)-L(x-1,y+1)-L(x+1,y-1)+L(x+1,y+1)),\\[6pt]L_{yy}(x,y)&=L(x,y-1)-2L(x,y)+L(x,y+1).\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d8978e3e1cfbf57b80b845fba2e89169b08e8e11) 

corresponding to the following filter masks:

      L  x x   =   [    1   − −  2   1    ]   L   and    L  x y   =   [    − −  1  /  4   0   1  /  4     0   0   0     1  /  4   0   − −  1  /  4    ]   L   and    L  y y   =   [    1     − −  2     1    ]   L .   {\displaystyle L_{xx}={\begin{bmatrix}1&-2&1\end{bmatrix}}L\quad {\text{and}}\quad L_{xy}={\begin{bmatrix}-1/4&0&1/4\\0&0&0\\1/4&0&-1/4\end{bmatrix}}L\quad {\text{and}}\quad L_{yy}={\begin{bmatrix}1\\-2\\1\end{bmatrix}}L.}  ![{\displaystyle L_{xx}={\begin{bmatrix}1&-2&1\end{bmatrix}}L\quad {\text{and}}\quad L_{xy}={\begin{bmatrix}-1/4&0&1/4\\0&0&0\\1/4&0&-1/4\end{bmatrix}}L\quad {\text{and}}\quad L_{yy}={\begin{bmatrix}1\\-2\\1\end{bmatrix}}L.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a22552d21fc380f8a2c130439aa6baa4036eb08e) 

Higher-order derivatives for the third-order sign condition can be obtained in an analogous fashion.

 

### Phase congruency-based

 

A recent development in edge detection techniques takes a frequency domain approach to finding edge locations.  [Phase congruency](./Phase_congruency) (also known as phase coherence) methods attempt to find locations in an image where all sinusoids in the frequency domain are in phase.  These locations will generally correspond to the location of a perceived edge, regardless of whether the edge is represented by a large change in intensity in the spatial domain.  A key benefit of this technique is that it responds strongly to [Mach bands](./Mach_bands), and avoids false positives typically found around [roof edges](./Roof_edge?action=edit&redlink=1). A roof edge, is a discontinuity in the first order derivative of a grey-level profile.[[19]](./Edge_detection#cite_note-19)

 

### Phase Stretch Transform (PST)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c0/PST_edge_detector_saint_Paul.tif/lossy-page1-500px-PST_edge_detector_saint_Paul.tif.jpg)](./File:PST_edge_detector_saint_Paul.tif) Feature enhancement in an image ([St Paul's Cathedral](./St_Paul's_Cathedral), London) using Phase Stretch Transform (PST). Left panel shows the original image and the right panel shows the detected features using PST. 

The [phase stretch transform](./Phase_stretch_transform) or PST is a physics-inspired computational approach to signal and image processing. One of its utilities is for feature detection and classification.[[20]](./Edge_detection#cite_note-original-20)[[21]](./Edge_detection#cite_note-21) PST is a spin-off from research on the [time stretch dispersive Fourier transform](./Time_stretch_dispersive_Fourier_transform). PST transforms the image by emulating propagation through a diffractive medium with engineered 3D dispersive property (refractive index). The operation relies on symmetry of the dispersion profile and can be understood in terms of dispersive eigenfunctions or stretch modes.[[22]](./Edge_detection#cite_note-22) PST performs similar functionality as phase contrast microscopy but on digital images. PST is also applicable to digital images as well as temporal, time series, data.

 

### Subpixel

To increase the precision of edge detection, several subpixel techniques had been proposed, including curve-fitting, moment-based,[[23]](./Edge_detection#cite_note-23)[[24]](./Edge_detection#cite_note-Christian-24) reconstructive, and partial area effect methods.[[25]](./Edge_detection#cite_note-25) These methods have different characteristics. Curve fitting methods are computationally simple but are easily affected by noise. Moment-based methods use an integral-based approach to reduce the effect of noise, but may require more computations in some cases. Reconstructive methods use horizontal gradients or vertical gradients to build a curve and find the peak of the curve as the sub-pixel edge. Partial area effect methods are based on the hypothesis that each pixel value depends on the area at both sides of the edge inside that pixel, producing accurate individual estimation for every edge pixel. Certain variants of the moment-based technique have been shown to be the most accurate for isolated edges.[[24]](./Edge_detection#cite_note-Christian-24)

[![](//upload.wikimedia.org/wikipedia/commons/4/45/Subpixel_edge_detection.png)](./File:Subpixel_edge_detection.png)Edge detection on an [angiographic image](./Angiography). On the left, edge detection is made at a pixel level. On the right, subpixel edge detection locates the edge inside the pixel precisely. 

### The Marr-Hildreth Edge Detector

 

[The Marr-Hildreth edge detector](./Marr–Hildreth_algorithm)[[26]](./Edge_detection#cite_note-26) is distinguished by its use of the Laplacian of Gaussian (LoG) operator for edge detection in digital images. Unlike other edge detection methods, the LoG approach combines Gaussian smoothing with second derivative operations, allowing for simultaneous noise reduction and edge enhancement. The key advantage of this method lies in its ability to detect edges at various scales by adjusting the standard deviation of the Gaussian kernel, enabling detection of fine details as well as broader transitions. Moreover, the technique leverages zero-crossing detection on the LoG response to precisely locate edges, offering robustness against noise and maintaining edge continuity. This approach is particularly effective for detecting edges with clear boundaries in images while minimizing false positives due to noise, making it a valuable tool in computer vision applications where accurate edge localization is crucial.

 

## Code for edge detection using Prewitt, Scharr and Sobel operator

 

Source:[[27]](./Edge_detection#cite_note-27)

 

### Edge detection using Prewitt operator

 
```
% MATLAB code for prewitt
% operator edge detection
k = imread("logo.png");
k = rgb2gray(k);
k1 = double(k);
p_msk = [-1 0 1; -1 0 1; -1 0 1];
kx = conv2(k1, p_msk, 'same');
ky = conv2(k1, p_msk', 'same');
ked = sqrt(kx.^2 + ky.^2);

% display the images.
imtool(k,[]);

% display the edge detection along x-axis.
imtool(abs(kx), []);

% display the edge detection along y-axis.
imtool(abs(ky),[]);

% display the full edge detection.
imtool(abs(ked),[]);

```
 

### Edge detection using Scharr operator

 
```
% Scharr operator -> edge detection
k = imread("logo.png");
k = rgb2gray(k);
k1 = double(k);
s_msk = [-3 0 3; -10 0 10; -3 0 3];
kx = conv2(k1, s_msk, 'same');
ky = conv2(k1, s_msk', 'same');
ked = sqrt(kx.^2 + ky.^2);
% display the images.
imtool(k,[]);
% display the edge detection along x-axis.
imtool(abs(kx), []);
% display the edge detection along y-axis.
imtool(abs(ky), []);
% display the full edge detection.
imtool(abs(ked), []);

```
 

### Edge detection using Sobel operator

 
```
% MATLAB code for Sobel operator
% edge detection
k = imread("logo.png");
k = rgb2gray(k);
k1 = double(k);
s_msk = [-1 0 1; -2 0 2; -1 0 1];
kx = conv2(k1, s_msk, 'same');
ky = conv2(k1, s_msk', 'same');
ked = sqrt(kx.^2 + ky.^2);

% display the images.
imtool(k,[]);

% display the edge detection along x-axis.
imtool(abs(kx), []);

% display the edge detection along y-axis.
imtool(abs(ky), []);

% display the full edge detection.
imtool(abs(ked), []);

```
 

## See also

 
- [Convolution § Applications](./Convolution#Applications)
- [Edge-preserving filtering](./Edge-preserving_filtering)
- [Feature detection (computer vision)](./Feature_detection_(computer_vision)) for other low-level feature detectors
- [Image derivative](./Image_derivative)
- [Gabor filter](./Gabor_filter)
- [Image noise reduction](./Image_noise_reduction)
- [Kirsch operator](./Kirsch_operator) for edge detection in the compass directions
- [Ridge detection](./Ridge_detection) for relations between edge detectors and ridge detectors
- [Log Gabor filter](./Log_Gabor_filter)
- [Phase stretch transform](./Phase_stretch_transform)

 

## References

 
1. [↑](./Edge_detection#cite_ref-1) Umbaugh, Scott E (2010). *Digital image processing and analysis : human and computer vision applications with CVIPtools* (2nd ed.). Boca Raton, FL: CRC Press. [ISBN](./ISBN_(identifier)) [978-1-4398-0205-2](./Special:BookSources/978-1-4398-0205-2).
2. [↑](./Edge_detection#cite_ref-2) H.G. Barrow and J.M. Tenenbaum (1981) "Interpreting line drawings as three-dimensional surfaces", Artificial Intelligence, vol 17, issues 1–3, pages 75–116.
3. [1](./Edge_detection#cite_ref-lin95_3-0) [2](./Edge_detection#cite_ref-lin95_3-1) Lindeberg, Tony (2001) [1994], ["Edge detection"](https://www.encyclopediaofmath.org/index.php?title=Edge_detection&oldid=17883), *[Encyclopedia of Mathematics](./Encyclopedia_of_Mathematics)*, [EMS Press](./European_Mathematical_Society)
4. [1](./Edge_detection#cite_ref-lin98_4-0) [2](./Edge_detection#cite_ref-lin98_4-1) [3](./Edge_detection#cite_ref-lin98_4-2) [4](./Edge_detection#cite_ref-lin98_4-3) [T. Lindeberg (1998) "Edge detection and ridge detection with automatic scale selection", International Journal of Computer Vision, 30, 2, pages 117–154.](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A452310&dswid=386)
5. [↑](./Edge_detection#cite_ref-5) W. Zhang and F. Bergholm (1997) "[Multi-scale blur estimation and edge type classification for scene analysis](https://link.springer.com/article/10.1023/A:1007923307644)", International Journal of Computer Vision, vol 24, issue 3, Pages: 219–250.
6. [↑](./Edge_detection#cite_ref-6) D. Ziou and S. Tabbone (1998) "[Edge detection techniques: An overview](https://web.archive.org/web/20191008173716/https://pdfs.semanticscholar.org/587a/acc01a4c33f0fe7fb172f5db785f40522b57.pdf)", International Journal of Pattern Recognition and Image Analysis, 8(4):537–559, 1998
7. [↑](./Edge_detection#cite_ref-7) [J. M. Park and Y. Lu (2008) "Edge detection in grayscale, color, and range images", in B. W. Wah (editor)  Encyclopedia of Computer Science and Engineering, doi 10.1002/9780470050118.ecse603](http://mrw.interscience.wiley.com/emrw/9780470050118/ecse/article/ecse603/current/abstract)
8. [↑](./Edge_detection#cite_ref-8) J. Canny (1986) "[A computational approach to edge detection](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.420.3300&rep=rep1&type=pdf)", IEEE Transactions on Pattern Analysis and Machine Intelligence, vol 8, pages 679–714.
9. [↑](./Edge_detection#cite_ref-9) 
R. Haralick, (1984) "[Digital step edges from zero crossing of second directional derivatives](http://haralick-org.torahcode.us/journals/04767475.pdf)", IEEE Transactions on Pattern Analysis and Machine Intelligence, 6(1):58–68.

10. [↑](./Edge_detection#cite_ref-10) ["R. Kimmel and A.M. Bruckstein (2003) "On regularized Laplacian zero crossings and other optimal edge integrators", *International Journal of Computer Vision*, 53(3) pages 225–243"](https://web.archive.org/web/20210308012954/https://www.cs.technion.ac.il/~ron/PAPERS/laplacian_ijcv2003.pdf) (PDF). Archived from [the original](https://www.cs.technion.ac.il/~ron/PAPERS/laplacian_ijcv2003.pdf) (PDF) on 2021-03-08. Retrieved 2019-09-15.
11. [↑](./Edge_detection#cite_ref-11) [Shapiro L. G.](./Linda_Shapiro) & Stockman G. C. (2001) Computer Vision. London etc.: Prentice Hall, Page 326.
12. [↑](./Edge_detection#cite_ref-12) Kovalevsky, V., Image Processing with Cellular Topology, Springer 2021, ISBN 978-981-16-5771-9, pp. 113-138
13. [↑](./Edge_detection#cite_ref-13)  Lee, J.-S., Digital image smoothing and the sigma filter. Computer Vision, Graphics, and Information Processing. 1983, 24(2): 255-69 
14. [↑](./Edge_detection#cite_ref-14) R. Deriche (1987) *Using Canny's criteria to derive an optimal edge detector recursively implemented*, Int. J. Computer Vision, vol 1, pages 167–187.
15. [↑](./Edge_detection#cite_ref-15) Sylvain Fischer, Rafael Redondo, Laurent Perrinet, Gabriel Cristobal. [Sparse approximation of images inspired from the functional architecture of the primary visual areas](https://link.springer.com/content/pdf/10.1155/2007/90727.pdf). EURASIP Journal on Advances in Signal Processing, special issue on Image Perception, 2007
16. [↑](./Edge_detection#cite_ref-16) Dim, Jules R.; Takamura, Tamio (2013-12-11). ["Alternative Approach for Satellite Cloud Classification: Edge Gradient Application"](https://doi.org/10.1155%2F2013%2F584816). *Advances in Meteorology*. **2013** (1): 1–8. [Bibcode](./Bibcode_(identifier)):[2013AdMet201384816D](https://ui.adsabs.harvard.edu/abs/2013AdMet201384816D). [doi](./Doi_(identifier)):[10.1155/2013/584816](https://doi.org/10.1155%2F2013%2F584816). [ISSN](./ISSN_(identifier)) [1687-9309](https://search.worldcat.org/issn/1687-9309).
17. [↑](./Edge_detection#cite_ref-17) Pak, Mesut; Bayazit, Ulug (2020-07-01). ["Regional bit allocation with visual attention and distortion sensitivity"](https://link.springer.com/article/10.1007/s11042-020-08686-z). *Multimedia Tools and Applications*. **79** (27): 19239–19263. [doi](./Doi_(identifier)):[10.1007/s11042-020-08686-z](https://doi.org/10.1007%2Fs11042-020-08686-z). [ISSN](./ISSN_(identifier)) [1573-7721](https://search.worldcat.org/issn/1573-7721).
18. [↑](./Edge_detection#cite_ref-lin93_18-0) [T. Lindeberg (1993) "Discrete derivative approximations with scale-space properties: A basis for low-level feature extraction", J. of Mathematical Imaging and Vision, 3(4), pages 349–376.](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A473368&dswid=5061)
19. [↑](./Edge_detection#cite_ref-19) T. Pajdla and V. Hlavac (1993) "[Surface discontinuities in range images](https://link.springer.com/chapter/10.1007/3-540-57233-3_54)," in Proc IEEE 4th Int. Conf. Comput. Vision, pp. 524–528.
20. [↑](./Edge_detection#cite_ref-original_20-0) M. H. Asghari, and B. Jalali, ["Edge detection in digital images using dispersive phase stretch,"](https://downloads.hindawi.com/journals/ijbi/2015/687819.pdf) International Journal of Biomedical Imaging, Vol. 2015, Article ID 687819, pp. 1–6 (2015).
21. [↑](./Edge_detection#cite_ref-21) M. H. Asghari, and B. Jalali, "[Physics-inspired image edge detection](https://ieeexplore.ieee.org/abstract/document/7032125/)," IEEE Global Signal and Information Processing Symposium (GlobalSIP 2014), paper: WdBD-L.1, Atlanta, December 2014.
22. [↑](./Edge_detection#cite_ref-22) B. Jalali and A. Mahjoubfar, "[Tailoring Wideband Signals With a Photonic Hardware Accelerator](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7118650)," Proceedings of the IEEE, Vol. 103, No. 7, pp. 1071–1086 (2015).

23. [↑](./Edge_detection#cite_ref-23) Ghosal, S.; Mehrota, R (1993-01-01). "Orthogonal Moment Operators for Subpixel Edge Detection". *Pattern Recognition*. **26** (2): 295–306. [Bibcode](./Bibcode_(identifier)):[1993PatRe..26..295G](https://ui.adsabs.harvard.edu/abs/1993PatRe..26..295G). [doi](./Doi_(identifier)):[10.1016/0031-3203(93)90038-X](https://doi.org/10.1016%2F0031-3203%2893%2990038-X).
24. [1](./Edge_detection#cite_ref-Christian_24-0) [2](./Edge_detection#cite_ref-Christian_24-1) Christian, John (2017-01-01). "Accurate Planetary Limb Localization for Image-Based Spacecraft Navigation". *Journal of Spacecraft and Rockets*. **54** (3): 708–730. [Bibcode](./Bibcode_(identifier)):[2017JSpRo..54..708C](https://ui.adsabs.harvard.edu/abs/2017JSpRo..54..708C). [doi](./Doi_(identifier)):[10.2514/1.A33692](https://doi.org/10.2514%2F1.A33692).
25. [↑](./Edge_detection#cite_ref-25) Trujillo-Pino, Agustín; Krissian, Karl; Alemán-Flores, Miguel; Santana-Cedrés, Daniel (2013-01-01). "Accurate subpixel edge location based on partial area effect". *Image and Vision Computing*. **31** (1): 72–90. [doi](./Doi_(identifier)):[10.1016/j.imavis.2012.10.005](https://doi.org/10.1016%2Fj.imavis.2012.10.005). [hdl](./Hdl_(identifier)):[10553/43474](https://hdl.handle.net/10553%2F43474).
26. [↑](./Edge_detection#cite_ref-26) Gonzalez, Rafael (2018). *Digital Image Processing* (4th ed.). Pearson Education. [ISBN](./ISBN_(identifier)) [978-0-13-335672-4](./Special:BookSources/978-0-13-335672-4).
27. [↑](./Edge_detection#cite_ref-27) ["Edge detection using Prewitt, Scharr and Sobel Operator"](https://www.geeksforgeeks.org/edge-detection-using-prewitt-scharr-and-sobel-operator/). *GeeksforGeeks*. 2021-10-11. Retrieved 2024-05-08.

 

## Further reading

 
- Lindeberg, Tony (2001) [1994], ["Edge detection"](https://www.encyclopediaofmath.org/index.php?title=Edge_detection&oldid=17883), *[Encyclopedia of Mathematics](./Encyclopedia_of_Mathematics)*, [EMS Press](./European_Mathematical_Society)
- [Entry on edge detection in Encyclopedia of Computer Science and Engineering](https://onlinelibrary.wiley.com/doi/10.1002/9780470050118.ecse603)
- [Edge Detection using FPGA](http://edge.kitiyo.com/)
- [A-contrario line segment detection with code and on-line demonstration](//doi.org/10.5201/ipol.2012.gjmr-lsd)
- [Edge detection using MATLAB](https://www.mathworks.com/discovery/edge-detection.html)
- [Subpixel edge detection using Matlab](http://www.mathworks.com/matlabcentral/fileexchange/48908-accurate-subpixel-edge-location) [Archived](https://web.archive.org/web/20211216123504/http://www.mathworks.com/matlabcentral/fileexchange/48908-accurate-subpixel-edge-location) 2021-12-16 at the [Wayback Machine](./Wayback_Machine)
- [Image Tools Effects - Edgedetect](https://photokit.com/tools/effects/edgedetect/)
- [Edge Detection for Image Processing](https://sdk.docutain.com/blogartikel/edge-detection-for-image-processing)