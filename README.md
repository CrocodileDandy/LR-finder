# LR-finder

A toy project to find the Largest Rectangle (LR) in a polygon.

## Bibliography
A few references have tackled this issue before:
- [Finding the Largest Axis-Aligned Rectangle in a Polygon in O(n log(n)) time](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.20.7210)
- Work in Progress

## Software That May Help

### Shapely
[Shapely](https://shapely.readthedocs.io/en/latest/manual.html) is a Python package for 2D geometry intended mostly for GIS. It is convenient for doing 2D geometry. It shares some functionalities with Skimage albeit on different objects but also stuff like Delaunay triangulation and Voronoi diagrams.

#### Notable Methods
It offers a methode to find the rotated bounding box of any geometric structure of set of structures: [minimum_rotated_rectangle()](https://shapely.readthedocs.io/en/latest/manual.html#object.minimum_rotated_rectangle)
Also nearest points in two structures: [nearest_point()](https://shapely.readthedocs.io/en/latest/manual.html#shapely.ops.nearest_points)

### Skimage
Has stuff like convex hull, bounding box, erosion, dilation (like Shapely) and contours, all working on image objects.

### OpenCV
OpenCV has more or less the same stuff than Skimage but also a minimum bounding box obtained with `rotatedRectangle()` or `minAreaRect()`: [OpenCV: Contour Features](https://docs.opencv.org/3.4/dd/d49/tutorial_py_contour_features.html)

### Naive Algorithm Implementations
- [algorithm - Find largest rectangle containing only zeros in an N×N binary matrix - Stack Overflow](https://stackoverflow.com/questions/2478447/find-largest-rectangle-containing-only-zeros-in-an-n%c3%97n-binary-matrix)
- [matlab - How can I detect the maximum-sized rectangle that I can draw onto the mask? - Stack Overflow](https://stackoverflow.com/questions/30133895/how-can-i-detect-the-maximum-sized-rectangle-that-i-can-draw-onto-the-mask)
    - the second answer seems to work and uses [Dynamic Programming](https://en.wikipedia.org/wiki/Dynamic_programming) 
