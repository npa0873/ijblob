# IJBlob #
## Use the IJBlob Library for Developing an ImageJ Plugin ##
I suppose you use Eclipse as IDE. You have to add IJBlob.jar to Librarys in the Java Build Path:

_Project->Properties->Java Build Path->Librarys->Add External JARs._

Furthermore you have to add the following import line to your code:
```
import ij.blob.*;
```

Now you are able to use the IJBlob Library (see Example 1).

For deploying a plugin, I also include the IJBlob.jar to the plugin JAR-File. Therefore I saved the IJBlob.jar in the folder "lib" in the plugins root directory and add the following property to the build.xml:
```
...
<property name="lib.dir"       value="lib"/>
...
```

Furthermore I add the marked line to the target in plugins build.xml:
```
...
<fileset dir="." includes="plugins.config" />
<fileset dir="${build}" includes="**/*.*" />
<fileset dir="${src}" includes="**/*.java"/>
<zipgroupfileset dir="${lib.dir}" includes="**/*.jar" /> <!-- THE ADDED LINE-->
...
```

Maybe this is not the best solution, but it works for me.
## Example 1: Extract the Blobs of an Image and Read the Perimeter of a Blob ##
```
import ij.blob.*;
...
private ManyBlobs allBlobs;
...
public void someMethod(ImagePlus imp) {
  ManyBlobs allBlobs = new ManyBlobs(imp); // Extended ArrayList
  allBlobs.findConnectedComponents(); // Start the Connected Component Algorithm
  allBlobs.get(0).getPerimeter(); // Read the perimeter of a Blob
}
```

## Example 2: Filter blobs by blob features ##
In IJBlob 1.1 a filter framework was introduced. Each build-in blob feature has a static identifier (in this example "GETENCLOSEDAREA") which contains the method name.
```
import ij.blob.*;
...
private ManyBlobs allBlobs;
...
public void someMethod(ImagePlus imp) {
  /* Extended ArrayList */
  ManyBlobs allBlobs = new ManyBlobs(imp); 
  
  /* Start the Connected Component Algorithm */
  allBlobs.findConnectedComponents(); 

  /* Return all blobs with an area between 20 and 100 pixel² */
  ManyBlobs filteredBlobs = allBlobs.filterBlobs(20,100, Blob.GETENCLOSEDAREA); 
}
```

## Example 3: Add your own features ##
IJBlob 1.1 is easily expandable by your own features. First you have to derive a feature class from the "CustomBlobFeature" class. The feature class can also contain multiple features. With the "getBlob()" method you get the reference to the Blob and have full access to the contour data and the other features.
**Please note: If your feature method have primitive data types (int/float/double) as parameters you have to use the wrapper classes (Integer/Float/Double).**
```
import ij.blob.*;

public class ExampleBlobFeature extends CustomBlobFeature {

	public double myFancyFeature(Integer a, Float b){
		double feature = b*getBlob().getEnclosedArea()*a;
		return feature;
	}
	
	public int mySecondFancyFeature(Integer a, Double b){
		int feature = (int)(b*getBlob().getAreaToPerimeterRatio() *a);
		return feature;
	}
	
	
}
```

Now you can easily add this feature to blob class and use it eg. for filtering or calculating the mean:
```
import ij.blob.*;
...
private ManyBlobs allBlobs;
...
public void addMyFeatures() {

  ExampleBlobFeature myOwnFeature = new ExampleBlobFeature();
  /* Static Method for adding custom features to the blob class */
  Blob.addCustomFeature(myOwnFeature); 

}

public int getMeanOfMyFeature(int a, double c) {

  int sum = 0;
  for(int i = 0; i < mb.size(); i++){
     /* 
      * The first parameter is the name of feature method followed 
      * by its parameters. Please note that you have to convert the
      * the return value in the corresponding data type.
      */
      sum += (Integer)allBlobs.get(i).evaluateCustomFeature("mySecondFancyFeature",a,c);
  }
  int mean = sum/allBlobs.size();


  return mean;

}
```

## Example 4: Filter blobs by your own features ##
I suppose you have added your own feature to the blob class as described in example 3. For filtering with custom feature you can proceed as in example 2:
```
import ij.blob.*;
...
private ManyBlobs allBlobs;
...
public void someMethod(ImagePlus imp) {
  ManyBlobs allBlobs = new ManyBlobs(imp); 
  allBlobs.findConnectedComponents(); 

  /* Return all blobs with an 'feature value' between 20 and 100 */
  int a = 10;
  double b = 20;
  ManyBlobs filteredBlobs = allBlobs.filterBlobs(20,100,"mySecondFancyFeature",a,b); 
}
```
**Please note that for filtering the return value of the custom method has to be Integer or Double.**
# Shape Filter #
## Install the `ShapeFilter` Plugin ##
Only copy the `ShapeFilter``_`vX.X.X`_`.jar in your ImageJ Plugin Folder