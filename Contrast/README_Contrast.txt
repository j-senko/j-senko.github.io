Contrast Examples:

This folder contains examples to show the power of the contrast enhancement algorithm, and also how useful it is when combined with HDR tone mapping by logarithmic range reduction.

Each jpg image contains 4 separate images.

1) The top left image is more or less the same as the input image. But for convenience of the driver it was run through a null filter that may have made it a little bit brighter, and otherwise is influenced by roundoff behavior that would be completely imperceptible to the human eye. (Almost always less than 3 gray-levels)

**********************************
2) The top right image is the result of doing a logarithmic range reduction on the dynamic range of the image. This is very similar to what is provided by some other image processing libraries, except for two things:

A) Most other algorithms seem to logarithmically reduce the range of the three color channels independently. This is not a good idea, because it changes the hues, and makes them generally less saturated, or tending towards white. The algorithm used here generates a brightness value, finds the ratio between the logarithmically reduced value and the original brightness value, and then multiplies the three color channels by that ratio, thus coming a lot closer to maintaining the original hue.

But also note: When doing contrast enhancement, sometimes pixels values can be generated that are larger than the original range, or the available range of the image representation. In general, if the entire image range is changed to accommodate this, the whole image may get much darker, especially when a small number of pixels become much brighter, such as when the are streetlights in the photograph. So the algorithm does a histogram, and sets the top end of the range to allow a very small percentage of the pixels to exceed this value. This is something that is difficult to do really well automatically all the time. The alternative is to simply allow all pixels that exceed the original range to clip/saturate their brightness.

B) Any way around it, sometimes there are pixels that will exceed the available output range. Many algorithms handle this by saturating the individual colors separately. This causes out of range pixels to desaturate the colors toward white.

Instead of that, this algorithm will not allow any of the colors values to exceed the maximum range, and will keep the proportions of the color channels the same. This keeps the hues nearly the same as the input. But it also has the effect that yellows and greens tend to experience range saturation more often than blues and reds, and to lose brightness contrast sooner. But this seems preferable.

**********************************
3) The bottom two images show two different levels of contrast enhancement as applied to the top right image.

Note that the three enhanced images for everything in this folder were processed automatically using the same three sets of settings for the algorithm parameters. 

Automatic selection of the amount of dynamic range reduction and contrast enhancement to apply is a difficult task. It is almost impossible without some future AI effort to recognize the aesthetic sensibilities that would be obvious to a human. For instance, the range reduction makes an effort to reduce the amount of really dark areas in the image, on the general assumption that they are just poorly illuminated. But it goes too far when you have images containing a lot of dark suits or hair, or anything that is close to black even in good lighting. And there can definitely be such a thing as too much contrast enhancement. 

The algorithm demonstrated provides an opportunity to do a lot of real contrast enhancement. Deciding how much is enough will always be a matter of personal preference. And what settings produce the same general effects is highly influenced by the quality of the original photograph. A slight change in focus can have a big influence.

The two bottom images COULD have been produced by starting with the top right image as input. But the automatic processing wouldn'92t have produced the same results, because the contrast enhancement parameter is automatically increased in a way related to the logarithmic range reduction. 

As seen when comparing the top two images, logarithmic range reduction will inherently reduce local contrast. The algorithm applies a contrast enhancement that is influenced by the range reduction PLUS some amount of additional specified increase in contrast. The amount of enhancement increase influenced by the range reduction is set such that if the additional contrast enhancement is set to 0, then the contrast is only increased by the maximum amount possible that will never increase the local contrast.

The bottom two images do apply a contrast increase greater than that amount influenced by the range reduction however.
