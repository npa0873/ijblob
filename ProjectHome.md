
---

**ijblob-1.3 and shape filter 1.2 released!**

**THE NEWEST BINARYS OF IJBLOB AND SHAPE-FILTER NOW ON BINTRAY**

Because google-code is shutting down the possibiltiy providing binarys, they are now
moved to bintray:

<a href='https://bintray.com/jumpfunky/ijblob-and-tools/ijblob/_latestVersion'><img src='https://api.bintray.com/packages/jumpfunky/ijblob-and-tools/ijblob/images/download.png'>

<a href='https://bintray.com/jumpfunky/ijblob-and-tools/shape-filter/_latestVersion'><img src='https://api.bintray.com/packages/jumpfunky/ijblob-and-tools/shape-filter/images/download.png'>
<hr />

The IJBlob library indentifying <a href='http://en.wikipedia.org/wiki/Connected_Component_Labeling'>connected components</a> in binary images. The algorithm used for connected component labeling is:<br>
<br>
Chang, F. (2004). A linear-time component-labeling algorithm using contour tracing technique. Computer Vision and Image Understanding, 93(2), 206–220. doi:10.1016/j.cviu.2003.09.002<br>
<br>
<br>
A connected component is a set of pixels which are connected by its 8-neigherhood and is often called a "blob". An Example:<br>
<br>
<br>
<img src='https://dl.dropbox.com/u/560426/components2.jpg' />


The image above contains 8 marked blobs. Also the holes (and the contours of the holes) of the two Bs and the O are identified. It is also possible to get a color labeled image:<br>
<br>
<img src='https://dl.dropbox.com/u/560426/imagej/ijbloblabeled.jpg' />

In addition nested objects are identified:<br>
<br>
<img src='https://dl.dropbox.com/u/560426/components3.jpg' />

The ImageJ <b>Shape Filter Plugin</b> (see downloads) uses this library for flitering the blobs by its shape.<br>
<br>
If you are using IJBlob in a scientific publication, please cite:<br>
<br>
Wagner, T and Lipinski, H 2013. IJBlob: An ImageJ Library for Connected Component Analysis and Shape Analysis. Journal of Open Research Software 1(1):e6, DOI: <a href='http://dx.doi.org/10.5334/jors.ae'>http://dx.doi.org/10.5334/jors.ae</a>

<h2>Features of IJBlob</h2>
<b>IJBlob 1.1 introduces a filter and extension framework! Please see the <a href='https://code.google.com/p/ijblob/wiki/HowToUSE'>HowToUSE</a> for more information</b>

<ul><li>Extract the outer contour of each blob.<br>
</li><li>Extracts also all inner contours of each blob (holes).<br>
</li><li>Detects also nested objects (blob in blob).<br>
</li><li>Calculates BasicFeatures of the blob.<br>
<ul><li>Center of Gravity<br>
</li><li><b>Enclosed Area</b>
</li><li><b>Area Convex Hull</b>
</li><li><b>Perimeter</b>
</li><li><b>Perimeter of the convex hull</b>
</li><li><b>Cicularity</b>
</li><li><b>Thinnes Ratio</b>
</li><li><b>Feret Diameter</b>
</li><li><b>Min. Feret Diameter</b>
</li><li><b>Long Side Min. Bounding Rect</b>
</li><li><b>Short Side Min. Bounding Rect</b>
</li><li><b>Aspect Ratio</b>
</li><li><b>Area/Perimeter Ratio</b>
</li><li><b>Temperatur of the outer contour</b>
</li><li><b>Fractal Box Dimension</b>
</li><li>Region Based Moments<br>
</li><li>Central Region Based Moments<br>
</li><li>Eigenvalue Major Axis<br>
</li><li>Eigenvalue Minor Axis<br>
</li><li><b>Elongation</b>
</li><li><b>Convexity</b>
</li><li><b>Solidity</b>
</li><li>Orientation<br>
</li><li>Outer Contour as Freeman-Chain-Code<br>
</li></ul></li><li>Rendering of Blobs and its Convex Hull</li></ul>

<h2>Features of Shape Filter Plugin</h2>
Remove objects by some basic features (see the bold features above).<br>
<h3>Please note the <a href='http://code.google.com/p/ijblob/wiki/ShapeFilter_HowToInstall'>install instructions</a> for the Shape Filter</h3>

<img src='https://dl.dropbox.com/u/560426/imagej/gui_.png' />

<h3>Restrictions:</h3>
The object/background has to be black (0) or white (255)<br>
<br>
<h3>Contact</h3>
If you miss some features or want to contribute to the project, do not hesitate to contact me at: wagner@biomedical-imaging.de<br>
