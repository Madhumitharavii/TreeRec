# TreeRecommendation
Tree Recommendation using Random Forest and QGIS 

## Introduction
In this project, a dataset was prepared by collecting information of Indian Tree species gathered through online search. Then, the data is trained to predict the suitability score for tree species using the Random Forest Regression Model and recommend the top 5 tree species for a given area, exported from QGIS.

## Method
* Using a spatial analysis tool like QGIS, polygon areas and their centerlines are mapped using satellite imagery. Areas like the community park and the railway station in Velachery (Chennai) are marked for further analysis. Important Attributes like land type, soil type, climate, category, and area width are included with the polygon, and the centerline is included with the area polygon and centerline exported as a GeoJSON file.

<p align="center">
  <img src="https://github.com/user-attachments/assets/cbb5c6aa-8873-4713-89fb-6b386ec27100" height="300"/>
  <img src="https://github.com/user-attachments/assets/77d0e300-8fff-467f-b46e-28003536fb1e" height="300"/>
</p>

* In the Tree Species Dataset, multi-label fields are expanded into binary columns (one-hot encoded) as part of the preprocessing pipeline. Each tree is then assigned a numerical score based on several weighted factors such as carbon sequestration, pollution filtration, space adaptability, maintenance level, and presence of flowers or edible fruits, reflecting both ecological and urban planning priorities. 
* The model is trained to predict the suitability score using both numeric and categorical inputs. The system uses Random Forest Regression for the prediction.
* The recommended tree species are spatially allocated along the centerline of the area polygon for visualization using Matplotlib. Additionally, the distribution and count of each tree species are displayed to provide a clear overview of species placement.

<p align="center">
  <img src="https://github.com/user-attachments/assets/27b2715a-c0d5-46f3-94fb-ac9970b96ef1" height="500"/>
  
  <img src="https://github.com/user-attachments/assets/d5ebeed6-bba9-4088-8cdc-cc222082685d" height="400"/>
</p>

## Result & Discussion
We evaluated our tree recommendation model using Random Forest Regression. The model achieved a high R² score of 0.974 on the training set and 0.960 on the test set, with a near-zero Mean Squared Error in both cases. Cross-validation further confirmed the model’s robustness with an average R² of 0.943 (±0.019). 
The Actual vs Predicted plot shows close alignment along the ideal line, indicating accurate predictions. 

<p align = "center">
<img src="https://github.com/user-attachments/assets/064a4fea-b999-4156-b7aa-c719a82baf62" height="300"/>
</p>

While the current model performs well, expanding the dataset to include more regions and incorporating a broader range of environmental and urban planning factors would further enhance the model’s generalizability. Additionally, using more advanced models could improve prediction accuracy and reduce the risk of overfitting.

## NOTE: 
The data used in this project was gathered through online searches and from publicly available sourcees found on the web. No restricted or private data was accessed. This project is intended strictly for educational purpose.
