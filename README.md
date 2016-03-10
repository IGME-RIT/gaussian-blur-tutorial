# Gaussian Blur Tutorial

This demo demonstrates the implementation of Gaussian blur filter using fragment shader.

# About

To implement a blur effect, we average the color values of a pixel with the values of the  nearby pixels. Gaussian blur just implements this "averaging between pixels" using Gaussian weights, which are computed on the CPU side application and sent to the GPU as uniforms.

To implement Gaussian blur, we need to implement 2 dimensional Gaussian equation. This would require a NxN sampling calls of a texture. where N is the number of pixels we average for one pixel in the final image.

We reduce this problem to an order of N, by adding another render call. in The first render call we average the values of the pixels horizontally. and in the second render call, we do this vertically. This is equivalent to implementing a 2D Gaussian function.

In this program, we first render the scene normally onto a texture using a frame buffer, and apply horizontal blur on it and render this onto another texture. On the third render call, we apply vertical blur and then we render this texture on a plane which covers the entire scene/window.

Use "SPACEBAR" to toggle blur on and off.

# Setup

In order to setup, run the following in a shell, then open the project in your preferred editor. Windows setup has been configured for use with Visual Studio.

Windows:
```
cd path/to/folder
setup.cmd
```
Linux:
```
cd path/to/folder
./setup
```

# Credits

Sample references the [OpenGL 4 Shading Language Cookbook](https://www.packtpub.com/game-development/opengl-4-shading-language-cookbook-second-edition), Second edition by David Wolff.
