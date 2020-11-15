# symbol_display
Create displays with predefined symbols for 3D printing

*Operation*
1. Select N binary images
2. Select dimension of the display width in cm
3. Select output .stl file
3. Run
4. Print .stl file
5. Attach LED to predefined positions
6. Power on :)

Status: Brainfart

*Algorithm*

1. Get aspect ratio of the N input images
2. Find N points on the image that maximize the distance to its nearest neighbor. These are the positions of the LED on the rear plane.
3. Sample points on the white areas of the input images. Discard points that are to close to each other. 
4. Simulate the following physical setup: Connect the sampled points of the display plane with the corresponding LED points on the rear plane to obtain a line. On this line, insert evenly spaced mass points. Connect the masspoints of a line with springs. Mass points for different symbols will repell each other. Furthermore, there is a repelling force of the boundaies of the display cube.
5. Once the setup had come to an equilibrium point, the pose of the mass points are saved.
6. Construct a 3D Voronoi diagram with the mass points. 
7. Connect neighbouring cells with the same symbol.
8. Dilate the remaining faces.
9. Add walls to the display cube
10. Export the resulting mesh as .stl





