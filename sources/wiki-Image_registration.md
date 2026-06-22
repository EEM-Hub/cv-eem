---
source: https://en.wikipedia.org/wiki/Image_registration
fetched: 2026-06-21
---

Mapping of data into a single system Not to be confused with [Printing registration](./Printing_registration). [![](//upload.wikimedia.org/wikipedia/commons/thumb/d/d7/Registrator_Demo2.png/250px-Registrator_Demo2.png)](./File:Registrator_Demo2.png)Registering and summing multiple exposures of the same scene improve signal to noise ratio, allowing one to see things previously impossible to see. In this picture, the distant Alps are made visible, although they are tens of kilometers into the haze. 

**Image registration** is the process of transforming different sets of data into one [coordinate system](./Coordinate_system). Data may be multiple photographs, data from different sensors, times, depths, or viewpoints.[[1]](./Image_registration#cite_note-1) It is used in [computer vision](./Computer_vision), [medical imaging](./Medical_imaging),[[2]](./Image_registration#cite_note-2) military [automatic target recognition](./Automatic_target_recognition), and compiling and analyzing images and data from satellites. Registration is necessary in order to be able to compare or integrate the data obtained from these different measurements.

 

## Algorithm classification

 

### Intensity-based vs feature-based

 

Image registration or image alignment algorithms can be classified into intensity-based and feature-based.[[3]](./Image_registration#cite_note-AG-3) One of the images is referred to as the *target*, *fixed* or *sensed* image and the others are referred to as the *moving* or *source* images. Image registration involves spatially transforming the source/moving image(s) to align with the target image. The reference frame in the target image is stationary, while the other datasets are transformed to match to the target.[[3]](./Image_registration#cite_note-AG-3) Intensity-based methods compare intensity patterns in images via correlation metrics, while feature-based methods find [correspondence](./Correspondence_problem) between image features such as points, lines, and contours.[[3]](./Image_registration#cite_note-AG-3) Intensity-based methods register entire images or sub-images. If sub-images are registered, centers of corresponding sub images are treated as corresponding feature points. Feature-based methods establish a correspondence between a number of especially distinct points in images. Knowing the correspondence between a number of points in images, a geometrical transformation is then determined to map the target image to the reference images, thereby establishing point-by-point correspondence between the reference and target images.[[3]](./Image_registration#cite_note-AG-3) Methods combining intensity-based and feature-based information have also been developed.[[4]](./Image_registration#cite_note-PapademetrisJackowski2004-4)

 

### Transformation models

 

Image registration algorithms can also be classified according to the transformation models they use to relate the target image space to the reference image space. The first broad category of transformation models includes [affine transformations](./Affine_transformation), which include rotation, scaling, translation and shearing.[[5]](./Image_registration#cite_note-5) Affine transformations are global in nature, thus, they cannot model local geometric differences between images.[[3]](./Image_registration#cite_note-AG-3)

 

The second category of transformations allow 'elastic' or 'nonrigid' transformations. These transformations are capable of locally warping the target image to align with the reference image.  Nonrigid transformations include [radial basis functions](./Radial_basis_functions) ([thin-plate](./Thin_plate_spline) or surface splines, [multiquadrics](./Radial_basis_functions#Types), and [compactly-supported transformations](./Support_(mathematics)#Compact_support)[[3]](./Image_registration#cite_note-AG-3)), physical continuum models (viscous fluids), and large deformation models ([diffeomorphisms](./Diffeomorphism)).

 

Transformations are commonly described by a parametrization, where the model dictates the number of parameters. For instance, the translation of a full image can be described by a translation vector parameter. These models are called parametric models. Non-parametric models on the other hand, do not follow any parameterization, allowing each image element to be displaced arbitrarily.[[6]](./Image_registration#cite_note-6)

 

There are a number of programs that implement both estimation and application of a warp-field. It is a part of the [SPM](./Statistical_parametric_mapping) and [AIR](./AIR_(program)) programs.

 

### Transformations of coordinates via the law of function composition rather than addition

 

Alternatively, many advanced methods for spatial normalization are building on structure preserving transformations [homeomorphisms](./Homeomorphism) and [diffeomorphisms](./Diffeomorphism) since they carry smooth submanifolds smoothly during transformation. Diffeomorphisms are generated in the modern field of [Computational Anatomy](./Computational_anatomy) based on flows since diffeomorphisms are not additive although they form a group, but a group under the law of function composition. For this reason, flows which generalize the ideas of additive groups allow for generating large deformations that preserve topology, providing 1-1 and onto transformations. Computational methods for generating such transformation are often called [LDDMM](./Large_deformation_diffeomorphic_metric_mapping)[[7]](./Image_registration#cite_note-7)[[8]](./Image_registration#cite_note-8)[[9]](./Image_registration#cite_note-9)[[10]](./Image_registration#cite_note-10) which provide flows of diffeomorphisms as the main computational tool for connecting coordinate systems corresponding to [the geodesic flows of Computational Anatomy](./Computational_anatomy#The_metric_on_geodesic_flows_of_landmarks,_surfaces,_and_volumes_within_the_orbit).

 

There are a number of programs which generate diffeomorphic transformations of coordinates via [diffeomorphic mapping](./Diffeomorphic_Mapping_in_Computational_Anatomy) including MRI Studio[[11]](./Image_registration#cite_note-11) and MRI Cloud.org[[12]](./Image_registration#cite_note-12)

 

### Spatial vs frequency domain methods

 

Spatial methods operate in the image domain, matching intensity patterns or features in images. Some of the feature matching algorithms are outgrowths of traditional techniques for performing manual image registration, in which an operator chooses corresponding [control points](./Feature_(computer_vision)) (CP) in images. When the number of control points exceeds the minimum required to define the appropriate transformation model, iterative algorithms like [RANSAC](./RANSAC) can be used to robustly estimate the parameters of a particular transformation type (e.g. affine) for registration of the images.

 

Frequency-domain methods find the transformation parameters for registration of the images while working in the transform domain. Such methods work for simple transformations, such as translation, rotation, and scaling. Applying the [phase correlation](./Phase_correlation) method to a pair of images produces a third image which contains a single peak. The location of this peak corresponds to the relative translation between the images. Unlike many spatial-domain algorithms, the phase correlation method is resilient to noise, occlusions, and other defects typical of medical or satellite images. Additionally, the phase correlation uses the [fast Fourier transform](./Fast_Fourier_transform) to compute the cross-correlation between the two images, generally resulting in large performance gains. The method can be extended to determine rotation and scaling differences between two images by first converting the images to [log-polar coordinates](./Log-polar_coordinates).[[13]](./Image_registration#cite_note-13)[[14]](./Image_registration#cite_note-14) Due to properties of the [Fourier transform](./Fourier_transform), the rotation and scaling parameters can be determined in a manner invariant to translation.

 

### Single- vs multi-modality methods

 

Another classification can be made between single-modality and multi-modality methods. Single-modality methods tend to register images in the same modality acquired by the same scanner/sensor type, while multi-modality registration methods tended to register images acquired by different scanner/sensor types.

 

Multi-modality registration methods are often used in [medical imaging](./Medical_imaging) as images of a subject are frequently obtained from different scanners. Examples include registration of brain [CT](./Computed_tomography)/[MRI](./MRI) images or whole body [PET](./Positron_emission_tomography)/[CT](./Computed_tomography) images for tumor localization, registration of contrast-enhanced [CT](./Computed_tomography) images against non-contrast-enhanced [CT](./Computed_tomography) images[[15]](./Image_registration#cite_note-15) for segmentation of specific parts of the anatomy, and registration of [ultrasound](./Ultrasound) and [CT](./Computed_tomography) images for [prostate](./Prostate) localization in [radiotherapy](./Radiotherapy).

 

### Automatic vs interactive methods

 

Registration methods may be classified based on the level of automation they provide. Manual, interactive, semi-automatic, and automatic methods have been developed. Manual methods provide tools to align the images manually. Interactive methods reduce user bias by performing certain key operations automatically while still relying on the user to guide the registration. Semi-automatic methods perform more of the registration steps automatically but depend on the user to verify the correctness of a registration. Automatic methods do not allow any user interaction and perform all registration steps automatically.

 

### Similarity measures for image registration

 

Image similarities are broadly used in [medical imaging](./Medical_imaging). An image [similarity measure](./Similarity_measure) quantifies the degree of similarity between intensity patterns in two images.[[3]](./Image_registration#cite_note-AG-3) The choice of an image similarity measure depends on the modality of the images to be registered. Common examples of image similarity measures include [cross-correlation](./Cross-correlation), [mutual information](./Mutual_information), sum of squared intensity differences, and ratio image uniformity. Mutual information and normalized mutual information are the most popular image similarity measures for registration of multimodality images. Cross-correlation, sum of squared intensity differences and ratio image uniformity are commonly used for registration of images in the same modality.

 

Many new features have been derived for cost functions based on matching methods via [large deformations](./Computational_anatomy) have emerged in the field [Computational Anatomy](./Computational_anatomy) including 
[Measure matching](./Computational_anatomy#Measure_matching:_unregistered_landmarks) which are pointsets or landmarks without correspondence, [Curve matching](./Computational_anatomy#Curve_matching) and [Surface matching](./Computational_anatomy#Surface_matching) via mathematical [currents](./Current_(mathematics)) and varifolds.

 

## Uncertainty

 

There is a level of [uncertainty](./Uncertainty) associated with registering images that have any spatio-temporal differences.  A confident registration with a measure of uncertainty is critical for many [change detection](./Change_detection) applications such as medical diagnostics.

 

In [remote sensing](./Remote_sensing) applications where a digital image pixel may represent several kilometers of spatial distance (such as NASA's [LANDSAT](./LANDSAT) imagery), an uncertain image registration can mean that a solution could be several kilometers from ground truth.  Several notable papers have attempted to quantify uncertainty in image registration in order to compare results.[[16]](./Image_registration#cite_note-simonson-16)[[17]](./Image_registration#cite_note-Domokos-17) However, many approaches to quantifying uncertainty or estimating deformations are computationally intensive or are only applicable to limited sets of spatial transformations.

 

## Applications

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/40/Mni-autoreg_03-registered.png/250px-Mni-autoreg_03-registered.png)](./File:Mni-autoreg_03-registered.png)Registration of two [MRI](./MRI) images of the brain 

Image registration has applications in remote sensing (cartography updating), and computer vision.  Due to the vast range of applications to which image registration can be applied, it is impossible to develop a general method that is optimized for all uses.

 

[Medical image](./Medical_imaging) registration (eg. for data of the same patient taken at different points in time such as change detection or tumor monitoring (longitudinal studies) often additionally involves *elastic* (also known as *nonrigid*) registration to cope with deformation of the subject (due to breathing, anatomical changes, and so forth) and large anatomical differences between different subjects.[[18]](./Image_registration#cite_note-18)[[19]](./Image_registration#cite_note-19)[[20]](./Image_registration#cite_note-20) Nonrigid registration of medical images can also be used to register a patient's data to an anatomical atlas, such as the [Talairach](./Talairach_coordinates) atlas for neuroimaging. Another application of image registration for medical imaging is the registration of a number of subjects to a single reference space for cohort-wise analyses [[21]](./Image_registration#cite_note-21). In other cases, nonrigid registration is explicitly not utilized since rigid registration methods preserve the underlying geometry, e.g., in [inner ear](./Inner_ear) imaging.[[22]](./Image_registration#cite_note-DOI10.1038/s41598-025-90842-2-22) This is preferred for structures with low variability in anatomy in the cohort that is being studied. 

 

In [Radiation therapy](./Radiation_therapy) rigid image registration (RIR) is a fundamental element in most imaging software systems. It involves aligning images by applying translational and rotational adjustments, up to a six degrees of freedom—three for translation along the x, y, and z axes, and three for rotation about these axes. RIR aligns images appropriately using these six parameters, allowing for precise treatment planning and delivery.[[23]](./Image_registration#cite_note-23)

 

In [astrophotography](./Astrophotography), image alignment and stacking are often used to increase the signal to noise ratio for faint objects. Without stacking it may be used to produce a timelapse of events such as a planet's rotation of a transit across the Sun.  Using control points (automatically or manually entered), the computer performs transformations on one image to make major features align with a second or multiple images. This technique may also be used for images of different sizes, to allow images taken through different telescopes or lenses to be combined.

 

In [cryo-TEM](./Cryo-TEM), instability causes specimen drift and many fast acquisitions with accurate image registration is required to preserve high resolution and obtain high signal to noise images. For low SNR data, the best image registration is achieved by cross-correlating all permutations of images in an image stack.[[24]](./Image_registration#cite_note-Savitsky-24)

 

Image registration is an essential part of panoramic image creation. There are many different techniques that can be implemented in real time and run on embedded devices like cameras and camera-phones.

 

## See also

 
- ![](//upload.wikimedia.org/wikipedia/commons/thumb/3/31/Free_and_open-source_software_logo_%282009%29.svg/40px-Free_and_open-source_software_logo_%282009%29.svg.png)[Free and open-source software portal](./Portal:Free_and_open-source_software)

 
- [Computational Anatomy](./Computational_Anatomy)
- [Correspondence problem](./Correspondence_problem)
- [Digital image correlation and tracking](./Digital_image_correlation_and_tracking)
- [Georeferencing](./Georeferencing)
- [Image correlation](./Image_correlation)
- [Image rectification](./Image_rectification)
- [Inverse consistency](./Inverse_consistency)
- [Point set registration](./Point_set_registration)
- [Rubbersheeting](./Rubbersheeting)
- [Spatial normalization](./Spatial_normalization)
- [Spatial verification](./Spatial_verification)

 

## References

 
1. [↑](./Image_registration#cite_ref-1) [Lisa Gottesfeld Brown, A survey of image registration techniques (*abstract*), ACM Computing Surveys archive, volume 24, issue 4, December 1992), pages 325 - 376](http://portal.acm.org/citation.cfm?id=146374)
2. [↑](./Image_registration#cite_ref-2) [biological imaging and brain mapping](https://www.nature.com/nmeth/journal/v8/n6/full/nmeth.1602.html)
3. [1](./Image_registration#cite_ref-AG_3-0) [2](./Image_registration#cite_ref-AG_3-1) [3](./Image_registration#cite_ref-AG_3-2) [4](./Image_registration#cite_ref-AG_3-3) [5](./Image_registration#cite_ref-AG_3-4) [6](./Image_registration#cite_ref-AG_3-5) [7](./Image_registration#cite_ref-AG_3-6) A. Ardeshir Goshtasby: [2-D and 3-D Image Registration for Medical, Remote Sensing, and Industrial Applications](http://www.wiley.com/WileyCDA/WileyTitle/productCd-0471649546.html) [Archived](https://web.archive.org/web/20090216200153/http://www.wiley.com/WileyCDA/WileyTitle/productCd-0471649546.html) 2009-02-16 at the [Wayback Machine](./Wayback_Machine), Wiley Press, 2005.
4. [↑](./Image_registration#cite_ref-PapademetrisJackowski2004_4-0) Papademetris, Xenophon; Jackowski, Andrea P.; Schultz, Robert T.; Staib, Lawrence H.; Duncan, James S. (2004). "Integrated Intensity and Point-Feature Nonrigid Registration". *Medical Image Computing and Computer-Assisted Intervention – MICCAI 2004*. Lecture Notes in Computer Science. Vol. 3216. pp. 763–770. [doi](./Doi_(identifier)):[10.1007/978-3-540-30135-6_93](https://doi.org/10.1007%2F978-3-540-30135-6_93). [ISBN](./ISBN_(identifier)) [978-3-540-22976-6](./Special:BookSources/978-3-540-22976-6). [ISSN](./ISSN_(identifier)) [0302-9743](https://search.worldcat.org/issn/0302-9743).
5. [↑](./Image_registration#cite_ref-5) Kheng, Leow Wee. ["Image Registration CS4243 Computer Vision and Pattern Recognition (powerpoint)"](https://www.comp.nus.edu.sg/~cs4243/lecture/register.pdf) (PDF). *National University of Singapore School of Computing*. [Archived](https://web.archive.org/web/20240629111027/https://www.comp.nus.edu.sg/~cs4243/lecture/register.pdf) (PDF) from the original on 2024-06-29.
6. [↑](./Image_registration#cite_ref-6) Sotiras, A.; Davatzikos, C.; Paragios, N. (July 2013). ["Deformable Medical Image Registration: A Survey"](https://hal.inria.fr/hal-00858737/document). *IEEE Transactions on Medical Imaging*. **32** (7): 1153–1190. [Bibcode](./Bibcode_(identifier)):[2013ITMI...32.1153S](https://ui.adsabs.harvard.edu/abs/2013ITMI...32.1153S). [doi](./Doi_(identifier)):[10.1109/TMI.2013.2265603](https://doi.org/10.1109%2FTMI.2013.2265603). [PMC](./PMC_(identifier)) [3745275](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3745275). [PMID](./PMID_(identifier)) [23739795](https://pubmed.ncbi.nlm.nih.gov/23739795).
7. [↑](./Image_registration#cite_ref-7) Toga, Arthur W. (1998-11-17). [*Brain Warping*](https://books.google.com/books?id=8WdlWJepgWMC). Academic Press. [ISBN](./ISBN_(identifier)) [9780080525549](./Special:BookSources/9780080525549).
8. [↑](./Image_registration#cite_ref-8) ["Landmark matching on brain surfaces via large deformation diffeomorphisms on the sphere — University of Utah"](https://web.archive.org/web/20180629235930/https://utah.pure.elsevier.com/en/publications/landmark-matching-on-brain-surfaces-via-large-deformation-diffeom-2). *utah.pure.elsevier.com*. Archived from [the original](https://utah.pure.elsevier.com/en/publications/landmark-matching-on-brain-surfaces-via-large-deformation-diffeom-2) on 2018-06-29. Retrieved 2016-03-21.
9. [↑](./Image_registration#cite_ref-9) Beg, M. Faisal; Miller, Michael I.; Trouvé, Alain; Younes, Laurent (2005). ["Computing Large Deformation Metric Mappings via Geodesic Flows of Diffeomorphisms"](https://www.researchgate.net/publication/220660081). *International Journal of Computer Vision*. **61** (2): 139–157. [doi](./Doi_(identifier)):[10.1023/B:VISI.0000043755.93987.aa](https://doi.org/10.1023%2FB%3AVISI.0000043755.93987.aa). [S2CID](./S2CID_(identifier)) [17772076](https://api.semanticscholar.org/CorpusID:17772076). Retrieved 2016-03-21.
10. [↑](./Image_registration#cite_ref-10) Joshi, S. C.; Miller, M. I. (2000-01-01). "Landmark matching via large deformation diffeomorphisms". *IEEE Transactions on Image Processing*. **9** (8): 1357–1370. [Bibcode](./Bibcode_(identifier)):[2000ITIP....9.1357J](https://ui.adsabs.harvard.edu/abs/2000ITIP....9.1357J). [doi](./Doi_(identifier)):[10.1109/83.855431](https://doi.org/10.1109%2F83.855431). [ISSN](./ISSN_(identifier)) [1057-7149](https://search.worldcat.org/issn/1057-7149). [PMID](./PMID_(identifier)) [18262973](https://pubmed.ncbi.nlm.nih.gov/18262973).
11. [↑](./Image_registration#cite_ref-11) ["MRI Studio"](https://www.mristudio.org).
12. [↑](./Image_registration#cite_ref-12) ["MRICloud Brain Mapping"](https://mricloud.org/).
13. [↑](./Image_registration#cite_ref-13) B. Srinivasa Reddy; B. N. Chatterji (Aug 1996). "An FFT-Based Technique for Translation, Rotation and Scale-Invariant Image Registration". *IEEE Transactions on Image Processing*. **5** (8): 1266–1271. [Bibcode](./Bibcode_(identifier)):[1996ITIP....5.1266R](https://ui.adsabs.harvard.edu/abs/1996ITIP....5.1266R). [doi](./Doi_(identifier)):[10.1109/83.506761](https://doi.org/10.1109%2F83.506761). [PMID](./PMID_(identifier)) [18285214](https://pubmed.ncbi.nlm.nih.gov/18285214). [S2CID](./S2CID_(identifier)) [6562358](https://api.semanticscholar.org/CorpusID:6562358).
14. [↑](./Image_registration#cite_ref-14) Zokai, S., Wolberg, G., ["Image Registration Using Log-Polar Mappings for Recovery of Large-Scale Similarity and Projective Transformations"](https://www-cs.ccny.cuny.edu/~wolberg/pub/tip05.pdf). *IEEE Transactions on Image Processing*, vol. 14, No. 10, October, 2005.
15. [↑](./Image_registration#cite_ref-15) Ristea, Nicolae-Catalin; Miron, Andreea-Iuliana; Savencu, Olivian; Georgescu, Mariana-Iuliana; Verga, Nicolae; Khan, Fahad Shahbaz; Ionescu, Radu Tudor (2023). "Cy *Tran*: A cycle-consistent transformer with multi-level consistency for non-contrast to contrast CT translation". *Neurocomputing*. **538** 126211. [arXiv](./ArXiv_(identifier)):[2110.06400](https://arxiv.org/abs/2110.06400). [doi](./Doi_(identifier)):[10.1016/j.neucom.2023.03.072](https://doi.org/10.1016%2Fj.neucom.2023.03.072). [S2CID](./S2CID_(identifier)) [257952429](https://api.semanticscholar.org/CorpusID:257952429).
16. [↑](./Image_registration#cite_ref-simonson_16-0) Simonson, K., Drescher, S., Tanner, F., A Statistics Based Approach to Binary Image Registration with Uncertainty Analysis.  IEEE Transactions on Pattern Analysis and Machine Intelligence, Vol. 29, No. 1, January 2007
17. [↑](./Image_registration#cite_ref-Domokos_17-0) Domokos, C., Kato, Z., Francos, J., Parametric estimation of affine deformations of binary images. Proceedings of IEEE [International Conference on Acoustics, Speech, and Signal Processing](./International_Conference_on_Acoustics,_Speech,_and_Signal_Processing), 2008
18. [↑](./Image_registration#cite_ref-18) Zhao, Shengyu; Lau, Tingfung; Luo, Ji; Chang, Eric I-Chao; Xu, Yan (2020). "Unsupervised 3D End-to-End Medical Image Registration With Volume Tweening Network". *IEEE Journal of Biomedical and Health Informatics*. **24** (5): 1394–1404. [arXiv](./ArXiv_(identifier)):[1902.05020](https://arxiv.org/abs/1902.05020). [Bibcode](./Bibcode_(identifier)):[2020IJBHI..24.1394Z](https://ui.adsabs.harvard.edu/abs/2020IJBHI..24.1394Z). [doi](./Doi_(identifier)):[10.1109/JBHI.2019.2951024](https://doi.org/10.1109%2FJBHI.2019.2951024). [ISSN](./ISSN_(identifier)) [2168-2208](https://search.worldcat.org/issn/2168-2208). [PMID](./PMID_(identifier)) [31689224](https://pubmed.ncbi.nlm.nih.gov/31689224). [S2CID](./S2CID_(identifier)) [61153704](https://api.semanticscholar.org/CorpusID:61153704).
19. [↑](./Image_registration#cite_ref-19) Chen, Junyu; He, Yufan; Frey, Eric C.; Li, Ye; Du, Yong (2021-04-13). "ViT-V-Net: Vision Transformer for Unsupervised Volumetric Medical Image Registration". [arXiv](./ArXiv_(identifier)):[2104.06468](https://arxiv.org/abs/2104.06468) [[eess.IV](https://arxiv.org/archive/eess.IV)].
20. [↑](./Image_registration#cite_ref-20) Burduja, Mihail; Ionescu, Radu Tudor (2021). "Unsupervised Medical Image Alignment with Curriculum Learning". *2021 IEEE International Conference on Image Processing (ICIP)*. pp. 3787–3791. [arXiv](./ArXiv_(identifier)):[2102.10438](https://arxiv.org/abs/2102.10438). [doi](./Doi_(identifier)):[10.1109/ICIP42928.2021.9506067](https://doi.org/10.1109%2FICIP42928.2021.9506067). [ISBN](./ISBN_(identifier)) [978-1-6654-4115-5](./Special:BookSources/978-1-6654-4115-5). [S2CID](./S2CID_(identifier)) [231986287](https://api.semanticscholar.org/CorpusID:231986287).
21. [↑](./Image_registration#cite_ref-21) Jönsson, Hanna; Ekström, Simon; Strand, Robin; Pedersen, Mette A.; Molin, Daniel; Ahlström, Håkan; Kullberg, Joel (2022-11-05). ["An image registration method for voxel-wise analysis of whole-body oncological PET-CT"](https://www.nature.com/articles/s41598-022-23361-z). *Scientific Reports*. **12** (1): 18768. [doi](./Doi_(identifier)):[10.1038/s41598-022-23361-z](https://doi.org/10.1038%2Fs41598-022-23361-z). [ISSN](./ISSN_(identifier)) [2045-2322](https://search.worldcat.org/issn/2045-2322). [PMC](./PMC_(identifier)) [9637131](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9637131). [PMID](./PMID_(identifier)) [36335130](https://pubmed.ncbi.nlm.nih.gov/36335130).
22. [↑](./Image_registration#cite_ref-DOI10.1038/s41598-025-90842-2_22-0) J. Gerb, V. Kirsch, E. Kierig, Thomas Brandt, Marianne Dieterich, Rainer Boegle: *Optimizing spatial normalization of multisubject inner ear MRI: comparison of different geometry-preserving co-registration approaches.* In: *Scientific Reports.* 2025, Band 15, Nummer 1 [doi](./Doi_(identifier)):[10.1038/s41598-025-90842-2](https://doi.org/10.1038%2Fs41598-025-90842-2).
23. [↑](./Image_registration#cite_ref-23) Yuen, Johnson; Barber, Jeffrey; Ralston, Anna; Gray, Alison; Walker, Amy; Hardcastle, Nicholas; Schmidt, Laurel; Harrison, Kristie; Poder, Joel; Sykes, Jonathan R.; Jameson, Michael G. (2020). ["An international survey on the clinical use of rigid and deformable image registration in radiotherapy"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7075391). *Journal of Applied Clinical Medical Physics*. **21** (10): 10–24. [doi](./Doi_(identifier)):[10.1002/acm2.12957](https://doi.org/10.1002%2Facm2.12957). [ISSN](./ISSN_(identifier)) [1526-9914](https://search.worldcat.org/issn/1526-9914). [PMC](./PMC_(identifier)) [7075391](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7075391). [PMID](./PMID_(identifier)) [32915492](https://pubmed.ncbi.nlm.nih.gov/32915492).
24. [↑](./Image_registration#cite_ref-Savitsky_24-0) Savitsky; El Baggari; Clement; Hovden; Kourkoutis (2018). "Image registration of low signal-to-noise cryo-STEM data". *Ultramicroscopy*. **191**: 56–65. [arXiv](./ArXiv_(identifier)):[1710.09281](https://arxiv.org/abs/1710.09281). [doi](./Doi_(identifier)):[10.1016/j.ultramic.2018.04.008](https://doi.org/10.1016%2Fj.ultramic.2018.04.008). [PMID](./PMID_(identifier)) [29843097](https://pubmed.ncbi.nlm.nih.gov/29843097). [S2CID](./S2CID_(identifier)) [26983019](https://api.semanticscholar.org/CorpusID:26983019).

 

## External links

   [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Image registration](https://commons.wikimedia.org/wiki/Category:Image%20registration).  
- Richard Szeliski, [Image Alignment and Stitching: A Tutorial](http://research.microsoft.com/apps/pubs/default.aspx?id=75695). Foundations and Trends in Computer Graphics and Computer Vision, 2:1-104, 2006.
- B. Fischer, J. Modersitzki: [Ill-posed medicine – an introduction to image registration](http://iopscience.iop.org/article/10.1088/0266-5611/24/3/034008/meta). Inverse Problems, 24:1–19, 2008
- Barbara Zitová, Jan Flusser: [Image registration methods: a survey](https://library.utia.cas.cz/prace/20030125.pdf). Image Vision Comput. 21(11): 977-1000 (2003).
- C. Je and H.-M. Park. [Optimized Hierarchical Block Matching for Fast and Accurate Image Registration](https://dx.doi.org/10.1016/j.image.2013.04.002). Signal Processing: Image Communication, Volume 28, Issue 7, pp. 779–791, August, 2013.
- [Registering Multimodal MRI Images](http://www.mathworks.com/help/images/registering-multimodal-mri-images.html) using [Matlab](./Matlab).
- [elastix](http://elastix.isi.uu.nl/) [Archived](https://web.archive.org/web/20120419053714/http://elastix.isi.uu.nl/) 2012-04-19 at the [Wayback Machine](./Wayback_Machine): a toolbox for rigid and nonrigid registration of images.
- [niftyreg](https://sourceforge.net/projects/niftyreg): a toolbox for doing near real-time robust rigid, affine (using block matching) and non-rigid image registration (using a refactored version of the free form deformation algorithm).
- [Image Registration techniques using MATLAB](http://www.mathworks.com/discovery/image-registration.html)
- [Image Compare](https://www.robots.ox.ac.uk/~vgg/software/image-compare/) application automatically compares a pair of images and highlights their differences. This application runs in desktop and mobile phone browsers without requiring installation.