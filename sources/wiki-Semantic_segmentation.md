---
source: https://en.wikipedia.org/wiki/Semantic_segmentation
fetched: 2026-06-21
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

 

## Multi-scale segmentation

 

Image segmentations are computed at multiple scales in [scale space](./Scale_space) and sometimes propagated from coarse to fine scales; see [scale-space segmentation](./Scale-space_segmentation).

 

Segmentation criteria can be arbitrarily complex and may take into account global as well as local criteria. A common requirement is that each region must be connected in some sense.

 

### One-dimensional hierarchical signal segmentation

 

Witkin's seminal work[[71]](./Image_segmentation#cite_note-71)[[72]](./Image_segmentation#cite_note-72) in scale space included the notion that a one-dimensional signal could be unambiguously segmented into regions, with one scale parameter controlling the scale of segmentation.

 

A key observation is that the zero-crossings of the second derivatives (minima and maxima of the first derivative or slope) of multi-scale-smoothed versions of a signal form a nesting tree, which defines hierarchical relations between segments at different scales. Specifically, slope extrema at coarse scales can be traced back to corresponding features at fine scales. When a slope maximum and slope minimum annihilate each other at a larger scale, the three segments that they separated merge into one segment, thus defining the hierarchy of segments.

 

### Image segmentation and primal sketch

 

There have been numerous research works in this area, out of which a few have now reached a state where they can be applied either with interactive manual intervention (usually with application to medical imaging) or fully automatically. The following is a brief overview of some of the main research ideas that current approaches are based upon.

 

