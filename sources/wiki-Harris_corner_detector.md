---
source: https://en.wikipedia.org/wiki/Harris_corner_detector
fetched: 2026-06-21
---

Computer vision algorithm 

The **Harris corner detector** is a [corner detection](./Corner_detection) operator that is commonly used in [computer vision](./Computer_vision) algorithms to extract corners and infer [features](./Feature_(computer_vision)) of an image. It was first introduced by Chris Harris and Mike Stephens in 1988 upon the improvement of [Moravec's corner detector](./Corner_detection#Moravec_corner_detection_algorithm).[[1]](./Harris_corner_detector#cite_note-harris-1) Compared to its predecessor, Harris' corner detector takes the differential of the corner score into account with reference to direction directly, instead of using shifting patches for every 45 degree angles, and has been proved to be more accurate in distinguishing between edges and corners.[[2]](./Harris_corner_detector#cite_note-dey-2) Since then, it has been improved and adopted in many algorithms to preprocess images for subsequent applications.

 

## Introduction

 

A corner is a point whose local neighborhood stands in two dominant and different edge directions.  In other words, a corner can be interpreted as the junction of two edges, where an edge is a sudden change in image brightness.[[3]](./Harris_corner_detector#cite_note-derpanis-3) Corners are the important features in the image, and they are generally termed as interest points which are invariant to translation, rotation and illumination. Although corners are only a small percentage of the image, they contain the most important features in restoring image information, and they can be used to minimize the amount of processed data for motion tracking, [image stitching](./Image_stitching), building 2D mosaics, [stereo vision](./Computer_stereo_vision), image representation and other related computer vision areas.

 

In order to capture the corners from the image, researchers have proposed many different corner detectors including the [Kanade-Lucas-Tomasi](./Kanade–Lucas–Tomasi_feature_tracker) (KLT) operator and the Harris operator which are most simple, efficient and reliable for use in corner detection. These two popular methodologies are both closely associated with and based on the local structure matrix. Compared to the Kanade-Lucas-Tomasi corner detector, the Harris corner detector provides good repeatability under changing illumination and rotation, and therefore, it is more often used in stereo matching and image database retrieval. Although there still exist drawbacks and limitations, the Harris corner detector is still an important and fundamental technique for many computer vision applications.

 

## Development of Harris corner detection algorithm

 

Source:[[1]](./Harris_corner_detector#cite_note-harris-1)

 

[Without loss of generality](./Without_loss_of_generality), we will assume a [grayscale](./Grayscale) 2-dimensional image is used. Let this image be given by     I   {\displaystyle I}  ![{\displaystyle I}](https://wikimedia.org/api/rest_v1/media/math/render/svg/535ea7fc4134a31cbe2251d9d3511374bc41be9f). Consider taking an image patch     ( x , y ) ∈ ∈  W   {\displaystyle (x,y)\in W}  ![{\displaystyle (x,y)\in W}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fad569e3058430c0c7d4cead6204ab70ac6b6d96)(window) and shifting it by     ( Δ Δ  x , Δ Δ  y )   {\displaystyle (\Delta x,\Delta y)}  ![{\displaystyle (\Delta x,\Delta y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/372af6c5d428b18941bf7c7aecda3bbb06ab5396). The *sum of squared differences* (SSD) between these two patches, denoted     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61), is given by:

     f ( Δ Δ  x , Δ Δ  y ) =   ∑ ∑   (  x  k   ,  y  k   ) ∈ ∈  W      (  I (  x  k   ,  y  k   ) − −  I (  x  k   + Δ Δ  x ,  y  k   + Δ Δ  y )  )   2     {\displaystyle f(\Delta x,\Delta y)={\underset {(x_{k},y_{k})\in W}{\sum }}\left(I(x_{k},y_{k})-I(x_{k}+\Delta x,y_{k}+\Delta y)\right)^{2}}  ![{\displaystyle f(\Delta x,\Delta y)={\underset {(x_{k},y_{k})\in W}{\sum }}\left(I(x_{k},y_{k})-I(x_{k}+\Delta x,y_{k}+\Delta y)\right)^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/94b3fd497ecd5170c4f1c92714a6eca52ea7ddfc) 

    I ( x + Δ Δ  x , y + Δ Δ  y )   {\displaystyle I(x+\Delta x,y+\Delta y)}  ![{\displaystyle I(x+\Delta x,y+\Delta y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bcf139e6b461ae7862cda8f2da3ffd8a2f929a13) can be approximated by a [Taylor expansion](./Taylor_series).  Let      I  x     {\displaystyle I_{x}}  ![{\displaystyle I_{x}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eed0dfcd8b1ce6eb2e6b7fbc426b895507d53004) and      I  y     {\displaystyle I_{y}}  ![{\displaystyle I_{y}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6f3eedd0871fd35e1fd8992c53812cd60d1b07c2) be the partial [derivatives](./Image_derivative) of     I   {\displaystyle I}  ![{\displaystyle I}](https://wikimedia.org/api/rest_v1/media/math/render/svg/535ea7fc4134a31cbe2251d9d3511374bc41be9f), such that

     I ( x + Δ Δ  x , y + Δ Δ  y ) ≈ ≈  I ( x , y ) +  I  x   ( x , y ) Δ Δ  x +  I  y   ( x , y ) Δ Δ  y   {\displaystyle I(x+\Delta x,y+\Delta y)\approx I(x,y)+I_{x}(x,y)\Delta x+I_{y}(x,y)\Delta y}  ![{\displaystyle I(x+\Delta x,y+\Delta y)\approx I(x,y)+I_{x}(x,y)\Delta x+I_{y}(x,y)\Delta y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4541aeb40a80caf4ebf805d11c1d7efc1fffd7d4) 

This produces the approximation

     f ( Δ Δ  x , Δ Δ  y ) ≈ ≈    ∑ ∑   ( x , y ) ∈ ∈  W      (   I  x   ( x , y ) Δ Δ  x +  I  y   ( x , y ) Δ Δ  y  )   2   ,   {\displaystyle f(\Delta x,\Delta y)\approx {\underset {(x,y)\in W}{\sum }}\left(I_{x}(x,y)\Delta x+I_{y}(x,y)\Delta y\right)^{2},}  ![{\displaystyle f(\Delta x,\Delta y)\approx {\underset {(x,y)\in W}{\sum }}\left(I_{x}(x,y)\Delta x+I_{y}(x,y)\Delta y\right)^{2},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6f4bb84a9f3e30eceec6f89b0ed8ba1990400570) 

which can be written in matrix form:

     f ( Δ Δ  x , Δ Δ  y ) ≈ ≈    (    Δ Δ  x   Δ Δ  y    )   M   (    Δ Δ  x     Δ Δ  y    )   ,   {\displaystyle f(\Delta x,\Delta y)\approx {\begin{pmatrix}\Delta x&\Delta y\end{pmatrix}}M{\begin{pmatrix}\Delta x\\\Delta y\end{pmatrix}},}  ![{\displaystyle f(\Delta x,\Delta y)\approx {\begin{pmatrix}\Delta x&\Delta y\end{pmatrix}}M{\begin{pmatrix}\Delta x\\\Delta y\end{pmatrix}},}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e884b4ad4ae58ecfcdfea77f9a5c2ca7c5420119) 

where *M* is the [structure tensor](./Structure_tensor),

     M =   ∑ ∑   ( x , y ) ∈ ∈  W      [     I  x   2      I  x    I  y        I  x    I  y      I  y   2      ]   =   [      ∑ ∑   ( x , y ) ∈ ∈  W     I  x   2       ∑ ∑   ( x , y ) ∈ ∈  W     I  x    I  y         ∑ ∑   ( x , y ) ∈ ∈  W     I  x    I  y       ∑ ∑   ( x , y ) ∈ ∈  W     I  y   2      ]     {\displaystyle M={\underset {(x,y)\in W}{\sum }}{\begin{bmatrix}I_{x}^{2}&I_{x}I_{y}\\I_{x}I_{y}&I_{y}^{2}\end{bmatrix}}={\begin{bmatrix}{\underset {(x,y)\in W}{\sum }}I_{x}^{2}&{\underset {(x,y)\in W}{\sum }}I_{x}I_{y}\\{\underset {(x,y)\in W}{\sum }}I_{x}I_{y}&{\underset {(x,y)\in W}{\sum }}I_{y}^{2}\end{bmatrix}}}  ![{\displaystyle M={\underset {(x,y)\in W}{\sum }}{\begin{bmatrix}I_{x}^{2}&I_{x}I_{y}\\I_{x}I_{y}&I_{y}^{2}\end{bmatrix}}={\begin{bmatrix}{\underset {(x,y)\in W}{\sum }}I_{x}^{2}&{\underset {(x,y)\in W}{\sum }}I_{x}I_{y}\\{\underset {(x,y)\in W}{\sum }}I_{x}I_{y}&{\underset {(x,y)\in W}{\sum }}I_{y}^{2}\end{bmatrix}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a617dda21e306dbfbdb7a186b1c203e3f3443867) 

## Process of Harris corner detection algorithm

 

Commonly, Harris corner detector algorithm can be divided into five steps. [[4]](./Harris_corner_detector#cite_note-4)[[5]](./Harris_corner_detector#cite_note-5)[[6]](./Harris_corner_detector#cite_note-sanchez-6)

 
1. Color to grayscale
2. Spatial derivative calculation
3. Structure tensor setup
4. Harris response calculation
5. Non-maximum suppression

 

### Color to grayscale

 

If we use Harris corner detector in a color image, the first step is to convert it into a grayscale image, which will enhance the processing speed.

 

The value of the gray scale [pixel](./Pixel) can be computed as a weighted sums of the values R, B and G of the color image, 

      ∑ ∑   C  ∈ ∈   { R , G , B }    w  C   ⋅ ⋅  C   {\displaystyle \sum _{C\,\in \,\{R,G,B\}}w_{C}\cdot C}  ![{\displaystyle \sum _{C\,\in \,\{R,G,B\}}w_{C}\cdot C}](https://wikimedia.org/api/rest_v1/media/math/render/svg/701cb53f7fa3e9b88ddd23baa8bdeef2f55ae597), 

where, e.g., 

      w  R   = 0.299 ,    w  G   = 0.587 ,    w  B   = 1 − −  (  w  R   +  w  G   ) = 0.114.   {\displaystyle w_{R}=0.299,\ w_{G}=0.587,\ w_{B}=1-(w_{R}+w_{G})=0.114.}  ![{\displaystyle w_{R}=0.299,\ w_{G}=0.587,\ w_{B}=1-(w_{R}+w_{G})=0.114.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3081c0bf12762f18efc074f8a8cc87f65f0a69fe) 

### Spatial derivative calculation

 

Next, we are going to find the derivative with respect to x and the derivative with respect to y,      I  x   ( x , y )   {\displaystyle I_{x}(x,y)}  ![{\displaystyle I_{x}(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/14e6d745a4ffed73e17220b14bb286ecf5b4a0ce) and      I  y   ( x , y )   {\displaystyle I_{y}(x,y)}  ![{\displaystyle I_{y}(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/39f7f9fd1ae104e18ca2603dfceb2e923d1d591d).
This can be approximated by applying [Sobel operators](./Sobel_operator).

 

### Structure tensor setup

 

With      I  x   ( x , y )   {\displaystyle I_{x}(x,y)}  ![{\displaystyle I_{x}(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/14e6d745a4ffed73e17220b14bb286ecf5b4a0ce) ,      I  y   ( x , y )   {\displaystyle I_{y}(x,y)}  ![{\displaystyle I_{y}(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/39f7f9fd1ae104e18ca2603dfceb2e923d1d591d), we can construct the structure tensor     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd).

 

### Harris response calculation

 

For     x ≪ ≪  y   {\displaystyle x\ll y}  ![{\displaystyle x\ll y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/aa24e30006077de6c6e962b966f9122dd996df6d), one has 
        x ⋅ ⋅  y   x + y     = x    1  1 + x  /  y     ≈ ≈  x .   {\displaystyle {\tfrac {x\cdot y}{x+y}}=x{\tfrac {1}{1+x/y}}\approx x.}  ![{\displaystyle {\tfrac {x\cdot y}{x+y}}=x{\tfrac {1}{1+x/y}}\approx x.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/88d628e4ec439a84f9f4d4da89368d325aef5f9f)
In this step, we compute the smallest [eigenvalue](./Eigenvalue) of the structure tensor using that approximation:

      λ λ   min   ≈ ≈      λ λ   1    λ λ   2     (  λ λ   1   +  λ λ   2   )    =    det ( M )   tr ⁡ ⁡  ( M )      {\displaystyle \lambda _{\min }\approx {\frac {\lambda _{1}\lambda _{2}}{(\lambda _{1}+\lambda _{2})}}={\frac {\det(M)}{\operatorname {tr} (M)}}}  ![{\displaystyle \lambda _{\min }\approx {\frac {\lambda _{1}\lambda _{2}}{(\lambda _{1}+\lambda _{2})}}={\frac {\det(M)}{\operatorname {tr} (M)}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7e3f4375663d389fe2f526b277b1529b7e7cdf2d) 

with the [trace](./Trace_of_a_matrix)      t r  ( M ) =  m  11   +  m  22     {\displaystyle \mathrm {tr} (M)=m_{11}+m_{22}}  ![{\displaystyle \mathrm {tr} (M)=m_{11}+m_{22}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f7c87da8bc8725ed86d6b25a88c9c33fbc8ac3bd). 

 

Another commonly used Harris response calculation is shown as below,

 

    R =  λ λ   1    λ λ   2   − −  k (  λ λ   1   +  λ λ   2    )  2   = det ( M ) − −  k tr ⁡ ⁡  ( M  )  2     {\displaystyle R=\lambda _{1}\lambda _{2}-k(\lambda _{1}+\lambda _{2})^{2}=\det(M)-k\operatorname {tr} (M)^{2}}  ![{\displaystyle R=\lambda _{1}\lambda _{2}-k(\lambda _{1}+\lambda _{2})^{2}=\det(M)-k\operatorname {tr} (M)^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/0d01c963a34e4c36da9e71676384c7fd14e0c14c)

 

where     k   {\displaystyle k}  ![{\displaystyle k}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3c9a2c7b599b37105512c5d570edc034056dd40) is an empirically determined constant;     k ∈ ∈  [ 0.04 , 0.06 ]   {\displaystyle k\in [0.04,0.06]}  ![{\displaystyle k\in [0.04,0.06]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/48479338fa85bef1a06885b8ec481b2f6b60a487) .

 

### Non-maximum suppression

 

In order to pick up the optimal values to indicate corners, we find the local maxima as corners within the window which is a 3 by 3 filter.

 

## Improvement

 

Sources:[[7]](./Harris_corner_detector#cite_note-7)[[8]](./Harris_corner_detector#cite_note-8)

 
1. [Harris-Laplace Corner Detector](./Harris–Laplace_detector)[[9]](./Harris_corner_detector#cite_note-9)
2. Differential Morphological Decomposition Based Corner Detector[[10]](./Harris_corner_detector#cite_note-10)
3. Multi-scale Bilateral Structure Tensor Based Corner Detector[[11]](./Harris_corner_detector#cite_note-11)

 

## Applications

 
1. Image Alignment, [Stitching](./Image_stitching) and [Registration](./Image_registration)[[12]](./Harris_corner_detector#cite_note-12)
2. 2D Mosaics Creation[[13]](./Harris_corner_detector#cite_note-13)
3. 3D Scene Modeling and [Reconstruction](./3D_reconstruction)[[14]](./Harris_corner_detector#cite_note-14)
4. [Motion Detection](./Moving_object_detection)[[15]](./Harris_corner_detector#cite_note-15)
5. [Object Recognition](./Object_Recognition)[[16]](./Harris_corner_detector#cite_note-16)
6. Image Indexing and [Content-based Retrieval](./Content-based_image_retrieval)[[17]](./Harris_corner_detector#cite_note-17)
7. [Video Tracking](./Video_Tracking)[[18]](./Harris_corner_detector#cite_note-18)

 

## See also

 
- [Structure tensor](./Structure_tensor)
- [Harris affine region detector](./Harris_affine_region_detector)
- [Corner detection](./Corner_detection)
- [Feature detection (computer vision)](./Feature_detection_(computer_vision))
- [Computer vision](./Computer_vision)
- [List of computer vision topics](./List_of_computer_vision_topics)

 

## References

  
1. [1](./Harris_corner_detector#cite_ref-harris_1-0) [2](./Harris_corner_detector#cite_ref-harris_1-1) Chris Harris and Mike Stephens (1988). "A Combined Corner and Edge Detector". *Alvey Vision Conference*. Vol. 15.
2. [↑](./Harris_corner_detector#cite_ref-dey_2-0) Dey, Nilanjan; et al. (2012). "A Comparative Study between Moravec and Harris Corner Detection of Noisy Images Using Adaptive Wavelet Thresholding Technique". [arXiv](./ArXiv_(identifier)):[1209.1558](https://arxiv.org/abs/1209.1558) [[cs.CV](https://arxiv.org/archive/cs.CV)].
3. [↑](./Harris_corner_detector#cite_ref-derpanis_3-0) Konstantinos G. Derpanis (2004). *The harris corner detector*. York University.
4. [↑](./Harris_corner_detector#cite_ref-4) ["Harris Operator Corner Detection using Sliding Window Method - Google Scholar"](https://scholar.google.com/scholar?q=++Harris+Operator+Corner+Detection+using+Sliding+Window+Method&btnG=&hl=en&as_sdt=0%252C36). *scholar.google.com*. Retrieved 2015-11-29.
5. [↑](./Harris_corner_detector#cite_ref-5) ["The Comparison and Application of Corner Detection Algorithms - Google Scholar"](https://scholar.google.com/scholar?hl=en&q=The+Comparison+and+Application+of+Corner+Detection+Algorithms&btnG=&as_sdt=1%252C36&as_sdtp=). *scholar.google.com*. Retrieved 2015-11-29.
6. [↑](./Harris_corner_detector#cite_ref-sanchez_6-0) Javier Sánchez, Nelson Monzón and Agustín Salgado (2018). ["An Analysis and Implementation of the Harris Corner Detector"](https://doi.org/10.5201%2Fipol.2018.229). *Image Processing on Line*. **8**: 305–328. [doi](./Doi_(identifier)):[10.5201/ipol.2018.229](https://doi.org/10.5201%2Fipol.2018.229). [hdl](./Hdl_(identifier)):[10553/43499](https://hdl.handle.net/10553%2F43499).
7. [↑](./Harris_corner_detector#cite_ref-7) Bellavia, F.; Tegolo, D.; Valenti, C. (2011-03-01). "Improving Harris corner selection strategy". *IET Computer Vision*. **5** (2): 87. [doi](./Doi_(identifier)):[10.1049/iet-cvi.2009.0127](https://doi.org/10.1049%2Fiet-cvi.2009.0127).
8. [↑](./Harris_corner_detector#cite_ref-8) Rosten, Edward; Drummond, Tom (2006-05-07). Leonardis, Aleš; Bischof, Horst; Pinz, Axel (eds.). *Machine Learning for High-Speed Corner Detection*. Lecture Notes in Computer Science. Springer Berlin Heidelberg. pp. 430–443. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.64.8513](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.64.8513). [doi](./Doi_(identifier)):[10.1007/11744023_34](https://doi.org/10.1007%2F11744023_34). [ISBN](./ISBN_(identifier)) [978-3-540-33832-1](./Special:BookSources/978-3-540-33832-1). [S2CID](./S2CID_(identifier)) [1388140](https://api.semanticscholar.org/CorpusID:1388140).
9. [↑](./Harris_corner_detector#cite_ref-9) ["A Comparison of Affine Region Detectors - Google Scholar"](https://scholar.google.com/scholar?q=+A+Comparison+of+Affine+Region+Detectors&btnG=&hl=en&as_sdt=0%252C36). *scholar.google.com*. Retrieved 2015-11-29.
10. [↑](./Harris_corner_detector#cite_ref-10) Gueguen, L.; Pesaresi, M. (2011). ["Multi scale Harris corner detector based on Differential Morphological Decomposition"](https://www.researchgate.net/publication/220644165). *Pattern Recognition Letters*. **32** (14): 1714–1719. [Bibcode](./Bibcode_(identifier)):[2011PaReL..32.1714G](https://ui.adsabs.harvard.edu/abs/2011PaReL..32.1714G). [doi](./Doi_(identifier)):[10.1016/j.patrec.2011.07.021](https://doi.org/10.1016%2Fj.patrec.2011.07.021).
11. [↑](./Harris_corner_detector#cite_ref-11) ["A Multi-scale Bilateral Structure Tensor Based Corner Detector - Google Scholar"](https://scholar.google.com/scholar?q=A+Multi-scale+Bilateral+Structure+Tensor+Based+Corner+Detector&btnG=&hl=en&as_sdt=0%252C36). *scholar.google.com*. Retrieved 2015-11-29.
12. [↑](./Harris_corner_detector#cite_ref-12) Kang, Juan; Xiao, Chuangbai; Deng, M.; Yu, Jing; Liu, Haifeng (2011-08-01). "Image registration based on harris corner and mutual information". *Proceedings of 2011 International Conference on Electronic & Mechanical Engineering and Information Technology*. Vol. 7. pp. 3434–3437. [doi](./Doi_(identifier)):[10.1109/EMEIT.2011.6023066](https://doi.org/10.1109%2FEMEIT.2011.6023066). [ISBN](./ISBN_(identifier)) [978-1-61284-087-1](./Special:BookSources/978-1-61284-087-1). [S2CID](./S2CID_(identifier)) [17367248](https://api.semanticscholar.org/CorpusID:17367248).
13. [↑](./Harris_corner_detector#cite_ref-13) ["Underwater Mosaic Creation using Video sequences from Different Altitudes - Google Scholar"](https://scholar.google.com/scholar?hl=en&q=Underwater+Mosaic+Creation+using+Video+sequences+from+Different+Altitudes&btnG=&as_sdt=1%252C23&as_sdtp=). *scholar.google.com*. Retrieved 2015-12-02.
14. [↑](./Harris_corner_detector#cite_ref-14) ["Automated reconstruction of 3D scenes from sequences of images - Google Scholar"](https://scholar.google.com/scholar?q=Automated+reconstruction+of+3D+scenes+from+sequences+of+images&btnG=&hl=en&as_sdt=0%252C23). *scholar.google.com*. Retrieved 2015-12-02.
15. [↑](./Harris_corner_detector#cite_ref-15) Liu, Meng; Wu, Chengdong; Zhang, Yunzhou (2008-07-01). "Multi-resolution optical flow tracking algorithm based on multi-scale Harris corner points feature". *2008 Chinese Control and Decision Conference*. pp. 5287–5291. [doi](./Doi_(identifier)):[10.1109/CCDC.2008.4598340](https://doi.org/10.1109%2FCCDC.2008.4598340). [ISBN](./ISBN_(identifier)) [978-1-4244-1733-9](./Special:BookSources/978-1-4244-1733-9). [S2CID](./S2CID_(identifier)) [8085227](https://api.semanticscholar.org/CorpusID:8085227).
16. [↑](./Harris_corner_detector#cite_ref-16) ["Object Recognition from Local Scale-Invariant Features - Google Scholar"](https://scholar.google.com/scholar?q=Object+Recognition+from+Local+Scale-Invariant+Features&btnG=&hl=en&as_sdt=0%252C36). *scholar.google.com*. Retrieved 2015-11-29.
17. [↑](./Harris_corner_detector#cite_ref-17) ["Salient Points for Content Based Retrieval - Google Scholar"](https://scholar.google.com/scholar?q=Salient+Points+for+Content+Based+Retrieval+&btnG=&hl=en&as_sdt=0%252C23). *scholar.google.com*. Retrieved 2015-12-02.
18. [↑](./Harris_corner_detector#cite_ref-18) ["Tracking and Recognition of Objects using SURF Descriptor and Harris Corner Detection - Google Scholar"](https://scholar.google.com/scholar?q=+Tracking+and+Recognition+of+Objects+using+SURF+Descriptor+and+Harris+Corner+Detection&btnG=&hl=en&as_sdt=0%252C23). *scholar.google.com*. Retrieved 2015-12-02.

 

## External links

 
- ["Learn OpenCV by Examples : Harris Corner Detection"](http://opencvexamples.blogspot.com/2013/10/harris-corner-detection.html)
- ["Harris Corner Detection - OpenCV Documentation"](http://docs.opencv.org/2.4/doc/tutorials/features2d/trackingmotion/harris_detector/harris_detector.html)
- ["Harris Corner Detection - OpenCV-Python Tutorials"](https://web.archive.org/web/20210507051910/https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_feature2d/py_features_harris/py_features_harris.html). Archived from [the original](http://opencv-python-tutroals.readthedocs.org/en/latest/py_tutorials/py_feature2d/py_features_harris/py_features_harris.html) on 2021-05-07.
- [Online Implementation of the Harris Corner Detector - IPOL](https://ipolcore.ipol.im/demo/clientApp/demo.html?id=229)