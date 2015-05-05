# IJBlob #

## V 1.1.1a 30.05.2013 ##
  * Fix a NullPointerException which occurs if a pixel belongs to an internal and to an external contour. ([Issue 4](https://code.google.com/p/ijblob/issues/detail?id=4))

## V 1.1.1 23.05.2013 ##
  * (`ManyBlobs.java`): A the feature for toggle the background/object color (black/white): setBackground() ([Issue 2](https://code.google.com/p/ijblob/issues/detail?id=2))
  * (`ManyBlobs.java`): Add the feature for getting a blob which encompasses a point: getSpecificBlob() ([Issue 3](https://code.google.com/p/ijblob/issues/detail?id=3))
  * Some Refactoring
  * Minor Bugfixes

## V 1.1 07.03.2013 ##

  * Adding filter / extension framework

## V 1.0.6 19.12.2012 ##
  * Bug Fix: Drawing-Method draws the outer contour imprecise
  * Bug Fix: Wrong values for fractal dimension
  * Add Blob Feature: "Feret Diameter" (getFeretDiameter)
  * The Area is now calculated based on the freeman chain code
  * The perimeter is now calculated based on the freeman chain code
  * Due to improved perimeter and area algorithms the circularity and thinnes ratio are much more consistent!
  * Elongation is now calculated based on a fitted ellipse instead of eigenvalues and therefore much more faster
  * Remove Option "Calculate Elongation" (see above)
  * Getter for Freeman chain code (8-connected) of the outer boundary (getOuterContourAsChainCode).

## V 1.0.5 23.11.2012 ##
  * Add Blob Feature: Region Based Moments (getMoments)
  * Add Blob Feature: Central Region Based Moments (getCentralMoments)
  * Add Blob Feature: Eigenvalue Major Axis (getEigenvalueMajorAxis)
  * Add Blob Feature: Eigenvalue Minor Axis (getEigenvalueMinorAxis)
  * Add Blob Feature: Elongation (getElongation)
  * Add Blob Feature: Orientation (getOrientationMajorAxis/getOrientationMinorAxis)
  * Bug Fix ([issue 1](https://code.google.com/p/ijblob/issues/detail?id=1))

## V 1.0.4 12.11.2012 ##
  * (Blob.java) Add Drawing-Option for the Labels
  * (Blob.java) Add getter for the inner contours
  * Some Refactoring

## V 1.0.3 07.11.2012 ##
  * Add "Center of Gravity" as Basic Feature
  * Add "Number of Holes" as Basic Feature
  * Add getter for the Convex Hull
  * Add Drawing-Function for the Convex-Hull

## V 1.0.2 03.11.2012 ##
  * Fractal Box Sizes are now configurable
  * Adding getter for fractal goodness (R-Squared).
  * IJBlob works with LUT Inverted Images

# Shape Filter #

## V 1.0.8a 30.05.2013 ##
  * Fix a NullPointerException which occurs if a pixel belongs to an internal and to an external contour. ([Issue 4](https://code.google.com/p/ijblob/issues/detail?id=4))

## V 1.0.8  23.05.2013 ##
  * Add Option: Black backgrounds are now supported (new GUI checkbox)
  * Add Option: Show color labeled image (new GUI checkbox)

## V 1.0.7 07.03.2013 ##
  * Code refactoring for IJBlob 1.1

## V 1.0.6 19.12.2012 ##
  * Based on IJBlob 1.0.6
  * Elongation is calculated much more faster. There is no need to make it "optional" anymore
  * Add Option: Feret Diameter

## V 1.0.5a 02.12.2012 ##
  * Add Option: Elongation (Computational Expensive) is now "optional".
  * Bug Fix: Plugin is not callable in Macro-Scripts
  * Bug Fix: Result-Image is of type RGB, even when no contour or label is plotted

## V 1.0.5 23.11.2012 ##
  * Bug Fix in IJBlob ([issue 1](https://code.google.com/p/ijblob/issues/detail?id=1))
  * Add Feature: Elongation

## V 1.0.4 12.11.2012 ##
  * More robust with binary images which saved in lossy formats.
  * `BugFix`: Zero-Line in the result table
  * Small GUI Changes
  * Add Drawing-Option: Draw Label
  * Labels, Convex-Hull etc. are now in color.
  * Add Column "Label" to the Result-Table

## V 1.0.3 07.11.2012 ##
  * Add "Center of Gravity" in the Result Table
  * Add "Number of Holes" as Basic Feature
  * Add Drawing-Option: Draw Convex-Hull
  * Add Drawing-Option: Draw Holes