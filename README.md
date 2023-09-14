# Sunflower-seed-detection-using-image-processing-and-machine-learning
If you require automatic seed detection (yield) in a sunflower image, this tool is a valuable resource. 
It operates on a trained Random Forest model using a dataset consisting of over 140,000 polygons representing sunflower seeds and leaves. It utilizes a combination of image processing and machine learning techniques to detect sunflower seeds representing sunflowers in RGB images. 
  
  ![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/ec31d54c-cab4-4ac1-97b2-ccb239f65fcc)

Table of Contents

•	Installation
•	Usage
•	Contributing
•	License

Installation

ARCGIS PRO version 3

[Download the tool and “rfsegment1.pkl” model then unzip that model]

[Go to the insert tab of your ArcGIS PRO project]
![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/794738d5-7b9a-433e-ad23-a0e8f327fa57)

 
[Select add folder and browse to the folder that you have saved your script and add that folder]

[Go to the Catalog and find your folder in the Folders section and then find the tool with the name of SunflowerSeedDetection_Ali.atbx, then open it to find the script]
  
  ![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/73e21251-36cf-4060-b152-e9808d965385)

 ![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/15f5b6ad-632f-43ef-a56b-60ab1767032a)

 [Double click and open the script]
 
![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/67ff8fef-86de-4f5b-a4bc-f3602d36fa39)

Specify the input file (RGB image of sunflower). The output directory should be the folder where you intend to save the results. The model directory should be the folder where “rfsegment1.pkl” model is located.

Usage

If you require automatic seed detection (yield) in a sunflower image, this tool is a valuable resource. It operates on a trained Random Forest model using a dataset consisting of over 140,000 polygons representing sunflower seeds and leaves. It utilizes a combination of image processing and machine learning techniques to detect sunflower seeds representing sunflowers in RGB images. 

![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/cc7f156e-b37b-464e-ab26-91b857decca9)

 
This tool follows several steps to analyze the image and predict the locations of seeds. Here's an overview of its workflow:
1.	RGB Image Splitting: The RGB image is initially split into separate bands, namely Red, Green, and Blue.
2.	ISO Clustering Segmentation: An ISO clustering approach is applied to segment the image, primarily based on the green band. This segmentation process separates the image into distinct regions.
3.	Shape Metrics Calculation: Various shape metrics are calculated for each segmented region. These metrics include circularity, compactness, area, perimeter, length, width, and shape index. These metrics provide valuable information about the characteristics of each segment.
4.	Random Forest Prediction: In the final stage, a trained random forest model is utilized. This model takes the calculated shape metrics as input and performs predictions based on these features. The model predicts the locations of seeds within the image.
By following these steps, the tool effectively analyzes the input image and provides predictions regarding the presence and locations of seeds in the sunflower image.
 
![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/f7103c9f-3a43-41ab-bb12-06cfa8dbf9b2)

 
Upon running the tool, you will discover a geodatabase named "66.gdb" in the specified output directory. Furthermore, you can find the individual RGB bands saved as separate files in the output directory.  Within 66 geodatabase, you'll find the extracted results thoughtfully organized and stored for your convenience. 

![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/59ae128c-cc0c-49c4-ac7e-cd8db491fc22)

 ![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/94f44aef-1df2-45b6-9326-417c0dc36f3a)


 
Output_polygon_features: the initial polygon of segmented image
Shape metrics layer: the results of shape metrics for each polygon
finalPrediction: a database that contains the prediction column

 ![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/8e4f2a48-9b90-44df-947b-5ae14c17ab09)

finalPrediction table


Open the "Output_polygon_features" and "finalPrediction" layers in ArcMap and utilize the "Join Field" operation to combine their tables. This will enable you to observe the prediction results for each polygon. You can further enhance the visualization by creating a symbology or save the results to a new directory for future reference. The "Join Field" operation should be performed based on the "ObjectID" field in the "Output_polygon_features" layer and the " ObjectID" field in the "final prediction" table. This will ensure a proper and accurate joining of the tables.

 ![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/81119292-535a-4e2c-bafb-697893a42135)

In the "Prediction" field, a value of 1 represents seed, and a value of 0 indicates other objects.
 
![image](https://github.com/AliBgisrs/Sunflower-seed-detection-using-image-processing-and-machine-learning/assets/109620013/fd96233d-1739-4915-9a73-b774c30d5273)

Contributing

Please execute the script, utilize its functionalities, and provide me with your valuable suggestions to enhance its performance.

License

About the Author

[Developed by Aliasghar Bazrafkan.]

Acknowledgments
[I would like to express my sincere appreciation to my supervisor, Dr. Paulo Flores, from North Dakota State University (NDSU), for providing invaluable support and guidance throughout the development of this script. His expertise and encouragement have been instrumental in making this project possible. I am also deeply grateful to Dr. Cannayen Igathinathane for his invaluable guidance and expertise in the field of image processing techniques. His insights and support have been instrumental in the development and improvement of this tool.


Contact

[Aliasghar.bazrafkan@ndus.edu]

Additional Notes

[https://sites.google.com/ndsu.edu/floreslab/home?authuser=0]
