# Finding-Asteroids-with-the-Zwicky-Transient-Facility

We extended an algorithm implemented in an existing software tool called ASTRiDE (Automated Streak Detection for Astronomical Images) to improve the reliability of detecting fast moving asteroids in the image data stream. ASTRiDE essentially aims to detect streaks in astronomical images by tracing the border of each object in the image (i.e. boundary or contour tracing) and by outputting a list of morphological parameters for each of the detected objects. 

The way the software tool works is by first removing the background (noise) from the image by calculating the background level and its standard deviation, and then proceeding to deriving the contour map, that is, the borders of all objects in the image. Each detected object by ASTRiDE has associated with it some output morphological parameters such as the area, perimeter, coordinates, shape factor, and radius deviation. Since streaking asteroids are our object of concern, we would like to only consider objects that are long and relatively thin when compared to other celestial objects such as stars and star-like sources. ASTRiDE takes care of that by setting thresholds on several morphological parameters, with the most crucial ones being the shape factor and the radius deviation which both represent a measure of circularity. Since our aim is to detect shorter and fainter streaks, the thresholding values of the previous parameters had to be more loosely set, which inevitably led to a bigger influx of false detections. 

From the analysis of a wide set of astronomical images containing real asteroid streaks, an area-to-perimeter ratio was devised as a preliminary initial filtering scheme to try and reduce the amount of false detections obtained at the output without sacrificing too many true detections. We further explore this ratio by collecting vast amount of data and by trying to find a thresholding value that will help us accomplish our goals.
