---
source: https://en.wikipedia.org/wiki/Canny_edge_detector
fetched: 2026-06-21
---

Image edge detection algorithm
|  | This articleneeds additional citations forverification.Please helpimprove this articlebyadding citations to reliable sources. Unsourced material may be challenged and removed.Find sources:"Canny edge detector"–news·newspapers·books·scholar·JSTOR(February 2026)(Learn how and when to remove this message) |
| --- | --- |

[![](//upload.wikimedia.org/wikipedia/commons/thumb/9/93/Valve_monochrome_canny_%286%29.PNG/250px-Valve_monochrome_canny_%286%29.PNG)](./File:Valve_monochrome_canny_(6).PNG)The Canny edge detector applied to a color photograph of a steam engine[![](//upload.wikimedia.org/wikipedia/commons/thumb/f/f0/Valve_original_%281%29.PNG/250px-Valve_original_%281%29.PNG)](./File:Valve_original_(1).PNG)The original image 
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

 

The **Canny edge detector** is an [edge detection](./Edge_detection) operator that uses a multi-stage [algorithm](./Algorithm) to detect a wide range of edges in images. It was developed by [John F. Canny](./John_F._Canny) in 1986. Canny also produced a *computational theory of edge detection* explaining why the technique works.

 

## Development

 

Canny edge detection is a technique to extract useful structural information from different vision objects and dramatically reduce the amount of data to be processed. It has been widely applied in various [computer vision](./Computer_vision) systems. Canny has found that the requirements for the application of [edge detection](./Edge_detection) on diverse vision systems are relatively similar. Thus, an edge detection solution to address these requirements can be implemented in a wide range of situations. 
The general criteria for edge detection include:

 
1. Detection of edge with low error rate, which means that the detection should accurately catch as many edges shown in the image as possible
2. The edge point detected from the operator should accurately localize on the center of the edge.
3. A given edge in the image should only be marked once, and where possible, [image noise](./Image_noise) should not create false edges.

 

To satisfy these requirements Canny used the [calculus of variations](./Calculus_of_variations) – a technique which finds the [function](./Function_(mathematics)) which optimizes a given [functional](./Functional_(mathematics)). The optimal function in Canny's detector is described by the sum of four [exponential](./Exponential_function) terms, but it can be approximated by the first [derivative](./Derivative) of a [Gaussian](./Gaussian_function).

 

Among the edge detection methods developed so far, Canny's algorithm is one of the most strictly defined methods that provides reliable detection. Owing to its optimality to meet with the three criteria for edge detection and the simplicity of the process for its implementation, it has become one of the most popular algorithms for edge detection.

 

## Process

 

The process of Canny edge detection algorithm can be broken down to five different steps:

 
1. Apply [Gaussian filter](./Gaussian_filter) to smooth the image in order to remove the noise
2. Find the intensity [gradients](./Gradient) of the image
3. Apply gradient magnitude thresholding or lower bound cut-off suppression to get rid of spurious response to edge detection
4. Apply double threshold to determine potential edges
5. Track edge by [hysteresis](./Hysteresis): Finalize the detection of edges by suppressing all the other edges that are weak and not connected to strong edges.

 

### Gaussian Filter

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/2e/Valve_gaussian_%282%29.PNG/250px-Valve_gaussian_%282%29.PNG)](./File:Valve_gaussian_(2).PNG)The image after a 5×5 Gaussian mask has been passed across each pixel 