The nesting structure that Witkin described is, however, specific for one-dimensional signals and does not trivially transfer to higher-dimensional images. Nevertheless, this general idea has inspired several other authors to investigate coarse-to-fine schemes for image segmentation. Koenderink[[73]](./Image_segmentation#cite_note-73) proposed to study how iso-intensity contours evolve over scales and this approach was investigated in more detail by Lifshitz and Pizer.[[74]](./Image_segmentation#cite_note-74) Unfortunately, however, the intensity of image features changes over scales, which implies that it is hard to trace coarse-scale image features to finer scales using iso-intensity information.

 

Lindeberg[[75]](./Image_segmentation#cite_note-75)[[76]](./Image_segmentation#cite_note-lin94-76) studied the problem of linking local extrema and saddle points over scales, and proposed an image representation called the scale-space primal sketch which makes explicit the relations between structures at different scales, and also makes explicit which image features are stable over large ranges of scale including locally appropriate scales for those. Bergholm proposed to detect edges at coarse scales in scale-space and then trace them back to finer scales with manual choice of both the coarse detection scale and the fine localization scale.

 

Gauch and Pizer[[77]](./Image_segmentation#cite_note-77) studied the complementary problem of ridges and valleys at multiple scales and developed a tool for interactive image segmentation based on multi-scale watersheds. The use of multi-scale watershed with application to the gradient map has also been investigated by Olsen and Nielsen[[78]](./Image_segmentation#cite_note-78) and been carried over to clinical use by Dam.[[79]](./Image_segmentation#cite_note-79) Vincken et al.[[80]](./Image_segmentation#cite_note-80) proposed a hyperstack for defining probabilistic relations between image structures at different scales. The use of stable image structures over scales has been furthered by Ahuja[[81]](./Image_segmentation#cite_note-81)[[82]](./Image_segmentation#cite_note-82) and his co-workers into a fully automated system. A fully automatic brain segmentation algorithm based on closely related ideas of multi-scale watersheds has been presented by Undeman and Lindeberg[[83]](./Image_segmentation#cite_note-83) and been extensively tested in brain databases.

 

These ideas for multi-scale image segmentation by linking image structures over scales have also been picked up by Florack and Kuijper.[[84]](./Image_segmentation#cite_note-84) Bijaoui and Rué[[85]](./Image_segmentation#cite_note-85) associate structures detected in scale-space above a minimum noise threshold into an object tree which spans multiple scales and corresponds to a kind of feature in the original signal. Extracted features are accurately reconstructed using an iterative conjugate gradient matrix method.

 

## Semi-automatic segmentation

 

In one kind of segmentation, the user outlines the region of interest with the mouse clicks and algorithms are applied so that the path that best fits the edge of the image is shown.

 

Techniques like [SIOX](./Simple_Interactive_Object_Extraction), [Livewire](./Livewire_Segmentation_Technique), Intelligent Scissors or IT-SNAPS are used in this kind of segmentation. In an alternative kind of semi-automatic segmentation, the algorithms return a spatial-taxon (i.e. foreground, object-group, object or object-part) selected by the user or designated via prior probabilities.[[86]](./Image_segmentation#cite_note-86)[[87]](./Image_segmentation#cite_note-87)

 

## Trainable segmentation

 

Most of the aforementioned segmentation methods are based only on color information of pixels in the image. Humans use much more knowledge when performing image segmentation, but implementing this knowledge would cost considerable human engineering and computational time, and would require a huge [domain knowledge](./Domain_knowledge) database which does not currently exist. Trainable segmentation methods, such as [neural network](./Neural_network) segmentation, overcome these issues by modeling the domain knowledge from a dataset of labeled pixels.

 

An image segmentation [neural network](./Neural_network) can process small areas of an image to extract simple features such as edges.[[88]](./Image_segmentation#cite_note-Transactions_on_Engineering,_Computing_and_Technology-88) Another neural network, or any decision-making mechanism, can then combine these features to label the areas of an image accordingly. A type of network designed this way is the [Kohonen map](./Kohonen_map).

 

[Pulse-coupled neural networks (PCNNs)](./Pulse-coupled_networks) are neural models proposed by modeling a cat's visual cortex and developed for high-performance [biomimetic](./Biomimetic) [image processing](./Image_processing). In 1989, Reinhard Eckhorn introduced a neural model to emulate the mechanism of a cat's visual cortex. The Eckhorn model provided a simple and effective tool for studying the visual cortex of small mammals, and was soon recognized as having significant application potential in image processing. In 1994, the Eckhorn model was adapted to be an image processing algorithm by John L. Johnson, who termed this algorithm Pulse-Coupled Neural Network.[[89]](./Image_segmentation#cite_note-89) Over the past decade, PCNNs have been utilized for a variety of image processing applications, including: image segmentation, feature generation, face extraction, motion detection, region growing, noise reduction, and so on. A PCNN is a two-dimensional neural network. Each neuron in the network corresponds to one pixel in an input image, receiving its corresponding pixel's color information (e.g. intensity) as an external stimulus. Each neuron also connects with its neighboring neurons, receiving local stimuli from them. The external and local stimuli are combined in an internal activation system, which accumulates the stimuli until it exceeds a dynamic threshold, resulting in a pulse output. Through iterative computation, PCNN neurons produce temporal series of pulse outputs. The temporal series of pulse outputs contain information of input images and can be utilized for various image processing applications, such as image segmentation and feature generation. Compared with conventional image processing means, PCNNs have several significant merits, including robustness against noise, independence of geometric variations in input patterns, capability of bridging minor intensity variations in input patterns, etc.

 

In 2015, [convolutional neural networks](./Convolutional_neural_network) reached state of the art in semantic segmentation.[[90]](./Image_segmentation#cite_note-90) [U-Net](./U-Net) is an architecture which takes as input an image and outputs a label for each pixel.[[91]](./Image_segmentation#cite_note-91) U-Net initially was developed to detect cell boundaries in biomedical images. U-Net follows classical [autoencoder](./Autoencoder) architecture, as such it contains two sub-structures. The encoder structure follows the traditional stack of convolutional and max pooling layers to increase the receptive field as it goes through the layers. It is used to capture the context in the image. The decoder structure utilizes transposed convolution layers for upsampling so that the end dimensions are close to that of the input image. Skip connections are placed between convolution and transposed convolution layers of the same shape in order to preserve details that would have been lost otherwise.

 

In addition to pixel-level semantic segmentation tasks which assign a given category to each pixel, modern segmentation applications include instance-level semantic segmentation tasks in which each individual in a given category must be uniquely identified, as well as panoptic segmentation tasks which combines these two tasks to provide a more complete scene segmentation.[[28]](./Image_segmentation#cite_note-Panoptic_Segmentation-28)

 

## Segmentation of related images and videos

 Main article: [Object co-segmentation](./Object_co-segmentation) 

Related images such as a photo album or a sequence of video frames often contain semantically similar objects and scenes, therefore it is often beneficial to exploit such correlations.[[92]](./Image_segmentation#cite_note-Vicente_Rother_Kolmogorov_2011_p.-92) The task of simultaneously segmenting scenes from related images or video frames is termed [co-segmentation](./Object_co-segmentation),[[23]](./Image_segmentation#cite_note-Liu_Wang_Hua_Zhang_2018_pp._5840–5853-23) which is typically used in [human action localization](./Activity_recognition). Unlike conventional [bounding box](./Minimum_bounding_box)-based [object detection](./Object_detection), human action localization methods provide finer-grained results, typically per-image segmentation masks delineating the human object of interest and its action category (e.g., *Segment-Tube*[[24]](./Image_segmentation#cite_note-Wang_Duan_Zhang_Niu_p=1657-24)). Techniques such as dynamic [Markov Networks](./Markov_random_field), [CNN](./Convolutional_neural_network) and [LSTM](./Long_short-term_memory) are often employed to exploit the inter-frame correlations.

 

## Other methods

 

There are many other methods of segmentation like [multispectral segmentation](./Multispectral_segmentation) or connectivity-based segmentation based on [DTI images](./Diffusion_MRI#Diffusion_tensor_imaging).[[93]](./Image_segmentation#cite_note-93)[[94]](./Image_segmentation#cite_note-94)

 

## See also

 
- [Object co-segmentation](./Object_co-segmentation) – Image segmentation in computer vision
- [Computer vision](./Computer_vision) – Computerized information extraction from images
- [Image-based meshing](./Image-based_meshing)
- [Range image segmentation](./Range_image_segmentation)
- [Vector quantization](./Vector_quantization) – Classical quantization technique from signal processing
- [Image quantization](./Image_quantization) – Lossy compression techniquePages displaying short descriptions of redirect targets
- [Color quantization](./Color_quantization) – Image processing technique
- [Object-based image analysis](./Object-based_image_analysis) – Extraction of information from images via digital image processing techniquesPages displaying short descriptions of redirect targets
- [List of manual image annotation tools](./List_of_manual_image_annotation_tools)
- [Rigid motion segmentation](./Rigid_motion_segmentation)
- [Text segmentation](./Text_segmentation) – Human writing practice

 

## Notes

  {{reflist|2}}  
1. [1](./Image_segmentation#cite_ref-computervision_1-0) [2](./Image_segmentation#cite_ref-computervision_1-1) [3](./Image_segmentation#cite_ref-computervision_1-2) [4](./Image_segmentation#cite_ref-computervision_1-3) [5](./Image_segmentation#cite_ref-computervision_1-4) [Linda G. Shapiro](./Linda_Shapiro) and George C. Stockman (2001):  "Computer Vision", pp 279–325, New Jersey, Prentice-Hall, [ISBN](./ISBN_(identifier)) [0-13-030796-3](./Special:BookSources/0-13-030796-3)
2. [↑](./Image_segmentation#cite_ref-2) Barghout, Lauren, and Lawrence W. Lee. "Perceptual information processing system." Paravue Inc. U.S. Patent Application 10/618,543, filed 11 July 2003.
3. [↑](./Image_segmentation#cite_ref-3) Nielsen, Frank; Nock, Richard (2003). "On region merging: The statistical soundness of fast sorting, with applications". *2003 IEEE Computer Society Conference on Computer Vision and Pattern Recognition, 2003. Proceedings*. Vol. 2. IEEE. pp. II:19–26. [doi](./Doi_(identifier)):[10.1109/CVPR.2003.1211447](https://doi.org/10.1109%2FCVPR.2003.1211447). [ISBN](./ISBN_(identifier)) [0-7695-1900-8](./Special:BookSources/0-7695-1900-8).
4. [↑](./Image_segmentation#cite_ref-4) Zachow, Stefan, Michael Zilske, and Hans-Christian Hege. "[3D reconstruction of individual anatomy from medical image data: Segmentation and geometry processing](https://opus4.kobv.de/opus4-zib/files/1044/ZR_07_41.pdf)[*[permanent dead link](./Wikipedia:Link_rot)*]." (2007).
5. [↑](./Image_segmentation#cite_ref-5) Belongie, Serge, et al. "[Color-and texture-based image segmentation using EM and its application to content-based image retrieval](http://people.eecs.berkeley.edu/~malik/papers/blobworld98.pdf)." Sixth International Conference on Computer Vision (IEEE Cat. No. 98CH36271). IEEE, 1998.
6. [↑](./Image_segmentation#cite_ref-6) Pham, Dzung L.; Xu, Chenyang; Prince, Jerry L. (2000). "Current Methods in Medical Image Segmentation". *Annual Review of Biomedical Engineering*. **2**: 315–337. [doi](./Doi_(identifier)):[10.1146/annurev.bioeng.2.1.315](https://doi.org/10.1146%2Fannurev.bioeng.2.1.315). [PMID](./PMID_(identifier)) [11701515](https://pubmed.ncbi.nlm.nih.gov/11701515).
7. [↑](./Image_segmentation#cite_ref-7) Forghani, M.; Forouzanfar, M.; Teshnehlab, M. (2010). "Parameter optimization of improved fuzzy c-means clustering algorithm for brain MR image segmentation". *Engineering Applications of Artificial Intelligence*. **23** (2): 160–168. [doi](./Doi_(identifier)):[10.1016/j.engappai.2009.10.002](https://doi.org/10.1016%2Fj.engappai.2009.10.002).
8. [↑](./Image_segmentation#cite_ref-8) Reznikov, Natalie; Buss, Dan J.; Provencher, Benjamin; McKee, Marc D.; Piché, Nicolas (October 2020). "Deep learning for 3D imaging and image analysis in biomineralization research". *Journal of Structural Biology*. **212** (1) 107598. [doi](./Doi_(identifier)):[10.1016/j.jsb.2020.107598](https://doi.org/10.1016%2Fj.jsb.2020.107598). [ISSN](./ISSN_(identifier)) [1047-8477](https://search.worldcat.org/issn/1047-8477). [PMID](./PMID_(identifier)) [32783967](https://pubmed.ncbi.nlm.nih.gov/32783967). [S2CID](./S2CID_(identifier)) [221126896](https://api.semanticscholar.org/CorpusID:221126896).
9. [↑](./Image_segmentation#cite_ref-9) Wu, Wei; Chen, Albert Y. C.; Zhao, Liang; Corso, Jason J. (2014). ["Brain tumor detection and segmentation in a CRF (Conditional random fields) framework with pixel-pairwise affinity and superpixel-level features"](https://link.springer.com/article/10.1007/s11548-013-0922-7). *International Journal of Computer Assisted Radiology and Surgery*. **9** (2): 241–253. [doi](./Doi_(identifier)):[10.1007/s11548-013-0922-7](https://doi.org/10.1007%2Fs11548-013-0922-7). [PMID](./PMID_(identifier)) [23860630](https://pubmed.ncbi.nlm.nih.gov/23860630). [S2CID](./S2CID_(identifier)) [13474403](https://api.semanticscholar.org/CorpusID:13474403).
10. [↑](./Image_segmentation#cite_ref-10) E. B. George and M. Karnan (2012): "[MR Brain image segmentation using Bacteria Foraging Optimization Algorithm](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.411.7411&rep=rep1&type=pdf)", *International Journal of Engineering and Technology*, Vol. 4.
11. [↑](./Image_segmentation#cite_ref-11) Ye, Run Zhou; Noll, Christophe; Richard, Gabriel; Lepage, Martin; Turcotte, Éric E.; Carpentier, André C. (February 2022). ["DeepImageTranslator: A free, user-friendly graphical interface for image translation using deep-learning and its applications in 3D CT image analysis"](https://doi.org/10.1016%2Fj.slast.2021.10.014). *SLAS Technology*. **27** (1): 76–84. [doi](./Doi_(identifier)):[10.1016/j.slast.2021.10.014](https://doi.org/10.1016%2Fj.slast.2021.10.014). [ISSN](./ISSN_(identifier)) [2472-6303](https://search.worldcat.org/issn/2472-6303). [PMID](./PMID_(identifier)) [35058205](https://pubmed.ncbi.nlm.nih.gov/35058205).
12. [↑](./Image_segmentation#cite_ref-12) Ye, En Zhou; Ye, En Hui; Bouthillier, Maxime; Ye, Run Zhou (18 February 2022). "DeepImageTranslator V2: analysis of multimodal medical images using semantic segmentation maps generated through deep learning". [bioRxiv](./BioRxiv_(identifier)) [10.1101/2021.10.12.464160](https://doi.org/10.1101%2F2021.10.12.464160).
13. [↑](./Image_segmentation#cite_ref-13) Kamalakannan, Sridharan; Gururajan, Arunkumar; Sari-Sarraf, Hamed; Rodney, Long; Antani, Sameer (17 February 2010). "Double-Edge Detection of Radiographic Lumbar Vertebrae Images Using Pressurized Open DGVF Snakes". *IEEE Transactions on Biomedical Engineering*. **57** (6): 1325–1334. [Bibcode](./Bibcode_(identifier)):[2010ITBE...57.1325K](https://ui.adsabs.harvard.edu/abs/2010ITBE...57.1325K). [doi](./Doi_(identifier)):[10.1109/tbme.2010.2040082](https://doi.org/10.1109%2Ftbme.2010.2040082). [PMID](./PMID_(identifier)) [20172792](https://pubmed.ncbi.nlm.nih.gov/20172792). [S2CID](./S2CID_(identifier)) [12766600](https://api.semanticscholar.org/CorpusID:12766600).
14. [↑](./Image_segmentation#cite_ref-14) Georgescu, Mariana-Iuliana; Ionescu, Radu Tudor; Miron, Andreea-Iuliana (21 December 2022). "Diversity-Promoting Ensemble for Medical Image Segmentation". [arXiv](./ArXiv_(identifier)):[2210.12388](https://arxiv.org/abs/2210.12388) [[eess.IV](https://arxiv.org/archive/eess.IV)].
15. [↑](./Image_segmentation#cite_ref-15) Basu, Anusua; Senapati, Pradip; Deb, Mainak; Rai, Rebika; Dhal, Krishna Gopal (6 March 2023). ["A survey on recent trends in deep learning for nucleus segmentation from histopathology images"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9987406). *Evolving Systems*. **15**: 203–248. [doi](./Doi_(identifier)):[10.1007/s12530-023-09491-3](https://doi.org/10.1007%2Fs12530-023-09491-3). [ISSN](./ISSN_(identifier)) [1868-6486](https://search.worldcat.org/issn/1868-6486). [PMC](./PMC_(identifier)) [9987406](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9987406). [PMID](./PMID_(identifier)) [38625364](https://pubmed.ncbi.nlm.nih.gov/38625364).
16. [↑](./Image_segmentation#cite_ref-16) Mahbod, Amirreza; Schaefer, Gerald; Dorffner, Georg; Hatamikia, Sepideh; Ecker, Rupert; Ellinger, Isabella (11 November 2022). ["A dual decoder U-Net-based model for nuclei instance segmentation in hematoxylin and eosin-stained histological images"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9691672). *Frontiers in Medicine*. **9** 978146. [doi](./Doi_(identifier)):[10.3389/fmed.2022.978146](https://doi.org/10.3389%2Ffmed.2022.978146). [ISSN](./ISSN_(identifier)) [2296-858X](https://search.worldcat.org/issn/2296-858X). [PMC](./PMC_(identifier)) [9691672](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9691672). [PMID](./PMID_(identifier)) [36438040](https://pubmed.ncbi.nlm.nih.gov/36438040).
17. [↑](./Image_segmentation#cite_ref-17) Ramakrishnan, Vignesh; Artinger, Annalena; Daza Barragan, Laura Alexandra; Daza, Jimmy; Winter, Lina; Niedermair, Tanja; Itzel, Timo; Arbelaez, Pablo; Teufel, Andreas; Cotarelo, Cristina L.; Brochhausen, Christoph (1 October 2024). ["Nuclei Detection and Segmentation of Histopathological Images Using a Feature Pyramidal Network Variant of a Mask R-CNN"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11504515). *Bioengineering*. **11** (10): 994. [doi](./Doi_(identifier)):[10.3390/bioengineering11100994](https://doi.org/10.3390%2Fbioengineering11100994). [ISSN](./ISSN_(identifier)) [2306-5354](https://search.worldcat.org/issn/2306-5354). [PMC](./PMC_(identifier)) [11504515](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11504515). [PMID](./PMID_(identifier)) [39451370](https://pubmed.ncbi.nlm.nih.gov/39451370).
18. [↑](./Image_segmentation#cite_ref-18) Shu, Jie; Fu, Hao; Qiu, Guoping; Kaye, Philip; Ilyas, Mohammad (2013). ["Segmenting overlapping cell nuclei in digital histopathology images"](https://pubmed.ncbi.nlm.nih.gov/24110968). *2013 35th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC)*. Vol. 2013. pp. 5445–5448. [doi](./Doi_(identifier)):[10.1109/EMBC.2013.6610781](https://doi.org/10.1109%2FEMBC.2013.6610781). [ISBN](./ISBN_(identifier)) [978-1-4577-0216-7](./Special:BookSources/978-1-4577-0216-7). [ISSN](./ISSN_(identifier)) [2694-0604](https://search.worldcat.org/issn/2694-0604). [PMID](./PMID_(identifier)) [24110968](https://pubmed.ncbi.nlm.nih.gov/24110968).
19. [↑](./Image_segmentation#cite_ref-19) ["PAN-CANCER-NUCLEI-SEG"](https://www.cancerimagingarchive.net/analysis-result/pan-cancer-nuclei-seg/). *The Cancer Imaging Archive (TCIA)*. Retrieved 13 October 2025.
20. [↑](./Image_segmentation#cite_ref-20) Mahbod, Amirreza; Polak, Christine; Feldmann, Katharina; Khan, Rumsha; Gelles, Katharina; Dorffner, Georg; Woitek, Ramona; Hatamikia, Sepideh; Ellinger, Isabella (14 March 2024). ["NuInsSeg: A fully annotated dataset for nuclei instance segmentation in H&E-stained histological images"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10940572). *Scientific Data*. **11** (1): 295. [Bibcode](./Bibcode_(identifier)):[2024NatSD..11..295M](https://ui.adsabs.harvard.edu/abs/2024NatSD..11..295M). [doi](./Doi_(identifier)):[10.1038/s41597-024-03117-2](https://doi.org/10.1038%2Fs41597-024-03117-2). [ISSN](./ISSN_(identifier)) [2052-4463](https://search.worldcat.org/issn/2052-4463). [PMC](./PMC_(identifier)) [10940572](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10940572). [PMID](./PMID_(identifier)) [38486039](https://pubmed.ncbi.nlm.nih.gov/38486039).
21. [↑](./Image_segmentation#cite_ref-21) Yoo, Inwan; Yoo, Donggeun; Paeng, Kyunghyun (22 July 2019), *PseudoEdgeNet: Nuclei Segmentation only with Point Annotations*, [arXiv](./ArXiv_(identifier)):[1906.02924](https://arxiv.org/abs/1906.02924)
22. [↑](./Image_segmentation#cite_ref-22) J. A. Delmerico, P. David and J. J. Corso (2011): "[Building façade detection, segmentation and parameter estimation for mobile robot localization and guidance](http://www.jeffdelmerico.com/wp-content/papercite-data/pdf/delmerico2011building.pdf)", International Conference on Intelligent Robots and Systems, pp. 1632–1639.
23. [1](./Image_segmentation#cite_ref-Liu_Wang_Hua_Zhang_2018_pp._5840–5853_23-0) [2](./Image_segmentation#cite_ref-Liu_Wang_Hua_Zhang_2018_pp._5840–5853_23-1) Liu, Ziyi; Wang, Le; Hua, Gang; Zhang, Qilin; Niu, Zhenxing; Wu, Ying; Zheng, Nanning (2018). ["Joint Video Object Discovery and Segmentation by Coupled Dynamic Markov Networks"](https://qilin-zhang.github.io/_pages/pdfs/Joint_Video_Object_Discovery_and_Segmentation_by_Coupled_Dynamic_Markov_Networks.pdf) (PDF). *IEEE Transactions on Image Processing*. **27** (12): 5840–5853. [Bibcode](./Bibcode_(identifier)):[2018ITIP...27.5840L](https://ui.adsabs.harvard.edu/abs/2018ITIP...27.5840L). [doi](./Doi_(identifier)):[10.1109/tip.2018.2859622](https://doi.org/10.1109%2Ftip.2018.2859622). [ISSN](./ISSN_(identifier)) [1057-7149](https://search.worldcat.org/issn/1057-7149). [PMID](./PMID_(identifier)) [30059300](https://pubmed.ncbi.nlm.nih.gov/30059300). [S2CID](./S2CID_(identifier)) [51867241](https://api.semanticscholar.org/CorpusID:51867241).
24. [1](./Image_segmentation#cite_ref-Wang_Duan_Zhang_Niu_p=1657_24-0) [2](./Image_segmentation#cite_ref-Wang_Duan_Zhang_Niu_p=1657_24-1) Wang, Le; Duan, Xuhuan; Zhang, Qilin; Niu, Zhenxing; Hua, Gang; Zheng, Nanning (22 May 2018). ["Segment-Tube: Spatio-Temporal Action Localization in Untrimmed Videos with Per-Frame Segmentation"](https://qilin-zhang.github.io/_pages/pdfs/Segment-Tube_Spatio-Temporal_Action_Localization_in_Untrimmed_Videos_with_Per-Frame_Segmentation.pdf) (PDF). *Sensors*. **18** (5): 1657. [Bibcode](./Bibcode_(identifier)):[2018Senso..18.1657W](https://ui.adsabs.harvard.edu/abs/2018Senso..18.1657W). [doi](./Doi_(identifier)):[10.3390/s18051657](https://doi.org/10.3390%2Fs18051657). [ISSN](./ISSN_(identifier)) [1424-8220](https://search.worldcat.org/issn/1424-8220). [PMC](./PMC_(identifier)) [5982167](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5982167). [PMID](./PMID_(identifier)) [29789447](https://pubmed.ncbi.nlm.nih.gov/29789447).
25. [↑](./Image_segmentation#cite_ref-25) Guo, Dazhou; Pei, Yanting; Zheng, Kang; Yu, Hongkai; Lu, Yuhang; Wang, Song (2020). ["Degraded Image Semantic Segmentation With Dense-Gram Networks"](https://doi.org/10.1109%2FTIP.2019.2936111). *IEEE Transactions on Image Processing*. **29**: 782–795. [Bibcode](./Bibcode_(identifier)):[2020ITIP...29..782G](https://ui.adsabs.harvard.edu/abs/2020ITIP...29..782G). [doi](./Doi_(identifier)):[10.1109/TIP.2019.2936111](https://doi.org/10.1109%2FTIP.2019.2936111). [ISSN](./ISSN_(identifier)) [1057-7149](https://search.worldcat.org/issn/1057-7149). [PMID](./PMID_(identifier)) [31449020](https://pubmed.ncbi.nlm.nih.gov/31449020). [S2CID](./S2CID_(identifier)) [201753511](https://api.semanticscholar.org/CorpusID:201753511).
26. [↑](./Image_segmentation#cite_ref-26) Mesh Flinders (11 September 2023). ["What is semantic segmentation?"](https://www.ibm.com/think/topics/semantic-segmentation). *IBM Think*. International Business Machines Corporation. Retrieved 21 October 2025.
27. [↑](./Image_segmentation#cite_ref-27) Yi, Jingru; Wu, Pengxiang; Jiang, Menglin; Huang, Qiaoying; Hoeppner, Daniel J.; Metaxas, Dimitris N. (July 2019). ["Attentive neural cell instance segmentation"](https://doi.org/10.1016%2Fj.media.2019.05.004). *Medical Image Analysis*. **55**: 228–240. [doi](./Doi_(identifier)):[10.1016/j.media.2019.05.004](https://doi.org/10.1016%2Fj.media.2019.05.004). [PMID](./PMID_(identifier)) [31103790](https://pubmed.ncbi.nlm.nih.gov/31103790). [S2CID](./S2CID_(identifier)) [159038604](https://api.semanticscholar.org/CorpusID:159038604).
28. [1](./Image_segmentation#cite_ref-Panoptic_Segmentation_28-0) [2](./Image_segmentation#cite_ref-Panoptic_Segmentation_28-1) Alexander Kirillov; Kaiming He; Ross Girshick; Carsten Rother; Piotr Dollár (2018). "Panoptic Segmentation". [arXiv](./ArXiv_(identifier)):[1801.00868](https://arxiv.org/abs/1801.00868) [[cs.CV](https://arxiv.org/archive/cs.CV)].
29. [↑](./Image_segmentation#cite_ref-29) Batenburg, K J.; Sijbers, J. (2009). "Adaptive thresholding of tomograms by projection distance minimization". *Pattern Recognition*. **42** (10): 2297–2305. [Bibcode](./Bibcode_(identifier)):[2009PatRe..42.2297B](https://ui.adsabs.harvard.edu/abs/2009PatRe..42.2297B). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.182.8483](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.182.8483). [doi](./Doi_(identifier)):[10.1016/j.patcog.2008.11.027](https://doi.org/10.1016%2Fj.patcog.2008.11.027).
30. [↑](./Image_segmentation#cite_ref-30) Batenburg, K J.; Sijbers, J. (June 2009). ["Optimal Threshold Selection for Tomogram Segmentation by Projection Distance Minimization"](https://web.archive.org/web/20130503171943/http://www.visielab.ua.ac.be/publications/optimal-threshold-selection-tomogram-segmentation-projection-distance-minimization). *IEEE Transactions on Medical Imaging*. **28** (5): 676–686. [Bibcode](./Bibcode_(identifier)):[2009ITMI...28..676B](https://ui.adsabs.harvard.edu/abs/2009ITMI...28..676B). [doi](./Doi_(identifier)):[10.1109/tmi.2008.2010437](https://doi.org/10.1109%2Ftmi.2008.2010437). [PMID](./PMID_(identifier)) [19272989](https://pubmed.ncbi.nlm.nih.gov/19272989). [S2CID](./S2CID_(identifier)) [10994501](https://api.semanticscholar.org/CorpusID:10994501). Archived from [the original](http://www.visielab.ua.ac.be/publications/optimal-threshold-selection-tomogram-segmentation-projection-distance-minimization) (PDF) on 3 May 2013. Retrieved 31 July 2012.
31. [↑](./Image_segmentation#cite_ref-31) Kashanipour, A.; Milani, N; Kashanipour, A.; Eghrary, H. (May 2008). "Robust Color Classification Using Fuzzy Rule-Based Particle Swarm Optimization". *2008 Congress on Image and Signal Processing*. Vol. 2. IEEE Congress on Image and Signal Processing. pp. 110–114. [doi](./Doi_(identifier)):[10.1109/CISP.2008.770](https://doi.org/10.1109%2FCISP.2008.770). [ISBN](./ISBN_(identifier)) [978-0-7695-3119-9](./Special:BookSources/978-0-7695-3119-9). [S2CID](./S2CID_(identifier)) [8422475](https://api.semanticscholar.org/CorpusID:8422475).
32. [↑](./Image_segmentation#cite_ref-32) Barghout, Lauren; Sheynin, Jacob (2013). ["Real-world scene perception and perceptual organization: Lessons from Computer Vision"](https://doi.org/10.1167%2F13.9.709). *Journal of Vision*. **13** (9): 709. [doi](./Doi_(identifier)):[10.1167/13.9.709](https://doi.org/10.1167%2F13.9.709).
33. [↑](./Image_segmentation#cite_ref-33) Hossein Mobahi; Shankar Rao; Allen Yang; Shankar Sastry; Yi Ma. (2011). ["Segmentation of Natural Images by Texture and Boundary Compression"](https://web.archive.org/web/20170808173212/http://perception.csl.illinois.edu/coding//papers/MobahiH2011-IJCV.pdf) (PDF). *International Journal of Computer Vision*. **95**: 86–98. [arXiv](./ArXiv_(identifier)):[1006.3679](https://arxiv.org/abs/1006.3679). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.180.3579](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.180.3579). [doi](./Doi_(identifier)):[10.1007/s11263-011-0444-0](https://doi.org/10.1007%2Fs11263-011-0444-0). [S2CID](./S2CID_(identifier)) [11070572](https://api.semanticscholar.org/CorpusID:11070572). Archived from [the original](http://perception.csl.illinois.edu/coding/papers/MobahiH2011-IJCV.pdf) (PDF) on 8 August 2017. Retrieved 8 May 2011.
34. [↑](./Image_segmentation#cite_ref-34) Shankar Rao, Hossein Mobahi, Allen Yang, Shankar Sastry and Yi Ma [Natural Image Segmentation with Adaptive Texture and Boundary Encoding](http://perception.csl.illinois.edu/coding/papers/RaoS2009-ACCV.pdf) [Archived](https://web.archive.org/web/20160519101956/http://perception.csl.illinois.edu/coding/papers/RaoS2009-ACCV.pdf) 19 May 2016 at the [Wayback Machine](./Wayback_Machine), Proceedings of the Asian Conference on Computer Vision (ACCV) 2009, H. Zha, R.-i. Taniguchi, and S. Maybank (Eds.), Part I, LNCS 5994, pp. 135–146, Springer.
35. [↑](./Image_segmentation#cite_ref-35) Ohlander, Ron; Price, Keith; Reddy, D. Raj (1978). "Picture Segmentation Using a Recursive Region Splitting Method". *Computer Graphics and Image Processing*. **8** (3): 313–333. [Bibcode](./Bibcode_(identifier)):[1978CGIP....8..313O](https://ui.adsabs.harvard.edu/abs/1978CGIP....8..313O). [doi](./Doi_(identifier)):[10.1016/0146-664X(78)90060-6](https://doi.org/10.1016%2F0146-664X%2878%2990060-6).
36. [↑](./Image_segmentation#cite_ref-36) [R. Kimmel and A.M. Bruckstein.](./R._Kimmel_and_A.M._Bruckstein.?action=edit&redlink=1) [https://www.cs.technion.ac.il/~ron/PAPERS/Paragios_chapter2003.pdf](https://www.cs.technion.ac.il/~ron/PAPERS/Paragios_chapter2003.pdf), *International Journal of Computer Vision* 2003; 53(3):225–243.
37. [↑](./Image_segmentation#cite_ref-37) [R. Kimmel](./R._Kimmel?action=edit&redlink=1), [https://www.cs.technion.ac.il/~ron/PAPERS/laplacian_ijcv2003.pdf](https://www.cs.technion.ac.il/~ron/PAPERS/laplacian_ijcv2003.pdf), chapter in Geometric Level Set Methods in Imaging, Vision and Graphics, (S. Osher, N. Paragios, Eds.), Springer Verlag, 2003. [ISBN](./ISBN_(identifier)) [0387954880](./Special:BookSources/0387954880)
38. [↑](./Image_segmentation#cite_ref-38) Barghout, Lauren. [Visual Taxometric approach Image Segmentation using Fuzzy-Spatial Taxon Cut Yields Contextually Relevant Regions](http://www.lirmm.fr/~lafourcade/pub/IPMU2014/papers/0443/04430163.pdf). Communications in Computer and Information Science (CCIS).  Springer-Verlag. 2014
39. [↑](./Image_segmentation#cite_ref-39) Witold Pedrycz (Editor), Andrzej Skowron (Co-Editor), Vladik Kreinovich (Co-Editor). Handbook of Granular Computing. Wiley 2008
40. [↑](./Image_segmentation#cite_ref-40) Barghout, Lauren (2014). Vision. Global Conceptual Context Changes Local Contrast Processing (Ph.D. Dissertation 2003). Updated to include Computer Vision Techniques. Scholars' Press. [ISBN](./ISBN_(identifier)) [978-3-639-70962-9](./Special:BookSources/978-3-639-70962-9).
41. [↑](./Image_segmentation#cite_ref-41) Barghout, Lauren, and Lawrence Lee. "Perceptual information processing system."  Google Patents
42. [↑](./Image_segmentation#cite_ref-42) Lindeberg, T.; Li, M.-X. (1997). ["Segmentation and classification of edges using minimum description length approximation and complementary junction cues"](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A473385&dswid=-8029). *Computer Vision and Image Understanding*. **67** (1): 88–98. [doi](./Doi_(identifier)):[10.1006/cviu.1996.0510](https://doi.org/10.1006%2Fcviu.1996.0510).
43. [1](./Image_segmentation#cite_ref-Digital_Image_Processing_2007_43-0) [2](./Image_segmentation#cite_ref-Digital_Image_Processing_2007_43-1) Digital Image Processing (2007, Pearson) by Rafael C. Gonzalez, Richard E. Woods
44. [↑](./Image_segmentation#cite_ref-44) [](http://gth.krammerbuch.at/sites/default/files/articles/AHAH%20callback/01_Guberman_KORR.pdf) [Archived](https://web.archive.org/web/20171013224758/http://gth.krammerbuch.at/sites/default/files/articles/AHAH%20callback/01_Guberman_KORR.pdf) 13 October 2017 at the [Wayback Machine](./Wayback_Machine)[Shelia Guberman](./Guberman_Shelia_(Shelija)), Vadim V. Maximov, Alex Pashintsev Gestalt and Image Understanding. GESTALT THEORY 2012, Vol. 34, No.2, 143–166.
45. [↑](./Image_segmentation#cite_ref-SRM_45-0) R. Nock and F. Nielsen, [Statistical Region Merging](http://www.academia.edu/download/3433683/Statistical_Region_Merging.pdf)[*[dead link](./Wikipedia:Link_rot)*], IEEE Transactions on Pattern Analysis and Machine Intelligence, Vol 26, No 11, pp 1452–1458, 2004.
46. [↑](./Image_segmentation#cite_ref-lambda-connectedness_46-0) L. Chen, H. D. Cheng, and J. Zhang, [Fuzzy subfiber and its application to seismic lithology classification](https://www.sciencedirect.com/science/article/pii/1069011594900094), Information Sciences: Applications, Vol 1, No 2, pp 77–95, 1994.
47. [↑](./Image_segmentation#cite_ref-split-and-merge1_47-0) S.L. Horowitz and T. Pavlidis, Picture Segmentation by a Directed Split and Merge Procedure, Proc. ICPR, 1974, Denmark, pp. 424–433.
48. [↑](./Image_segmentation#cite_ref-split-and-merge2_48-0) S.L. Horowitz and T. Pavlidis, Picture Segmentation by a Tree Traversal Algorithm, Journal of the ACM, 23 (1976), pp. 368–388.
49. [↑](./Image_segmentation#cite_ref-split-and-merge3_49-0) L. Chen, [The lambda-connected segmentation and the optimal algorithm for split-and-merge segmentation](http://www.spclab.com/research/lambda/lambdaConn91.pdf) [Archived](https://web.archive.org/web/20160310054934/http://www.spclab.com/research/lambda/lambdaConn91.pdf) 10 March 2016 at the [Wayback Machine](./Wayback_Machine), Chinese J. Computers, 14(1991), pp 321–331
50. [↑](./Image_segmentation#cite_ref-50) Caselles, V.; Kimmel, R.; Sapiro, G. (1997). ["Geodesic active contours"](https://www.cs.technion.ac.il/~ron/PAPERS/CasKimSap_IJCV1997.pdf) (PDF). *International Journal of Computer Vision*. **22** (1): 61–79. [doi](./Doi_(identifier)):[10.1023/A:1007979827043](https://doi.org/10.1023%2FA%3A1007979827043). [S2CID](./S2CID_(identifier)) [406088](https://api.semanticscholar.org/CorpusID:406088).
51. [↑](./Image_segmentation#cite_ref-51) Dervieux, A. and Thomasset, F. 1979. A finite element method for the simulation of Raleigh-Taylor instability. Springer Lect. Notes in Math., 771:145–158.
52. [↑](./Image_segmentation#cite_ref-52) Dervieux, A. and Thomasset, F. 1981. [Multifluid incompressible flows by a finite element method](https://www.researchgate.net/profile/Alain_Dervieux/publication/226529379_Multifluid_Incompressible_Flows_by_a_Finite_Element_Method/links/57176a3e08ae2679a8c766ac.pdf). Lecture Notes in Physics, 11:158–163.
53. [↑](./Image_segmentation#cite_ref-OsherSethian1988_53-0) Osher, Stanley; Sethian, James A (1988). "Fronts propagating with curvature-dependent speed: Algorithms based on Hamilton-Jacobi formulations". *Journal of Computational Physics*. **79** (1): 12–49. [Bibcode](./Bibcode_(identifier)):[1988JCoPh..79...12O](https://ui.adsabs.harvard.edu/abs/1988JCoPh..79...12O). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.46.1266](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.46.1266). [doi](./Doi_(identifier)):[10.1016/0021-9991(88)90002-2](https://doi.org/10.1016%2F0021-9991%2888%2990002-2). [ISSN](./ISSN_(identifier)) [0021-9991](https://search.worldcat.org/issn/0021-9991).
54. [↑](./Image_segmentation#cite_ref-54) S. Osher and N. Paragios.
[Geometric Level Set Methods in Imaging Vision and Graphics](http://www.mas.ecp.fr/vision/Personnel/nikos/osher-paragios/), Springer Verlag, [ISBN](./ISBN_(identifier)) [0-387-95488-0](./Special:BookSources/0-387-95488-0), 2003.
55. [↑](./Image_segmentation#cite_ref-55) James A. Sethian. ["Segmentation in Medical Imaging"](http://math.berkeley.edu/~sethian/2006/Applications/Medical_Imaging/artery.html). Retrieved 15 January 2012.
56. [↑](./Image_segmentation#cite_ref-56) Forcadel, Nicolas; Le Guyader, Carole; Gout, Christian (July 2008), "Generalized fast marching method: applications to image segmentation", *Numerical Algorithms*, **48** (1–3): 189–211, [doi](./Doi_(identifier)):[10.1007/s11075-008-9183-x](https://doi.org/10.1007%2Fs11075-008-9183-x), [S2CID](./S2CID_(identifier)) [7467344](https://api.semanticscholar.org/CorpusID:7467344)
57. [↑](./Image_segmentation#cite_ref-57) Chan, T.F.; [Vese, L.](./Luminița_Vese) (2001). "Active contours without edges". *IEEE Transactions on Image Processing*. **10** (2): 266–277. [Bibcode](./Bibcode_(identifier)):[2001ITIP...10..266C](https://ui.adsabs.harvard.edu/abs/2001ITIP...10..266C). [doi](./Doi_(identifier)):[10.1109/83.902291](https://doi.org/10.1109%2F83.902291). [PMID](./PMID_(identifier)) [18249617](https://pubmed.ncbi.nlm.nih.gov/18249617). [S2CID](./S2CID_(identifier)) [7602622](https://api.semanticscholar.org/CorpusID:7602622).
58. [↑](./Image_segmentation#cite_ref-58) [David Mumford](./David_Mumford) and Jayant Shah (1989): [Optimal approximations by piecewise smooth functions and associated variational problems](https://dash.harvard.edu/bitstream/handle/1/3637121/Mumford_OptimalApproxPiece.pdf?sequence=1), *Communications on Pure and Applied Mathematics*, pp 577–685, Vol. 42, No. 5
59. [↑](./Image_segmentation#cite_ref-59) Jianbo Shi and [Jitendra Malik](./Jitendra_Malik) (2000): ["Normalized Cuts and Image Segmentation"](https://www.cs.cmu.edu/~jshi/papers/pami_ncut.pdf), *IEEE Transactions on Pattern Analysis and Machine Intelligence*, pp 888–905, Vol. 22, No. 8
60. [↑](./Image_segmentation#cite_ref-60) Leo Grady (2006): ["Random Walks for Image Segmentation"](http://vision.cse.psu.edu/people/chenpingY/paper/grady2006random.pdf), *IEEE Transactions on Pattern Analysis and Machine Intelligence*, pp. 1768–1783, Vol. 28, No. 11
61. [↑](./Image_segmentation#cite_ref-61) Z. Wu and R. Leahy (1993): ["An optimal graph theoretic approach to data clustering: Theory and its application to image segmentation"](ftp://sipi.usc.edu/pub/leahy/pdfs/MAP93.pdf)[*[dead link](./Wikipedia:Link_rot)*], *IEEE Transactions on Pattern Analysis and Machine Intelligence*, pp. 1101–1113, Vol. 15, No. 11
62. [↑](./Image_segmentation#cite_ref-62) Leo Grady and Eric L. Schwartz (2006): ["Isoperimetric Graph Partitioning for Image Segmentation"](http://www.cns.bu.edu/~lgrady/grady2006isoperimetric.pdf) [Archived](https://web.archive.org/web/20110719090404/http://www.cns.bu.edu/~lgrady/grady2006isoperimetric.pdf) 19 July 2011 at the [Wayback Machine](./Wayback_Machine), *IEEE Transactions on Pattern Analysis and Machine Intelligence*, pp. 469–475, Vol. 28, No. 3
63. [↑](./Image_segmentation#cite_ref-63) C. T. Zahn (1971): ["Graph-theoretical methods for detecting and describing gestalt clusters"](http://web.cse.msu.edu/~cse802/Papers/zahn.pdf), *IEEE Transactions on Computers*, pp. 68–86, Vol. 20, No. 1
64. [↑](./Image_segmentation#cite_ref-64) S. Geman and D. Geman (1984): "Stochastic relaxation, Gibbs Distributions and Bayesian Restoration of Images", IEEE Transactions on Pattern Analysis and Machine Intelligence, pp. 721–741, Vol. 6, No. 6.
65. [↑](./Image_segmentation#cite_ref-65) A. Bouman and M. Shapiro (2002): "A multiscale Random field model for Bayesian image segmentation", IEEE Transactions on Image Processing, pp. 162–177, Vol. 3.
66. [↑](./Image_segmentation#cite_ref-66) J. Liu and Y. H. Yang (1994): "[Multiresolution color image segmentation](https://ieeexplore.ieee.org/abstract/document/297949/)", IEEE Transactions on Pattern Analysis and Machine Intelligence, pp. 689–700, Vol. 16.
67. [↑](./Image_segmentation#cite_ref-67) S. Vicente, V. Kolmogorov and C. Rother (2008): "[Graph cut based image segmentation with connectivity priors](http://www0.cs.ucl.ac.uk/staff/s.vicente/papers/connectedGC-CVPR08-TR.pdf)", CVPR
68. [↑](./Image_segmentation#cite_ref-68) Corso, Z. Tu, and A. Yuille (2008): "MRF Labelling with Graph-Shifts Algorithm", Proceedings of International workshop on combinatorial Image Analysis
69. [↑](./Image_segmentation#cite_ref-69) B. J. Frey and D. MacKayan (1997): "[A Revolution: Belief propagation in Graphs with Cycles](http://papers.nips.cc/paper/1467-a-revolution-belief-propagation-in-graphs-with-cycles.pdf)", Proceedings of Neural Information Processing Systems (NIPS)
70. [↑](./Image_segmentation#cite_ref-StaibDuncan1992_70-0) Staib, L.H.; Duncan, J.S. (1992). "Boundary finding with parametrically deformable models". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **14** (11): 1061–1075. [Bibcode](./Bibcode_(identifier)):[1992ITPAM..14.1061S](https://ui.adsabs.harvard.edu/abs/1992ITPAM..14.1061S). [doi](./Doi_(identifier)):[10.1109/34.166621](https://doi.org/10.1109%2F34.166621). [ISSN](./ISSN_(identifier)) [0162-8828](https://search.worldcat.org/issn/0162-8828).
71. [↑](./Image_segmentation#cite_ref-71) Witkin, A. P. "Scale-space filtering", Proc. 8th Int. Joint Conf. Art. Intell., Karlsruhe, Germany,1019–1022, 1983.
72. [↑](./Image_segmentation#cite_ref-72) A. Witkin, "[Scale-space filtering: A new approach to multi-scale description](https://ieeexplore.ieee.org/abstract/document/1172729/)," in Proc. IEEE Int. Conf. Acoust., Speech, Signal Processing ([ICASSP](./ICASSP)), vol. 9, San Diego, CA, March 1984, pp. 150–153.
73. [↑](./Image_segmentation#cite_ref-73) Koenderink, Jan "The structure of images", Biological Cybernetics, 50:363–370, 1984
74. [↑](./Image_segmentation#cite_ref-74) [Lifshitz, L. and Pizer, S.: A multiresolution hierarchical approach to image segmentation based on intensity extrema, IEEE Transactions on Pattern Analysis and Machine Intelligence, 12:6, 529–540, 1990.](http://portal.acm.org/citation.cfm?id=80964&dl=GUIDE&coll=GUIDE)
75. [↑](./Image_segmentation#cite_ref-75) [Lindeberg, T.: Detecting salient blob-like image structures and their scales with a scale-space primal sketch: A method for focus-of-attention, International Journal of Computer Vision, 11(3), 283–318, 1993.](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A472969&dswid=2693)
76. [↑](./Image_segmentation#cite_ref-lin94_76-0) [Lindeberg, Tony, Scale-Space Theory in Computer Vision, Kluwer Academic Publishers, 1994](http://www.csc.kth.se/~tony/book.html), [ISBN](./ISBN_(identifier)) [0-7923-9418-6](./Special:BookSources/0-7923-9418-6)
77. [↑](./Image_segmentation#cite_ref-77) [Gauch, J. and Pizer, S.: Multiresolution analysis of ridges and valleys in grey-scale images, IEEE Transactions on Pattern Analysis and Machine Intelligence, 15:6  (June 1993), pages: 635–646, 1993.](http://portal.acm.org/citation.cfm?coll=GUIDE&dl=GUIDE&id=628490)
78. [↑](./Image_segmentation#cite_ref-78) Olsen,  O. and Nielsen, M.: [Multi-scale gradient magnitude watershed segmentation](https://link.springer.com/content/pdf/10.1007/3-540-63507-6_178.pdf), Proc. of ICIAP 97, Florence, Italy, Lecture Notes in Computer Science, pages 6–13. Springer Verlag, September 1997.
79. [↑](./Image_segmentation#cite_ref-79) Dam, E., Johansen, P., Olsen, O. Thomsen,, A. Darvann, T., Dobrzenieck, A., Hermann, N., Kitai, N., Kreiborg, S., Larsen, P., Nielsen, M.: "Interactive multi-scale segmentation in clinical use" in European Congress of Radiology 2000.
80. [↑](./Image_segmentation#cite_ref-80) Vincken, K.L.; Koster, A.S.E.; Viergever, M.A. (1997). "Probabilistic multiscale image segmentation". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **19** (2): 109–120. [Bibcode](./Bibcode_(identifier)):[1997ITPAM..19..109V](https://ui.adsabs.harvard.edu/abs/1997ITPAM..19..109V). [doi](./Doi_(identifier)):[10.1109/34.574787](https://doi.org/10.1109%2F34.574787).
81. [↑](./Image_segmentation#cite_ref-81) [M. Tabb and N. Ahuja, Unsupervised multiscale image segmentation by integrated edge and region detection, IEEE Transactions on Image Processing, Vol. 6, No. 5, 642–655, 1997.](http://vision.ai.uiuc.edu/~msingh/segmen/seg/MSS.html) [Archived](https://web.archive.org/web/20110720084911/http://vision.ai.uiuc.edu/~msingh/segmen/seg/MSS.html) 20 July 2011 at the [Wayback Machine](./Wayback_Machine)
82. [↑](./Image_segmentation#cite_ref-82) Akbas, Emre; Ahuja, Narendra (2010). ["From Ramp Discontinuities to Segmentation Tree"](https://doi.org/10.1007%2F978-3-642-12307-8_12). *Computer Vision – ACCV 2009*. Lecture Notes in Computer Science. Vol. 5994. pp. 123–134. [doi](./Doi_(identifier)):[10.1007/978-3-642-12307-8_12](https://doi.org/10.1007%2F978-3-642-12307-8_12). [ISBN](./ISBN_(identifier)) [978-3-642-12306-1](./Special:BookSources/978-3-642-12306-1).
83. [↑](./Image_segmentation#cite_ref-83) [C. Undeman and T. Lindeberg (2003) "Fully Automatic Segmentation of MRI Brain Images using Probabilistic Anisotropic Diffusion and Multi-Scale Watersheds", Proc. Scale-Space'03, Isle of Skye, Scotland, Springer Lecture Notes in Computer Science, volume 2695, pages 641–656.](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A451266&dswid=-4540)
84. [↑](./Image_segmentation#cite_ref-84) Florack, L. and Kuijper, A.: The topological structure of scale-space images, Journal of Mathematical Imaging and Vision, 12:1, 65–79, 2000.
85. [↑](./Image_segmentation#cite_ref-85) Bijaoui, A.; Rué, F. (1995). "A Multiscale Vision Model". *Signal Processing*. **46** (3): 345. [doi](./Doi_(identifier)):[10.1016/0165-1684(95)00093-4](https://doi.org/10.1016%2F0165-1684%2895%2900093-4).
86. [↑](./Image_segmentation#cite_ref-86) Barghout, Lauren.  Visual Taxometric Approach to Image Segmentation using Fuzzy-Spatial Taxon Cut Yields Contextually Relevant Regions.  IPMU 2014, Part II.  A. Laurent et al (Eds.) CCIS 443, pp 163–173. Springer International Publishing Switzerland
87. [↑](./Image_segmentation#cite_ref-87) Barghout, Lauren (2014). [*Vision: How Global Perceptual Context Changes Local Contrast Processing (Ph.D. Dissertation 2003). Updated to include Computer Vision Techniques*](https://www.morebooks.de/store/gb/book/vision/isbn/978-3-639-70962-9). Scholars Press. [ISBN](./ISBN_(identifier)) [978-3-639-70962-9](./Special:BookSources/978-3-639-70962-9).
88. [↑](./Image_segmentation#cite_ref-Transactions_on_Engineering,_Computing_and_Technology_88-0) [Mahinda Pathegama](./Mahinda_Pathegama?action=edit&redlink=1) & Ö Göl (2004): "Edge-end pixel extraction for edge-based image segmentation", *Transactions on Engineering, Computing and Technology,* vol. 2, pp 213–216, ISSN 1305-5313
89. [↑](./Image_segmentation#cite_ref-89) Johnson, John L. (September 1994). "Pulse-coupled neural nets: translation, rotation, scale, distortion, and intensity signal invariance for images". *Applied Optics*. **33** (26). OSA: 6239–6253. [Bibcode](./Bibcode_(identifier)):[1994ApOpt..33.6239J](https://ui.adsabs.harvard.edu/abs/1994ApOpt..33.6239J). [doi](./Doi_(identifier)):[10.1364/AO.33.006239](https://doi.org/10.1364%2FAO.33.006239). [PMID](./PMID_(identifier)) [20936043](https://pubmed.ncbi.nlm.nih.gov/20936043).
90. [↑](./Image_segmentation#cite_ref-90) Long, Jonathan; Shelhamer, Evan; Darrell, Trevor (2015). [*Fully Convolutional Networks for Semantic Segmentation*](https://openaccess.thecvf.com/content_cvpr_2015/html/Long_Fully_Convolutional_Networks_2015_CVPR_paper.html). Proceedings of the IEEE conference on computer vision and pattern recognition. pp. 3431–3440.
91. [↑](./Image_segmentation#cite_ref-91) Ronneberger, Olaf; Fischer, Philipp; Brox, Thomas (2015). "U-Net: Convolutional Networks for Biomedical Image Segmentation". [arXiv](./ArXiv_(identifier)):[1505.04597](https://arxiv.org/abs/1505.04597) [[cs.CV](https://arxiv.org/archive/cs.CV)].
92. [↑](./Image_segmentation#cite_ref-Vicente_Rother_Kolmogorov_2011_p._92-0) Vicente, Sara; Rother, Carsten; Kolmogorov, Vladimir (2011). "Object cosegmentation". *CVPR 2011*. IEEE. pp. 2217–2224. [doi](./Doi_(identifier)):[10.1109/cvpr.2011.5995530](https://doi.org/10.1109%2Fcvpr.2011.5995530). [ISBN](./ISBN_(identifier)) [978-1-4577-0394-2](./Special:BookSources/978-1-4577-0394-2).
93. [↑](./Image_segmentation#cite_ref-93) Saygin, ZM, Osher, DE, Augustinack, J, Fischl, B, and Gabrieli, JDE.: [Connectivity-based segmentation of human amygdala nuclei using probabilistic tractography.](https://doi.org/10.1016%2Fj.neuroimage.2011.03.006), Neuroimage, 56:3, pp. 1353–61, 2011.
94. [↑](./Image_segmentation#cite_ref-94) Menke, RA, Jbabdi, S, Miller, KL, Matthews, PM and Zarei, M.: [Connectivity-based segmentation of the substantia nigra in human and its implications in Parkinson's disease](https://doi.org/10.1016%2Fj.neuroimage.2010.05.086),  Neuroimage, 52:4, pp. 1175–80, 2010.]

 

## References

  
- [3D Entropy Based Image Segmentation](https://web.archive.org/web/20080314011622/http://instrumentation.hit.bg/Papers/2008-02-02%203D%20Multistage%20Entropy.htm)
- Frucci, Maria; Sanniti di Baja, Gabriella (2008). "From Segmentation to Binarization of Gray-level Images". *[Journal of Pattern Recognition Research](./Journal_of_Pattern_Recognition_Research?action=edit&redlink=1)*. **3** (1): 1–13. [doi](./Doi_(identifier)):[10.13176/11.54](https://doi.org/10.13176%2F11.54).

  

## External links

 
- [Some sample code that performs basic segmentation](https://web.archive.org/web/20100518124644/http://csc.fsksm.utm.my/syed/projects/image-processing.html), by Syed Zainudeen. University Technology of Malaysia.
- [Generalized Fast Marching method](https://rd.springer.com/article/10.1007/s11075-008-9183-x) by Forcadel et al. [2008] for applications in image segmentation.
- [Image Processing Research Group](https://web.archive.org/web/20201228051352/http://www.iprg.co.in/) An Online Open Image Processing Research Community.
- [Segmentation methods in image processing and analysis](https://www.mathworks.com/discovery/image-segmentation.html) and [Minimizing energy to segment images](https://blogs.mathworks.com/pick/2017/12/07/minimizing-energy-to-segment-images-or-cluster-data/) by Mathworks
- [More image segmentation methods with detailed algorithms](http://disp.ee.ntu.edu.tw/meeting/%E6%98%B1%E7%BF%94/Segmentation%20tutorial.pdf) [Archived](https://web.archive.org/web/20191101050028/http://disp.ee.ntu.edu.tw/meeting/%E6%98%B1%E7%BF%94/Segmentation%20tutorial.pdf) 1 November 2019 at the [Wayback Machine](./Wayback_Machine) by Yu-Hsiang Wang (王昱翔), National Taiwan University, Taipei, Taiwan, ROC
- [Online demonstration of piecewise linear image segmentation](https://ipolcore.ipol.im/demo/clientApp/demo.html?id=295) by IPOL Journal