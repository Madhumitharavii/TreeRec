# Tree Recommendation System

Tree Recommendation using Random Forest and QGIS

**Technologies:** Python, Pandas, Scikit-learn, Random Forest, QGIS, GeoPandas, Matplotlib

## Introduction

In this project, a dataset was prepared by collecting information on Indian tree species from online sources. The data was then used to train a Random Forest Regression model to predict the suitability score of tree species and recommend the top 5 tree species for a given area, based on spatial data exported from QGIS.

## Method

* Using a spatial analysis tool like QGIS, polygon areas and their centerlines are mapped using satellite imagery. Areas such as the community park and the railway station in Velachery (Chennai) are marked for further analysis. Important attributes such as land type, soil type, climate, category, and area width are included with the polygon, and the centerline is included with the area polygon. The area polygon and centerline are exported as a GeoJSON file.

<p align="center">
  <img src="https://github.com/user-attachments/assets/cbb5c6aa-8873-4713-89fb-6b386ec27100" height="300"/>
  <img src="https://github.com/user-attachments/assets/77d0e300-8fff-467f-b46e-28003536fb1e" height="300"/>
</p>

* In the Tree Species Dataset, multi-label fields are expanded into binary columns (one-hot encoded) as part of the preprocessing pipeline. Each tree is then assigned a numerical score based on several weighted factors such as carbon sequestration, pollution filtration, space adaptability, maintenance level, and the presence of flowers or edible fruits, reflecting both ecological and urban planning priorities.

* The model is trained to predict the suitability score using both numeric and categorical inputs. The system uses Random Forest Regression for the prediction.

* The recommended tree species are spatially allocated along the centerline of the area polygon for visualization using Matplotlib. Additionally, the distribution and count of each tree species are displayed to provide a clear overview of species placement.

<p align="center">
  <img src="https://github.com/user-attachments/assets/27b2715a-c0d5-46f3-94fb-ac9970b96ef1" height="500"/>
  
  <img src="https://github.com/user-attachments/assets/d5ebeed6-bba9-4088-8cdc-cc222082685d" height="400"/>
</p>

## Results & Discussion

We evaluated our tree recommendation model using Random Forest Regression. The model achieved an R² score of 0.974 on the training set and 0.960 on the test set, with a near-zero Mean Squared Error in both cases. Cross-validation further confirmed the model’s performance with an average R² of 0.943 (±0.019).

The Actual vs. Predicted plot shows close alignment along the ideal line, indicating accurate predictions.

<p align="center">
<img src="https://github.com/user-attachments/assets/064a4fea-b999-4156-b7aa-c719a82baf62" height="300"/>
</p>

While the current model performs well, expanding the dataset to include more regions and incorporating a broader range of environmental and urban planning factors could further enhance the model’s generalizability. Additionally, evaluating more advanced models could improve prediction accuracy and reduce the risk of overfitting.

## Note

The data used in this project was gathered through online searches and from publicly available sources found on the web. No restricted or private data was accessed. This project is intended strictly for educational purposes.
