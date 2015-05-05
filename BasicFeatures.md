**Area** (A):
The area enclosed by the outer contour of the blob.

**Area Convex Hull** (C):
The area enclosed by the convex hull of the outer contour of the blob.

**Perimeter** (P):
The perimeter of outer contur of the blob.

**Perimeter of the convex hull** (H):
The perimeter of the convex hull of the blob.


**Feret diameter**:
The greatest distance between any two points along the contour of the blob.

**Min. Feret diameter**:
Minimum rotating caliper width

**Long Side Min. Bounding Rect** (L):
The larger side of the minimum bounding rectangle.

**Short Side Min. Bounding Rect** (S):
The smaller side of the minimum bounding rectangle.

**Aspect ratio**
Defined as L/S

**Area/Perimeter Ratio**:
Defined as A/P.

**Cicularity**:
Defined as P^2 / A. Has its minimum for a perfect circle by 4\*PI.

**Elongation**
Defined as (1 - minor axis of a fitted ellipse / major axis of a fitted ellipse)

**Convexity**
Defined as H/P

**Solidity**
Defined as A/C

**The number of holes**: More specifically, the number of internal contours of a blob.


**Thinnes Ratio**:
Inverse proportional to the circularity. Furthermore it is normed. It is defined as: 4 `*`PI`*`(A/P^2)

**Temperatur of the outer contour**: Defined as ![https://dl.dropbox.com/u/560426/imagej/temp.gif](https://dl.dropbox.com/u/560426/imagej/temp.gif). It has a strong relationship to the fractal dimension. For further information see `[`1`]`.

**Fractal Box Dimension**: Estimated fractal dimension by the box count algorithm. The default Box-Sizes are "2,3,4,6,8,12,16,32,64". For other sizes you can use the method "getFractalBoxDimension(int`[``]` sizes)". Where sizes is an ordered array of the box sizes.


**Region Based Moments**: Moment of a Region R of order (p+q) is defined as:
![https://dl.dropbox.com/u/560426/imagej/moment.gif](https://dl.dropbox.com/u/560426/imagej/moment.gif) where x,y are the coordinates of the pixels insede the region R.

**Central Region Based Moments**:  Moment of a Region R of order (p+q) with the center of gravity (xc,yc) is defined as: ![https://dl.dropbox.com/u/560426/imagej/centralmoments.gif](https://dl.dropbox.com/u/560426/imagej/centralmoments.gif)


**Freeman Chain Code**: Outer Contour as Freeman-Chain-Code

`[`1`]` Luciano da Fontoura Costa, Roberto Marcondes Cesar, Jr.Shape Classification and Analysis: Theory and Practice, Second Edition, 2009, CRC Press