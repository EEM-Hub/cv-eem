---
source: sources/wiki-Point_cloud.md
source_url: https://en.wikipedia.org/wiki/Point_cloud
---

## Point Clouds: Representation, Registration, and Surface Reconstruction

A point cloud is a discrete set of data points in 3D space, where each point has Cartesian coordinates (X, Y, Z) and may carry additional attributes such as RGB color, surface normals, and timestamps. Point clouds are the primary output of 3D scanners and photogrammetry software, and serve as a foundational data representation in computer vision, CAD, GIS, metrology, and immersive media.

## Key Concepts

- **Definition**: A discrete set of points in space, each with (X, Y, Z) coordinates, representing a 3D shape or object surface
- **Per-point attributes**: Position (mandatory), plus optional RGB color, surface normals, timestamps, intensity, and other metadata
- **Acquisition methods**: 3D scanners (LiDAR, structured light, time-of-flight) and photogrammetry software (e.g., Agisoft Photoscan, Pix4D, DroneDeploy)
- **Point set registration**: The process of aligning multiple point clouds or aligning a point cloud to a 3D model; essential when combining partial scans into a complete scene
- **ICP (Iterative Closest Point)**: Classic algorithm for aligning two overlapping point clouds separated by a rigid transformation; NICP extends this to non-rigid/elastic transforms
- **Deep learning registration**: End-to-end neural networks (e.g., DeepVCP) can perform point cloud registration, replacing or augmenting traditional ICP
- **Surface reconstruction**: Converting point clouds into polygon/triangle meshes, NURBS surfaces, or CAD models
- **Reconstruction techniques**:
  - **Delaunay triangulation / alpha shapes / ball pivoting** — build triangle networks over existing point vertices
  - **Volumetric methods** — convert to a voxel distance field, then extract the implicit surface via marching cubes
- **GIS applications**: Point clouds feed digital elevation models (DEMs) and 3D urban environment models
- **Medical imaging**: Point clouds can represent volumetric data, enabling multi-sampling and data compression
- **MPEG Point Cloud Compression (PCC)**: Standardization began in 2017 with three categories:
  - **Category 1**: Static point clouds (G-PCC)
  - **Category 2**: Dynamic point clouds (V-PCC)
  - **Category 3**: LiDAR sequences (G-PCC)
- **G-PCC** (Geometry-based PCC, ISO/IEC 23090-9): Compresses geometry directly; used for static and LiDAR data
- **V-PCC** (Video-based PCC, ISO/IEC 23090-5): Projects point cloud onto 2D patches and leverages video codecs; used for dynamic data

## Commands and Syntax

No specific CLI commands on this topic, but key tools and libraries for working with point clouds:

- **MeshLab** — open-source tool for point cloud management and conversion to triangle meshes
- **CloudCompare** — open-source tool for viewing, editing, and processing high-density 3D point clouds
- **Point Cloud Library (PCL)** — BSD-licensed C++ library for n-D point cloud and 3D geometry processing
- **CGAL** — Computational Geometry Algorithms Library with point set processing packages
- **Photogrammetry platforms**: Agisoft Photoscan, Pix4D, DroneDeploy, Hammer Missions (drone RGB to point cloud pipelines)

## Relationships

- **LiDAR / 3D Scanning** → Primary acquisition source for point clouds
- **Photogrammetry** → Alternative acquisition via multi-view RGB images (especially drone-based)
- **Depth Maps** → Can be converted to/from point clouds; used in multi-view 3D shape synthesis
- **Mesh Reconstruction** → Point clouds are upstream of polygon meshes, triangle meshes, and NURBS surfaces
- **Voxels / Distance Fields** → Intermediate volumetric representation used during surface reconstruction
- **ICP / Registration** → Algorithms that align multiple point clouds into a unified coordinate frame
- **Digital Elevation Models (DEMs)** → Downstream GIS product derived from point clouds
- **CAD / Metrology** → Point clouds are compared against CAD models for quality inspection and GD&T extraction
- **Video Compression (HEVC/VVC)** → V-PCC leverages existing video codecs for dynamic point cloud compression
- **Neural Networks** → Modern approaches to registration, segmentation, and generation from point clouds

## Exam-Relevant Points

- A point cloud stores discrete (X, Y, Z) positions with optional per-point attributes (color, normals, timestamps)
- **ICP** aligns two overlapping point clouds under rigid transformation; **NICP** handles non-rigid/elastic transforms
- Know the distinction between surface reconstruction methods: **vertex-based** (Delaunay, alpha shapes, ball pivoting) vs. **volumetric** (distance field + marching cubes)
- Point clouds are produced by both **active sensing** (LiDAR, structured light) and **passive sensing** (photogrammetry from RGB images)
- MPEG PCC defines two codecs: **G-PCC** for static/LiDAR point clouds, **V-PCC** for dynamic point clouds
- G-PCC compresses geometry directly; V-PCC projects to 2D patches and uses video codecs — know which category maps to which codec
- In GIS, point clouds are a primary input for generating **digital elevation models**
- In industrial metrology, point clouds are aligned to CAD models to extract **geometric dimensions and tolerances (GD&T)**
- Key open-source tools: **PCL** (library), **MeshLab** and **CloudCompare** (applications)
