---
layout: page
title: Face Localization Using Active Shape Model
description: Project for undergraduate thesis
img: assets/img/face_localization_using_active_shape_model.gif
importance: 4
category: Research
---
Here’s the reformatted text:

---

The Active Shape Model (ASM) is a popular statistical tool for locating examples of known objects in images. It was first introduced by Cootes et al. [1] in 1995 and has been developed and improved over many years. ASM is a model-based method that uses a prior model of what is expected in the image. Essentially, the Active Shape Model consists of a set of profile models and a deformable shape model. The shape model describes the typical variations of an object exhibited in a set of manually annotated images, while the profile models provide a statistical representation of the gray-level structures around each model point. Given a sufficiently accurate starting position, the ASM search attempts to find the best match of the shape model to the data in a new image using the profile models. ASM also has global constraints that allow the shape model to deform only in ways observed in the training set.

Many researchers have tried to combine pure ASM with other approaches or models to enhance its robustness, addressing some inherent limitations of the ASM model. For example, the ASM model is sensitive to illumination changes, so some researchers refine the model by introducing Local Binary Patterns (LBP) [2] into ASM model construction to make it more robust to illumination variations.

A direct extension of the ASM approach led to the development of the Active Appearance Model (AAM) [3]. In addition to shape information, AAM incorporates textual information—namely, pixel intensities across the object—into the model. The AAM algorithm seeks to match both the position of the model points and a representation of the object’s texture to an image.

### References
[1] T.F. Cootes, G.J. Edwards, and Taylor C.J. Active appearance models.[R] In 5th European Conference on Computer Vision, Berlin, Germany,1998. Springer.

[2] Jean Keomany of Swiss Federal Institute of Technology (EPFL), Lausanne, S´ebastien Marcelof IDIAP Research Institute Martigny. Active Shape Models Using Local Binary Patterns[R],February 2006 

[3] G.J. Edwards, C.J. Taylor and T.F. Cootes,Wolfson .Interpreting Face Images using Active Appearance Models Image Analysis Unit[R]. Department of Medical Biophysics, University of Manchester, of Manchester M13 9PT, U.K.  