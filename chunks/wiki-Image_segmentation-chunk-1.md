---
source: sources/wiki-Image_segmentation.md
source_url: https://en.wikipedia.org/wiki/Image_segmentation
chunk: 1/5
---

Partitioning a digital image into segments 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/21/Model_of_a_segmented_femur_-_journal.pone.0079004.g005.png/250px-Model_of_a_segmented_femur_-_journal.pone.0079004.g005.png)](./File:Model_of_a_segmented_femur_-_journal.pone.0079004.g005.png)Model of a segmented left human [femur](./Femur). It shows the outer surface (red), the surface between compact bone and spongy bone (green) and the surface of the bone marrow (blue). 

In [digital image processing](./Digital_image_processing) and [computer vision](./Computer_vision), **image segmentation** is the process of partitioning a [digital image](./Digital_image) into multiple **image segments**, also known as **image regions** or **image objects** ([sets](./Set_(mathematics)) of [pixels](./Pixel)). The goal of segmentation is to simplify and/or change the representation of an image into something that is more meaningful and easier to analyze.[[1]](./Image_segmentation#cite_note-computervision-1)[[2]](./Image_segmentation#cite_note-2) Image segmentation is typically used to locate objects and [boundaries](./Boundary_tracing) (lines, curves, etc.) in images. More precisely, image segmentation is the process of assigning a label to every pixel in an image such that pixels with the same label share certain characteristics.

 

The result of image segmentation is a set of segments that collectively cover the entire image, or a set of [contours](./Contour_line) extracted from the image (see [edge detection](./Edge_detection)). Each of the pixels in a region are similar with respect to some characteristic or computed property,[[3]](./Image_segmentation#cite_note-3) such as [color](./Color), [intensity](./Luminous_intensity), or [texture](./Image_texture). Adjacent regions are significantly different with respect to the same characteristic(s).[[1]](./Image_segmentation#cite_note-computervision-1) When applied to a stack of images, typical in [medical imaging](./Medical_imaging), the resulting contours after image segmentation can be used to create [3D reconstructions](./3D_reconstruction) with the help of geometry reconstruction algorithms like [marching cubes](./Marching_cubes).[[4]](./Image_segmentation#cite_note-4)

 

## Applications

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/bd/3D_CT_of_thorax.jpg/250px-3D_CT_of_thorax.jpg)](./File:3D_CT_of_thorax.jpg)Volume segmentation of a 3D-rendered [CT scan](./CT_scan) of the [thorax](./Thorax): The anterior thoracic wall, the airways and the pulmonary vessels anterior to the root of the lung have been digitally removed in order to visualize thoracic contents: 
– blue: [pulmonary arteries](./Pulmonary_arteries) 
– red: [pulmonary veins](./Pulmonary_veins) (and also the [abdominal wall](./Abdominal_wall))
– yellow: the [mediastinum](./Mediastinum) 
– violet: the [diaphragm](./Thoracic_diaphragm)  

