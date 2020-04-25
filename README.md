# LR-finder

A toy project to find the Largest Rectangle (LR) in a polygon.

## Bibliography

There are two ways to approach this problem:
- use the power of Maths to find the exact solution,
- devise a smart but potentially faulty algorithm to iteratively search for the solution.

### Research papers
A few references have tackled this issue before. We limit ourselves to recent work. Some results before 2000 are presented in a similar table in []Molano12].

| Author  | Year | Link | Polygon | LR Orientation | Convergence Speed |
| :--- | :---: | :--- | :---: | :---: | :---: |
| Boland et al.  [Boland01] | 2001 | [CiteSeerX — Finding the Largest Axis-Aligned Rectangle in a Polygon in ...](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.20.7210) | Arbitrary | Axis-Aligned | $\mathcal{O} (n \; \log(n))$ | 
| Knauer et al. [Knauer12] | 2012 | https://doi.org/10.1016/j.jda.2012.01.002 | Convex | Free | ? |
| Knauer et al. [Knauer12] | 2012 | https://doi.org/10.1016/j.jda.2012.01.002 | Arbitrary | Free | ? |
| Molano et al. [Molano12] | 2012 | https://doi.org/10.1016/j.amc.2012.03.063 | Arbitrary | Free | $\mathcal{O} ( n^3)$ |
| Cabello et al. [Cabello12]  | 2016 | https://doi.org/10.1016/j.comgeo.2015.08.001 | Convex | ? | ? |
| Sarkar et al. [Sarkar18]| 2018 | https://doi.org/10.1016/j.jcss.2017.05.006 | ? | ? | ? |

### Empiric Algorithm Implementations

People have been very creative when it comes to implementing an approximate solution to this problem, each with their own knowledge and constraints.

| Author | Year | Link | Polygon | LR Orientation | Convergence Speed | Comment |
| :--- | :---: | :--- | :---: | :---: | :---: | :--- |
| Abu-Qasmieh et al. | 2018 | https://doi.org/10.1049/iet-ipr.2017.0509 | Arbitrary | Axis-Aligned | ? | Seems interesting |
| jfs/zed | 2011 | [algorithm - Find largest rectangle containing only zeros in an N×N binary matrix - Stack Overflow](https://stackoverflow.com/questions/2478447/find-largest-rectangle-containing-only-zeros-in-an-n%c3%97n-binary-matrix) | N.A | Axis-Aligned (?) | ? | Slightly different problem. See implementation [Find height, width of the largest rectangle containing all 0's in the matrix · GitHub](https://gist.github.com/zed/776423) |
| DanielHsH | 2015 | [matlab - How can I detect the maximum-sized rectangle that I can draw onto the mask? - Stack Overflow](https://stackoverflow.com/questions/30133895/how-can-i-detect-the-maximum-sized-rectangle-that-i-can-draw-onto-the-mask) | Convex (?) | Axis-Aligned (?) | ? | Uses [Dynamic Programming](https://en.wikipedia.org/wiki/Dynamic_programming), in matlab |
| Daniel Smilkov | 2014 | [Largest rectangle in a polygon \| D3plus](https://d3plus.org/blog/behind-the-scenes/2014/07/08/largest-rect/) | Arbitrary | Free | ? | Iterative search, in javascript |

## Software That May Help

### Python Modules

#### Shapely
[Shapely](https://shapely.readthedocs.io/en/latest/manual.html) is a Python package for 2D geometry intended mostly for GIS. It is convenient for doing 2D geometry. It shares some functionalities with Skimage albeit on different objects but also stuff like Delaunay triangulation and Voronoi diagrams.

##### Notable Methods
It offers a methode to find the rotated bounding box of any geometric structure of set of structures: [minimum_rotated_rectangle()](https://shapely.readthedocs.io/en/latest/manual.html#object.minimum_rotated_rectangle)
Also nearest points in two structures: [nearest_point()](https://shapely.readthedocs.io/en/latest/manual.html#shapely.ops.nearest_points)

#### Skimage
Has stuff like convex hull, bounding box, erosion, dilation (like Shapely) and contours, all working on image objects.

#### OpenCV
OpenCV has more or less the same stuff than Skimage but also a minimum bounding box obtained with `rotatedRectangle()` or `minAreaRect()`: [OpenCV: Contour Features](https://docs.opencv.org/3.4/dd/d49/tutorial_py_contour_features.html)


## References:
[Boland01]: [CiteSeerX — Finding the Largest Axis-Aligned Rectangle in a Polygon in ...](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.20.7210)
[Knauer12]: [Redirecting](https://doi.org/10.1016/j.jda.2012.01.002)
[Molano12]: [Redirecting](https://doi.org/10.1016/j.amc.2012.03.063)
[Cabello12]: [Redirecting](https://doi.org/10.1016/j.comgeo.2015.08.001)
[Sarkar18]: [Redirecting](https://doi.org/10.1016/j.jcss.2017.05.006)
[Abu-Qasmieh18]: [Current Links for doi: 10.1049/iet-ipr.2017.0509](https://doi.org/10.1049/iet-ipr.2017.0509)
