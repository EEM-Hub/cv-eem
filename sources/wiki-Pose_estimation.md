---
source: https://en.wikipedia.org/wiki/Pose_estimation
fetched: 2026-06-21
---

Process of determining spatial characteristics of objects For broader coverage of this topic, see [Pose (computer vision)](./Pose_(computer_vision)). Pose estimation in a [motion capture](./Motion_capture) system 

**3D pose estimation** is a process of predicting the transformation of an object from a user-defined reference pose, given an image or a [3D scan](./3D_scanning).  It arises in [computer vision](./Computer_vision) or [robotics](./Robotics) where the pose or transformation of an object can be used for alignment of a [computer-aided design](./Computer-aided_design) models, identification, [grasping](./Grasping), or manipulation of the object.

 

The image data from which the pose of an object is determined can be either a single image, a [stereo image](./Computer_stereo_vision) pair, or an image sequence where, typically, the camera is moving with a known velocity.  The objects which are considered can be rather general, including a living being or body parts, e.g., a head or hands.  The methods which are used for determining the pose of an object, however, are usually specific for a class of objects and cannot generally be expected to work well for other types of objects.

 

## From an uncalibrated 2D camera

 

It is possible to estimate the 3D rotation and translation of a 3D object from a single 2D photo, if an approximate 3D model of the object is known and the [corresponding points](./Correspondence_problem) in the 2D image are known. A common technique developed in 1995 for solving this is POSIT,[[1]](./3D_pose_estimation#cite_note-1) where the 3D pose is estimated directly from the 3D model points and the 2D image points, and corrects the errors iteratively until a good estimate is found from a single image.[[2]](./3D_pose_estimation#cite_note-2) Most implementations of POSIT only work on non-coplanar points (in other words, it won't work with flat objects or planes).[[3]](./3D_pose_estimation#cite_note-3)

 

Another approach is to register a [3D](./3D_computer_graphics) CAD model over the photograph of a known object by [optimizing](./Optimizing) a suitable distance measure with respect to the pose parameters.[[4]](./3D_pose_estimation#cite_note-4)[[5]](./3D_pose_estimation#cite_note-5)
The distance measure is computed between the object in the photograph and the 3D [CAD model](./CAD_model) projection at a given pose.
[Perspective projection](./Perspective_projection) or [orthogonal projection](./Orthogonal_projection) is possible depending on the pose representation used.
This approach is appropriate for applications where a 3D CAD model of a known object (or object category) is available.

 

## From a calibrated 2D camera

 

Given a 2D image of an object, and the camera that is calibrated with respect to a world coordinate system, it is also possible to find the pose which gives the 3D object in its object coordinate system.[[6]](./3D_pose_estimation#cite_note-Bodo_Rosenhahn-6) This works as follows.

 

### Extracting 3D from 2D

 

Starting with a 2D image, image points are extracted which correspond to corners in an image.  The projection rays from the image points are reconstructed from the 2D points so that the 3D points, which must be incident with the reconstructed rays, can be determined.

 

### Pseudocode

 

The algorithm for determining pose estimation is based on the [iterative closest point](./Iterative_closest_point) algorithm. The main idea is to determine the correspondences between 2D image features and points on the 3D model curve.  

 
```
(a) Reconstruct projection rays from the image points
(b) Estimate the nearest point of each projection ray to a point on the 3D contour
(c) Estimate the pose of the contour with the use of this correspondence set
(d) goto (b)
```
 

The above algorithm does not account for images containing an object that is partially occluded.  The following algorithm assumes that all contours are rigidly coupled, meaning the pose of one contour defines the pose of another contour.

 
```
(a) Reconstruct projection rays from the image points
(b) For each projection ray R:
     (c) For each 3D contour:
          (c1) Estimate the nearest point P1 of ray R to a point on the contour
          (c2) if (n == 1) choose P1 as actual P for the point-line correspondence
          (c3) else compare P1 with P:
                   if dist(P1, R) is smaller than dist(P, R) then
                       choose P1 as new P
(d) Use (P, R) as correspondence set.
(e) Estimate pose with this correspondence set
(f) Transform contours, goto (b)
```
 

## Estimating pose through comparison

 

Systems exist which use a database of an object at different rotations and translations to compare an input image against to estimate pose.  These systems accuracy is limited to situations which are represented in their database of images, however the goal is to recognize a pose, rather than determine it.[[7]](./3D_pose_estimation#cite_note-7)

 

## Software

 
- [posest](http://www.ics.forth.gr/%7elourakis/posest/), a [GPL](./GPL) [C](./C_(programming_language))/[C++](./C++) library for 6DoF pose estimation from 3D-2D correspondences.
- [diffgeom2pose](https://github.com/rfabbri/diffgeom2pose), fast Matlab solver for 6DoF pose estimation from only *two* 3D-2D correspondences of points with directions (vectors), or points at curves (point-tangents). The points can be [SIFT](./Scale-invariant_feature_transform) attributed with feature directions.
- [MINUS](https://github.com/rfabbri/minus): C++ package for (relative) pose estimation of three views. Includes cases of three corresponding points with lines at these points (as in feature positions and orientations, or curve points with tangents), and also for three corresponding points and one line correspondence.
- [Nvidia FoundationPose](https://github.com/NVlabs/FoundationPose), a unified deep learning foundation model for 6DoF object pose estimation and tracking, supporting both 3D model-based and 3D model-free setups.

 

## See also

 
- [Gesture recognition](./Gesture_recognition)
- [3D object recognition](./3D_object_recognition)
- [Articulated body pose estimation](./Articulated_body_pose_estimation)
- [Camera calibration](./Camera_resectioning)
- [Homography (computer vision)](./Homography_(computer_vision))
- [Trifocal tensor](./Trifocal_tensor)
- [Pose estimation](./Pose_estimation)

 

## References

 
1. [↑](./3D_pose_estimation#cite_ref-1) Javier Barandiaran (28 December 2017). ["POSIT tutorial"](https://github.com/opencv/opencv/wiki/Posit). OpenCV.
2. [↑](./3D_pose_estimation#cite_ref-2) Daniel F. Dementhon; Larry S. Davis (1995). ["Model-based object pose in 25 lines of code"](http://portal.acm.org/citation.cfm?id=204015). *International Journal of Computer Vision*. **15** (1–2): 123–141. [Bibcode](./Bibcode_(identifier)):[1995IJCV...15..123D](https://ui.adsabs.harvard.edu/abs/1995IJCV...15..123D). [doi](./Doi_(identifier)):[10.1007/BF01450852](https://doi.org/10.1007%2FBF01450852). [S2CID](./S2CID_(identifier)) [14501637](https://api.semanticscholar.org/CorpusID:14501637). Retrieved 2010-05-29.
3. [↑](./3D_pose_estimation#cite_ref-3) Javier Barandiaran. ["POSIT tutorial with OpenCV and OpenGL"](https://web.archive.org/web/20100620131054/http://opencv.willowgarage.com/wiki/Posit). Archived from [the original](http://opencv.willowgarage.com/wiki/Posit) on 20 June 2010. Retrieved 29 May 2010.
4. [↑](./3D_pose_estimation#cite_ref-4)  Srimal Jayawardena and Marcus Hutter and Nathan Brewer (2011). "A Novel Illumination-Invariant Loss for Monocular 3D Pose Estimation". *2011 International Conference on Digital Image Computing: Techniques and Applications*. pp. 37–44. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.766.3931](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.766.3931). [doi](./Doi_(identifier)):[10.1109/DICTA.2011.15](https://doi.org/10.1109%2FDICTA.2011.15). [ISBN](./ISBN_(identifier)) [978-1-4577-2006-2](./Special:BookSources/978-1-4577-2006-2). [S2CID](./S2CID_(identifier)) [17296505](https://api.semanticscholar.org/CorpusID:17296505). 
5. [↑](./3D_pose_estimation#cite_ref-5)  Srimal Jayawardena and Di Yang and Marcus Hutter (2011). "3D Model Assisted Image Segmentation". *2011 International Conference on Digital Image Computing: Techniques and Applications*. pp. 51–58. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.751.8774](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.751.8774). [doi](./Doi_(identifier)):[10.1109/DICTA.2011.17](https://doi.org/10.1109%2FDICTA.2011.17). [ISBN](./ISBN_(identifier)) [978-1-4577-2006-2](./Special:BookSources/978-1-4577-2006-2). [S2CID](./S2CID_(identifier)) [1665253](https://api.semanticscholar.org/CorpusID:1665253). 
6. [↑](./3D_pose_estimation#cite_ref-Bodo_Rosenhahn_6-0) Bodo Rosenhahn. ["Foundations about 2D-3D Pose Estimation"](http://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/ROSENHAHN1/CVOnlinePose.html). CV Online. Retrieved 2008-06-09.
7. [↑](./3D_pose_estimation#cite_ref-7) Vassilis Athitsos; Stan Sclarof (April 1, 2003). [*Estimating 3D Hand Pose from a Cluttered Image*](https://web.archive.org/web/20190731014346/https://open.bu.edu/bitstream/handle/2144/1505/2003-009-3D-hand-pose-from-cluttered.pdf?sequence=1) (PDF) (Technical report). Boston University Computer Science Tech. Archived from [the original](https://open.bu.edu/xmlui/bitstream/handle/2144/1505/2003-009-3D-hand-pose-from-cluttered.pdf?sequence=1) (PDF) on 2019-07-31.

 

## Bibliography

 
- Rosenhahn, B. "Foundations about 2D-3D Pose Estimation."
- Rosenhahn, B. ["Pose Estimation of 3D Free-form Contours in Conformal Geometry."](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.14.2633)
- Athitsos, V. ["Estimating 3D Hand Pose from a Cluttered Image."](https://athitsos.utasites.cloud/publications/athitsos_cvpr2003.pdf)

 

## External links

 
- [Estimación de una Postura 3D](https://es.wikipedia.org/wiki/Estimación%20de%20una%20Postura%203D)