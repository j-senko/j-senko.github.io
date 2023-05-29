This folder demonstrates how Perona-Malik based smoothing can function in the most popular form: Edge Preserving smoothing. This is mostly used by AI applications.

The general aim is that some level of detail can be smoothed away, but that whatever edges are not erased remain sharp, and do not shift position the way they would with local area gaussian smoothing.

This  "EdgePreservingSmoothing"  folder presents black and white images. 

There is no claimed assertion that the equations generating the diffusion weights being used are ideal.  They are not even the same as any published version of Edge Preserving Smoothing, because there has not been an opportunity to properly study and address that yet.

In fact, there CANNOT be one set of equations and settings that is optimal for all applications. This is heavily influenced by the needs of the application, and by the quality of the input images, which is influenced by the camera involved. Cameras that produce inherently sharper images would want to use different settings and possibly different equations than other cameras.

The software used to generate the examples in these folders was developed along side and general anisotropic diffusion algorithm that can take externally derived diffusion coefficients, and be used to experiment with whatever equations are wanted. Hopefully that will be available in some form, somewhere, soon.
