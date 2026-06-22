---
source: https://en.wikipedia.org/wiki/Image_pyramid
fetched: 2026-06-21
---

Type of multi-scale signal representation [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/43/Image_pyramid.svg/330px-Image_pyramid.svg.png)](./File:Image_pyramid.svg)Visual representation of an image pyramid with 5 levels 
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

 

**Pyramid**, or **pyramid representation**, is a type of [multi-scale](./Scale_model) [signal](./Signal_(information_theory)) [representation](./Knowledge_representation) developed by the [computer vision](./Computer_vision), [image processing](./Image_processing) and [signal processing](./Signal_processing) communities, in which a signal or an image is subject to repeated [smoothing](./Smoothing) and [subsampling](./Downsampling). Pyramid representation is a predecessor to [scale-space representation](./Scale_space) and [multiresolution analysis](./Multiresolution_analysis).

 

## Pyramid generation

 

There are two main types of pyramids: lowpass and bandpass.

 

A lowpass pyramid is made by smoothing the image with an appropriate smoothing filter and then subsampling the smoothed image, usually by a factor of 2 along each coordinate direction. The resulting image is then subjected to the same procedure, and the cycle is repeated multiple times. Each cycle of this process results in a smaller image with increased smoothing, but with decreased spatial sampling density (that is, decreased image resolution). If illustrated graphically, the entire multi-scale representation will look like a pyramid, with the original image on the bottom and each cycle's resulting smaller image stacked one atop the other.

 

