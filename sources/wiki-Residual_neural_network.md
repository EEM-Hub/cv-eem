---
source: https://en.wikipedia.org/wiki/Residual_neural_network
fetched: 2026-06-21
---

Type of artificial neural network "ResNet" redirects here. For other uses, see [ResNet (disambiguation)](./ResNet_(disambiguation)). [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/ba/ResBlock.png/250px-ResBlock.png)](./File:ResBlock.png)A residual block in a deep residual network. Here, the residual connection skips two layers. 

A **residual neural network** (also referred to as a **residual network** or **ResNet**)[[1]](./Residual_neural_network#cite_note-resnet-1) is a [deep learning](./Deep_learning) architecture in which the layers learn residual functions with reference to the layer inputs. It was developed in 2015 for [image recognition](./Image_recognition), and won the [ImageNet](./ImageNet) Large Scale Visual Recognition Challenge ([ILSVRC](https://image-net.org/challenges/LSVRC/)) of that year.[[2]](./Residual_neural_network#cite_note-ilsvrc2015-2)[[3]](./Residual_neural_network#cite_note-imagenet-3)

 

As a point of terminology, "residual connection" refers to the specific architectural motif of     x ↦ ↦  f ( x ) + x   {\displaystyle x\mapsto f(x)+x}  ![{\displaystyle x\mapsto f(x)+x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c9ce5caa1d71c263eddc969f5501804aad6fd3ec), where     f   {\displaystyle f}  ![{\displaystyle f}](https://wikimedia.org/api/rest_v1/media/math/render/svg/132e57acb643253e7810ee9702d9581f159a1c61) is an arbitrary neural network module. The motif had been used previously (see [§History](./Residual_neural_network#History) for details). However, the publication of ResNet made it widely popular for [feedforward networks](./Feedforward_neural_network), appearing in neural networks that are seemingly unrelated to ResNet.

 

The residual connection stabilizes the training and convergence of deep neural networks with hundreds of layers, and is a common motif in deep neural networks, such as [transformer](./Transformer_(deep_learning_architecture)) models (e.g., [BERT](./BERT_(language_model)), and [GPT](./Generative_pre-trained_transformer) models such as [ChatGPT](./ChatGPT)), the [AlphaGo Zero](./AlphaGo_Zero) system, the [AlphaStar](./AlphaStar_(software)) system, and the [AlphaFold](./AlphaFold) system.

 

## Mathematics

 

### Residual connection

 

In a multilayer neural network model, consider a (non-residual) subnetwork with a certain number of stacked layers (e.g., 2 or 3). Let     H ( x ; α α  )   {\displaystyle H(x;\alpha )}  ![{\displaystyle H(x;\alpha )}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3c8c5be74cacf8c64e9519cc608b859cc83dcd69) denote the subnetwork. Suppose      H  ∗ ∗      {\displaystyle H^{*}}  ![{\displaystyle H^{*}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8ea7c513e82e824fda85563a940fbc2dc131fc4) is the desired optimal output of this subnetwork. Residual learning simply adds     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) directly to the output, such that the optimal learned output now becomes      H  ∗ ∗    − −  x   {\displaystyle H^{*}-x}  ![{\displaystyle H^{*}-x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/776b2e20d0c285e763c2af0d83faf3f5a8fdafe3), which is interpreted as a "residual" with respect to     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4).

 

The operation of "adding     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4)" is implemented via a "skip connection" that performs an identity mapping to connect the input of the subnetwork with its output. This connection is referred to as a "residual connection" in later work.

 

Let     F ( x ; α α  ) = H ( x ; a ) + x   {\displaystyle F(x;\alpha )=H(x;a)+x}  ![{\displaystyle F(x;\alpha )=H(x;a)+x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d3f95f89e4d44204e44465eaac99ae23801b3e1c). The function     F   {\displaystyle F}  ![{\displaystyle F}](https://wikimedia.org/api/rest_v1/media/math/render/svg/545fd099af8541605f7ee55f08225526be88ce57) is often represented by matrix multiplication interlaced with [activation functions](./Activation_function) and normalization operations (e.g., [batch normalization](./Batch_normalization) or [layer normalization](./Normalization_(machine_learning)#Layer_normalization)). As a whole, one of these subnetworks is referred to as a "residual block".[[1]](./Residual_neural_network#cite_note-resnet-1) A deep residual network is constructed by simply stacking these blocks.

 

[Long short-term memory](./Long_short-term_memory) (LSTM) has a memory mechanism that serves as a residual connection.[[4]](./Residual_neural_network#cite_note-lstm1997-4) In an LSTM without a forget [gate](./Gating_mechanism), an input      x  t     {\displaystyle x_{t}}  ![{\displaystyle x_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f279a30bc8eabc788f3fe81c9cfb674e72e858db) is processed by a function     F   {\displaystyle F}  ![{\displaystyle F}](https://wikimedia.org/api/rest_v1/media/math/render/svg/545fd099af8541605f7ee55f08225526be88ce57) and added to a memory cell      c  t     {\displaystyle c_{t}}  ![{\displaystyle c_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/93578e37f3234419a34df79845836bc0ec5ef76c), resulting in      c  t + 1   =  c  t   + F (  x  t   )   {\displaystyle c_{t+1}=c_{t}+F(x_{t})}  ![{\displaystyle c_{t+1}=c_{t}+F(x_{t})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/73d44bdefbabb949b35083ee270ce23b541fab34). An LSTM with a forget gate essentially functions as a [highway network](./Highway_network).

 

To stabilize the [variance](./Variance) of the layers' inputs, it is recommended to replace the residual connections     x + f ( x )   {\displaystyle x+f(x)}  ![{\displaystyle x+f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1636566acc3bf415c7ce092c9f727f4094dcad3f) with     x  /  L + f ( x )   {\displaystyle x/L+f(x)}  ![{\displaystyle x/L+f(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7735805308d2f1ebece5a039970a9e72f5ab45e8), where     L   {\displaystyle L}  ![{\displaystyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/103168b86f781fe6e9a4a87b8ea1cebe0ad4ede8) is the total number of residual layers.[[5]](./Residual_neural_network#cite_note-5)

 

### Projection connection

 

If the function     F   {\displaystyle F}  ![{\displaystyle F}](https://wikimedia.org/api/rest_v1/media/math/render/svg/545fd099af8541605f7ee55f08225526be88ce57) is of type     F :   R   n   → →    R   m     {\displaystyle F:\mathbb {R} ^{n}\to \mathbb {R} ^{m}}  ![{\displaystyle F:\mathbb {R} ^{n}\to \mathbb {R} ^{m}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ce4e55aadeaa9c838a71166dce4477f4ce9a6ce2) where     n ≠ ≠  m   {\displaystyle n\neq m}  ![{\displaystyle n\neq m}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3994a24401e2dfabca26e4f36e53097a07a57af5), then     F ( x ) + x   {\displaystyle F(x)+x}  ![{\displaystyle F(x)+x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/82306dd17830de33a8bb33a6625322ba317ad6e2) is undefined. To handle this special case, a projection connection is used:

 

    y = F ( x ) + P ( x )   {\displaystyle y=F(x)+P(x)}  ![{\displaystyle y=F(x)+P(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/e51ed489385892b4377872fd523737eb35de8cf9)

 

where     P   {\displaystyle P}  ![{\displaystyle P}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b4dc73bf40314945ff376bd363916a738548d40a) is typically a linear projection, defined by     P ( x ) = M x   {\displaystyle P(x)=Mx}  ![{\displaystyle P(x)=Mx}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9372dbfca0dc4cdd37a9a430d5f38dd74762c85c) where     M   {\displaystyle M}  ![{\displaystyle M}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f82cade9898ced02fdd08712e5f0c0151758a0dd) is a     m × ×  n   {\displaystyle m\times n}  ![{\displaystyle m\times n}](https://wikimedia.org/api/rest_v1/media/math/render/svg/12b23d207d23dd430b93320539abbb0bde84870d) matrix. The matrix is trained via [backpropagation](./Backpropagation), as is any other parameter of the model.

 

### Signal propagation

 

The introduction of identity mappings facilitates signal propagation in both forward and backward paths.[[6]](./Residual_neural_network#cite_note-resnetv2-6)

 

#### Forward propagation

 

If the output of the     ℓ ℓ    {\displaystyle \ell }  ![{\displaystyle \ell }](https://wikimedia.org/api/rest_v1/media/math/render/svg/f066e981e530bacc07efc6a10fa82deee985929e)-th residual block is the input to the     ( ℓ ℓ  + 1 )   {\displaystyle (\ell +1)}  ![{\displaystyle (\ell +1)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e04cef624cd31431d7030278d479e8f19d65a87)-th residual block (assuming no activation function between blocks), then the     ( ℓ ℓ  + 1 )   {\displaystyle (\ell +1)}  ![{\displaystyle (\ell +1)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/6e04cef624cd31431d7030278d479e8f19d65a87)-th input is:

 

     x  ℓ ℓ  + 1   = F (  x  ℓ ℓ    ) +  x  ℓ ℓ      {\displaystyle x_{\ell +1}=F(x_{\ell })+x_{\ell }}  ![{\displaystyle x_{\ell +1}=F(x_{\ell })+x_{\ell }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/5381463a54dc896c6478ef42b326c51ea16c04ba)

 

Applying this formulation recursively, e.g.:

 

         x  ℓ ℓ  + 2      = F (  x  ℓ ℓ  + 1   ) +  x  ℓ ℓ  + 1         = F (  x  ℓ ℓ  + 1   ) + F (  x  ℓ ℓ    ) +  x  ℓ ℓ          {\displaystyle {\begin{aligned}x_{\ell +2}&=F(x_{\ell +1})+x_{\ell +1}\\&=F(x_{\ell +1})+F(x_{\ell })+x_{\ell }\end{aligned}}}  ![{\displaystyle {\begin{aligned}x_{\ell +2}&=F(x_{\ell +1})+x_{\ell +1}\\&=F(x_{\ell +1})+F(x_{\ell })+x_{\ell }\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/782f0d61edb959b3388cdaf33dd4cc692ff88d5f)

 

yields the general relationship:

 

     x  L   =  x  ℓ ℓ    +  ∑ ∑   i = ℓ ℓ    L − −  1   F (  x  i   )   {\displaystyle x_{L}=x_{\ell }+\sum _{i=\ell }^{L-1}F(x_{i})}  ![{\displaystyle x_{L}=x_{\ell }+\sum _{i=\ell }^{L-1}F(x_{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/ed464f3e25e72e1036b88a36a58fc269fda3e60d)

 

where     L   {\textstyle L}  ![{\textstyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8fb88de7e4d31737dae8f02575033272f29e6720) is the index of a residual block and     ℓ ℓ    {\textstyle \ell }  ![{\textstyle \ell }](https://wikimedia.org/api/rest_v1/media/math/render/svg/554d626bee80ffdb3ab924a78a2d05c5a9e642db) is the index of some earlier block. This formulation suggests that there is always a signal that is directly sent from a shallower block     ℓ ℓ    {\textstyle \ell }  ![{\textstyle \ell }](https://wikimedia.org/api/rest_v1/media/math/render/svg/554d626bee80ffdb3ab924a78a2d05c5a9e642db) to a deeper block     L   {\textstyle L}  ![{\textstyle L}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8fb88de7e4d31737dae8f02575033272f29e6720).

 

#### Backward propagation

 

The residual learning formulation provides the added benefit of mitigating the [vanishing gradient problem](./Vanishing_gradient_problem) to some extent. However, it is crucial to acknowledge that the vanishing gradient issue is not the root cause of the degradation problem, which is tackled through the use of normalization. To observe the effect of residual blocks on backpropagation, consider the partial derivative of a [loss function](./Loss_functions_for_classification)       E     {\displaystyle {\mathcal {E}}}  ![{\displaystyle {\mathcal {E}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9c298ed828ff778065aeb5f0f305097f55bb9ae0) with respect to some residual block input      x  ℓ ℓ      {\displaystyle x_{\ell }}  ![{\displaystyle x_{\ell }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/3053f1eff42f8fec1d692efa1d5e0eee60c12b30). Using the equation above from forward propagation for a later residual block     L > ℓ ℓ    {\displaystyle L>\ell }  ![{\displaystyle L>\ell }](https://wikimedia.org/api/rest_v1/media/math/render/svg/55c2ccc0b11cc989eb580b34fcc306d18d4bcc5e):[[6]](./Residual_neural_network#cite_note-resnetv2-6)

 

           ∂ ∂    E     ∂ ∂   x  ℓ ℓ          =    ∂ ∂    E     ∂ ∂   x  L         ∂ ∂   x  L     ∂ ∂   x  ℓ ℓ             =    ∂ ∂    E     ∂ ∂   x  L       (  1 +   ∂ ∂   ∂ ∂   x  ℓ ℓ        ∑ ∑   i = ℓ ℓ    L − −  1   F (  x  i   )  )        =    ∂ ∂    E     ∂ ∂   x  L      +    ∂ ∂    E     ∂ ∂   x  L        ∂ ∂   ∂ ∂   x  ℓ ℓ        ∑ ∑   i = ℓ ℓ    L − −  1   F (  x  i   )       {\displaystyle {\begin{aligned}{\frac {\partial {\mathcal {E}}}{\partial x_{\ell }}}&={\frac {\partial {\mathcal {E}}}{\partial x_{L}}}{\frac {\partial x_{L}}{\partial x_{\ell }}}\\&={\frac {\partial {\mathcal {E}}}{\partial x_{L}}}\left(1+{\frac {\partial }{\partial x_{\ell }}}\sum _{i=\ell }^{L-1}F(x_{i})\right)\\&={\frac {\partial {\mathcal {E}}}{\partial x_{L}}}+{\frac {\partial {\mathcal {E}}}{\partial x_{L}}}{\frac {\partial }{\partial x_{\ell }}}\sum _{i=\ell }^{L-1}F(x_{i})\end{aligned}}}  ![{\displaystyle {\begin{aligned}{\frac {\partial {\mathcal {E}}}{\partial x_{\ell }}}&={\frac {\partial {\mathcal {E}}}{\partial x_{L}}}{\frac {\partial x_{L}}{\partial x_{\ell }}}\\&={\frac {\partial {\mathcal {E}}}{\partial x_{L}}}\left(1+{\frac {\partial }{\partial x_{\ell }}}\sum _{i=\ell }^{L-1}F(x_{i})\right)\\&={\frac {\partial {\mathcal {E}}}{\partial x_{L}}}+{\frac {\partial {\mathcal {E}}}{\partial x_{L}}}{\frac {\partial }{\partial x_{\ell }}}\sum _{i=\ell }^{L-1}F(x_{i})\end{aligned}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f2f8d63293b43f4715d382dd1ab800d7f6fc69e1)

 

This formulation suggests that the gradient computation of a shallower layer,        ∂ ∂    E     ∂ ∂   x  ℓ ℓ         {\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{\ell }}}}  ![{\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{\ell }}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75de64c2cb5928655ac6775b47fe44b930f3d138), always has a later term        ∂ ∂    E     ∂ ∂   x  L        {\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{L}}}}  ![{\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{L}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/28364496b63442451b27ef8651ca8130f4c5b79f) that is directly added. Even if the gradients of the     F (  x  i   )   {\displaystyle F(x_{i})}  ![{\displaystyle F(x_{i})}](https://wikimedia.org/api/rest_v1/media/math/render/svg/54290e388c0dd2693499b3e01585c9755079c16c) terms are small, the total gradient        ∂ ∂    E     ∂ ∂   x  ℓ ℓ         {\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{\ell }}}}  ![{\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{\ell }}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75de64c2cb5928655ac6775b47fe44b930f3d138) resists vanishing due to the added term        ∂ ∂    E     ∂ ∂   x  L        {\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{L}}}}  ![{\textstyle {\frac {\partial {\mathcal {E}}}{\partial x_{L}}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/28364496b63442451b27ef8651ca8130f4c5b79f).

 

## Variants of residual blocks

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/86/ResBlockVariants.png/250px-ResBlockVariants.png)](./File:ResBlockVariants.png)Two variants of convolutional Residual Blocks.[[1]](./Residual_neural_network#cite_note-resnet-1) **Left**: a *basic block* that has two 3x3 convolutional layers. **Right**: a *bottleneck block* that has a 1x1 convolutional layer for dimension reduction, a 3x3 convolutional layer, and another 1x1 convolutional layer for dimension restoration. 

### Basic block

 

A *basic block* is the simplest building block studied in the original ResNet.[[1]](./Residual_neural_network#cite_note-resnet-1) This block consists of two sequential 3x3 [convolutional](./Convolutional_neural_network) layers and a residual connection. The input and output dimensions of both layers are equal.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b3/ResNet_block.svg/250px-ResNet_block.svg.png)](./File:ResNet_block.svg)Block diagram of ResNet (2015). It shows a ResNet block with and without the 1x1 convolution. The 1x1 convolution (with stride) can be used to change the shape of the array, which is necessary for residual connection through an upsampling/downsampling layer. 

### Bottleneck block

 

A *bottleneck block*[[1]](./Residual_neural_network#cite_note-resnet-1) consists of three sequential convolutional layers and a residual connection. The first layer in this block is a 1×1 convolution for dimension reduction (e.g., to 1/2 of the input dimension); the second layer performs a 3×3 convolution; the last layer is another 1×1 convolution for dimension restoration. The models of ResNet-50, ResNet-101, and ResNet-152 are all based on bottleneck blocks.[[1]](./Residual_neural_network#cite_note-resnet-1)

 

### Pre-activation block

 

The *pre-activation residual block*[[6]](./Residual_neural_network#cite_note-resnetv2-6) applies activation functions before applying the residual function     F   {\displaystyle F}  ![{\displaystyle F}](https://wikimedia.org/api/rest_v1/media/math/render/svg/545fd099af8541605f7ee55f08225526be88ce57). Formally, the computation of a pre-activation residual block can be written as:

 

     x  ℓ ℓ  + 1   = F ( ϕ ϕ  (  x  ℓ ℓ    ) ) +  x  ℓ ℓ      {\displaystyle x_{\ell +1}=F(\phi (x_{\ell }))+x_{\ell }}  ![{\displaystyle x_{\ell +1}=F(\phi (x_{\ell }))+x_{\ell }}](https://wikimedia.org/api/rest_v1/media/math/render/svg/bc1bb6e183eaac49cde948630067c739fe28d254)

 

where     ϕ ϕ    {\displaystyle \phi }  ![{\displaystyle \phi }](https://wikimedia.org/api/rest_v1/media/math/render/svg/72b1f30316670aee6270a28334bdf4f5072cdde4) can be any activation (e.g. [ReLU](./ReLU)) or normalization (e.g. [LayerNorm](./LayerNorm)) operation. This design reduces the number of non-identity mappings between residual blocks, and allows an identity mapping directly from the input to the output. This design was used to train models with 200 to over 1000 layers, and was found to consistently outperform variants where the residual path is not an identity function. The pre-activation ResNet with 200 layers took 3 weeks to train for [ImageNet](./ImageNet) on 8 [GPUs](./Graphics_processing_unit) in 2016.[[6]](./Residual_neural_network#cite_note-resnetv2-6)

 

Since [GPT-2](./GPT-2), [transformer](./Transformer_(deep_learning_architecture)) blocks have been mostly implemented as pre-activation blocks. This is often referred to as "pre-normalization" in the literature of transformer models.[[7]](./Residual_neural_network#cite_note-gpt2paper-7)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Resnet-18_architecture.svg/250px-Resnet-18_architecture.svg.png)](./File:Resnet-18_architecture.svg)The original Resnet-18 architecture. Up to 152 layers were trained in the original publication (as "ResNet-152").[[8]](./Residual_neural_network#cite_note-:1-8) 

## Applications

Originally, ResNet was designed for [computer vision](./Computer_vision).[[1]](./Residual_neural_network#cite_note-resnet-1)[[8]](./Residual_neural_network#cite_note-:1-8)[[9]](./Residual_neural_network#cite_note-inceptionv42-9)

[![](//upload.wikimedia.org/wikipedia/commons/thumb/3/34/Transformer%2C_full_architecture.png/250px-Transformer%2C_full_architecture.png)](./File:Transformer,_full_architecture.png)The Transformer architecture includes residual connections. 

All transformer architectures include residual connections. Indeed, very deep transformers cannot be trained without them.[[10]](./Residual_neural_network#cite_note-lose_rank-10)

 

The original ResNet paper made no claim on being inspired by biological systems. However, later research has related ResNet to biologically-plausible algorithms.[[11]](./Residual_neural_network#cite_note-liao2016-11)[[12]](./Residual_neural_network#cite_note-xiao2018-12)

 

A study published in [*Science*](./Science_(journal)) in 2023[[13]](./Residual_neural_network#cite_note-Winding2023-13) disclosed the complete [connectome](./Connectome) of an insect brain (specifically that of a fruit fly larva). This study discovered "multilayer shortcuts" that resemble the skip connections in artificial neural networks, including ResNets.

 

## History

 

### Previous work

 

Residual connections were noticed in [neuroanatomy](./Neuroanatomy), such as [Lorente de No](./Rafael_Lorente_de_Nó) (1938).[[14]](./Residual_neural_network#cite_note-14): Fig 3  [McCulloch](./Warren_Sturgis_McCulloch) and [Pitts](./Walter_Pitts) (1943) proposed artificial neural networks and considered those with residual connections.[[15]](./Residual_neural_network#cite_note-15): Fig 1.h 

 

In 1961, [Frank Rosenblatt](./Frank_Rosenblatt) described a three-layer [multilayer perceptron](./Multilayer_perceptron) (MLP) model with skip connections.[[16]](./Residual_neural_network#cite_note-mlpbook-16): 313, Chapter 15  The model was referred to as a "cross-coupled system", and the skip connections were forms of cross-coupled connections.

During the late 1980s, "skip-layer" connections were sometimes used in neural networks. Examples include:[[17]](./Residual_neural_network#cite_note-17)[[18]](./Residual_neural_network#cite_note-massbook-18) Lang and Witbrock (1988)[[19]](./Residual_neural_network#cite_note-skip1988-19) trained a fully connected feedforward network where each layer skip-connects to all subsequent layers, like the later DenseNet (2016). In this work, the residual connection was the form     x ↦ ↦  F ( x ) + P ( x )   {\displaystyle x\mapsto F(x)+P(x)}  ![{\displaystyle x\mapsto F(x)+P(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/8c3dfe9d901cf5d246a3409679805d9a49108643), where     P   {\displaystyle P}  ![{\displaystyle P}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b4dc73bf40314945ff376bd363916a738548d40a) is a randomly-initialized projection connection. They termed it a "short-cut connection". An early neural language model used residual connections and named them "direct connections".[[20]](./Residual_neural_network#cite_note-20)

[![](//upload.wikimedia.org/wikipedia/commons/thumb/f/fd/LSTM_3.svg/330px-LSTM_3.svg.png)](./File:LSTM_3.svg)The long short-term memory (LSTM) cell can process data sequentially and keep its hidden state through time. The cell state      c  t     {\displaystyle c_{t}}  ![{\displaystyle c_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/93578e37f3234419a34df79845836bc0ec5ef76c) can function as a generalized residual connection. 

### Degradation problem

 

[Sepp Hochreiter](./Sepp_Hochreiter) discovered the [vanishing gradient problem](./Vanishing_gradient_problem) in 1991[[21]](./Residual_neural_network#cite_note-hochreiter1991-21) and argued that it explained why the then-prevalent forms of [recurrent neural networks](./Recurrent_neural_network) did not work for long sequences. He and [Schmidhuber](./Jürgen_Schmidhuber) later designed the LSTM architecture to solve this problem,[[4]](./Residual_neural_network#cite_note-lstm1997-4)[[22]](./Residual_neural_network#cite_note-lstm2000-22) which has a "cell state"      c  t     {\displaystyle c_{t}}  ![{\displaystyle c_{t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/93578e37f3234419a34df79845836bc0ec5ef76c) that can function as a generalized residual connection. The [highway network](./Highway_network) (2015)[[23]](./Residual_neural_network#cite_note-highway2015may-23)[[24]](./Residual_neural_network#cite_note-highway2015july-24) applied the idea of an LSTM [unfolded in time](./Recurrent_neural_network) to [feedforward neural networks](./Feedforward_neural_network), resulting in the highway network. ResNet is equivalent to an open-gated highway network.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b5/Recurrent_neural_network_unfold.svg/250px-Recurrent_neural_network_unfold.svg.png)](./File:Recurrent_neural_network_unfold.svg)Standard (left) and unfolded (right) basic recurrent neural network 

During the early days of deep learning, there were attempts to train increasingly deep models. Notable examples included the [AlexNet](./AlexNet) (2012), which had 8 layers, and the [VGG-19](./VGGNet) (2014), which had 19 layers.[[25]](./Residual_neural_network#cite_note-simonyan2015very-25) However, stacking too many layers led to a steep reduction in [training](./Training,_validation,_and_test_data_sets) accuracy,[[26]](./Residual_neural_network#cite_note-prelu-26) known as the "degradation" problem.[[1]](./Residual_neural_network#cite_note-resnet-1) In theory, adding additional layers to deepen a network should not result in a higher training [loss](./Loss_functions_for_classification), but this is what happened with [VGGNet](./VGGNet).[[1]](./Residual_neural_network#cite_note-resnet-1) If the extra layers can be set as [identity mappings](./Identity_mapping), however, then the deeper network would represent the same function as its shallower counterpart. There is some evidence that the optimizer is not able to approach identity mappings for the parameterized layers, and the benefit of residual connections was to allow identity mappings by default.[[6]](./Residual_neural_network#cite_note-resnetv2-6)

 

In 2014, the state of the art was training deep neural networks with 20 to 30 layers.[[25]](./Residual_neural_network#cite_note-simonyan2015very-25) The research team for ResNet attempted to train deeper ones by empirically testing various methods for training deeper networks, until they came upon the ResNet architecture.[[27]](./Residual_neural_network#cite_note-27)

 

### Subsequent work

 

**Wide Residual Network** (2016) found that using more channels and fewer layers than the original ResNet improves performance and GPU-computational efficiency, and that a block with two 3×3 convolutions is superior to other configurations of convolution blocks.[[28]](./Residual_neural_network#cite_note-28)

 

**DenseNet** (2016)[[29]](./Residual_neural_network#cite_note-29) connects the output of each layer to the input to each subsequent layer:

 

     x  ℓ ℓ  + 1   = F (  x  1   ,  x  2   , … …  ,  x  ℓ ℓ  − −  1   ,  x  ℓ ℓ    )   {\displaystyle x_{\ell +1}=F(x_{1},x_{2},\dots ,x_{\ell -1},x_{\ell })}  ![{\displaystyle x_{\ell +1}=F(x_{1},x_{2},\dots ,x_{\ell -1},x_{\ell })}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c70160e717bcf4ff486a0011b4bde13f37835329)

 

**Stochastic depth**[[30]](./Residual_neural_network#cite_note-30) is a [regularization](./Regularization_(mathematics)) method that randomly drops a subset of layers and lets the signal propagate through the identity skip connections. Also known as *DropPath*, this regularizes training for deep models, such as [vision transformers](./Vision_transformer).[[31]](./Residual_neural_network#cite_note-31)

[![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c3/ResNext_block.svg/250px-ResNext_block.svg.png)](./File:ResNext_block.svg)ResNeXt block diagram 

**ResNeXt** (2017) combines the [Inception module](./Inception_(deep_learning_architecture)) with ResNet.[[32]](./Residual_neural_network#cite_note-32)[[8]](./Residual_neural_network#cite_note-:1-8)

 

**Squeeze-and-Excitation Networks** (2018) added squeeze-and-excitation (SE) modules to ResNet.[[33]](./Residual_neural_network#cite_note-33) An SE module is applied after a convolution, and takes a tensor of shape       R   H × ×  W × ×  C     {\displaystyle \mathbb {R} ^{H\times W\times C}}  ![{\displaystyle \mathbb {R} ^{H\times W\times C}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/017d01e20d272f34402165cca04b85e2b6cb1a62) (height, width, channels) as input. Each channel is averaged, resulting in a vector of shape       R   C     {\displaystyle \mathbb {R} ^{C}}  ![{\displaystyle \mathbb {R} ^{C}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/81aec4687bbf2159e80b972672af27bd5dd0feac). This is then passed through a [multilayer perceptron](./Multilayer_perceptron) (with an architecture such as *linear-ReLU-linear-sigmoid*) before it is multiplied with the original tensor. It won the [ILSVRC](./ILSVRC) in 2017.[[34]](./Residual_neural_network#cite_note-34)

 

## References

 
1. [1](./Residual_neural_network#cite_ref-resnet_1-0) [2](./Residual_neural_network#cite_ref-resnet_1-1) [3](./Residual_neural_network#cite_ref-resnet_1-2) [4](./Residual_neural_network#cite_ref-resnet_1-3) [5](./Residual_neural_network#cite_ref-resnet_1-4) [6](./Residual_neural_network#cite_ref-resnet_1-5) [7](./Residual_neural_network#cite_ref-resnet_1-6) [8](./Residual_neural_network#cite_ref-resnet_1-7) [9](./Residual_neural_network#cite_ref-resnet_1-8) [He, Kaiming](./Kaiming_He); Zhang, Xiangyu; Ren, Shaoqing; Sun, Jian (2016). [*Deep Residual Learning for Image Recognition*](https://openaccess.thecvf.com/content_cvpr_2016/papers/He_Deep_Residual_Learning_CVPR_2016_paper.pdf) (PDF). [Conference on Computer Vision and Pattern Recognition](./Conference_on_Computer_Vision_and_Pattern_Recognition). [arXiv](./ArXiv_(identifier)):[1512.03385](https://arxiv.org/abs/1512.03385). [doi](./Doi_(identifier)):[10.1109/CVPR.2016.90](https://doi.org/10.1109%2FCVPR.2016.90).
2. [↑](./Residual_neural_network#cite_ref-ilsvrc2015_2-0) ["ILSVRC2015 Results"](https://image-net.org/challenges/LSVRC/2015/results.php). *image-net.org*.
3. [↑](./Residual_neural_network#cite_ref-imagenet_3-0) Deng, Jia; Dong, Wei; Socher, Richard; Li, Li-Jia; Li, Kai; [Li, Fei-Fei](./Fei-Fei_Li) (2009). *ImageNet: A large-scale hierarchical image database*. [Conference on Computer Vision and Pattern Recognition](./Conference_on_Computer_Vision_and_Pattern_Recognition). [doi](./Doi_(identifier)):[10.1109/CVPR.2009.5206848](https://doi.org/10.1109%2FCVPR.2009.5206848).
4. [1](./Residual_neural_network#cite_ref-lstm1997_4-0) [2](./Residual_neural_network#cite_ref-lstm1997_4-1) [Sepp Hochreiter](./Sepp_Hochreiter); [Jürgen Schmidhuber](./Jürgen_Schmidhuber) (1997). ["Long short-term memory"](https://www.researchgate.net/publication/13853244). *[Neural Computation](./Neural_Computation_(journal))*. **9** (8): 1735–1780. [doi](./Doi_(identifier)):[10.1162/neco.1997.9.8.1735](https://doi.org/10.1162%2Fneco.1997.9.8.1735). [PMID](./PMID_(identifier)) [9377276](https://pubmed.ncbi.nlm.nih.gov/9377276). [S2CID](./S2CID_(identifier)) [1915014](https://api.semanticscholar.org/CorpusID:1915014).
5. [↑](./Residual_neural_network#cite_ref-5) Hanin, Boris; Rolnick, David (2018). [*How to Start Training: The Effect of Initialization and Architecture*](https://proceedings.neurips.cc/paper/2018/hash/d81f9c1be2e08964bf9f24b15f0e4900-Paper.pdf) (PDF). [Conference on Neural Information Processing Systems](./Conference_on_Neural_Information_Processing_Systems). Vol. 31. Curran Associates, Inc. [arXiv](./ArXiv_(identifier)):[1803.01719](https://arxiv.org/abs/1803.01719).
6. [1](./Residual_neural_network#cite_ref-resnetv2_6-0) [2](./Residual_neural_network#cite_ref-resnetv2_6-1) [3](./Residual_neural_network#cite_ref-resnetv2_6-2) [4](./Residual_neural_network#cite_ref-resnetv2_6-3) [5](./Residual_neural_network#cite_ref-resnetv2_6-4) [He, Kaiming](./Kaiming_He); Zhang, Xiangyu; Ren, Shaoqing; Sun, Jian (2016). [*Identity Mappings in Deep Residual Networks*](https://link.springer.com/content/pdf/10.1007/978-3-319-46493-0_38.pdf) (PDF). [European Conference on Computer Vision](./European_Conference_on_Computer_Vision). [arXiv](./ArXiv_(identifier)):[1603.05027](https://arxiv.org/abs/1603.05027). [doi](./Doi_(identifier)):[10.1007/978-3-319-46493-0_38](https://doi.org/10.1007%2F978-3-319-46493-0_38).
7. [↑](./Residual_neural_network#cite_ref-gpt2paper_7-0) Radford, Alec; Wu, Jeffrey; Child, Rewon; Luan, David; Amodei, Dario; Sutskever, Ilya (14 February 2019). ["Language models are unsupervised multitask learners"](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf) (PDF). [Archived](https://web.archive.org/web/20210206183945/https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf) (PDF) from the original on 6 February 2021. Retrieved 19 December 2020.
8. [1](./Residual_neural_network#cite_ref-:1_8-0) [2](./Residual_neural_network#cite_ref-:1_8-1) [3](./Residual_neural_network#cite_ref-:1_8-2) Zhang, Aston; Lipton, Zachary; Li, Mu; Smola, Alexander J. (2024). ["8.6. Residual Networks (ResNet) and ResNeXt"](https://d2l.ai/chapter_convolutional-modern/resnet.html). *Dive into deep learning*. Cambridge New York Port Melbourne New Delhi Singapore: Cambridge University Press. [ISBN](./ISBN_(identifier)) [978-1-009-38943-3](./Special:BookSources/978-1-009-38943-3).
9. [↑](./Residual_neural_network#cite_ref-inceptionv42_9-0) Szegedy, Christian; Ioffe, Sergey; Vanhoucke, Vincent; Alemi, Alex (2017). [*Inception-v4, Inception-ResNet and the impact of residual connections on learning*](https://cdn.aaai.org/ojs/11231/11231-13-14759-1-2-20201228.pdf) (PDF). [AAAI Conference on Artificial Intelligence](./AAAI_Conference_on_Artificial_Intelligence). [arXiv](./ArXiv_(identifier)):[1602.07261](https://arxiv.org/abs/1602.07261). [doi](./Doi_(identifier)):[10.1609/aaai.v31i1.11231](https://doi.org/10.1609%2Faaai.v31i1.11231).
10. [↑](./Residual_neural_network#cite_ref-lose_rank_10-0) Dong, Yihe; Cordonnier, Jean-Baptiste; Loukas, Andreas (2021). [*Attention is not all you need: pure attention loses rank doubly exponentially with depth*](https://proceedings.mlr.press/v139/dong21a/dong21a.pdf) (PDF). [International Conference on Machine Learning](./International_Conference_on_Machine_Learning). PMLR. pp. 2793–2803. [arXiv](./ArXiv_(identifier)):[2103.03404](https://arxiv.org/abs/2103.03404).
11. [↑](./Residual_neural_network#cite_ref-liao2016_11-0)  Liao, Qianli; Poggio, Tomaso (2016). "Bridging the Gaps Between Residual Learning, Recurrent Neural Networks and Visual Cortex". [arXiv](./ArXiv_(identifier)):[1604.03640](https://arxiv.org/abs/1604.03640) [[cs.LG](https://arxiv.org/archive/cs.LG)].
12. [↑](./Residual_neural_network#cite_ref-xiao2018_12-0)  Xiao, Will; Chen, Honglin; Liao, Qianli; Poggio, Tomaso (2019). *Biologically-Plausible Learning Algorithms Can Scale to Large Datasets*. [International Conference on Learning Representations](./International_Conference_on_Learning_Representations). [arXiv](./ArXiv_(identifier)):[1811.03567](https://arxiv.org/abs/1811.03567).
13. [↑](./Residual_neural_network#cite_ref-Winding2023_13-0) Winding, Michael; Pedigo, Benjamin; Barnes, Christopher; Patsolic, Heather; Park, Youngser; Kazimiers, Tom; Fushiki, Akira; Andrade, Ingrid; Khandelwal, Avinash; Valdes-Aleman, Javier; Li, Feng; Randel, Nadine; Barsotti, Elizabeth; Correia, Ana; Fetter, Fetter; Hartenstein, Volker; Priebe, Carey; Vogelstein, Joshua; [Cardona, Albert](./Albert_Cardona); Zlatic, Marta (10 Mar 2023). ["The connectome of an insect brain"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7614541). *Science*. **379** (6636) eadd9330. [bioRxiv](./BioRxiv_(identifier)) [10.1101/2022.11.28.516756v1](https://doi.org/10.1101%2F2022.11.28.516756v1). [doi](./Doi_(identifier)):[10.1126/science.add9330](https://doi.org/10.1126%2Fscience.add9330). [PMC](./PMC_(identifier)) [7614541](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7614541). [PMID](./PMID_(identifier)) [36893230](https://pubmed.ncbi.nlm.nih.gov/36893230). [S2CID](./S2CID_(identifier)) [254070919](https://api.semanticscholar.org/CorpusID:254070919).
14. [↑](./Residual_neural_network#cite_ref-14) De N, Rafael Lorente (1938-05-01). ["Analysis of the Activity of the Chains of Internuncial Neurons"](https://www.physiology.org/doi/10.1152/jn.1938.1.3.207). *Journal of Neurophysiology*. **1** (3): 207–244. [doi](./Doi_(identifier)):[10.1152/jn.1938.1.3.207](https://doi.org/10.1152%2Fjn.1938.1.3.207). [ISSN](./ISSN_(identifier)) [0022-3077](https://search.worldcat.org/issn/0022-3077).
15. [↑](./Residual_neural_network#cite_ref-15) McCulloch, Warren S.; Pitts, Walter (1943-12-01). ["A logical calculus of the ideas immanent in nervous activity"](https://link.springer.com/article/10.1007/BF02478259). *The Bulletin of Mathematical Biophysics*. **5** (4): 115–133. [doi](./Doi_(identifier)):[10.1007/BF02478259](https://doi.org/10.1007%2FBF02478259). [ISSN](./ISSN_(identifier)) [1522-9602](https://search.worldcat.org/issn/1522-9602).
16. [↑](./Residual_neural_network#cite_ref-mlpbook_16-0)  Rosenblatt, Frank (1961). [*Principles of neurodynamics. perceptrons and the theory of brain mechanisms*](https://safari.ethz.ch/digitaltechnik/spring2018/lib/exe/fetch.php?media=neurodynamics1962rosenblatt.pdf#page=327) (PDF).
17. [↑](./Residual_neural_network#cite_ref-17) Rumelhart, David E., Geoffrey E. Hinton, and Ronald J. Williams. "Learning internal representations by error propagation", *Parallel Distributed Processing*. Vol. 1. 1986.
18. [↑](./Residual_neural_network#cite_ref-massbook_18-0) Venables, W. N.; Ripley, Brain D. (1994). [*Modern Applied Statistics with S-Plus*](https://books.google.com/books?id=ayDvAAAAMAAJ). Springer. pp. 261–262. [ISBN](./ISBN_(identifier)) [978-3-540-94350-1](./Special:BookSources/978-3-540-94350-1).
19. [↑](./Residual_neural_network#cite_ref-skip1988_19-0) Lang, Kevin; Witbrock, Michael (1988). ["Learning to tell two spirals apart"](https://gwern.net/doc/ai/nn/fully-connected/1988-lang.pdf) (PDF). *Proceedings of the 1988 Connectionist Models Summer School*: 52–59.
20. [↑](./Residual_neural_network#cite_ref-20) [Bengio, Yoshua](./Yoshua_Bengio); Ducharme, Réjean; Vincent, Pascal; Jauvin, Christian (2003). ["A Neural Probabilistic Language Model"](https://www.jmlr.org/papers/v3/bengio03a.html). *Journal of Machine Learning Research*. **3** (Feb): 1137–1155. [ISSN](./ISSN_(identifier)) [1533-7928](https://search.worldcat.org/issn/1533-7928).
21. [↑](./Residual_neural_network#cite_ref-hochreiter1991_21-0) Hochreiter, Sepp (1991). [*Untersuchungen zu dynamischen neuronalen Netzen*](https://www.bioinf.jku.at/publications/older/3804.pdf) (PDF) (diploma thesis). [Technical University of Munich](./Technical_University_of_Munich), Institute of Computer Science, advisor: J. Schmidhuber.
22. [↑](./Residual_neural_network#cite_ref-lstm2000_22-0) Felix A. Gers; Jürgen Schmidhuber; Fred Cummins (2000). "Learning to Forget: Continual Prediction with LSTM". *[Neural Computation](./Neural_Computation_(journal))*. **12** (10): 2451–2471. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.55.5709](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.55.5709). [doi](./Doi_(identifier)):[10.1162/089976600300015015](https://doi.org/10.1162%2F089976600300015015). [PMID](./PMID_(identifier)) [11032042](https://pubmed.ncbi.nlm.nih.gov/11032042). [S2CID](./S2CID_(identifier)) [11598600](https://api.semanticscholar.org/CorpusID:11598600).
23. [↑](./Residual_neural_network#cite_ref-highway2015may_23-0) Srivastava, Rupesh Kumar; Greff, Klaus; Schmidhuber, Jürgen (3 May 2015). "Highway Networks". [arXiv](./ArXiv_(identifier)):[1505.00387](https://arxiv.org/abs/1505.00387) [[cs.LG](https://arxiv.org/archive/cs.LG)].
24. [↑](./Residual_neural_network#cite_ref-highway2015july_24-0) Srivastava, Rupesh Kumar; Greff, Klaus; Schmidhuber, Jürgen (2015). [*Training Very Deep Networks*](https://proceedings.neurips.cc/paper/2015/file/215a71a12769b056c3c32e7299f1c5ed-Paper.pdf) (PDF). [Conference on Neural Information Processing Systems](./Conference_on_Neural_Information_Processing_Systems). [arXiv](./ArXiv_(identifier)):[1507.06228](https://arxiv.org/abs/1507.06228).
25. [1](./Residual_neural_network#cite_ref-simonyan2015very_25-0) [2](./Residual_neural_network#cite_ref-simonyan2015very_25-1) Simonyan, Karen; Zisserman, Andrew (2015-04-10). "Very Deep Convolutional Networks for Large-Scale Image Recognition". [arXiv](./ArXiv_(identifier)):[1409.1556](https://arxiv.org/abs/1409.1556) [[cs.CV](https://arxiv.org/archive/cs.CV)].
26. [↑](./Residual_neural_network#cite_ref-prelu_26-0) [He, Kaiming](./Kaiming_He); Zhang, Xiangyu; Ren, Shaoqing; Sun, Jian (2015). [*Delving Deep into Rectifiers: Surpassing Human-Level Performance on ImageNet Classification*](https://openaccess.thecvf.com/content_iccv_2015/papers/He_Delving_Deep_into_ICCV_2015_paper.pdf) (PDF). [International Conference on Computer Vision](./International_Conference_on_Computer_Vision). [arXiv](./ArXiv_(identifier)):[1502.01852](https://arxiv.org/abs/1502.01852). [doi](./Doi_(identifier)):[10.1109/ICCV.2015.123](https://doi.org/10.1109%2FICCV.2015.123).
27. [↑](./Residual_neural_network#cite_ref-27) Linn, Allison (2015-12-10). ["Microsoft researchers win ImageNet computer vision challenge"](https://blogs.microsoft.com/ai/microsoft-researchers-win-imagenet-computer-vision-challenge/). *The AI Blog*. Retrieved 2024-06-29.
28. [↑](./Residual_neural_network#cite_ref-28) Zagoruyko, Sergey; Komodakis, Nikos (2016-05-23). "Wide Residual Networks". [arXiv](./ArXiv_(identifier)):[1605.07146](https://arxiv.org/abs/1605.07146) [[cs.CV](https://arxiv.org/archive/cs.CV)].
29. [↑](./Residual_neural_network#cite_ref-29) Huang, Gao; Liu, Zhuang; van der Maaten, Laurens; Weinberger, Kilian (2017). [*Densely Connected Convolutional Networks*](https://openaccess.thecvf.com/content_cvpr_2017/papers/Huang_Densely_Connected_Convolutional_CVPR_2017_paper.pdf) (PDF). [Conference on Computer Vision and Pattern Recognition](./Conference_on_Computer_Vision_and_Pattern_Recognition). [arXiv](./ArXiv_(identifier)):[1608.06993](https://arxiv.org/abs/1608.06993). [doi](./Doi_(identifier)):[10.1109/CVPR.2017.243](https://doi.org/10.1109%2FCVPR.2017.243).
30. [↑](./Residual_neural_network#cite_ref-30) Huang, Gao; Sun, Yu; Liu, Zhuang; Weinberger, Kilian (2016). [*Deep Networks with Stochastic Depth*](https://link.springer.com/content/pdf/10.1007/978-3-319-46493-0_39.pdf) (PDF). [European Conference on Computer Vision](./European_Conference_on_Computer_Vision). [arXiv](./ArXiv_(identifier)):[1603.09382](https://arxiv.org/abs/1603.09382). [doi](./Doi_(identifier)):[10.1007/978-3-319-46493-0_39](https://doi.org/10.1007%2F978-3-319-46493-0_39).
31. [↑](./Residual_neural_network#cite_ref-31) Lee, Youngwan; Kim, Jonghee; Willette, Jeffrey; Hwang, Sung Ju (2022). [*MPViT: Multi-Path Vision Transformer for Dense Prediction*](https://openaccess.thecvf.com/content/CVPR2022/papers/Lee_MPViT_Multi-Path_Vision_Transformer_for_Dense_Prediction_CVPR_2022_paper.pdf) (PDF). [Conference on Computer Vision and Pattern Recognition](./Conference_on_Computer_Vision_and_Pattern_Recognition). pp. 7287–7296. [arXiv](./ArXiv_(identifier)):[2112.11010](https://arxiv.org/abs/2112.11010). [doi](./Doi_(identifier)):[10.1109/CVPR52688.2022.00714](https://doi.org/10.1109%2FCVPR52688.2022.00714).
32. [↑](./Residual_neural_network#cite_ref-32) Xie, Saining; Girshick, Ross; Dollar, Piotr; Tu, Zhuowen; [He, Kaiming](./Kaiming_He) (2017). [*Aggregated Residual Transformations for Deep Neural Networks*](https://openaccess.thecvf.com/content_cvpr_2017/papers/Xie_Aggregated_Residual_Transformations_CVPR_2017_paper.pdf) (PDF). [Conference on Computer Vision and Pattern Recognition](./Conference_on_Computer_Vision_and_Pattern_Recognition). pp. 1492–1500. [arXiv](./ArXiv_(identifier)):[1611.05431](https://arxiv.org/abs/1611.05431). [doi](./Doi_(identifier)):[10.1109/CVPR.2017.634](https://doi.org/10.1109%2FCVPR.2017.634).
33. [↑](./Residual_neural_network#cite_ref-33) Hu, Jie; Shen, Li; Sun, Gang (2018). [*Squeeze-and-Excitation Networks*](https://openaccess.thecvf.com/content_cvpr_2018/papers/Hu_Squeeze-and-Excitation_Networks_CVPR_2018_paper.pdf) (PDF). [Conference on Computer Vision and Pattern Recognition](./Conference_on_Computer_Vision_and_Pattern_Recognition). pp. 7132–7141. [arXiv](./ArXiv_(identifier)):[1709.01507](https://arxiv.org/abs/1709.01507). [doi](./Doi_(identifier)):[10.1109/CVPR.2018.00745](https://doi.org/10.1109%2FCVPR.2018.00745).
34. [↑](./Residual_neural_network#cite_ref-34) Jie, Hu (2017). [*Squeeze-and-Excitation Networks*](https://image-net.org/static_files/files/SENet.pdf) (PDF). Beyond ImageNet Large Scale Visual Recognition Challenge, Workshop at CVPR 2017 (Presentation).

 
| vteArtificial intelligence(AI) |
| --- |
| HistorytimelineGlossaryCompaniesProjectsList of open-source AI software |
| Concepts | Automated reasoningParameterHyperparameterLoss functionsRegressionBias–variance tradeoffDouble descentOverfittingClusteringGradient descentSGDQuasi-Newton methodConjugate gradient methodBackpropagationAttentionConvolutionNormalizationBatchnormActivationSoftmaxSigmoidRectifierGatingWeight initializationRegularizationDatasetsAugmentationPrompt engineeringReinforcement learningQ-learningSARSAImitationPolicy gradientDiffusionLatent diffusion modelAutoregressionAdversaryRAGUncanny valleyRLHFSelf-supervised learningReflectionRecursive self-improvementHallucinationWord embeddingVibe codingSymbolic AINeuro-symbolic AI |
| Applications | Automated theorem provingMachine learningIn-context learningArtificial neural networkDeep learningLanguage modelLargeNMTReasoningModel Context ProtocolIntelligent agentAI agentArtificial human companionHumanity's Last ExamLethal autonomous weapons (LAWs)Generative AIWeak AIHypotheticalArtificial general intelligence (AGI)Artificial superintelligence (ASI)Agent2Agent protocol |
| Implementations | Audio–visualAlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasisTextList of large language modelsProject DebaterIBM WatsonIBM WatsonxDecisionalAlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot controlReasoning systemsDeductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systemsCognitive architecturesACT-RSoarCLARIONLIDAOpenCogKnowledge basesConceptNetWikidataDBpediaYAGO | Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis | Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx | Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control | Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems | Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog | Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis |
| Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx |
| Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control |
| Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems |
| Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog |
| Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| People | Alan TuringWarren Sturgis McCullochWalter PittsJohn von NeumannChristopher D. ManningClaude ShannonShun'ichi AmariKunihiko FukushimaTakeo KanadeMarvin MinskyJohn McCarthyNathaniel RochesterAllen NewellCliff ShawHerbert A. SimonOliver SelfridgeFrank RosenblattBernard WidrowJoseph WeizenbaumSeymour PapertSeppo LinnainmaaPaul WerbosGeoffrey HintonJohn HopfieldJürgen SchmidhuberYann LeCunYoshua BengioLotfi A. ZadehStephen GrossbergAlex GravesJames GoodnightAndrew NgFei-Fei LiAlex KrizhevskyIlya SutskeverOriol VinyalsQuoc V. LeIan GoodfellowDemis HassabisDavid SilverAndrej KarpathyAshish VaswaniNoam ShazeerAidan GomezJohn SchulmanMustafa SuleymanJan LeikeDaniel KokotajloFrançois Chollet |
| Neural network architectures | Neural Turing machineDifferentiable neural computerTransformerVision transformer (ViT)Recurrent neural network (RNN)Long short-term memory (LSTM)Gated recurrent unit (GRU)Echo state networkMultilayer perceptron (MLP)Convolutional neural network (CNN)Residual neural network (RNN)Highway networkMambaAutoencoderVariational autoencoder (VAE)Generative adversarial network (GAN)Graph neural network (GNN) |
| Political | AI Cold WarAI safety(Alignment)AI takeoverElectionsEthics of AIEUAI ActNationalismPrecautionary principleRegulation of AIUSVirtual politicianPropaganda |
| Social and economic | AI boomAI bubbleAI data centerAI effectAI literacyAI slopAI veganismAI winterAnthropomorphismArms raceCompetitionEnvironmental impactExplainable AIGenerative engine optimizationIn architectureIn educationIn fictionIn healthcareChatbot psychosisIn marketingIn video gamesIn visual artMilitary applicationsAI warfareWorkplace impact |
| Category |