Some of the practical applications of image segmentation are:

 
- [Content-based image retrieval](./Content-based_image_retrieval)[[5]](./Image_segmentation#cite_note-5)
- [Machine vision](./Machine_vision)
- [Medical imaging](./Medical_imaging),[[6]](./Image_segmentation#cite_note-6)[[7]](./Image_segmentation#cite_note-7) and imaging studies in biomedical research, including [volume rendered](./Volume_rendering) images from [computed tomography](./CT_scan), [magnetic resonance imaging](./Magnetic_resonance_imaging), as well as volume electron microscopy techniques such as FIB-SEM.[[8]](./Image_segmentation#cite_note-8) 
- Locate tumors and other pathologies[[9]](./Image_segmentation#cite_note-9)[[10]](./Image_segmentation#cite_note-10)
- Measure tissue volumes[[11]](./Image_segmentation#cite_note-11)[[12]](./Image_segmentation#cite_note-12)
- Diagnosis, study of anatomical structure[[13]](./Image_segmentation#cite_note-13)
- Surgery planning
- Virtual surgery simulation
- Intra-surgery navigation
- Radiotherapy[[14]](./Image_segmentation#cite_note-14)
- [Digital Pathology](./Digital_pathology) and [Histopathology](./Histopathology). Nuclei [instance](./Instance_variable) segmentation in variously [stained](./Staining) [whole slide images](./Whole-slide_image) (WSIs) refers to the automatic delineation of individual cells' nuclei borders. This task is a specialized subproblem of instance segmentation, with high practical importance in biomedical research and diagnostics (e.g. cell counting, morphometric feature extraction, tumor grading, prognostic biomarker extraction).[[15]](./Image_segmentation#cite_note-15) The modern approach to the problem is the use of [deep learning](./Deep_learning) architectures developed to encompass the main challenges of separating overlapping or fused nuclei.[[16]](./Image_segmentation#cite_note-16)[[17]](./Image_segmentation#cite_note-17)[[18]](./Image_segmentation#cite_note-18) The availability of few humanly-annotated datasets poses another challenge to the problem.[[19]](./Image_segmentation#cite_note-19)[[20]](./Image_segmentation#cite_note-20)[[21]](./Image_segmentation#cite_note-21)

- [Object detection](./Object_detection)[[22]](./Image_segmentation#cite_note-22) 
- [Pedestrian detection](./Pedestrian_detection)
- [Face detection](./Face_detection)
- Brake light detection
- Locate objects in satellite images (roads, forests, crops, etc.)

- Recognition Tasks

- [Face recognition](./Face_recognition)
- [Fingerprint recognition](./Fingerprint_recognition)
- [Iris recognition](./Iris_recognition)
- Prohibited Item at [Airport security](./Airport_security) checkpoints

- Traffic control systems
- [Video surveillance](./Video_surveillance)
- [Video object co-segmentation and action localization](./Object_co-segmentation)[[23]](./Image_segmentation#cite_note-Liu_Wang_Hua_Zhang_2018_pp._5840–5853-23)[[24]](./Image_segmentation#cite_note-Wang_Duan_Zhang_Niu_p=1657-24)

 

Several general-purpose [algorithms](./Algorithm) and techniques have been developed for image segmentation. To be useful, these techniques must typically be combined with a domain's specific knowledge in order to effectively solve the domain's segmentation problems.

 

## Classes of segmentation techniques

 

There are two classes of segmentation techniques.

 
- Classical computer vision approaches
- AI based techniques

 

## Groups of image segmentation

 
- **Semantic segmentation** is an approach detecting, for every pixel, the belonging class.[[25]](./Image_segmentation#cite_note-25) For example, in a figure with many people, all the pixels belonging to persons will have the same class id and the pixels in the background will be classified as background.[[26]](./Image_segmentation#cite_note-26)
- **Instance segmentation** is an approach that identifies, for every pixel, the specific belonging instance of the object. It detects each distinct object of interest in the image.[[27]](./Image_segmentation#cite_note-27) For example, when each person in a figure is segmented as an individual object.
- **Panoptic segmentation** combines both semantic and instance segmentation. Like semantic segmentation, panoptic segmentation is an approach that identifies, for every pixel, the belonging class. Moreover, like in instance segmentation, panoptic segmentation distinguishes different instances of the same class.[[28]](./Image_segmentation#cite_note-Panoptic_Segmentation-28)

 

## Thresholding

 Main article: [Thresholding (image processing)](./Thresholding_(image_processing)) 

The simplest method of image segmentation is called the [thresholding](./Thresholding_(image_processing)) method. This method is based on a clip-level (or a threshold value) to turn a gray-scale image into a binary image.

 

The key of this method is to select the threshold value (or values when multiple-levels are selected). Several popular methods are used in industry including the maximum entropy method, [balanced histogram thresholding](./Balanced_histogram_thresholding), [Otsu's method](./Otsu's_method) (maximum variance), and [k-means clustering](./K-means_clustering).

 

Recently, methods have been developed for thresholding computed tomography (CT) images. The key idea is that, unlike Otsu's method, the thresholds are derived from the radiographs instead of the (reconstructed) image.[[29]](./Image_segmentation#cite_note-29)[[30]](./Image_segmentation#cite_note-30)

 

New methods suggest the use of multi-dimensional, fuzzy rule-based, non-linear thresholds. In these approaches, the decision regarding each pixel's membership in a segment is based on multi-dimensional rules derived from fuzzy logic and evolutionary algorithms, considering factors such as image lighting, environment, and application.[[31]](./Image_segmentation#cite_note-31)

 

## Clustering methods

 Main article: [Data clustering](./Data_clustering) [![Original image](//upload.wikimedia.org/wikipedia/commons/thumb/d/d3/Aurora_borealis_over_Eielson_Air_Force_Base%2C_Alaska.jpg/330px-Aurora_borealis_over_Eielson_Air_Force_Base%2C_Alaska.jpg)](./File:Aurora_borealis_over_Eielson_Air_Force_Base,_Alaska.jpg)Source image[![Processed image](//upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Polarlicht_2_kmeans_16_large.png/330px-Polarlicht_2_kmeans_16_large.png)](./File:Polarlicht_2_kmeans_16_large.png)Image after running *k*-means with *k = 16*. Note that a common technique to improve performance for large images is to downsample the image, compute the clusters, and then reassign the values to the larger image if necessary. 

The [K-means algorithm](./K-means_algorithm) is an [iterative](./Iterative) technique that is used to [partition an image](./Cluster_analysis) into *K* clusters.[[32]](./Image_segmentation#cite_note-32) The basic [algorithm](./Algorithm) is

 
1. Pick *K* cluster centers, either [randomly](./Random) or based on some [heuristic](./Heuristic) method, for example [K-means++](./K-means++)
2. Assign each pixel in the image to the cluster that minimizes the [distance](./Distance) between the pixel and the cluster center
3. Re-compute the cluster centers by averaging all of the pixels in the cluster
4. Repeat steps 2 and 3 until convergence is attained (i.e. no pixels change clusters)

 

In this case, [distance](./Distance) is the squared or absolute difference between a pixel and a cluster center. The difference is typically based on pixel [color](./Hue), [intensity](./Brightness), [texture](./Texture_(computer_graphics)), and location, or a weighted combination of these factors. *K* can be selected manually, [randomly](./Random), or by a [heuristic](./Heuristic). This algorithm is guaranteed to converge, but it may not return the [optimal](./Global_optimum) solution. The quality of the solution depends on the initial set of clusters and the value of *K*.

 

The [Mean Shift](./Mean_shift) algorithm is a technique that is used to partition an image into an unknown [apriori](./A_priori_and_a_posteriori) number of clusters. This has the advantage of not having to start with an initial guess of such parameter which makes it a better general solution for more diverse cases.

 

## Motion and interactive segmentation

 

Motion based segmentation is a technique that relies on motion in the image to perform segmentation.

 

The idea is simple: look at the differences between a pair of images. Assuming the object of interest is moving, the difference will be exactly that object.

 

Improving on this idea, Kenney et al. proposed interactive segmentation [](http://www.robotics.tu-berlin.de/fileadmin/fg170/Publikationen_pdf/2009-icra.pdf). They use a robot to poke objects in order to generate the motion signal necessary for motion-based segmentation.

 

Interactive segmentation follows the interactive perception framework proposed by Dov Katz [](http://www.dubikatz.com) and Oliver Brock [](http://www.robotics.tu-berlin.de/menue/team/oliver_brock).

 

Another technique that is based on motion is [rigid motion segmentation](./Rigid_motion_segmentation).

 

## Compression-based methods

 

Compression based methods postulate that the optimal segmentation is the one that minimizes, over all possible segmentations, the coding length of the data.[[33]](./Image_segmentation#cite_note-33)[[34]](./Image_segmentation#cite_note-34) The connection between these two concepts is that segmentation tries to find patterns in an image and any regularity in the image can be used to compress it. The method describes each segment by its texture and boundary shape. Each of these components is modeled by a probability distribution function and its coding length is computed as follows:

 
1. The boundary encoding leverages the fact that regions in natural images tend to have a smooth contour. This prior is used by [Huffman coding](./Huffman_coding) to encode the difference [chain code](./Chain_code) of the contours in an image. Thus, the smoother a boundary is, the shorter coding length it attains.
2. Texture is encoded by [lossy compression](./Lossy_compression) in a way similar to [minimum description length](./Minimum_description_length) (MDL) principle, but here the length of the data given the model is approximated by the number of samples times the [entropy](./Entropy_(information_theory)) of the model. The texture in each region is modeled by a [multivariate normal distribution](./Multivariate_normal_distribution) whose entropy has a closed form expression. An interesting property of this model is that the estimated entropy bounds the true entropy of the data from above. This is because among all distributions with a given mean and covariance, normal distribution has the largest entropy. Thus, the true coding length cannot be more than what the algorithm tries to minimize.

 

For any given segmentation of an image, this scheme yields the number of bits required to encode that image based on the given segmentation. Thus, among all possible segmentations of an image, the goal is to find the segmentation which produces the shortest coding length. This can be achieved by a simple agglomerative clustering method. The distortion in the lossy compression determines the coarseness of the segmentation and its optimal value may differ for each image. This parameter can be estimated heuristically from the contrast of textures in an image. For example, when the textures in an image are similar, such as in camouflage images, stronger sensitivity and thus lower quantization is required.

 

## Histogram-based methods

 

[Histogram](./Histogram)-based methods are very efficient compared to other image segmentation methods because they typically require only one pass through the [pixels](./Pixel). In this technique, a histogram is computed from all of the pixels in the image, and the peaks and valleys in the histogram are used to locate the [clusters](./Cluster_analysis) in the image.[[1]](./Image_segmentation#cite_note-computervision-1) [Color](./Hue) or [intensity](./Brightness) can be used as the measure.

 

A refinement of this technique is to [recursively](./Recursion_(computer_science)) apply the histogram-seeking method to clusters in the image in order to divide them into smaller clusters. This operation is repeated with smaller and smaller clusters until no more clusters are formed.[[1]](./Image_segmentation#cite_note-computervision-1)[[35]](./Image_segmentation#cite_note-35)

 

One disadvantage of the histogram-seeking method is that it may be difficult to identify significant peaks and valleys in the image.

 

Histogram-based approaches can also be quickly adapted to apply to multiple frames, while maintaining their single pass efficiency. The histogram can be done in multiple fashions when multiple frames are considered. The same approach that is taken with one frame can be applied to multiple, and after the results are merged, peaks and valleys that were previously difficult to identify are more likely to be distinguishable. The histogram can also be applied on a per-pixel basis where the resulting information is used to determine the most frequent color for the pixel location. This approach segments based on active objects and a static environment, resulting in a different type of segmentation useful in [video tracking](./Video_tracking).

 

## Edge detection

 

[Edge detection](./Edge_detection) is a well-developed field on its own within image processing. Region boundaries and edges are closely related,
since there is often a sharp adjustment in intensity at the region boundaries. Edge detection techniques have therefore been used as the base of another segmentation technique.

 

The edges identified by edge detection are often disconnected. To segment an object from an image however, one needs closed region boundaries. The desired edges are the boundaries between such objects or spatial-taxons.[[36]](./Image_segmentation#cite_note-36)[[37]](./Image_segmentation#cite_note-37)

 

Spatial-taxons[[38]](./Image_segmentation#cite_note-38) are information granules,[[39]](./Image_segmentation#cite_note-39) consisting of a crisp pixel region, stationed at abstraction levels within a hierarchical nested scene architecture. They are similar to the [Gestalt](./Gestalt_psychology) psychological designation of figure-ground, but are extended to include foreground, object groups, objects and salient object parts. Edge detection methods can be applied to the spatial-taxon region, in the same manner they would be applied to a silhouette. This method is particularly useful when the disconnected edge is part of an illusory contour[[40]](./Image_segmentation#cite_note-40)[[41]](./Image_segmentation#cite_note-41)

 

Segmentation methods can also be applied to edges obtained from edge detectors. Lindeberg and Li[[42]](./Image_segmentation#cite_note-42) developed an integrated method that segments edges into straight and curved edge segments for parts-based object recognition, based on a minimum description length (MDL) criterion that was optimized by a split-and-merge-like method with candidate breakpoints obtained from complementary junction cues to obtain more likely points at which to consider partitions into different segments.

 

## Isolated Point Detection

 

The detection of isolated points in an image is a fundamental part of image segmentation. This process primarily depends on the second derivative, indicating the use of the Laplacian operator. The Laplacian of a function     f ( x , y )   {\displaystyle f(x,y)}  ![{\displaystyle f(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/29473ed0c4e838ac9dbe074535e507166c0e9101) is given by:

      ∇ ∇   2   f ( x , y ) =     ∂ ∂   2   f   ∂ ∂   x  2      +     ∂ ∂   2   f   ∂ ∂   y  2        {\displaystyle \nabla ^{2}f(x,y)={\frac {\partial ^{2}f}{\partial x^{2}}}+{\frac {\partial ^{2}f}{\partial y^{2}}}}  ![{\displaystyle \nabla ^{2}f(x,y)={\frac {\partial ^{2}f}{\partial x^{2}}}+{\frac {\partial ^{2}f}{\partial y^{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4651e5fed3b2a9ffec40cd4dc27794732f371150) 

The Laplacian operator is employed such that the partial derivatives are derived from a specific equation. The second [partial derivative](./Partial_derivative) of     f ( x , y )   {\displaystyle f(x,y)}  ![{\displaystyle f(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/29473ed0c4e838ac9dbe074535e507166c0e9101) with respect to     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) and     y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d) are given by:

         ∂ ∂   2   f ( x , y )   ∂ ∂   x  2      = f ( x + 1 , y ) + f ( x − −  1 , y ) − −  2 f ( x , y )   {\displaystyle {\frac {\partial ^{2}f(x,y)}{\partial x^{2}}}=f(x+1,y)+f(x-1,y)-2f(x,y)}  ![{\displaystyle {\frac {\partial ^{2}f(x,y)}{\partial x^{2}}}=f(x+1,y)+f(x-1,y)-2f(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ab0d7b0fccd531919471b6cf23466ef38e709a7f)         ∂ ∂   2   f ( x , y )   ∂ ∂   y  2      = f ( x , y + 1 ) + f ( x , y − −  1 ) − −  2 f ( x , y )   {\displaystyle {\frac {\partial ^{2}f(x,y)}{\partial y^{2}}}=f(x,y+1)+f(x,y-1)-2f(x,y)}  ![{\displaystyle {\frac {\partial ^{2}f(x,y)}{\partial y^{2}}}=f(x,y+1)+f(x,y-1)-2f(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b834af4c311b1f25b0096313153e93c4444f3426) 

These partial derivatives are then used to compute the Laplacian as:

      ∇ ∇   2   f ( x , y ) = f ( x + 1 , y ) + f ( x − −  1 , y ) + f ( x , y + 1 ) + f ( x , y − −  1 ) − −  4 f ( x , y )   {\displaystyle \nabla ^{2}f(x,y)=f(x+1,y)+f(x-1,y)+f(x,y+1)+f(x,y-1)-4f(x,y)}  ![{\displaystyle \nabla ^{2}f(x,y)=f(x+1,y)+f(x-1,y)+f(x,y+1)+f(x,y-1)-4f(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dc67fb950fb7e25092c5dd7bcb0bdac562eb0167) 

This mathematical expression can be implemented by convolving with an appropriate mask. If we extend this equation to three dimensions (x,y,z), the intensity at each pixel location around a central pixel at (x, y, z) is replaced by their corresponding values. This equation becomes particularly useful when we assume that all pixels have unit spacing along each axis.

 

A sphere mask has been developed for use with three-dimensional datasets. The sphere mask is designed to use only integer arithmetic during calculations, thereby eliminating the need for floating-point hardware or software.

 

When applying these concepts to actual images represented as arrays of numbers, we need to consider what happens when we reach an edge or border region. The function     g ( x , y )   {\displaystyle g(x,y)}  ![{\displaystyle g(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bf358a54b0375e22ae5f3ab2c3e1a22c0c87e11c) is defined as:

     g ( x , y ) =   {    1    if    |  R ( x , y )  |  ≥ ≥  T     0    otherwise          {\displaystyle g(x,y)={\begin{cases}1&{\text{if }}|R(x,y)|\geq T\\0&{\text{otherwise}}\end{cases}}}  ![{\displaystyle g(x,y)={\begin{cases}1&{\text{if }}|R(x,y)|\geq T\\0&{\text{otherwise}}\end{cases}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75f5cc4a55ba6242608e3a114fafd371579b8b45) 

This above equation is used to determine whether a point in the image is an isolated point based on the response magnitude      |  R ( x , y )  |    {\displaystyle |R(x,y)|}  ![{\displaystyle |R(x,y)|}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d2ea8a46da16bdb516039e190a2c8b642bf3829b) and a threshold value     T   {\displaystyle T}  ![{\displaystyle T}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ec7200acd984a1d3a3d7dc455e262fbe54f7f6e0). If the response magnitude is greater than or equal to the threshold, the function returns 1, indicating the presence of an isolated point; otherwise, it returns 0. This helps in the effective detection and segmentation of isolated points in the image.[[43]](./Image_segmentation#cite_note-Digital_Image_Processing_2007-43)

 

## Application of Isolated Point Detection in X-ray Image Processing

 

The detection of isolated points has significant applications in various fields, including X-ray image processing. For instance, an original X-ray image of a turbine blade can be examined pixel-by-pixel to detect porosity in the upper-right quadrant of the blade. The result of applying an edge detector's response to this X-ray image can be approximated. This demonstrates the segmentation of isolated points in an image with the aid of single-pixel probes.[[43]](./Image_segmentation#cite_note-Digital_Image_Processing_2007-43)

 

## Dual clustering method

 

This method is a combination of three characteristics of the image: partition of the image based on histogram analysis is checked by high compactness of the clusters (objects), and high gradients of their borders. For that purpose two spaces have to be introduced: one space is the one-dimensional histogram of brightness *H* = *H*(*B*); the second space is the dual 3-dimensional space of the original image itself *B* = *B*(*x*, *y*). The first space allows to measure how compactly the brightness of the image is distributed by calculating a minimal clustering kmin. Threshold brightness T corresponding to kmin defines the binary (black-and-white) image – bitmap *b* = *φ*(*x*, *y*), where *φ*(*x*, *y*) = 0, if *B*(*x*, *y*) < *T*, and *φ*(*x*, *y*) = 1, if *B*(*x*, *y*) ≥ *T*. The bitmap *b* is an object in [dual space](./Dual_space). On that bitmap a measure has to be defined reflecting how compact distributed black (or white) pixels are. So, the goal is to find objects with good borders. For all *T* the measure *M*DC = *G*/(*k* × *L*) has to be calculated (where *k* is difference in brightness between the object and the background, *L* is length of all borders, and *G* is mean gradient on the borders). Maximum of MDC defines the segmentation.[[44]](./Image_segmentation#cite_note-44)

 