A bandpass pyramid is made by forming the difference between images at adjacent levels in the pyramid and performing image interpolation between adjacent levels of resolution, to enable computation of pixelwise differences.[[1]](./Pyramid_(image_processing)#cite_note-1)

 

## Pyramid generation kernels

 

A variety of different smoothing [kernels](./Kernel_(image_processing)) have been proposed for generating pyramids.[[2]](./Pyramid_(image_processing)#cite_note-2)[[3]](./Pyramid_(image_processing)#cite_note-Crowley1981-3)[[4]](./Pyramid_(image_processing)#cite_note-4)[[5]](./Pyramid_(image_processing)#cite_note-5)[[6]](./Pyramid_(image_processing)#cite_note-6)[[7]](./Pyramid_(image_processing)#cite_note-7) Among the suggestions that have been given, the *binomial kernels* arising from the [binomial coefficients](./Binomial_coefficient) stand out as a particularly useful and theoretically well-founded class.[[3]](./Pyramid_(image_processing)#cite_note-Crowley1981-3)[[8]](./Pyramid_(image_processing)#cite_note-8)[[9]](./Pyramid_(image_processing)#cite_note-9)[[10]](./Pyramid_(image_processing)#cite_note-10)[[11]](./Pyramid_(image_processing)#cite_note-LinBre03-ScSp-11)[[12]](./Pyramid_(image_processing)#cite_note-12) Thus, given a two-dimensional image, we may apply the (normalized) binomial filter (1/4, 1/2, 1/4) typically twice or more along each spatial dimension and then subsample the image by a factor of two. This operation may then proceed as many times as desired, leading to a compact and efficient multi-scale representation. If motivated by specific requirements, intermediate scale levels may also be generated where the subsampling stage is sometimes left out, leading to an *oversampled* or *hybrid pyramid*.[[11]](./Pyramid_(image_processing)#cite_note-LinBre03-ScSp-11) With the increasing computational efficiency of [CPUs](./CPU) available today, it is in some situations also feasible to use wider supported [Gaussian filters](./Gaussian_filter) as smoothing kernels in the pyramid generation steps.

 

### Gaussian pyramid

 

In a Gaussian pyramid, subsequent images are weighted down using a Gaussian average ([Gaussian blur](./Gaussian_blur)) and scaled down. Each pixel containing a local average corresponds to a neighborhood pixel on a lower level of the pyramid. This technique is used especially in [texture synthesis](./Texture_synthesis).

 

### Laplacian pyramid

 

A Laplacian pyramid is very similar to a Gaussian pyramid but saves the difference image of the blurred versions between each levels. Only the smallest level is not a difference image to enable reconstruction of the high resolution image using the difference images on higher levels.  This technique can be used in [image compression](./Image_compression).[[13]](./Pyramid_(image_processing)#cite_note-13)

 

### Steerable pyramid

 

A steerable pyramid, developed by [Simoncelli](./Eero_Simoncelli) and others, is an implementation of a multi-scale, multi-orientation [band-pass filter](./Band-pass_filter) bank used for applications including [image compression](./Image_compression), [texture synthesis](./Texture_synthesis), and [object recognition](./Outline_of_object_recognition).  It can be thought of as an orientation selective version of a Laplacian pyramid, in which a bank of [steerable filters](./Steerable_filter) are used at each level of the pyramid instead of a single Laplacian or [Gaussian filter](./Gaussian_filter).[[14]](./Pyramid_(image_processing)#cite_note-14)[[15]](./Pyramid_(image_processing)#cite_note-15)[[16]](./Pyramid_(image_processing)#cite_note-16)

 

## Applications of pyramids

 

### Alternative representation

 

In the early days of computer vision, pyramids were used as the main type of multi-scale representation for computing multi-scale image [features](./Feature_detection_(computer_vision)) from real-world image data. More recent techniques include [scale-space representation](./Scale_space), which has been popular among some researchers due to its theoretical foundation, the ability to decouple the subsampling stage from the multi-scale representation, the more powerful tools for theoretical analysis as well as the ability to compute a representation at *any* desired scale, thus avoiding the algorithmic problems of relating image representations at different resolution. Nevertheless, pyramids are still frequently used for expressing computationally efficient approximations to [scale-space representation](./Scale_space).[[11]](./Pyramid_(image_processing)#cite_note-LinBre03-ScSp-11)[[17]](./Pyramid_(image_processing)#cite_note-17)[[18]](./Pyramid_(image_processing)#cite_note-18)

 

### Detail manipulation

 

Levels of a Laplacian pyramid can be added to or removed from the original image to amplify or reduce detail at different scales. However, detail manipulation of this form is known to produce halo artifacts in many cases, leading to the development of alternatives such as the [bilateral filter](./Bilateral_filter). 

 

Some [image compression](./Image_compression) file formats use the [Adam7 algorithm](./Adam7_algorithm) or some other [interlacing](./Interlacing_(bitmaps)) technique.
These can be seen as a kind of image pyramid.
Because those file format store the "large-scale" features first, and fine-grain details later in the file,
a particular viewer displaying a small "thumbnail" or on a small screen can quickly download just enough of the image to display it in the available pixels—so one file can support many viewer resolutions, rather than having to store or generate a different file for each resolution.

 

## See also

 
- [Mipmap](./Mipmap)
- [Scale space implementation](./Scale_space_implementation)
- [Level of detail](./Level_of_detail_(computer_graphics))
- [JPEG 2000#Multiple resolution representation](./JPEG_2000#Multiple_resolution_representation)

 

## References

  
1. [↑](./Pyramid_(image_processing)#cite_ref-1) 
E.H. Andelson and C.H. Anderson and J.R. Bergen and P.J. Burt and J.M. Ogden.
["Pyramid methods in image processing"](http://persci.mit.edu/pub_pdfs/RCA84.pdf).
1984.

2. [↑](./Pyramid_(image_processing)#cite_ref-2) Burt, P. J. (May 1981). "Fast filter transform for image processing". *Computer Graphics and Image Processing*. **16**: 20–51. [doi](./Doi_(identifier)):[10.1016/0146-664X(81)90092-7](https://doi.org/10.1016%2F0146-664X%2881%2990092-7).
3. [1](./Pyramid_(image_processing)#cite_ref-Crowley1981_3-0) [2](./Pyramid_(image_processing)#cite_ref-Crowley1981_3-1) Crowley, James L. (November 1981). ["A representation for visual information"](http://www.ri.cmu.edu/publication_view.html?pub_id=37). *Interim Report Carnegie-Mellon Univ*. Carnegie-Mellon University, Robotics Institute. [Bibcode](./Bibcode_(identifier)):[1981cmu..reptR....C](https://ui.adsabs.harvard.edu/abs/1981cmu..reptR....C). tech. report CMU-RI-TR-82-07.
4. [↑](./Pyramid_(image_processing)#cite_ref-4) Burt, Peter; Adelson, Ted (1983). ["The Laplacian Pyramid as a Compact Image Code"](http://persci.mit.edu/pub_pdfs/pyramid83.pdf) (PDF). *IEEE Transactions on Communications*. **9** (4): 532–540. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.54.299](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.54.299). [doi](./Doi_(identifier)):[10.1109/TCOM.1983.1095851](https://doi.org/10.1109%2FTCOM.1983.1095851). [S2CID](./S2CID_(identifier)) [8018433](https://api.semanticscholar.org/CorpusID:8018433).
5. [↑](./Pyramid_(image_processing)#cite_ref-5) Crowley, J. L.; [Parker, A. C.](./Alice_C._Parker) (March 1984). "A representation for shape based on peaks and ridges in the difference of low-pass transform". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **6** (2): 156–170. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.161.3102](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.161.3102). [doi](./Doi_(identifier)):[10.1109/TPAMI.1984.4767500](https://doi.org/10.1109%2FTPAMI.1984.4767500). [PMID](./PMID_(identifier)) [21869180](https://pubmed.ncbi.nlm.nih.gov/21869180). [S2CID](./S2CID_(identifier)) [14348919](https://api.semanticscholar.org/CorpusID:14348919).
6. [↑](./Pyramid_(image_processing)#cite_ref-6) Crowley, J. L.; Sanderson, A. C. (1987). ["Multiple resolution representation and probabilistic matching of 2-D gray-scale shape"](http://www-prima.inrialpes.fr/Prima/Homepages/jlc/papers/Crowley-Sanderson-PAMI87.pdf) (PDF). *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **9** (1): 113–121. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.1015.9294](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.1015.9294). [doi](./Doi_(identifier)):[10.1109/tpami.1987.4767876](https://doi.org/10.1109%2Ftpami.1987.4767876). [PMID](./PMID_(identifier)) [21869381](https://pubmed.ncbi.nlm.nih.gov/21869381). [S2CID](./S2CID_(identifier)) [14999508](https://api.semanticscholar.org/CorpusID:14999508).
7. [↑](./Pyramid_(image_processing)#cite_ref-7) Meer, P.; Baugher, E. S.; Rosenfeld, A. (1987). "Frequency domain analysis and synthesis of image generating kernels". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **9** (4): 512–522. [doi](./Doi_(identifier)):[10.1109/tpami.1987.4767939](https://doi.org/10.1109%2Ftpami.1987.4767939). [PMID](./PMID_(identifier)) [21869409](https://pubmed.ncbi.nlm.nih.gov/21869409). [S2CID](./S2CID_(identifier)) [5978760](https://api.semanticscholar.org/CorpusID:5978760).
8. [↑](./Pyramid_(image_processing)#cite_ref-8) Lindeberg, Tony, "[Scale-space for discrete signals](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A472968&dswid=77)," PAMI(12), No. 3, March 1990, pp. 234-254.
9. [↑](./Pyramid_(image_processing)#cite_ref-9) Haddad, R. A.; Akansu, A. N. (March 1991). ["A Class of Fast Gaussian Binomial Filters for Speech and Image Processing"](https://web.njit.edu/~akansu/PAPERS/Haddad-AkansuFastGaussianBinomialFiltersIEEE-TSP-March1991.pdf) (PDF). *IEEE Transactions on Signal Processing*. **39** (3): 723–727. [Bibcode](./Bibcode_(identifier)):[1991ITSP...39..723H](https://ui.adsabs.harvard.edu/abs/1991ITSP...39..723H). [doi](./Doi_(identifier)):[10.1109/78.80892](https://doi.org/10.1109%2F78.80892).
10. [↑](./Pyramid_(image_processing)#cite_ref-10) Lindeberg, Tony. [Scale-Space Theory in Computer Vision](http://www.csc.kth.se/~tony/book.html), Kluwer Academic Publishers, 1994, [ISBN](./ISBN_(identifier)) [0-7923-9418-6](./Special:BookSources/0-7923-9418-6) (see specifically Chapter 2 for an overview of Gaussian and Laplacian image pyramids and Chapter 3 for theory about generalized binomial kernels and discrete Gaussian kernels)
11. [1](./Pyramid_(image_processing)#cite_ref-LinBre03-ScSp_11-0) [2](./Pyramid_(image_processing)#cite_ref-LinBre03-ScSp_11-1) [3](./Pyramid_(image_processing)#cite_ref-LinBre03-ScSp_11-2) Lindeberg, T. and Bretzner, L. [Real-time scale selection in hybrid multi-scale representations](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A440700&dswid=-2509), Proc. Scale-Space'03, Isle of Skye, Scotland, Springer Lecture Notes in Computer Science, volume 2695, pages 148-163, 2003.
12. [↑](./Pyramid_(image_processing)#cite_ref-12) See the article on [multi-scale approaches](./Multi-scale_approaches) for a very brief theoretical statement
13. [↑](./Pyramid_(image_processing)#cite_ref-13) Burt, Peter J.; Adelson, Edward H. (1983). ["The Laplacian Pyramid as a Compact Image Code"](http://persci.mit.edu/pub_pdfs/pyramid83.pdf) (PDF). *IEEE Transactions on Communications*. **31** (4): 532–540. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.54.299](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.54.299). [doi](./Doi_(identifier)):[10.1109/TCOM.1983.1095851](https://doi.org/10.1109%2FTCOM.1983.1095851). [S2CID](./S2CID_(identifier)) [8018433](https://api.semanticscholar.org/CorpusID:8018433).
14. [↑](./Pyramid_(image_processing)#cite_ref-14) Simoncelli, Eero. ["The Steerable Pyramid"](http://www.cns.nyu.edu/~eero/STEERPYR/). cns.nyu.edu.
15. [↑](./Pyramid_(image_processing)#cite_ref-15) Manduchi, Roberto; Perona, Pietro; Shy, Doug (1997). ["Efficient Deformable Filter Banks"](http://www.vision.caltech.edu/publications/ManduchiPeronaShy_efficient_deformable.pdf) (PDF). [California Institute of Technology](./California_Institute_of_Technology)/[University of Padua](./University_of_Padua). 
Also in Manduchi, R.; Perona, P.; Shy, D. (1998). "Efficient Deformable Filter Banks". *IEEE Transactions on Signal Processing*. **46** (4): 1168–1173. [Bibcode](./Bibcode_(identifier)):[1998ITSP...46.1168M](https://ui.adsabs.harvard.edu/abs/1998ITSP...46.1168M). [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.5.3102](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.5.3102). [doi](./Doi_(identifier)):[10.1109/78.668570](https://doi.org/10.1109%2F78.668570).
16. [↑](./Pyramid_(image_processing)#cite_ref-16) Klein, Stanley A.; Carney, Thom; Barghout-Stein, Lauren; Tyler, Christopher W. (1997). "Seven models of masking". In Rogowitz, Bernice E.; Pappas, Thrasyvoulos N. (eds.). *Human Vision and Electronic Imaging II*. Vol. 3016. pp. 13–24. [doi](./Doi_(identifier)):[10.1117/12.274510](https://doi.org/10.1117%2F12.274510). [S2CID](./S2CID_(identifier)) [8366504](https://api.semanticscholar.org/CorpusID:8366504).
17. [↑](./Pyramid_(image_processing)#cite_ref-17) Crowley, J, Riff O. [Fast computation of scale normalised Gaussian receptive fields](http://www-prima.inrialpes.fr/Prima/Homepages/jlc/papers/Crowley-ScaleSpace03.pdf), Proc. Scale-Space'03, Isle of Skye, Scotland, Springer [Lecture Notes in Computer Science](./Lecture_Notes_in_Computer_Science), volume 2695, 2003.
18. [↑](./Pyramid_(image_processing)#cite_ref-18) Lowe, D. G. (2004). ["Distinctive image features from scale-invariant keypoints"](http://citeseer.ist.psu.edu/lowe04distinctive.html). *International Journal of Computer Vision*. **60** (2): 91–110. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.73.2924](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.73.2924). [doi](./Doi_(identifier)):[10.1023/B:VISI.0000029664.99615.94](https://doi.org/10.1023%2FB%3AVISI.0000029664.99615.94). [S2CID](./S2CID_(identifier)) [221242327](https://api.semanticscholar.org/CorpusID:221242327).

 

## External links

 
- [Gaussian-Laplacian Pyramid Image Coding](http://fourier.eng.hmc.edu/e161/lectures/canny/node3.html) - illustrates methods of [Downsampling](./Downsampling), [Upsampling](./Upsampling), and [Gaussian](./Gaussian_function) [convolution](./Convolution)
- [The Gaussian Pyramid](http://www.cse.yorku.ca/~kosta/CompVis_Notes/gaussian_pyramid.pdf) - provides a brief introduction for the procedure and cites several sources
- [Laplacian Irregular Graph Pyramid](http://www.prip.tuwien.ac.at/twist/irregulargraphpyramid.php) - Figure 1 on this page illustrates an example of the Gaussian Pyramid
- [The Laplacian Pyramid as a Compact Image Code](https://archive.today/20130117073108/http://aspdf.com/ebook/the-laplacian-pyramid-as-a-compact-image-code-pdf.html) on [eBook Submission](http://aspdf.com/)