Since all edge detection results are easily affected by the noise in the image, it is essential to filter out the noise to prevent false detection caused by it. To smooth the image, a Gaussian filter kernel is convolved with the image. This step will slightly smooth the image to reduce the effects of obvious noise on the edge detector. The equation for a Gaussian filter kernel of size (2*k*+1)×(2*k*+1) is given by:

 

     H  i j   =   1  2 π π   σ σ   2      exp ⁡ ⁡   (  − −     ( i − −  ( k + 1 )  )  2   + ( j − −  ( k + 1 )  )  2     2  σ σ   2       )  ; 1 ≤ ≤  i , j ≤ ≤  ( 2 k + 1 )   {\displaystyle H_{ij}={\frac {1}{2\pi \sigma ^{2}}}\exp \left(-{\frac {(i-(k+1))^{2}+(j-(k+1))^{2}}{2\sigma ^{2}}}\right);1\leq i,j\leq (2k+1)}  ![{\displaystyle H_{ij}={\frac {1}{2\pi \sigma ^{2}}}\exp \left(-{\frac {(i-(k+1))^{2}+(j-(k+1))^{2}}{2\sigma ^{2}}}\right);1\leq i,j\leq (2k+1)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4a36d7f727beeaff58352d671bb41a3aca9f44d6)

 

Here is an example of a 5×5 Gaussian filter, used to create the adjacent image, with     σ σ    {\displaystyle \sigma }  ![{\displaystyle \sigma }](https://wikimedia.org/api/rest_v1/media/math/render/svg/59f59b7c3e6fdb1d0365a494b81fb9a696138c36) = 2.  (The asterisk denotes a [convolution](./Convolution) operation.)

      B  =   1 159     [    2   4   5   4   2     4   9   12   9   4     5   12   15   12   5     4   9   12   9   4     2   4   5   4   2    ]   ∗ ∗   A  .   {\displaystyle \mathbf {B} ={\frac {1}{159}}{\begin{bmatrix}2&4&5&4&2\\4&9&12&9&4\\5&12&15&12&5\\4&9&12&9&4\\2&4&5&4&2\end{bmatrix}}*\mathbf {A} .}  ![{\displaystyle \mathbf {B} ={\frac {1}{159}}{\begin{bmatrix}2&4&5&4&2\\4&9&12&9&4\\5&12&15&12&5\\4&9&12&9&4\\2&4&5&4&2\end{bmatrix}}*\mathbf {A} .}](https://wikimedia.org/api/rest_v1/media/math/render/svg/efce20969e243d1ba3f34c2f7126041095bd4656) 

It is important to understand that the selection of the size of the Gaussian kernel will affect the performance of the detector. The larger the size is, the lower the detector's sensitivity to noise. Additionally, the localization error to detect the edge will slightly increase with the increase of the Gaussian filter kernel size. A 5×5 is a good size for most cases, but this will also vary depending on specific situations.

 

### Finding the intensity gradient of the image

 

An edge in an image may point in a variety of directions, so the Canny algorithm uses four filters to detect horizontal, vertical and diagonal edges in the blurred image.  The [edge detection operator](./Edge_detection) (such as [Roberts](./Roberts_Cross), [Prewitt](./Prewitt_operator), or [Sobel](./Sobel_operator)) returns a value for the first derivative in the horizontal direction (G*x*) and the vertical direction (G*y*). From this the edge gradient and direction can be determined:

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Semicirc.jpg/250px-Semicirc.jpg)](./File:Semicirc.jpg)Gradient direction      G  =       G   x     2   +     G   y     2       {\displaystyle \mathbf {G} ={\sqrt {{\mathbf {G} _{x}}^{2}+{\mathbf {G} _{y}}^{2}}}}  ![{\displaystyle \mathbf {G} ={\sqrt {{\mathbf {G} _{x}}^{2}+{\mathbf {G} _{y}}^{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/23ae6772c5f58751fc6014b71d6adafb30a31c79)      Θ Θ   = atan2 ⁡ ⁡   (    G   y   ,   G   x    )    {\displaystyle \mathbf {\Theta } =\operatorname {atan2} \left(\mathbf {G} _{y},\mathbf {G} _{x}\right)}  ![{\displaystyle \mathbf {\Theta } =\operatorname {atan2} \left(\mathbf {G} _{y},\mathbf {G} _{x}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b3e4efe0d943867ba795d1a960f36d71c1812880), 

where G can be computed using the [hypot](./Hypot) function and [atan2](./Atan2) is the arctangent function with two arguments.
The edge direction angle is rounded to one of four angles representing vertical, horizontal, and the two diagonals (0°, 45°, 90°, and 135°). An edge direction falling in each color region will be set to a specific angle value, for instance, θ in [0°, 22.5°] or [157.5°, 180°] maps to 0°.

 

### Gradient magnitude thresholding or lower bound cut-off suppression

 

Minimum cut-off suppression of gradient magnitudes, or lower bound thresholding, is an [edge thinning](./Edge_detection#Edge_thinning) technique.

 

Lower bound cut-off suppression is applied to find the locations with the sharpest change of intensity value. The algorithm for each pixel in the gradient image is:

 
1. Compare the edge strength of the current pixel with the edge strength of the pixel in the positive and negative gradient directions.
2. If the edge strength of the current pixel is the largest compared to the other pixels in the mask with the same direction (e.g., a pixel that is pointing in the y-direction will be compared to the pixel above and below it in the vertical axis), the value will be preserved. Otherwise, the value will be suppressed.

 

In some implementations, the algorithm categorizes the continuous gradient directions into a small set of discrete directions, and then moves a 3x3 filter over the output of the previous step (that is, the edge strength and gradient directions). At every pixel, it suppresses the edge strength of the center pixel (by setting its value to 0) if its magnitude is not greater than the magnitude of the two neighbors in the gradient direction. For example,

 
- if the rounded gradient angle is 0° (i.e. the edge is in the north–south direction) the point will be considered to be on the edge if its gradient magnitude is greater than the magnitudes at pixels in the **east and west** directions,
- if the rounded gradient angle is 90° (i.e. the edge is in the east–west direction) the point will be considered to be on the edge if its gradient magnitude is greater than the magnitudes at pixels  in the **north and south** directions,
- if the rounded gradient angle is 135° (i.e. the edge is in the northeast–southwest direction) the point will be considered to be on the edge if its gradient magnitude is greater than the magnitudes at pixels  in the **north-west and south-east** directions,
- if the rounded gradient angle is 45° (i.e. the edge is in the northwest–southeast direction) the point will be considered to be on the edge if its gradient magnitude is greater than the magnitudes at pixels in the **north-east and south-west** directions.

 

In more accurate implementations, [linear interpolation](./Linear_interpolation) is used between the two neighbouring pixels that straddle the gradient direction. For example, if the gradient angle is between 89° and 180°, interpolation between gradients at the **north** and **north-east** pixels will give one interpolated value, and interpolation between the **south** and **south-west** pixels will give the other (using the conventions of the last paragraph). The gradient magnitude at the central pixel must be greater than both of these for it to be marked as an edge.

 

Note that the sign of the direction is irrelevant, i.e. north–south is the same as south–north and so on.

 

### Double threshold

 

After application of non-maximum suppression, the remaining edge pixels provide a more accurate representation of real edges in an image. However, some edge pixels remain that are caused by noise and color variation. To account for these spurious responses, it is essential to filter out edge pixels with a weak gradient value and preserve edge pixels with a high gradient value.  This is accomplished by selecting high and low threshold values.  If an edge pixel’s gradient value is higher than the high threshold value, it is marked as a strong edge pixel. If an edge pixel’s gradient value is smaller than the high threshold value and larger than the low threshold value, it is marked as a weak edge pixel. If an edge pixel's gradient value is smaller than the low threshold value, it will be suppressed. The two threshold values are empirically determined and their definition will depend on the content of a given input image.

 

### Edge tracking by hysteresis

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/20/%C3%84%C3%A4retuvastuse_n%C3%A4ide.png/500px-%C3%84%C3%A4retuvastuse_n%C3%A4ide.png)](./File:Ääretuvastuse_näide.png)Canny edge detection applied to a photograph 

The strong edge pixels should certainly be involved in the final edge image; they are deemed to come from true edges in the image. However, there will be some debate on the weak edge pixels. We want to determine whether these pixels come from a true edge, or noise/color variations. Weak edge pixels should be dropped from consideration if it is the latter. This algorithm uses the idea that weak edge pixels from true edges will (usually) be connected to a strong edge pixel while noise responses are unconnected. 
To track the edge connection, [blob analysis](./Connected-component_labeling) is applied by looking at a weak edge pixel and its 8-connected neighborhood pixels. As long as there is one strong edge pixel that is involved in the blob, that weak edge point can be identified as one that should be preserved. These weak edge pixels become strong edges that can then cause their neighboring weak edge pixels to be preserved.

 

## Walkthrough of the algorithm

 

This section will show the progression of an image through each of the five steps.

 [![A lizard](//upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Large_Scaled_Forest_Lizard.jpg/250px-Large_Scaled_Forest_Lizard.jpg)](./File:Large_Scaled_Forest_Lizard.jpg)The original image[![A grayscale, blurred lizard](//upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Canny_Walkthrough_1_Gaussian_Blur.png/250px-Canny_Walkthrough_1_Gaussian_Blur.png)](./File:Canny_Walkthrough_1_Gaussian_Blur.png)Image has been reduced to grayscale, and a 5x5 Gaussian filter with σ=1.4 has been applied.[![Outlines of a lizard](//upload.wikimedia.org/wikipedia/commons/thumb/e/e5/Canny_Walkthrough_2_Intensity_Gradient.png/250px-Canny_Walkthrough_2_Intensity_Gradient.png)](./File:Canny_Walkthrough_2_Intensity_Gradient.png)The intensity gradient of the previous image. The edges of the image have been handled by replicating.[![Outlines of a lizard](//upload.wikimedia.org/wikipedia/commons/thumb/e/e7/Canny_Walkthrough_3_Non-maximum_suppression.png/250px-Canny_Walkthrough_3_Non-maximum_suppression.png)](./File:Canny_Walkthrough_3_Non-maximum_suppression.png)Non-maximum suppression applied to the previous image[![Outlines of a lizard](//upload.wikimedia.org/wikipedia/commons/thumb/3/38/Canny_Walkthrough_4_Double_Threshold.png/250px-Canny_Walkthrough_4_Double_Threshold.png)](./File:Canny_Walkthrough_4_Double_Threshold.png)Double thresholding applied to the previous image. Weak pixels are those with a gradient value between 0.1 and 0.3. Strong pixels have a gradient value greater than 0.3.[![Outlines of a lizard](//upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Canny_Walkthrough_5_Hysteresis_2026.png/250px-Canny_Walkthrough_5_Hysteresis_2026.png)](./File:Canny_Walkthrough_5_Hysteresis_2026.png)Hysteresis applied to the previous image 

## Improvements

 

While traditional Canny edge detection provides a relatively simple but precise methodology for the edge detection problem, with more demanding requirements on the accuracy and robustness on the detection, the traditional algorithm can no longer handle the challenging edge detection task. The main defects[[1]](./Canny_edge_detector#cite_note-1) of the traditional algorithm can be summarized as follows:

 
1. A Gaussian filter is applied to smooth out the noise, but it will also smooth the edge, which is considered as the high frequency feature. This will increase the possibility of missing weak edges, and the appearance of isolated edges in the result.
2. For the gradient amplitude calculation, the old Canny edge detection algorithm uses the center in a small 2×2 neighborhood window to calculate the [finite difference](./Finite_difference) mean value to represent the gradient amplitude. This method is sensitive to noise and can easily detect false edges and lose real edges.
3. In the traditional Canny edge detection algorithm, there will be two fixed global threshold values to filter out the false edges. However, as the image gets complex, different local areas will need very different threshold values to accurately find the real edges. In addition, the global threshold values are determined manually through experiments in the traditional method, which leads to a complexity of calculation when a large number of different images need to be dealt with.
4. The result of the traditional detection cannot reach a satisfactory high accuracy of a single response for each edge - multi-point responses will appear.

 

In order to address these defects, an improvement to the canny edge algorithm is presented in the following paragraphs.

 

### Replace Gaussian filter

 

As both edge and noise will be identified as a high frequency signal, a simple Gaussian filter will add a smooth effect on both of them. However, in order to reach high accuracy of detection of the real edge, it is expected that a more smooth effect should be applied to noise and a less smooth effect should be added to the edge. Bing Wang and Shaosheng Fan from Changsha University of Science and Technology developed an [adaptive filter](./Adaptive_filter), where the filter will evaluate discontinuity between greyscale values of each pixel.[*[citation needed](./Wikipedia:Citation_needed)*] The higher the discontinuity, the lower the weight value is set for the smooth filter at that point. Contrarily, the lower the discontinuity between the greyscale values, the higher the weight value is set to the filter. The process to implement this adaptive filter can be summarized in five steps:

 1. K = 1, set the iteration n and the coefficient of the amplitude of the edge h. 2. Calculate the gradient value      G  x   ( x , y )   {\displaystyle G_{x}(x,y)}  ![{\displaystyle G_{x}(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/297b177cac5b858cfcf035eae382745652fc2c29) and      G  y   ( x , y )   {\displaystyle G_{y}(x,y)}  ![{\displaystyle G_{y}(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9f90a18b8200bd14a1e96097f2f66d9077b2baa6) 3. Calculate the weight according to the formulae below: 

    d ( x , y ) =    G  x   ( x , y  )  2   +  G  y   ( x , y  )  2       {\displaystyle d(x,y)={\sqrt {G_{x}(x,y)^{2}+G_{y}(x,y)^{2}}}}  ![{\displaystyle d(x,y)={\sqrt {G_{x}(x,y)^{2}+G_{y}(x,y)^{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5cd713fe1a9e6658f3fb02d08d4f7bdda13b9757)

 

    w ( x , y ) = exp ⁡ ⁡   (  − −     d ( x , y )   2  h  2       )    {\displaystyle w(x,y)=\exp \left(-{\frac {\sqrt {d(x,y)}}{2h^{2}}}\right)}  ![{\displaystyle w(x,y)=\exp \left(-{\frac {\sqrt {d(x,y)}}{2h^{2}}}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/366f0f11eb497fdadd69156b2a700a0ded45e8c4)

 4. The definition of the adaptive filter is: 

    f ( x , y ) =   1 N    ∑ ∑   i = − −  1   1    ∑ ∑   j = − −  1   1   f ( x + i , y + j ) w ( x + i , y + j )   {\displaystyle f(x,y)={\frac {1}{N}}\sum \limits _{i=-1}^{1}\sum \limits _{j=-1}^{1}f(x+i,y+j)w(x+i,y+j)}  ![{\displaystyle f(x,y)={\frac {1}{N}}\sum \limits _{i=-1}^{1}\sum \limits _{j=-1}^{1}f(x+i,y+j)w(x+i,y+j)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65db8b1414fc1ccfbb306bf900b248b249ea03f7)

 

to smooth the image, where

 

    N =  ∑ ∑   i = − −  1   1    ∑ ∑   j = − −  1   1   w ( x + i , y + j )   {\displaystyle N=\sum \limits _{i=-1}^{1}\sum \limits _{j=-1}^{1}w(x+i,y+j)}  ![{\displaystyle N=\sum \limits _{i=-1}^{1}\sum \limits _{j=-1}^{1}w(x+i,y+j)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5a14ded0e0d4f2438729b3927181ae91f39eef40)

 5. When K = n, stop the iteration, otherwise, k = k+1, keep doing the second step 

### Improvement on gradient magnitude and direction calculation

 

The gradient magnitude and direction can be calculated with a variety of different edge detection operators, and the choice of operator can influence the quality of results. A very commonly chosen one is the 3x3 [Sobel](./Sobel_operator) filter. However, other filters may be better, such as a 5x5 Sobel filter, which will reduce noise, or the [Scharr](./Sobel_operator#Alternative_operators) filter, which has better [rotational symmetry](./Rotational_symmetry). Other common choices are [Prewitt](./Prewitt_operator) (used by Zhou[[2]](./Canny_edge_detector#cite_note-2)) and [Roberts Cross](./Roberts_Cross).

 

### Robust method to determine the dual-threshold value

 

In order to resolve the challenges where it is hard to determine the dual-threshold value empirically, [Otsu's method](./Otsu's_method)[[3]](./Canny_edge_detector#cite_note-3) can be used on the non-maximum suppressed gradient magnitude image to generate the high threshold. The low threshold is typically set to 1/2 of the high threshold in this case. Since the gradient magnitude image is continuous-valued without a well-defined maximum, Otsu's method has to be adapted to use value/count pairs instead of a complete [histogram](./Histogram).

 

### The thinning of the edge

 

While the traditional Canny edge detection implements a good detection result to meet the first two criteria, it does not meet the single response per edge strictly. A [mathematical morphology](./Mathematical_morphology) technique to thin the detected edge is developed by Mallat S and Zhong.[[4]](./Canny_edge_detector#cite_note-4)

 

### Use of curvelets

 

[Curvelets](./Curvelet) have been used in place of the Gaussian filter and gradient estimation to compute a [vector field](./Vector_field) whose directions and magnitudes approximate the direction and strength of edges in the image, to which steps 3 - 5 of the Canny algorithm are then applied. Curvelets decompose signals into separate components of different scales, and dropping the components of finer scales can reduce noise.[[5]](./Canny_edge_detector#cite_note-5)

 

## Differential geometric formulation

 

A more refined approach to obtain edges with sub-pixel accuracy is [differential edge detection](./Edge_detection#Differential), where the requirement of non-maximum suppression is formulated in terms of second- and third-order derivatives computed from a [scale space](./Scale_space) representation (Lindeberg 1998) – see the article on [edge detection](./Edge_detection#Differential) for a detailed description.

 

## Variational formulation of the Haralick–Canny edge detector

 

A variational explanation for the main ingredient of the Canny edge detector, that is, 
finding the zero crossings of the 2nd derivative along the gradient direction, was shown 
to be the result of minimizing a Kronrod–Minkowski functional while maximizing the integral 
over the alignment of the edge  with the gradient field (Kimmel and Bruckstein 2003). See the article on
regularized Laplacian zero crossings and other optimal edge integrators for a detailed description.

 

## Parameters

 

The Canny algorithm contains a number of adjustable parameters, which can affect the computation time and effectiveness of the algorithm.

 
- The size of the Gaussian filter: the smoothing filter used in the first stage directly affects the results of the Canny algorithm.  Smaller filters cause less blurring, and allow detection of small, sharp lines.  A larger filter causes more blurring, smearing out the value of a given pixel over a larger area of the image.  Larger blurring radii are more useful for detecting larger, smoother edges – for instance, the edge of a rainbow.
- Thresholds: the use of two thresholds with hysteresis allows more flexibility than a single-threshold approach, but general problems of thresholding approaches still apply.  A threshold set too high can miss important information.  On the other hand, a threshold set too low will falsely identify irrelevant information (such as noise) as important.  It is difficult to give a generic threshold that works well on all images.  No tried and tested approach to this problem yet exists.

 

## Conclusion

 

The Canny algorithm is adaptable to various environments.  Its parameters allow it to be tailored to recognition of edges of differing characteristics depending on the particular requirements of a given implementation. In Canny's original paper, the derivation of the optimal filter led to a [Finite Impulse Response](./Finite_Impulse_Response) filter, which can be slow to compute in the spatial domain if the amount of smoothing required is important (the filter will have a large spatial support in that case). For this reason, it is often suggested to use Rachid Deriche's [infinite impulse response](./Infinite_impulse_response)  form of Canny's filter (the [Canny–Deriche detector](./Deriche_edge_detector)), which is recursive, and which can be computed in a short, fixed amount of time for any desired amount of smoothing. The second form is suitable for real time implementations in [FPGAs](./FPGA) or [DSPs](./Digital_signal_processor), or very fast embedded PCs. In this context, however, the regular recursive implementation of the Canny operator does not give a good approximation of rotational symmetry and therefore gives a bias towards horizontal and vertical edges.

 

## See also

 
- [Computer vision](./Computer_vision)
- [Digital image processing](./Digital_image_processing)
- [Feature detection (computer vision)](./Feature_detection_(computer_vision))
- [Feature extraction](./Feature_extraction)
- [Ridge detection](./Ridge_detection)
- [Robinson compass mask](./Robinson_compass_mask)
- [Scale space](./Scale_space)

 

## References

  
1. [↑](./Canny_edge_detector#cite_ref-1) Rong, Weibin; Li, Zhanjing; Zhang, Wei; Sun, Lining (2014). ["An improved Canny edge detection algorithm"](http://ieeexplore.ieee.org/document/6885761/). *IEEE International Conference on Mechatronics and Automation*. IEEE: 577–582. [doi](./Doi_(identifier)):[10.1109/ICMA.2014.6885761](https://doi.org/10.1109%2FICMA.2014.6885761). [ISBN](./ISBN_(identifier)) [978-1-4799-3979-4](./Special:BookSources/978-1-4799-3979-4).
2. [↑](./Canny_edge_detector#cite_ref-2) Zhou, P., Ye, W., & Wang, Q. (2011). An Improved Canny Algorithm for Edge Detection. Journal of Computational Information Systems, 7(5), 1516-1523.
3. [↑](./Canny_edge_detector#cite_ref-3) Otsu N. A threshold selection method from gray-level histograms. IEEE Trans Systems, Man and Cybernetics,9(1):62-66,1979.
4. [↑](./Canny_edge_detector#cite_ref-4) Mallat S, Zhong S. Characterization of Signals from Multi scale Edges [J]. IEEE Trans on PAMI, 1992, 14 (7):710-732.
5. [↑](./Canny_edge_detector#cite_ref-5) Gebäck, T.; Koumoutsakos, P. (2009). ["Edge detection in microscopy images using curvelets"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2663783). *BMC Bioinformatics*. **10**: 75. [doi](./Doi_(identifier)):[10.1186/1471-2105-10-75](https://doi.org/10.1186%2F1471-2105-10-75). [PMC](./PMC_(identifier)) [2663783](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2663783). [PMID](./PMID_(identifier)) [19257905](https://pubmed.ncbi.nlm.nih.gov/19257905).

  
- Canny, J., *[A Computational Approach To Edge Detection](https://www.researchgate.net/publication/224377985_A_Computational_Approach_To_Edge_Detection)*, IEEE Transactions on Pattern Analysis and Machine Intelligence, 8(6):679–698, 1986.
- R. Deriche, *[Using Canny's criteria to derive a recursively implemented optimal edge detector](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.476.5736&rep=rep1&type=pdf)*, Int. J. Computer Vision, Vol. 1, pp. 167–187, April 1987.
- [Lindeberg, Tony "Edge detection and ridge detection with automatic scale selection", International Journal of Computer Vision, 30, 2, pp 117—154, 1998. (Includes the differential approach to non-maximum suppression.)](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A452310&dswid=-7063)
- Kimmel, Ron and [Bruckstein, Alfred M.](./Alfred_Marcel_Bruckstein) ["On regularized Laplacian zero crossings and other optimal edge integrators",  International Journal of Computer Vision, 53(3):225–243, 2003. (Includes the geometric variational interpretation for the Haralick–Canny edge detector.)](https://www.cs.technion.ac.il/~ron/PAPERS/laplacian_ijcv2003.pdf)
- [Moeslund, T. (2009, March 23). Canny Edge Detection. Retrieved December 3, 2014](https://web.archive.org/web/20150421090938/http://www.cse.iitd.ernet.in/~pkalra/csl783/canny.pdf)
- Thomas B. Moeslund. Image and Video Processing. August 2008
- [Green, B. (2002, January 1). Canny Edge Detection Tutorial. Retrieved December 3, 2014](http://dasl.mem.drexel.edu/alumni/bGreen/www.pages.drexel.edu/_weg22/can_tut.html); archived [here](https://web.archive.org/web/20160324173252/http://dasl.mem.drexel.edu/alumni/bGreen/www.pages.drexel.edu/_weg22/can_tut.html)

  

## External links

 
- [John Canny's home page](http://www.cs.berkeley.edu/~jfc/)
- [Publication List of Rachid Deriche](http://www-sop.inria.fr/odyssee/team/Rachid.Deriche/Publications/RD.references.html)
- [Journal Publications of Ron Kimmel](https://www.cs.technion.ac.il/~ron/PAPERS)
- [Canny edge detection in c++ OpenCV](http://docs.opencv.org/doc/tutorials/imgproc/imgtrans/canny_detector/canny_detector.html)
- [Canny edge detection in Python OpenCV](http://opencv-python-tutroals.readthedocs.org/en/latest/py_tutorials/py_imgproc/py_canny/py_canny.html) [Archived](https://web.archive.org/web/20140429184236/http://opencv-python-tutroals.readthedocs.org/en/latest/py_tutorials/py_imgproc/py_canny/py_canny.html) 2014-04-29 at the [Wayback Machine](./Wayback_Machine)
- [Canny Edge World - example video](https://www.youtube.com/watch?v=GLYU8yCWkpU)
- [Edge Detection for Image Processing](https://sdk.docutain.com/blogartikel/edge-detection-for-image-processing)