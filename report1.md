# Depth of field effects (realtime bokeh) report 1
I have started working on the project by gathering some materials and reading through different techniques used. From the real time solutions I’ve found, I decided to pick one that uses two different techniques to achieve the final result.

## Circle of Confusion

To use these techniques, the Circle of Confusion has to be computed for each pixel based on the drawn object's distance and the camera parameters (aperture, focal length, plane in focus).
The distance of the object is calculated using the z-buffer values.


## The Gaussian Blur

The first technique is applying a generated gaussian blur to the whole rendered image based on the Circle of confusion size and depth. 

## The Point Sprites

The second technique picks out each pixel and computes the brightness of the block around it. If the pixel is much brighter than the average of the block and it also passes a threshold for the circle of confusion, we pass the color, position and circle of confusion size to the geometry shader, where it is expanded into a quad. Then the result is additively blended with the chosen aperture shape in the pixel shader.

These two techniques are then summed together in a pixel shader. 

## Preparing the project

To demonstrate this technique, I needed a Direct3D project with a simple scene and camera. I went through the examples provided by the course and decided the TexturingExample is the closest to what I needed. However, to make sure I have a scene that allows for proper testing, I will need to add some more assets. Mostly I need some bright spots on a darker background to see if the point sprites work correctly. For that, I want to add a starry night sky. 

If needed, I’ll also add some more assets to see how the objects blend into each other in different depth levels. 

## The Progress   

Sadly, I don’t have anything to show yet. As I have no experience with Direct3D, even extracting the TexturingExample from the provided project to use as a standalone scene proved to be a challenge for me and I haven’t managed to implement anything worth showing yet.


