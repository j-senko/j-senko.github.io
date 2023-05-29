There are five folders here with images in them to help demonstrate the functionality developed for image enhancement. This includes algorithms for local contrast enhancement, dynamic range adjustment, and edge preserving smoothing. Each directory has its own own _README* documents.

The images can be viewed directly, except for the "*HDR.exr" images in the Source Images folder. Or all of the images in the individual folders can be downloaded as zipped files in those directories.

The images in folder "SourceImages" are the input used to generate the results in the other four folders. These are provided so that you might have the ability to apply other image enhancement software to them for comparison. (Note: the are mostly .jpg files, with a few HDR ".exr" format files.)

The other folders all contain composites of 2 or 4 images generated with different setting for ease of comparison.

The amount of dynamic range reduction in these examples has all been done automatically. Hand chosen settings for that and the amount of contrast enhancement will coften produce more aesthetically pleasing results.

Contrast enhancement and dynamic range adjustment are inherently a monochrome processes. It does not make sense to apply these processed to the three color channels independently for multiple reasons, the most important of which is that the color hue and saturation will change if the same adjustments are not used. And if the same adjustments are used, then it is faster and easier to process the brightness values, and to multiply the color channels by the changes, which is what the color processing demonstrated here does.

********************************
Folder "Contrast" contains examples that demonstrate the power of the local contrast enhancement algorithm, And how valuable that is when applied to HDR "tone mapping" by simple logarithmic range reduction. These all use the "Normal" recipe, but with different levels of contrast enhancement. This shows that there is really an ability to choose how much contrast enhancement to apply, and that it happens LOCALLY and very smoothly as this value is increased.

But applying contrast enhancement is a complicated and subtle process.
********************************
Folder "Faces" compares three different "recipes" that have been developed. Quite often, a lot of contrast enhancement can amplify unflattering details on people's faces too much. But the algorithm has the ability to enhance finer details less than the broader ones. So this is what the "Faces" recipe attempts to do. It can still get large amount of overall contrast enhancement without making people look as old and wrinkled.

Those images also show a third contrast recipe that is called "Evidence". This attempts to make as many details of the image simultaneously visible as possible. This is what you might want to use for such things as crime scene photos or rental agent property inspection. It is not designed to be aesthetically pleasing. It is designed to present as many details as possible.
********************************
The folder "EdgePreservingSmoothing" demonstrates how Perona-Malik anisotropic diffusion based smoothing can function. This is mostly used by AI applications.

This  "EdgePreservingSmoothing"  folder presents black and white images. It should be treated as a monochrome process on the brightness of an image, for the same reasons as with contrast as discussed above.

There is no claimed assertion that the equations generating the diffusion weights being used are ideal. In fact, there CANNOT be one set of equations and settings that is optimal for all applications. This is heavily influenced by the needs of the application, and by the quality of the input images, which is influenced by the camera involved. Cameras that produce inherently sharper images would want to use different settings and possibly different equations than other cameras.
********************************
Folder "HandAdjusted" contains images that show an original input and a hand adjusted image.
