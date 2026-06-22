---
source: https://en.wikipedia.org/wiki/Point_cloud
fetched: 2026-06-21
---

Set of data points in three-dimensional space [![](//upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Point_cloud_torus.gif/250px-Point_cloud_torus.gif)](./File:Point_cloud_torus.gif)A point cloud image of a [torus](./Torus) [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Geo-Referenced_Point_Cloud.JPG/250px-Geo-Referenced_Point_Cloud.JPG)](./File:Geo-Referenced_Point_Cloud.JPG)Geo-referenced point cloud of [Red Rocks, Colorado](./Red_Rocks_Park) (by DroneMapper) 

A **point cloud** is a [discrete set](./Discrete_set) of data [points](./Point_(geometry)) in [space](./Space). The points may represent a [3D shape](./3D_shape) or object. Each point [position](./Position_(geometry)) has its set of [Cartesian coordinates](./Cartesian_coordinates) (X, Y, Z).[[1]](./Point_cloud#cite_note-1)[[2]](./Point_cloud#cite_note-:0-2) Points may contain data other than position such as [RGB colors](./RGB_color_spaces),[[2]](./Point_cloud#cite_note-:0-2) [normals](./Normal_(geometry)),[[3]](./Point_cloud#cite_note-3) [timestamps](./Timestamp)[[4]](./Point_cloud#cite_note-4) and others. Point clouds are generally produced by [3D scanners](./3D_scanner) or by [photogrammetry](./Photogrammetry) software, which measure many points on the external surfaces of objects around them. As the output of 3D scanning processes, point clouds are used for many purposes, including to create 3D [computer-aided design](./Computer-aided_design) (CAD) or [geographic information systems](./Geographic_information_systems) (GIS) models for manufactured parts, for [metrology](./Metrology) and quality inspection, and for a multitude of visualizing, animating, rendering, and [mass customization](./Mass_customization) applications.

 

## Alignment and registration

 Main article: [Point set registration](./Point_set_registration) 

When scanning a scene in real world using [Lidar](./Lidar), the captured point clouds contain snippets of the scene, which requires alignment to generate a full map of the scanned environment.

 

Point clouds are often aligned with 3D models or with other point clouds, a process termed [point set registration](./Point_set_registration).

 

The [Iterative closest point (ICP) algorithm](./Iterative_closest_point) can be used to align two point clouds that have an overlap between them, and are separated by a [rigid transform](./Rigid_transformation).[[5]](./Point_cloud#cite_note-5) Point clouds with elastic transforms can also be aligned by using a non-rigid variant of the ICP (NICP).[[6]](./Point_cloud#cite_note-6) With advancements in [machine learning](./Machine_learning) in recent years, point cloud registration may also be done using [end-to-end](./End-to-end_principle) [neural networks](./Neural_network_(machine_learning)).[[7]](./Point_cloud#cite_note-7)

 

For industrial metrology or inspection using [industrial computed tomography](./Industrial_computed_tomography), the point cloud of a manufactured part can be aligned to an existing model and compared to check for differences. [Geometric dimensions and tolerances](./GD&T) can also be extracted directly from the point cloud.

 

## Conversion to 3D surfaces

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c0/Extract_Video_Beit_Ghazaleh_Orthophoto_Survey_AG%26P_2017.gif/250px-Extract_Video_Beit_Ghazaleh_Orthophoto_Survey_AG%26P_2017.gif)](./File:Extract_Video_Beit_Ghazaleh_Orthophoto_Survey_AG&P_2017.gif)An example of a 1.2 billion data point cloud render of [Beit Ghazaleh](./Beit_Ghazaleh), a heritage site in danger in [Aleppo](./Aleppo) (Syria)[[8]](./Point_cloud#cite_note-8) [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Synthesizing_3D_Shapes_via_Modeling_Multi-View_Depth_Maps_and_Silhouettes_With_Deep_Generative_Networks.png/250px-Synthesizing_3D_Shapes_via_Modeling_Multi-View_Depth_Maps_and_Silhouettes_With_Deep_Generative_Networks.png)](./File:Synthesizing_3D_Shapes_via_Modeling_Multi-View_Depth_Maps_and_Silhouettes_With_Deep_Generative_Networks.png)Generating or reconstructing 3D shapes from single or multi-view [depth maps](./Depth_map) or silhouettes and visualizing them in dense point clouds[[9]](./Point_cloud#cite_note-3DVAE-9) 

While point clouds can be directly rendered and inspected,[[10]](./Point_cloud#cite_note-10)[[11]](./Point_cloud#cite_note-11) point clouds are often converted to [polygon mesh](./Polygon_mesh) or [triangle mesh](./Triangle_mesh) models, [non-uniform rational B-spline](./Non-uniform_rational_B-spline) (NURBS) surface models, or CAD models through a process commonly referred to as surface reconstruction.

 

There are many techniques for converting a point cloud to a 3D surface.[[12]](./Point_cloud#cite_note-12) Some approaches, like [Delaunay triangulation](./Delaunay_triangulation), [alpha shapes](./Alpha_shape), and ball pivoting, build a network of triangles over the existing vertices of the point cloud, while other approaches convert the point cloud into a [volumetric](./Voxel) [distance field](./Distance_field) and reconstruct the [implicit surface](./Implicit_surface) so defined through a [marching cubes](./Marching_cubes) algorithm.[[13]](./Point_cloud#cite_note-13)

 

In [geographic information systems](./Geographic_information_system), point clouds are one of the sources used to make [digital elevation model](./Digital_elevation_model) of the terrain.[[14]](./Point_cloud#cite_note-14) They are also used to generate 3D models of urban environments.[[15]](./Point_cloud#cite_note-15) Drones are often used to collect a series of [RGB](./RGB_color_model) images which can be later processed on a computer vision algorithm platform such as on AgiSoft Photoscan, Pix4D, DroneDeploy or Hammer Missions to create RGB point clouds from where distances and volumetric estimations can be made.[*[citation needed](./Wikipedia:Citation_needed)*]

 

Point clouds can also be used to represent volumetric data, as is sometimes done in [medical imaging](./Medical_imaging). Using point clouds, multi-sampling and [data compression](./Data_compression) can be achieved.[[16]](./Point_cloud#cite_note-16)

 

## MPEG point cloud compression

 

MPEG began standardizing point cloud compression (PCC) with a Call for Proposal (CfP) in 2017.[[17]](./Point_cloud#cite_note-17)[[18]](./Point_cloud#cite_note-18)[[19]](./Point_cloud#cite_note-19) Three categories of point clouds were identified: category 1 for static point clouds, category 2 for dynamic point clouds, and category 3 for Lidar sequences (dynamically acquired point clouds). Two technologies were finally defined: [G-PCC](./G-PCC?action=edit&redlink=1) (Geometry-based PCC, ISO/IEC 23090 part 9)[[20]](./Point_cloud#cite_note-20) for category 1 and category 3; and [V-PCC](./V-PCC?action=edit&redlink=1) (Video-based PCC, ISO/IEC 23090 part 5)[[21]](./Point_cloud#cite_note-21) for category 2. The first test models were developed in October 2017, one for [G-PCC](./G-PCC?action=edit&redlink=1) (TMC13) and another one for [V-PCC](./V-PCC?action=edit&redlink=1) (TMC2). Since then, the two test models have evolved through technical contributions and collaboration, and the first version of the PCC standard specifications was expected to be finalized in 2020 as part of the ISO/IEC 23090 series on the coded representation of immersive media content.[[22]](./Point_cloud#cite_note-22)

 

## See also

 
- [Euclideon](./Euclideon) – 3D graphics engine which makes use of a point cloud search algorithm to render images
- [MeshLab](./MeshLab) – open source tool to manage point clouds and convert them into 3D triangular meshes
- [CloudCompare](./CloudCompare) – open source tool to view, edit, and process high density 3D point clouds
- [Point Cloud Library](./Point_Cloud_Library) (PCL) – comprehensive BSD open source library for n-D point clouds and 3D geometry processing
- [Point Set Processing](https://doc.cgal.org/latest/Manual/packages.html#PkgPointSetProcessing3) in [CGAL](./CGAL), the Computational Geometry Algorithms Library

 

## References

  
1. [↑](./Point_cloud#cite_ref-1) ["What are Point Clouds"](https://tech27.com/resources/point-clouds/). *Tech27*.
2. [1](./Point_cloud#cite_ref-:0_2-0) [2](./Point_cloud#cite_ref-:0_2-1) ["What is a Point Cloud? - GIGABYTE Global"](https://www.gigabyte.com/Glossary/point-cloud). *GIGABYTE*. Retrieved 2024-06-26.
3. [↑](./Point_cloud#cite_ref-3) Simsangcheol (2023-02-21). ["Estimate normals in Point Cloud"](https://medium.com/@sim30217/estimate-normals-in-point-cloud-eb3a4f9a2e85). *Medium*. Retrieved 2024-06-26.
4. [↑](./Point_cloud#cite_ref-4) ["Defra Data Services Platform"](https://environment.data.gov.uk/dataset/094d4ec8-4c21-4aa6-817f-b7e45843c5e0). *environment.data.gov.uk*. Retrieved 2024-06-26.
5. [↑](./Point_cloud#cite_ref-5) ["Continuous ICP (CICP)"](https://www.cs.cmu.edu/~halismai/cicp/). *www.cs.cmu.edu*. Retrieved 2024-06-26.
6. [↑](./Point_cloud#cite_ref-6) Li, Hao; Sumner, Robert W.; Pauly, Mark (July 2008). ["Global Correspondence Optimization for Non-Rigid Registration of Depth Scans"](https://onlinelibrary.wiley.com/doi/10.1111/j.1467-8659.2008.01282.x). *Computer Graphics Forum*. **27** (5): 1421–1430. [doi](./Doi_(identifier)):[10.1111/j.1467-8659.2008.01282.x](https://doi.org/10.1111%2Fj.1467-8659.2008.01282.x). [ISSN](./ISSN_(identifier)) [0167-7055](https://search.worldcat.org/issn/0167-7055).
7. [↑](./Point_cloud#cite_ref-7) Lu, Weixin; Wan, Guowei; Zhou, Yao; Fu, Xiangyu; Yuan, Pengfei; Song, Shiyu (2019). ["DeepVCP: An End-to-End Deep Neural Network for Point Cloud Registration"](https://openaccess.thecvf.com/content_ICCV_2019/html/Lu_DeepVCP_An_End-to-End_Deep_Neural_Network_for_Point_Cloud_Registration_ICCV_2019_paper.html): 12–21. `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
8. [↑](./Point_cloud#cite_ref-8) [*English: Image from a very high precision 3D laser scanner survey (1.2 billion data points) of Beit Ghazaleh -- a heritage site in danger in Aleppo Syria. This was a collaborative scientific work for the study, safeguarding and emergency consolidation of remains of the structure.*](https://commons.wikimedia.org/wiki/File:Extract_Video_Beit_Ghazaleh_Orthophoto_Survey_AG&P_2017.gif), 2017-11-02, retrieved 2018-06-11
9. [↑](./Point_cloud#cite_ref-3DVAE_9-0) ["Soltani, A. A., Huang, H., Wu, J., Kulkarni, T. D., & Tenenbaum, J. B. Synthesizing 3D Shapes via Modeling Multi-View Depth Maps and Silhouettes With Deep Generative Networks. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (pp. 1511-1519)"](https://github.com/Amir-Arsalan/Synthesize3DviaDepthOrSil). *[GitHub](./GitHub)*. 27 January 2022.
10. [↑](./Point_cloud#cite_ref-10) Levoy, M. and Whitted, T., ["The use of points as a display primitive"](http://graphics.stanford.edu/papers/points).. Technical Report 85-022, Computer Science Department, University of North Carolina at Chapel Hill, January, 1985
11. [↑](./Point_cloud#cite_ref-11) Rusinkiewicz, S. and Levoy, M. 2000. QSplat: a multiresolution point rendering system for large meshes. In Siggraph 2000. ACM, New York, NY, 343–352. DOI= [http://doi.acm.org/10.1145/344779.344940](http://doi.acm.org/10.1145/344779.344940)
12. [↑](./Point_cloud#cite_ref-12) [Berger, M., Tagliasacchi, A., Seversky, L. M., Alliez, P., Guennebaud, G., Levine, J. A., Sharf, A. and Silva, C. T. (2016), A Survey of Surface Reconstruction from Point Clouds. Computer Graphics Forum.](https://hal.inria.fr/hal-01348404v2/document)
13. [↑](./Point_cloud#cite_ref-13) [Meshing Point Clouds](https://meshlabstuff.blogspot.com/2009/09/meshing-point-clouds.html) A short tutorial on how to build surfaces from point clouds
14. [↑](./Point_cloud#cite_ref-14) [From Point Cloud to Grid DEM: A Scalable Approach](http://terrain.cs.duke.edu/pubs/lidar_interpolation.pdf)
15. [↑](./Point_cloud#cite_ref-15) [K. Hammoudi, F. Dornaika, B. Soheilian, N. Paparoditis. Extracting Wire-frame Models of Street Facades from 3D Point Clouds and the Corresponding Cadastral Map. International Archives of Photogrammetry, Remote Sensing and Spatial Information Sciences (IAPRS), vol. 38, part 3A, pp. 91–96, Saint-Mandé, France, 1–3 September 2010.](http://www.isprs.org/proceedings/XXXVIII/part3/a/pdf/91_XXXVIII-part3A.pdf)
16. [↑](./Point_cloud#cite_ref-16) Sitek; et al. (2006). ["Tomographic Reconstruction Using an Adaptive Tetrahedral Mesh Defined by a Point Cloud"](https://zenodo.org/record/1232253). *IEEE Trans. Med. Imaging*. **25** (9): 1172–9. [doi](./Doi_(identifier)):[10.1109/TMI.2006.879319](https://doi.org/10.1109%2FTMI.2006.879319). [PMID](./PMID_(identifier)) [16967802](https://pubmed.ncbi.nlm.nih.gov/16967802). [S2CID](./S2CID_(identifier)) [27545238](https://api.semanticscholar.org/CorpusID:27545238).
17. [↑](./Point_cloud#cite_ref-17) ["MPEG Point Cloud Compression"](http://www.mpeg-pcc.org/). Retrieved 2020-10-22.
18. [↑](./Point_cloud#cite_ref-18) Schwarz, Sebastian; Preda, Marius; Baroncini, Vittorio; Budagavi, Madhukar; Cesar, Pablo; Chou, Philip A.; Cohen, Robert A.; Krivokuća, Maja; Lasserre, Sébastien; Li, Zhu; Llach, Joan; Mammou, Khaled; Mekuria, Rufael; Krivokuća, Maja; Nakagami, Ohji; Siahaan, Ernestasia; Tabatabai, Ali; Tourapis, Alexis M.; Zakharchenko, Vladyslav (2018-12-10). ["Emerging MPEG Standards for Point Cloud Compression"](https://doi.org/10.1109%2FJETCAS.2018.2885981). *IEEE Journal on Emerging and Selected Topics in Circuits and Systems*. **9** (1): 133–148. [doi](./Doi_(identifier)):[10.1109/JETCAS.2018.2885981](https://doi.org/10.1109%2FJETCAS.2018.2885981).
19. [↑](./Point_cloud#cite_ref-19) Graziosi, Danillo; Nakagami, Ohji; Kuma, Satoru; Zaghetto, Alexandre; Suzuki, Teruhiko; Tabatabai, Ali (2020-04-03). ["An overview of ongoing point cloud compression standardization activities: video-based (V-PCC) and geometry-based (G-PCC)"](https://doi.org/10.1017%2FATSIP.2020.12). *APSIPA Transactions on Signal and Information Processing*. **9**: 1–17. [doi](./Doi_(identifier)):[10.1017/ATSIP.2020.12](https://doi.org/10.1017%2FATSIP.2020.12).
20. [↑](./Point_cloud#cite_ref-20) ["ISO/IEC DIS 23090-9"](https://www.iso.org/cms/render/live/en/sites/isoorg/contents/data/standard/07/89/78990.html). *ISO*. Retrieved 2020-06-07.
21. [↑](./Point_cloud#cite_ref-21) ["ISO/IEC DIS 23090-5"](https://www.iso.org/standard/73025.html). *ISO*. Retrieved 2020-10-21.
22. [↑](./Point_cloud#cite_ref-22) ["Immersive Media Architectures | MPEG"](https://mpeg.chiariglione.org/standards/mpeg-i/immersive-media-architectures). *mpeg.chiariglione.org*. Retrieved 2020-06-07.

 
| Authority control databases |
| --- |
| International | GND |
| National | FranceBnF dataLatvia |
| Other | IdRef |