---
source: https://en.wikipedia.org/wiki/Optical_flow
fetched: 2026-06-21
---

Pattern of motion in a visual scene due to relative motion of the observer [![](//upload.wikimedia.org/wikipedia/commons/thumb/5/55/Opticfloweg.png/500px-Opticfloweg.png)](./File:Opticfloweg.png)The optic flow experienced by a rotating observer (in this case a fly). The direction and magnitude of optic flow at each location is represented by the direction and length of each arrow. 

**Optical flow** or **optic flow** is the pattern of apparent [motion](./Motion_(physics)) of objects, surfaces, and edges in a visual scene caused by the [relative motion](./Relative_motion) between an observer and a scene.[[1]](./Optical_flow#cite_note-1)[[2]](./Optical_flow#cite_note-2) Optical flow can also be defined as the distribution of apparent velocities of movement of brightness pattern in an image.[[3]](./Optical_flow#cite_note-Horn_1980-3)

 

The concept of optic flow has roots as far back as [Euclid](./Euclid)'s *[Optics](./Euclid's_Optics)*, but its modern formulation arose from [Second World War](./Second_World_War) research into pilot vision during landing. Several researchers arrived at the idea independently; [James J. Gibson](./James_J._Gibson) gave it its most influential treatment, publishing his theory in 1947 and created the term "optic flow" in 1950. 

 

The term optical flow is also used by roboticists, encompassing related techniques from image processing and control of navigation including [motion detection](./Motion_detection), [object segmentation](./Image_segmentation), time-to-contact information, focus of expansion calculations, luminance, [motion compensated](./Motion_compensation) encoding, and stereo disparity measurement.[[4]](./Optical_flow#cite_note-Kelson_R._T._Aires,_Andre_M._Santana,_Adelardo_A._D._Medeiros_2008-4)[[5]](./Optical_flow#cite_note-5)

 

## Estimation

 

Optical flow can be estimated in a number of ways. Broadly, optical flow estimation approaches can be divided into machine learning based models (sometimes called data-driven models), classical models (sometimes called knowledge-driven models) which do not use machine learning and hybrid models which use aspects of both learning based models and classical models.[[6]](./Optical_flow#cite_note-6)

 

### Classical models

 

Many classical models use the intuitive assumption of *brightness constancy*; that even if a point moves between frames, its brightness stays constant.[[7]](./Optical_flow#cite_note-Fortun_Survey_2015-7)
To formalise this intuitive assumption, consider two consecutive frames from a video sequence, with intensity     I ( x , y , t )   {\displaystyle I(x,y,t)}  ![{\displaystyle I(x,y,t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/943e368e17aa82dd32682aa0a2f44fc544c5268d), where     ( x , y )   {\displaystyle (x,y)}  ![{\displaystyle (x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/41cf50e4a314ca8e2c30964baa8d26e5be7a9386) refer to pixel coordinates and     t   {\displaystyle t}  ![{\displaystyle t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/65658b7b223af9e1acc877d848888ecdb4466560) refers to time.
In this case, the brightness constancy constraint is

     I ( x , y , t ) − −  I ( x + u , y + v , t + 1 ) = 0 ,   {\displaystyle I(x,y,t)-I(x+u,y+v,t+1)=0,}  ![{\displaystyle I(x,y,t)-I(x+u,y+v,t+1)=0,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9d655d5f78df6c1c635ff9ab0e588a4999f2d1c3) 

where      w  := ( u , v )   {\displaystyle \mathbf {w} :=(u,v)}  ![{\displaystyle \mathbf {w} :=(u,v)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f96b082344bfc0ac464c0351fe2e3a66788bd02a) is the displacement vector between a point in the first frame and the corresponding point in the second frame.
By itself, the brightness constancy constraint cannot be solved for     u   {\displaystyle u}  ![{\displaystyle u}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c3e6bb763d22c20916ed4f0bb6bd49d7470cffd8) and     v   {\displaystyle v}  ![{\displaystyle v}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e07b00e7fc0847fbd16391c778d65bc25c452597) at each pixel, since there is only one equation and two unknowns.
This is known as the *[aperture problem](./Motion_perception#The_aperture_problem)*.
Therefore, additional constraints must be imposed to estimate the flow field.[[8]](./Optical_flow#cite_note-Brox_2004-8)[[9]](./Optical_flow#cite_note-Baker_2011-9)

 

#### Regularized models

 

Perhaps the most natural approach to addressing the aperture problem is to apply a smoothness constraint or a *regularization constraint* to the flow field.
One can combine both of these constraints to formulate estimating optical flow as an [optimization problem](./Optimization_problem), where the goal is to minimize the cost function of the form,

     E =  ∬ ∬   Ω Ω    Ψ Ψ  ( I ( x + u , y + v , t + 1 ) − −  I ( x , y , t ) ) + α α  Ψ Ψ  (  |  ∇ ∇  u  |  ) + α α  Ψ Ψ  (  |  ∇ ∇  v  |  ) d x d y ,   {\displaystyle E=\iint _{\Omega }\Psi (I(x+u,y+v,t+1)-I(x,y,t))+\alpha \Psi (|\nabla u|)+\alpha \Psi (|\nabla v|)dxdy,}  ![{\displaystyle E=\iint _{\Omega }\Psi (I(x+u,y+v,t+1)-I(x,y,t))+\alpha \Psi (|\nabla u|)+\alpha \Psi (|\nabla v|)dxdy,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3151c0f34883abb8c19db2694f285f305df99a72) 

where     Ω Ω    {\displaystyle \Omega }  ![{\displaystyle \Omega }](https://wikimedia.org/api/rest_v1/media/math/render/svg/24b0d5ca6f381068d756f6337c08e0af9d1eeb6f) is the extent of the images     I ( x , y )   {\displaystyle I(x,y)}  ![{\displaystyle I(x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/4ec533ce0db7ddc246c115f375d6892597775732),     ∇ ∇    {\displaystyle \nabla }  ![{\displaystyle \nabla }](https://wikimedia.org/api/rest_v1/media/math/render/svg/a3d0e93b78c50237f9ea83d027e4ebbdaef354b2) is the gradient operator,     α α    {\displaystyle \alpha }  ![{\displaystyle \alpha }](https://wikimedia.org/api/rest_v1/media/math/render/svg/b79333175c8b3f0840bfb4ec41b8072c83ea88d3) is a constant, and     Ψ Ψ  ( )   {\displaystyle \Psi ()}  ![{\displaystyle \Psi ()}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5eb2effaeef8814ef9b6811e38b30d1a40fe7328) is a [loss function](./Loss_function).[[7]](./Optical_flow#cite_note-Fortun_Survey_2015-7)[[8]](./Optical_flow#cite_note-Brox_2004-8)

 

This optimisation problem is difficult to solve owing to its non-linearity.
To address this issue, one can use a *variational approach* and linearise the brightness constancy constraint using a first order [Taylor series](./Taylor_series) approximation. Specifically, the brightness constancy constraint is approximated as,

        ∂ ∂  I   ∂ ∂  x    u +    ∂ ∂  I   ∂ ∂  y    v +    ∂ ∂  I   ∂ ∂  t    = 0.   {\displaystyle {\frac {\partial I}{\partial x}}u+{\frac {\partial I}{\partial y}}v+{\frac {\partial I}{\partial t}}=0.}  ![{\displaystyle {\frac {\partial I}{\partial x}}u+{\frac {\partial I}{\partial y}}v+{\frac {\partial I}{\partial t}}=0.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/80383652c57f66751a6d13625b06faf7dae544e7) 

For convenience, the derivatives of the image,         ∂ ∂  I   ∂ ∂  x       {\displaystyle {\tfrac {\partial I}{\partial x}}}  ![{\displaystyle {\tfrac {\partial I}{\partial x}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/cc9a3135c6f690d3bac59164e7ffdd94a8e134ea),         ∂ ∂  I   ∂ ∂  y       {\displaystyle {\tfrac {\partial I}{\partial y}}}  ![{\displaystyle {\tfrac {\partial I}{\partial y}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/824a2c1da4733074d8ce7b1c70882799080d9463) and         ∂ ∂  I   ∂ ∂  t       {\displaystyle {\tfrac {\partial I}{\partial t}}}  ![{\displaystyle {\tfrac {\partial I}{\partial t}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/64b817827ab67c30ca91a3d7c0049bde9ae00ad6) are often condensed to become      I  x     {\displaystyle I_{x}}  ![{\displaystyle I_{x}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eed0dfcd8b1ce6eb2e6b7fbc426b895507d53004),      I  y     {\displaystyle I_{y}}  ![{\displaystyle I_{y}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6f3eedd0871fd35e1fd8992c53812cd60d1b07c2) and      I  t     {\displaystyle I_{t}}  ![{\displaystyle I_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/fc386d951e8ffae76357542f14e160621e6668b1).
Doing so, allows one to rewrite the linearised brightness constancy constraint as,[[9]](./Optical_flow#cite_note-Baker_2011-9)

      I  x   u +  I  y   v +  I  t   = 0.   {\displaystyle I_{x}u+I_{y}v+I_{t}=0.}  ![{\displaystyle I_{x}u+I_{y}v+I_{t}=0.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1e8f4c4b11f92802dfa2fa15335b0ae5d02d5580) 

The optimization problem can now be rewritten as

     E =  ∬ ∬   Ω Ω    Ψ Ψ  (  I  x   u +  I  y   v +  I  t   ) + α α  Ψ Ψ  (  |  ∇ ∇  u  |  ) + α α  Ψ Ψ  (  |  ∇ ∇  v  |  ) d x d y .   {\displaystyle E=\iint _{\Omega }\Psi (I_{x}u+I_{y}v+I_{t})+\alpha \Psi (|\nabla u|)+\alpha \Psi (|\nabla v|)dxdy.}  ![{\displaystyle E=\iint _{\Omega }\Psi (I_{x}u+I_{y}v+I_{t})+\alpha \Psi (|\nabla u|)+\alpha \Psi (|\nabla v|)dxdy.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b4c0b1d1aa26b6fcb0d647bc62671abbb95df887) 

For the choice of     Ψ Ψ  ( x ) =  x  2     {\displaystyle \Psi (x)=x^{2}}  ![{\displaystyle \Psi (x)=x^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a044c75fb79281ba0b1445ebb1814bf9c5205705), this method is the same as the [Horn-Schunck method](./Horn-Schunck_method).[[3]](./Optical_flow#cite_note-Horn_1980-3)
Of course, other choices of cost function have been used such as     Ψ Ψ  ( x ) =    x  2   +  ϵ ϵ   2       {\displaystyle \Psi (x)={\sqrt {x^{2}+\epsilon ^{2}}}}  ![{\displaystyle \Psi (x)={\sqrt {x^{2}+\epsilon ^{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/137eefb06f1315920dc10fe76969d199faf19a6e), which is a differentiable variant of the [     L  1     {\displaystyle L^{1}}  ![{\displaystyle L^{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/74c288d1089f1ec85b01b4de25c441fc792bd2d9) norm](./Taxicab_geometry).[[7]](./Optical_flow#cite_note-Fortun_Survey_2015-7)[[10]](./Optical_flow#cite_note-10)

 

To solve the aforementioned optimization problem, one can use the [Euler-Lagrange equations](./Euler-Lagrange_equations) to provide a system of partial differential equations for each point in     I ( x , y , t )   {\displaystyle I(x,y,t)}  ![{\displaystyle I(x,y,t)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/943e368e17aa82dd32682aa0a2f44fc544c5268d). In the simplest case of using     Ψ Ψ  ( x ) =  x  2     {\displaystyle \Psi (x)=x^{2}}  ![{\displaystyle \Psi (x)=x^{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a044c75fb79281ba0b1445ebb1814bf9c5205705), these equations are,

      I  x   (  I  x   u +  I  y   v +  I  t   ) − −  α α  Δ Δ  u = 0 ,   {\displaystyle I_{x}(I_{x}u+I_{y}v+I_{t})-\alpha \Delta u=0,}  ![{\displaystyle I_{x}(I_{x}u+I_{y}v+I_{t})-\alpha \Delta u=0,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d6d3134041427f4a6c09101791cac01013420c23)      I  y   (  I  x   u +  I  y   v +  I  t   ) − −  α α  Δ Δ  v = 0 ,   {\displaystyle I_{y}(I_{x}u+I_{y}v+I_{t})-\alpha \Delta v=0,}  ![{\displaystyle I_{y}(I_{x}u+I_{y}v+I_{t})-\alpha \Delta v=0,}](https://wikimedia.org/api/rest_v1/media/math/render/svg/72d1adca289156b529283d4045b844bb419e8fa7) 

where     Δ Δ  =    ∂ ∂   2    ∂ ∂   x  2      +    ∂ ∂   2    ∂ ∂   y  2        {\displaystyle \Delta ={\frac {\partial ^{2}}{\partial x^{2}}}+{\frac {\partial ^{2}}{\partial y^{2}}}}  ![{\displaystyle \Delta ={\frac {\partial ^{2}}{\partial x^{2}}}+{\frac {\partial ^{2}}{\partial y^{2}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b9b5313f0b1b67aae3e44844d07eab84391360f4) denotes the [Laplace operator](./Laplace_operator).
Since the image data is made up of discrete pixels, these equations are discretised.
Doing so yields a system of linear equations which can be solved for     ( u , v )   {\displaystyle (u,v)}  ![{\displaystyle (u,v)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eadf12294edccd7a29c99cfc1765e4a14bf47e58) at each pixel, using an iterative scheme such as [Gauss-Seidel](./Gauss-Seidel).[[3]](./Optical_flow#cite_note-Horn_1980-3)

 

Although, linearising the brightness constancy constraint simplifies the optimisation problem significantly, the linearisation is only valid for small displacements and/or smooth images. To avoid this problem, a multi-scale or coarse-to-fine approach is often used. In such a scheme, the images are initially [downsampled](./Downsampling) and the linearised Euler-Lagrange equations are solved at the reduced resolution. The estimated flow field at this scale is then used to initialise the process at next scale.[[11]](./Optical_flow#cite_note-11) This initialisation process is often performed by [warping](./Image_warping) one frame using the current estimate of flow field so that it is as similar to other as possible.[[8]](./Optical_flow#cite_note-Brox_2004-8)[[12]](./Optical_flow#cite_note-12)

 

An alternate approach is to discretize the optimisation problem and then perform a search of the possible     ( u , v )   {\displaystyle (u,v)}  ![{\displaystyle (u,v)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/eadf12294edccd7a29c99cfc1765e4a14bf47e58) values without linearising it.[[13]](./Optical_flow#cite_note-13)
This search is often performed using [Max-flow min-cut theorem](./Max-flow_min-cut_theorem) algorithms, [linear programming](./Linear_programming) or [belief propagation](./Belief_propagation) methods.

 

These regularized methods typically require manual tuning of the Lagrange multiplier, the so-called regularization parameters. There has been some progress in the automatic determination of these parameters in the context of optical flow applied to particle image velocimetry (PIV) data.[[14]](./Optical_flow#cite_note-14)[[15]](./Optical_flow#cite_note-15)

 

#### Parametric models

 

Instead of applying the regularization constraint on a point by point basis as per a regularized model, one can group pixels into regions and estimate the motion of these regions.
This is known as a *parametric model*, since the motion of these regions is [parameterized](./Parameter).
In formulating optical flow estimation in this way, one makes the assumption that the motion field in each region be fully characterised by a set of parameters.
Therefore, the goal of a parametric model is to estimate the motion parameters that minimise a loss function which can be written as,

        α α  ^ ^     = arg ⁡ ⁡   min  α α     ∑ ∑   ( x , y ) ∈ ∈    R     g ( x , y ) ρ ρ  ( x , y ,  I  1   ,  I  2   ,  u  α α    ,  v  α α    ) ,   {\displaystyle {\hat {\boldsymbol {\alpha }}}=\arg \min _{\boldsymbol {\alpha }}\sum _{(x,y)\in {\mathcal {R}}}g(x,y)\rho (x,y,I_{1},I_{2},u_{\boldsymbol {\alpha }},v_{\boldsymbol {\alpha }}),}  ![{\displaystyle {\hat {\boldsymbol {\alpha }}}=\arg \min _{\boldsymbol {\alpha }}\sum _{(x,y)\in {\mathcal {R}}}g(x,y)\rho (x,y,I_{1},I_{2},u_{\boldsymbol {\alpha }},v_{\boldsymbol {\alpha }}),}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1c50a28133a221a93117794f9233bbd6043ab13a) 

where      α α     {\displaystyle {\boldsymbol {\alpha }}}  ![{\displaystyle {\boldsymbol {\alpha }}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a585d2bb19071162720ea56a7b087dab3ec17156) is the set of parameters determining the motion in the region       R     {\displaystyle {\mathcal {R}}}  ![{\displaystyle {\mathcal {R}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/74532dc308c806964b832df0d0d73352195c2f2f),     ρ ρ  ( )   {\displaystyle \rho ()}  ![{\displaystyle \rho ()}](https://wikimedia.org/api/rest_v1/media/math/render/svg/dc9c892f7d2c6675d4ad5e6a6c54de0c5b8e5bfa) is data cost term,     g ( )   {\displaystyle g()}  ![{\displaystyle g()}](https://wikimedia.org/api/rest_v1/media/math/render/svg/470796058e31f0716079ef2047568896bdd748ac) is a weighting function that determines the influence of pixel     ( x , y )   {\displaystyle (x,y)}  ![{\displaystyle (x,y)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/41cf50e4a314ca8e2c30964baa8d26e5be7a9386) on the total cost, and      I  1     {\displaystyle I_{1}}  ![{\displaystyle I_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/03f18d041b2df30adef07164dbf285878893dedc) and      I  2     {\displaystyle I_{2}}  ![{\displaystyle I_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5e3506ae39df854f347365bae6f326ef4f565be5) are frames 1 and 2 from a pair of consecutive frames.[[7]](./Optical_flow#cite_note-Fortun_Survey_2015-7)

 

The simplest parametric model is the [Lucas-Kanade method](./Lucas-Kanade_method). This uses rectangular regions and parameterises the motion as purely translational. The Lucas-Kanade method uses the original brightness constancy constraint as the data cost term and selects     g ( x , y ) = 1   {\displaystyle g(x,y)=1}  ![{\displaystyle g(x,y)=1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/35122b42cb66c9a7d7ab38c0aae54496721c2376).
This yields the local loss function,

        α α  ^ ^     = arg ⁡ ⁡   min  α α     ∑ ∑   ( x , y ) ∈ ∈    R      |  I ( x +  u  α α    , y +  v  α α    , t + 1 ) − −  I ( x , y , t )  |  .   {\displaystyle {\hat {\boldsymbol {\alpha }}}=\arg \min _{\boldsymbol {\alpha }}\sum _{(x,y)\in {\mathcal {R}}}|I(x+u_{\boldsymbol {\alpha }},y+v_{\boldsymbol {\alpha }},t+1)-I(x,y,t)|.}  ![{\displaystyle {\hat {\boldsymbol {\alpha }}}=\arg \min _{\boldsymbol {\alpha }}\sum _{(x,y)\in {\mathcal {R}}}|I(x+u_{\boldsymbol {\alpha }},y+v_{\boldsymbol {\alpha }},t+1)-I(x,y,t)|.}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a7175cc3b595ef217241f35dff6d596080813f4b) 

Other possible local loss functions include the negative normalized [cross-correlation](./Cross-correlation) between the two frames.[[16]](./Optical_flow#cite_note-16)

 

### Learning-based models

 

Instead of seeking to model optical flow directly, one can train a [machine learning](./Machine_learning) system to estimate optical flow. Since 2015, when FlowNet[[17]](./Optical_flow#cite_note-:0-17) was proposed, learning based models have been applied to optical flow and have gained prominence. Initially, these approaches were based on [Convolutional Neural Networks](./Convolutional_neural_network) arranged in a [U-Net](./U-Net) architecture, often utilizing encoder-decoder or feature pyramid structures, such as PWC-Net,[[18]](./Optical_flow#cite_note-18) which integrated cost volumes (a 4D [tensor](./Tensor) representing the matching costs between all pairs of pixels in two feature maps) and [warping](./Image_warping) (the process of spatially transforming one image based on a predicted flow field) to refine flow estimates across multiple scales. However, with the advent of [transformer architecture](./Transformer_(deep_learning_architecture)) in 2017, transformer based models have gained prominence.[[19]](./Optical_flow#cite_note-19) A significant shift occurred with the introduction of RAFT[[20]](./Optical_flow#cite_note-20) (Recurrent All-Pairs Field Transforms), which replaced coarse-to-fine pyramids with a single [GRU](./Gated_recurrent_unit)-based state that iteratively updates the flow field. By maintaining a constant feature resolution at 1/8 of the input, RAFT significantly improved the preservation of fine details and robustness to fast motion compared to previous bottleneck-heavy designs, influencing a wide range of subsequent models that adopt similar iterative update mechanisms.

 

However, the all-pairs correlation used in such models is computationally expensive; for high-resolution content like [FullHD](./FullHD) or [4K](./4K_resolution), global matching can require more than 32 GB of [VRAM](./Video_random-access_memory),[[21]](./Optical_flow#cite_note-:1-21) making it impractical for consumer-grade [GPUs](./Graphics_processing_unit). To address this, efficiency-focused methods such as Flow1D,[[21]](./Optical_flow#cite_note-:1-21) MeFlow,[[22]](./Optical_flow#cite_note-22) and Memfof[[23]](./Optical_flow#cite_note-23) have been developed. While these approaches generally optimize memory usage by decomposing the 2D search space, the latter optimizes correlation volumes for high-resolution multi-frame sequences, providing a practical implementation for standard [GPUs](./Graphics_processing_unit).

 

Most learning-based approaches to optical flow use [supervised learning](./Supervised_learning). In this case, many frame pairs of video data and their corresponding [ground-truth](./Ground_truth) flow fields are used to optimise the parameters of the learning-based model to accurately estimate optical flow. This process often relies on vast synthetic training datasets, such as FlyingChairs[[17]](./Optical_flow#cite_note-:0-17) and FlyingThings3D,[[24]](./Optical_flow#cite_note-24) due to the number of parameters involved.[[25]](./Optical_flow#cite_note-25) The models are then evaluated on benchmarks like MPI Sintel,[[26]](./Optical_flow#cite_note-26) KITTI,[[27]](./Optical_flow#cite_note-27) and the high-resolution Spring[[28]](./Optical_flow#cite_note-28) dataset. However, models trained exclusively on synthetic data often struggle with the domain gap when applied to real-world footage.

 

To address this, some learning-based optical flow approaches use [self-supervised learning](./Self-supervised_learning) (sometimes called [unsupervised learning](./Unsupervised_learning)) to reduce the need for large datasets with ground-truth data and leverage real-world footage without labels during training. Instead of training models to minimise the differences between estimated and ground-truth flow fields, they are trained to achieve learning objectives such as brightness constancy and smoothness of the flow field.[[29]](./Optical_flow#cite_note-29) More recently, methods like CroCo[[30]](./Optical_flow#cite_note-30) have introduced cross-view completion pre-training. Forcing the network to predict the masked regions of one image using the full second image teaches the model a strong geometric understanding and better generalization than models trained solely on task-specific labels.

 

## Uses

 

[Motion estimation](./Motion_estimation) and [video compression](./Video_compression) have developed as a major aspect of optical flow research. While the optical flow field is superficially similar to a dense motion field derived from the techniques of motion estimation, optical flow is the study of not only the determination of the optical flow field itself, but also of its use in estimating the three-dimensional nature and structure of the scene, as well as the 3D motion of objects and the observer relative to the scene, most of them using the image Jacobian.[[31]](./Optical_flow#cite_note-31)

 

Optical flow was used by robotics researchers in many areas such as: [object detection](./Object_detection) and tracking, image dominant plane extraction, movement detection, robot navigation and [visual odometry](./Visual_odometry).[[4]](./Optical_flow#cite_note-Kelson_R._T._Aires,_Andre_M._Santana,_Adelardo_A._D._Medeiros_2008-4) Optical flow information has been recognized as being useful for controlling micro air vehicles.[[32]](./Optical_flow#cite_note-32)

 

The application of optical flow includes the problem of inferring not only the motion of the observer and objects in the scene, but also the [structure](./Structure) of objects and the environment. Since awareness of motion and the generation of mental maps of the structure of our environment are critical components of animal (and human) [vision](./Visual_perception), the conversion of this innate ability to a computer capability is similarly crucial in the field of [machine vision](./Machine_vision).[[33]](./Optical_flow#cite_note-33)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/10/Optical_flow_example_v2.png/250px-Optical_flow_example_v2.png)](./File:Optical_flow_example_v2.png)The optical flow vector of a moving object in a video sequence 

Consider a five-frame clip of a ball moving from the bottom left of a field of vision, to the top right. Motion estimation techniques can determine that on a two dimensional plane the ball is moving up and to the right and vectors describing this motion can be extracted from the sequence of frames. For the purposes of video compression (e.g., [MPEG](./MPEG)), the sequence is now described as well as it needs to be. However, in the field of machine vision, the question of whether the ball is moving to the right or if the observer is moving to the left is unknowable yet critical information. Not even if a static, patterned background were present in the five frames, could we confidently state that the ball was moving to the right, because the pattern might have an infinite distance to the observer.

 

Optical flow has also been applied to [fluid mechanics](./Fluid_mechanics) as a method of estimating flow patterns in a non-invasive way if visible tracer particles are added.[[34]](./Optical_flow#cite_note-Alfarano2024-34) This approach is called [particle image velocimetry](./Particle_image_velocimetry) (PIV)[[35]](./Optical_flow#cite_note-35). It has been shown that optical flow methods can provide higher accuracy than traditional cross-correlation in PIV processing[[36]](./Optical_flow#cite_note-36)
.

 

## Optical flow sensor

 Not to be confused with [Optical flowmeter](./Optical_flowmeter). 

Various configurations of optical flow sensors exist. One configuration is an image sensor chip connected to a processor programmed to run an optical flow algorithm. Another configuration uses a vision chip, which is an [integrated circuit](./Integrated_circuit) having both the [image sensor](./Image_sensor) and the processor on the same die, allowing for a compact implementation.[[37]](./Optical_flow#cite_note-37)[[38]](./Optical_flow#cite_note-38) An example of this is a generic optical mouse sensor used in an [optical mouse](./Optical_mouse). In some cases the processing circuitry may be implemented using analog or mixed-signal circuits to enable fast optical flow computation using minimal current consumption.

 

One area of contemporary research is the use of [neuromorphic engineering](./Neuromorphic_engineering) techniques to implement circuits that respond to optical flow, and thus may be appropriate for use in an optical flow sensor.[[39]](./Optical_flow#cite_note-39) Such circuits may draw inspiration from biological neural circuitry that similarly responds to optical flow.

 

Optical flow sensors are used extensively in computer [optical mice](./Optical_mouse), as the main sensing component for measuring the motion of the mouse across a surface.

 

Optical flow sensors are also being used in [robotics](./Robotics) applications, primarily where there is a need to measure visual motion or relative motion between the robot and other objects in the vicinity of the robot. The use of optical flow sensors in [ unmanned aerial vehicles (UAVs)](./Unmanned_aerial_vehicle), for stability and obstacle avoidance, is also an area of current research.[[40]](./Optical_flow#cite_note-40)

 

## History

 

As early as [Euclid](./Euclid)'s *[Optics](./Euclid's_Optics)* note was made of the geometry underlying optic flow. [Helmholtz](./Hermann_von_Helmholtz)'s nineteenth-century account of [motion parallax](./Motion_parallax) also implicitly concerns it. However, its explicit identification arose during the [Second World War](./Second_World_War) due the need to understand how pilots judge height and direction during landing. [John T. MacCurdy](./John_T._MacCurdy), in advise to the [Royal Air Force](./Royal_Air_Force) in the late 1920s, had earlier observed that during a straight descent the point on the ground being approached stays fixed in the pilot's visual field while all other points appear to stream away from it. [G. C. Grindley](./G._C._Grindley), in a classified 1942 report then mathematically analyzed how retinal velocity changed during self-motion to enable an individual to accurately estimate visual speed. He, however, considered only this as a cue to altitude and not information to determine travel.[[41]](./Optical_flow#cite_note-:3-41)

 

[James J. Gibson](./James_J._Gibson) working for the [U.S. Army Air Forces](./United_States_Army_Air_Forces), first identified that retinal velocities radiate from a "focus of expansion" in the direction of travel. Moreover, that eye movements do not disturb this, and that it was the global pattern—not individual velocities—that provided this information.  In 1947, he published the theory,[[42]](./Optical_flow#cite_note-42)  and in 1950 gave the phenomenon the name "optic flow".[[43]](./Optical_flow#cite_note-:2-43)  In 1955, he together with [Paul Olum](./Paul_Olum) and [Frank Rosenblatt](./Frank_Rosenblatt) detailed its mathematics.[[44]](./Optical_flow#cite_note-44) Independently, the E. S. Calvert at the [Royal Aircraft Establishment](./Royal_Aircraft_Establishment) came to a similar ideas when researching on airport approach lighting. In 1949, he proposed them as the "parafoveal streamer theory" which described how pilots use the pattern and speed of visual streamers to control their descent.[[41]](./Optical_flow#cite_note-:3-41)

 

Gibson stressed the importance of optic flow for [affordance perception](./Affordance), the ability to discern possibilities for action within the environment. Followers of Gibson and his [ecological approach to psychology](./Ecological_Psychology) have further demonstrated the role of the optical flow stimulus for the perception of movement by the observer in the world; perception of the shape, distance and movement of objects in the world; and the control of [locomotion](./Animal_locomotion).[[45]](./Optical_flow#cite_note-45)

 

## See also

 
- [Ambient optic array](./Ambient_optic_array)
- [Optical mouse](./Optical_mouse)
- [Range imaging](./Range_imaging)
- [Vision processing unit](./Vision_processing_unit)
- [Continuity Equation](./Continuity_Equation)
- [Motion field](./Motion_field)

 

## References

 
1. [↑](./Optical_flow#cite_ref-1) Burton, Andrew; Radford, John (1978). [*Thinking in Perspective: Critical Essays in the Study of Thought Processes*](https://books.google.com/books?id=CSgOAAAAQAAJ&pg=PA77&dq=%22optical+flow%22). Routledge. [ISBN](./ISBN_(identifier)) [978-0-416-85840-2](./Special:BookSources/978-0-416-85840-2).
2. [↑](./Optical_flow#cite_ref-2) Warren, David H.; Strelow, Edward R. (1985). [*Electronic Spatial Sensing for the Blind: Contributions from Perception*](https://books.google.com/books?id=-I_Hazgqx8QC&pg=PA414&dq=%22optical+flow%22). Springer. [ISBN](./ISBN_(identifier)) [978-90-247-2689-9](./Special:BookSources/978-90-247-2689-9).
3. [1](./Optical_flow#cite_ref-Horn_1980_3-0) [2](./Optical_flow#cite_ref-Horn_1980_3-1) [3](./Optical_flow#cite_ref-Horn_1980_3-2) Horn, Berthold K.P.; Schunck, Brian G. (August 1981). ["Determining optical flow"](https://web.archive.org/web/20241225022617/http://image.diku.dk/imagecanon/material/HornSchunckOptical_Flow.pdf) (PDF). *Artificial Intelligence*. **17** (1–3): 185–203. [doi](./Doi_(identifier)):[10.1016/0004-3702(81)90024-2](https://doi.org/10.1016%2F0004-3702%2881%2990024-2). [hdl](./Hdl_(identifier)):[1721.1/6337](https://hdl.handle.net/1721.1%2F6337). Archived from [the original](http://image.diku.dk/imagecanon/material/HornSchunckOptical_Flow.pdf) (PDF) on 2024-12-25. Retrieved 2018-11-15.
4. [1](./Optical_flow#cite_ref-Kelson_R._T._Aires,_Andre_M._Santana,_Adelardo_A._D._Medeiros_2008_4-0) [2](./Optical_flow#cite_ref-Kelson_R._T._Aires,_Andre_M._Santana,_Adelardo_A._D._Medeiros_2008_4-1) Aires, Kelson R. T.; Santana, Andre M.; Medeiros, Adelardo A. D. (2008). [*Optical Flow Using Color Information*](http://www.dca.ufrn.br/~adelardo/artigos/SAC08.pdf) (PDF). ACM New York, NY, USA. [ISBN](./ISBN_(identifier)) [978-1-59593-753-7](./Special:BookSources/978-1-59593-753-7).
5. [↑](./Optical_flow#cite_ref-5) Beauchemin, S. S.; Barron, J. L. (1995). ["The computation of optical flow"](http://portal.acm.org/ft_gateway.cfm?id=212141&type=pdf&coll=GUIDE&dl=GUIDE&CFID=72158298&CFTOKEN=85078203). *ACM Computing Surveys*. **27** (3). ACM New York, USA: 433–466. [doi](./Doi_(identifier)):[10.1145/212094.212141](https://doi.org/10.1145%2F212094.212141). [S2CID](./S2CID_(identifier)) [1334552](https://api.semanticscholar.org/CorpusID:1334552).
6. [↑](./Optical_flow#cite_ref-6) Zhai, Mingliang; Xiang, Xuezhi; Lv, Ning; Kong, Xiangdong (2021). ["Optical flow and scene flow estimation: A survey"](https://www.sciencedirect.com/science/article/pii/S0031320321000480). *Pattern Recognition*. **114** 107861. [Bibcode](./Bibcode_(identifier)):[2021PatRe.11407861Z](https://ui.adsabs.harvard.edu/abs/2021PatRe.11407861Z). [doi](./Doi_(identifier)):[10.1016/j.patcog.2021.107861](https://doi.org/10.1016%2Fj.patcog.2021.107861).
7. [1](./Optical_flow#cite_ref-Fortun_Survey_2015_7-0) [2](./Optical_flow#cite_ref-Fortun_Survey_2015_7-1) [3](./Optical_flow#cite_ref-Fortun_Survey_2015_7-2) [4](./Optical_flow#cite_ref-Fortun_Survey_2015_7-3) Fortun, Denis; Bouthemy, Patrick; Kervrann, Charles (2015-05-01). ["Optical flow modeling and computation: A survey"](https://www.sciencedirect.com/science/article/pii/S1077314215000429). *Computer Vision and Image Understanding*. **134**: 1–21. [Bibcode](./Bibcode_(identifier)):[2015CVIU..134....1F](https://ui.adsabs.harvard.edu/abs/2015CVIU..134....1F). [doi](./Doi_(identifier)):[10.1016/j.cviu.2015.02.008](https://doi.org/10.1016%2Fj.cviu.2015.02.008). Retrieved 2024-12-23.
8. [1](./Optical_flow#cite_ref-Brox_2004_8-0) [2](./Optical_flow#cite_ref-Brox_2004_8-1) [3](./Optical_flow#cite_ref-Brox_2004_8-2) Brox, Thomas; Bruhn, Andrés; Papenberg, Nils; Weickert, Joachim (2004). ["High Accuracy Optical Flow Estimation Based on a Theory for Warping"](http://link.springer.com/10.1007/978-3-540-24673-2_3). *Computer Vision - ECCV 2004*. ECCV 2004. Berlin, Heidelberg: Springer Berlin Heidelberg. pp. 25–36. [doi](./Doi_(identifier)):[10.1007/978-3-540-24673-2_3](https://doi.org/10.1007%2F978-3-540-24673-2_3).
9. [1](./Optical_flow#cite_ref-Baker_2011_9-0) [2](./Optical_flow#cite_ref-Baker_2011_9-1) Baker, Simon; Scharstein, Daniel; Lewis, J. P.; Roth, Stefan; Black, Michael J.; Szeliski, Richard (1 March 2011). ["A Database and Evaluation Methodology for Optical Flow"](https://doi.org/10.1007%2Fs11263-010-0390-2). *International Journal of Computer Vision*. **92** (1): 1–31. [doi](./Doi_(identifier)):[10.1007/s11263-010-0390-2](https://doi.org/10.1007%2Fs11263-010-0390-2). [ISSN](./ISSN_(identifier)) [1573-1405](https://search.worldcat.org/issn/1573-1405).
10. [↑](./Optical_flow#cite_ref-10) Sun, Deqing; Roth, Stefan; Black, Micahel J. (2010). ["Secrets of optical flow estimation and their principles"](https://ieeexplore.ieee.org/document/5539939). *2010 IEEE Computer Society Conference on Computer Vision and Pattern Recognition*. 2010 IEEE Computer Society Conference on Computer Vision and Pattern Recognition. San Francisco, CA, USA: IEEE. pp. 2432–2439.
11. [↑](./Optical_flow#cite_ref-11) Meinhardt-Llopis, Enric; Pérez, Javier Sánchez; Kondermann, Daniel (19 July 2013). ["Horn-Schunck Optical Flow with a Multi-Scale Strategy"](https://doi.org/10.5201%2Fipol.2013.20). *Image Processing on Line*. **3**: 151–172. [doi](./Doi_(identifier)):[10.5201/ipol.2013.20](https://doi.org/10.5201%2Fipol.2013.20).
12. [↑](./Optical_flow#cite_ref-12) Black, Michael J.; Anandan, P. (1 January 1996). "The Robust Estimation of Multiple Motions: Parametric and Piecewise-Smooth Flow Fields". *Computer Vision and Image Understanding*. **63** (1): 75–104. [doi](./Doi_(identifier)):[10.1006/cviu.1996.0006](https://doi.org/10.1006%2Fcviu.1996.0006). [ISSN](./ISSN_(identifier)) [1077-3142](https://search.worldcat.org/issn/1077-3142).
13. [↑](./Optical_flow#cite_ref-13) Steinbr¨ucker, Frank; Pock, Thomas; Cremers, Daniel; Weickert, Joachim (2009). ["Large Displacement Optical Flow Computation without Warping"](https://ieeexplore.ieee.org/document/5459364). *2009 IEEE 12th International Conference on Computer Vision*. 2009 IEEE 12th International Conference on Computer Vision. IEEE. pp. 1609–1614.
14. [↑](./Optical_flow#cite_ref-14) Jassal, Gauresh Raj; Somersalo, Erkki; Calvetti, Daniela; Schmidt, Bryan E. (May 2025). ["A Bayesian approach to locally varying regularization in optical flow velocimetry"](https://pubs.aip.org/aip/pof/article/37/5/057132/3347355/A-Bayesian-approach-to-locally-varying). *Physics of Fluids*. **37** (5): 057132. [Bibcode](./Bibcode_(identifier)):[2025PhFl...37e7132J](https://ui.adsabs.harvard.edu/abs/2025PhFl...37e7132J). [doi](./Doi_(identifier)):[10.1063/5.0270225](https://doi.org/10.1063%2F5.0270225).
15. [↑](./Optical_flow#cite_ref-15) Jassal, Gauresh Raj; Thielicke, William; Schmidt, Bryan E. (October 2025). ["An Optical Flow Algorithm with Automatic Parameter Adjustment for Fluid Velocimetry"](https://doi.org/10.5334%2Fjors.584). *Journal of Open Research Software*. **13** (1): 22. [doi](./Doi_(identifier)):[10.5334/jors.584](https://doi.org/10.5334%2Fjors.584).
16. [↑](./Optical_flow#cite_ref-16) Lucas, Bruce D.; Kanade, Takeo (1981-08-24). [*An iterative image registration technique with an application to stereo vision*](https://dl.acm.org/doi/10.5555/1623264.1623280). *Proceedings of the 7th International Joint Conference on Artificial Intelligence - Volume 2*. IJCAI'81. San Francisco, CA, USA: Morgan Kaufmann Publishers Inc. pp. 674–679.
17. [1](./Optical_flow#cite_ref-:0_17-0) [2](./Optical_flow#cite_ref-:0_17-1) Dosovitskiy, Alexey; Fischer, Philipp; Ilg, Eddy; Hausser, Philip; Hazirbas, Caner; Golkov, Vladimir; Smagt, Patrick van der; Cremers, Daniel; Brox, Thomas (2015). *FlowNet: Learning Optical Flow with Convolutional Networks*. 2015 IEEE International Conference on Computer Vision (ICCV). IEEE. pp. 2758–2766. [doi](./Doi_(identifier)):[10.1109/ICCV.2015.316](https://doi.org/10.1109%2FICCV.2015.316). [ISBN](./ISBN_(identifier)) [978-1-4673-8391-2](./Special:BookSources/978-1-4673-8391-2).
18. [↑](./Optical_flow#cite_ref-18) Sun, Deqing; Yang, Xiaodong; Liu, Ming-Yu; Kautz, Jan (2018-06-25). "PWC-Net: CNNs for Optical Flow Using Pyramid, Warping, and Cost Volume". [arXiv](./ArXiv_(identifier)):[1709.02371](https://arxiv.org/abs/1709.02371) [[cs.CV](https://arxiv.org/archive/cs.CV)].
19. [↑](./Optical_flow#cite_ref-19) Alfarano, Andrea; Maiano, Luca; Papa, Lorenzo; Amerini, Irene (2024). ["Estimating optical flow: A comprehensive review of the state of the art"](https://linkinghub.elsevier.com/retrieve/pii/S1077314224002418). *Computer Vision and Image Understanding*. **249** 104160. [doi](./Doi_(identifier)):[10.1016/j.cviu.2024.104160](https://doi.org/10.1016%2Fj.cviu.2024.104160). [hdl](./Hdl_(identifier)):[11573/1726258](https://hdl.handle.net/11573%2F1726258).
20. [↑](./Optical_flow#cite_ref-20) Teed, Zachary; Deng, Jia (2020-08-25). "RAFT: Recurrent All-Pairs Field Transforms for Optical Flow". [arXiv](./ArXiv_(identifier)):[2003.12039](https://arxiv.org/abs/2003.12039) [[cs.CV](https://arxiv.org/archive/cs.CV)].
21. [1](./Optical_flow#cite_ref-:1_21-0) [2](./Optical_flow#cite_ref-:1_21-1) Xu, Haofei; Yang, Jiaolong; Cai, Jianfei; Zhang, Juyong; Tong, Xin (2021-08-29). "High-Resolution Optical Flow from 1D Attention and Correlation". [arXiv](./ArXiv_(identifier)):[2104.13918](https://arxiv.org/abs/2104.13918) [[cs.CV](https://arxiv.org/archive/cs.CV)].
22. [↑](./Optical_flow#cite_ref-22) Xu, Gangwei; Chen, Shujun; Jia, Hao; Feng, Miaojie; Yang, Xin (2025-03-04). "Memory-Efficient Optical Flow via Radius-Distribution Orthogonal Cost Volume". [arXiv](./ArXiv_(identifier)):[2312.03790](https://arxiv.org/abs/2312.03790) [[cs.CV](https://arxiv.org/archive/cs.CV)].
23. [↑](./Optical_flow#cite_ref-23) Bargatin, Vladislav; Chistov, Egor; Yakovenko, Alexander; Vatolin, Dmitriy (2025-06-29). "MEMFOF: High-Resolution Training for Memory-Efficient Multi-Frame Optical Flow Estimation". [arXiv](./ArXiv_(identifier)):[2506.23151](https://arxiv.org/abs/2506.23151) [[cs.CV](https://arxiv.org/archive/cs.CV)].
24. [↑](./Optical_flow#cite_ref-24) Mayer, Nikolaus; Ilg, Eddy; Häusser, Philip; Fischer, Philipp; Cremers, Daniel; Dosovitskiy, Alexey; Brox, Thomas (2015-12-07). "A Large Dataset to Train Convolutional Networks for Disparity, Optical Flow, and Scene Flow Estimation". *2016 IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*. pp. 4040–4048. [arXiv](./ArXiv_(identifier)):[1512.02134](https://arxiv.org/abs/1512.02134). [doi](./Doi_(identifier)):[10.1109/CVPR.2016.438](https://doi.org/10.1109%2FCVPR.2016.438). [ISBN](./ISBN_(identifier)) [978-1-4673-8851-1](./Special:BookSources/978-1-4673-8851-1).
25. [↑](./Optical_flow#cite_ref-25) Tu, Zhigang; Xie, Wei; Zhang, Dejun; Poppe, Ronald; Veltkamp, Remco C.; Li, Baoxin; Yuan, Junsong (1 March 2019). "A survey of variational and CNN-based optical flow techniques". *Signal Processing: Image Communication*. **72**: 9–24. [doi](./Doi_(identifier)):[10.1016/j.image.2018.12.002](https://doi.org/10.1016%2Fj.image.2018.12.002). [hdl](./Hdl_(identifier)):[1874/379559](https://hdl.handle.net/1874%2F379559).
26. [↑](./Optical_flow#cite_ref-26) Butler, Daniel J.; Wulff, Jonas; Stanley, Garrett B.; Black, Michael J. (2012). ["A Naturalistic Open Source Movie for Optical Flow Evaluation"](https://link.springer.com/chapter/10.1007/978-3-642-33783-3_44). In Fitzgibbon, Andrew; Lazebnik, Svetlana; Perona, Pietro; Sato, Yoichi; Schmid, Cordelia (eds.). *Computer Vision – ECCV 2012*. Lecture Notes in Computer Science. Vol. 7577. Berlin, Heidelberg: Springer. pp. 611–625. [doi](./Doi_(identifier)):[10.1007/978-3-642-33783-3_44](https://doi.org/10.1007%2F978-3-642-33783-3_44). [ISBN](./ISBN_(identifier)) [978-3-642-33783-3](./Special:BookSources/978-3-642-33783-3).
27. [↑](./Optical_flow#cite_ref-27) Menze, Moritz; Geiger, Andreas (2015). "Object scene flow for autonomous vehicles". *2015 IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*. pp. 3061–3070. [doi](./Doi_(identifier)):[10.1109/CVPR.2015.7298925](https://doi.org/10.1109%2FCVPR.2015.7298925). [ISBN](./ISBN_(identifier)) [978-1-4673-6964-0](./Special:BookSources/978-1-4673-6964-0).
28. [↑](./Optical_flow#cite_ref-28) Mehl, Lukas; Schmalfuss, Jenny; Jahedi, Azin; Nalivayko, Yaroslava; Bruhn, Andrés (2023-03-03). "Spring: A High-Resolution High-Detail Dataset and Benchmark for Scene Flow, Optical Flow and Stereo". [arXiv](./ArXiv_(identifier)):[2303.01943](https://arxiv.org/abs/2303.01943) [[cs.CV](https://arxiv.org/archive/cs.CV)].
29. [↑](./Optical_flow#cite_ref-29) Jonschkowski, Rico; Stone, Austin; Barron, Jonathan T.; Gordon, Ariel; Konolige, Kurt; Angelova, Anelia (2020). "What Matters in Unsupervised Optical Flow". *Computer Vision – ECCV 2020*. Lecture Notes in Computer Science. Vol. 12347. Cham: Springer International Publishing. pp. 557–572. [arXiv](./ArXiv_(identifier)):[2006.04902](https://arxiv.org/abs/2006.04902). [doi](./Doi_(identifier)):[10.1007/978-3-030-58536-5_33](https://doi.org/10.1007%2F978-3-030-58536-5_33). [ISBN](./ISBN_(identifier)) [978-3-030-58536-5](./Special:BookSources/978-3-030-58536-5).
30. [↑](./Optical_flow#cite_ref-30) Weinzaepfel, Philippe; Lucas, Thomas; Leroy, Vincent; Cabon, Yohann; Arora, Vaibhav; Brégier, Romain; Csurka, Gabriela; Antsfeld, Leonid; Chidlovskii, Boris (2023-08-18). "CroCo v2: Improved Cross-view Completion Pre-training for Stereo Matching and Optical Flow". [arXiv](./ArXiv_(identifier)):[2211.10408](https://arxiv.org/abs/2211.10408) [[cs.CV](https://arxiv.org/archive/cs.CV)].
31. [↑](./Optical_flow#cite_ref-31) [Corke, Peter](./Peter_Corke) (8 May 2017). ["The Image Jacobian"](https://robotacademy.net.au/lesson/the-image-jacobian/). *QUT Robot Academy*.
32. [↑](./Optical_flow#cite_ref-32) Barrows, G. L.; Chahl, J. S.; Srinivasan, M. V. (2003). ["Biologically inspired visual sensing and flight control"](https://www.cambridge.org/core/journals/aeronautical-journal/article/biologically-inspired-visual-sensing-and-flight-control/0B3884D11BB0A54C2A196BF57162C153). *Aeronautical Journal*. **107** (1069): 159–268. [doi](./Doi_(identifier)):[10.1017/S0001924000011891](https://doi.org/10.1017%2FS0001924000011891). [S2CID](./S2CID_(identifier)) [108782688](https://api.semanticscholar.org/CorpusID:108782688) – via Cambridge University Press.
33. [↑](./Optical_flow#cite_ref-33) Brown, Christopher M. (1987). [*Advances in Computer Vision*](https://books.google.com/books?id=c97huisjZYYC&pg=PA133&dq=%22optic%2Bflow%22). Lawrence Erlbaum Associates. [ISBN](./ISBN_(identifier)) [978-0-89859-648-9](./Special:BookSources/978-0-89859-648-9).
34. [↑](./Optical_flow#cite_ref-Alfarano2024_34-0)  
35. [↑](./Optical_flow#cite_ref-35) Mendes, Luís P. N.; Ricardo, Ana M. C.; Bernardino, Alexandre J. M.; Ferreira, Rui M. L. (15 December 2021). ["A comparative study of optical flow methods for fluid mechanics"](https://link.springer.com/article/10.1007/s00348-021-03357-7). *Experiments in Fluids*. **63** (1): 7. [doi](./Doi_(identifier)):[10.1007/s00348-021-03357-7](https://doi.org/10.1007%2Fs00348-021-03357-7). [ISSN](./ISSN_(identifier)) [1432-1114](https://search.worldcat.org/issn/1432-1114).
36. [↑](./Optical_flow#cite_ref-36) Jassal, Gauresh Raj; Schmidt, Bryan E. (2025-02-10). ["A review of optical flow velocimetry in fluid mechanics"](https://iop.org). *Measurement Science and Technology*. **36** (3): 032002. [Bibcode](./Bibcode_(identifier)):[2025MeScT..36c2002J](https://ui.adsabs.harvard.edu/abs/2025MeScT..36c2002J). [doi](./Doi_(identifier)):[10.1088/1361-6501/adafcf](https://doi.org/10.1088%2F1361-6501%2Fadafcf).
37. [↑](./Optical_flow#cite_ref-37) Moini, Alireza (2000). *Vision Chips*. Boston, MA: Springer US. [ISBN](./ISBN_(identifier)) [9781461552673](./Special:BookSources/9781461552673). [OCLC](./OCLC_(identifier)) [851803922](https://search.worldcat.org/oclc/851803922).
38. [↑](./Optical_flow#cite_ref-38) Mead, Carver (1989). [*Analog VLSI and neural systems*](https://archive.org/details/analogvlsineural00mead). Reading, Mass.: Addison-Wesley. [ISBN](./ISBN_(identifier)) [0201059924](./Special:BookSources/0201059924). [OCLC](./OCLC_(identifier)) [17954003](https://search.worldcat.org/oclc/17954003).
39. [↑](./Optical_flow#cite_ref-39) Stocker, Alan A. (2006). *Analog VLSI circuits for the perception of visual motion*. Chichester, England: John Wiley & Sons. [ISBN](./ISBN_(identifier)) [0470034882](./Special:BookSources/0470034882). [OCLC](./OCLC_(identifier)) [71521689](https://search.worldcat.org/oclc/71521689).
40. [↑](./Optical_flow#cite_ref-40) Floreano, Dario; Zufferey, Jean-Christophe; Srinivasan, Mandyam V.; Ellington, Charlie, eds. (2009). *Flying insects and robots*. Heidelberg: Springer. [ISBN](./ISBN_(identifier)) [9783540893936](./Special:BookSources/9783540893936). [OCLC](./OCLC_(identifier)) [495477442](https://search.worldcat.org/oclc/495477442).
41. [1](./Optical_flow#cite_ref-:3_41-0) [2](./Optical_flow#cite_ref-:3_41-1) Niehorster, Diederick C. (2021). ["Optic Flow: A History"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8652193). *i-Perception*. **12** (6) 20416695211055766. [doi](./Doi_(identifier)):[10.1177/20416695211055766](https://doi.org/10.1177%2F20416695211055766). [ISSN](./ISSN_(identifier)) [2041-6695](https://search.worldcat.org/issn/2041-6695). [PMC](./PMC_(identifier)) [8652193](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8652193). [PMID](./PMID_(identifier)) [34900212](https://pubmed.ncbi.nlm.nih.gov/34900212).
42. [↑](./Optical_flow#cite_ref-42) Gibson, James Jerome (1947). [*Motion Picture Testing and Research*](https://books.google.com/books?id=dzdaAAAAYAAJ). Aviation Psychology Program Research Reports. Washington, D.C.: U.S. Government Printing Office. Retrieved 4 March 2026.
43. [↑](./Optical_flow#cite_ref-:2_43-0) Gibson, J.J. (1950). *The Perception of the Visual World*. Houghton Mifflin.
44. [↑](./Optical_flow#cite_ref-44) Gibson, James J.; Olum, Paul; Rosenblatt, Frank (1955). ["Parallax and Perspective during Aircraft Landings"](https://www.jstor.org/stable/1418521). *The American Journal of Psychology*. **68** (3): 372–385. [doi](./Doi_(identifier)):[10.2307/1418521](https://doi.org/10.2307%2F1418521). [JSTOR](./JSTOR_(identifier)) [1418521](https://www.jstor.org/stable/1418521). [PMID](./PMID_(identifier)) [13248971](https://pubmed.ncbi.nlm.nih.gov/13248971).
45. [↑](./Optical_flow#cite_ref-45) Royden, C. S.; Moore, K. D. (2012). ["Use of speed cues in the detection of moving objects by moving observers"](https://doi.org/10.1016%2Fj.visres.2012.02.006). *Vision Research*. **59**: 17–24. [doi](./Doi_(identifier)):[10.1016/j.visres.2012.02.006](https://doi.org/10.1016%2Fj.visres.2012.02.006). [PMID](./PMID_(identifier)) [22406544](https://pubmed.ncbi.nlm.nih.gov/22406544). [S2CID](./S2CID_(identifier)) [52847487](https://api.semanticscholar.org/CorpusID:52847487).

 

## External links

   [![Wikimedia Commons logo](//upload.wikimedia.org/wikipedia/en/thumb/4/4a/Commons-logo.svg/40px-Commons-logo.svg.png)](./File:Commons-logo.svg) Wikimedia Commons has media related to [Optic flow](https://commons.wikimedia.org/wiki/Category:Optic%20flow).  
- [Finding Optic Flow](http://users.fmrib.ox.ac.uk/~steve/review/review/node1.html#SECTION00010000000000000000)
- [Art of Optical Flow](http://www.fxguide.com/featured/art_of_optical_flow/) article on fxguide.com (using optical flow in visual effects)
- [Optical flow evaluation and ground truth sequences.](https://of-eval.sourceforge.net/)
- [Middlebury Optical flow evaluation and ground truth sequences.](http://vision.middlebury.edu/flow/)
- [mrf-registration.net](http://www.mrf-registration.net/) - Optical flow estimation through [MRF](./Markov_Random_Field)
- [The French Aerospace Lab:](https://web.archive.org/web/20091014150930/http://www.onera.fr/dtim-en/gpu-for-image/folkigpu.php) GPU implementation of a Lucas-Kanade based optical flow
- [CUDA Implementation](https://web.archive.org/web/20111102071946/http://www.cuvilib.com/features/motion-estimation/) by CUVI (CUDA Vision & Imaging Library)
- [Horn and Schunck Optical Flow:](http://www.ipol.im/pub/art/2013/20/) Online demo and source code of the Horn and Schunck method
- [TV-L1 Optical Flow:](http://www.ipol.im/pub/art/2013/26/) Online demo and source code of the Zach et al. method
- [Robust Optical Flow:](http://www.ipol.im/pub/art/2013/21/) Online demo and source code of the Brox et al. method