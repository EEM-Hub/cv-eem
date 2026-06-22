---
source: sources/wiki-Image_segmentation.md
source_url: https://en.wikipedia.org/wiki/Image_segmentation
chunk: 3/5
---

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

 


