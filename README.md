# Crop Yield Prediction

Dataset link: https://www.kaggle.com/datasets/akshatgupta7/crop-yield-in-indian-states-dataset

* Problem Statement: The goal is to predict crop yield based on various features related to agriculture in Indian states.

* Task type: **Regression**

* Features: 

| **Column**         | **Description**                                                            |
|--------------------|----------------------------------------------------------------------------|
| Crop               | The name of the crop cultivated.                                           |
| Crop_Year          | The year in which the crop was grown.                                      |
| Season             | The specific cropping season (e.g., Kharif, Rabi, Whole Year).             |
| State              | The Indian state where the crop was cultivated.                            |
| Area               | The total land area (in hectares) under cultivation for the specific crop. |
| Production         | The quantity of crop production (in metric tons).                          |
| Annual_Rainfall    | The annual rainfall received in the crop-growing region (in mm).           |
| Fertilizer         | The total amount of fertilizer used for the crop (in kilograms).           |
| Pesticide          | The total amount of pesticide used for the crop (in kilograms).            |
| Yield              | The calculated crop yield (production per unit area).                      |

## Pipeline:

1. Data Loading: Data Loading: Loading the data and reviewing the first and last five rows.

2. Data Description: Providing a basic description of the dataset, including column information (data types and non-null counts), statistics for numerical columns (max, min, standard deviation, quantiles, etc.), and counting null values in columns.

3. Data Encoding: Cleaning the data by encoding categorical values.

4. Model Creation and Evaluation: Building models and evaluating their performance based on metrics.

## Models used as of version 1.0:

* Linear Regression

* Xtreme Gradient Boosting(XGB) Regressor

* Decision Tree Regressor or Regression Tree

* Best Metrics (VERS 1.0): Regression Tree

Mean Absolute Error: 7.983686352867446

Mean Squared Error: 126.0381354941169

R-squared Score: 0.9794002575574614

* Contender: XGB Regressor

Mean Absolute Error: 13.342473329651927

Mean Squared Error: 126.96814795459791

R-squared Score: 0.9790951324643361

---

## Website integration

The ML model can be "pickled" using Python's pickle library for object serialization into a byte-file, which can be stored as a web resource to be called at runtime.

By building a website which takes in necessary details, running it through similar encoding procedures to be turned into numerical values and deserializing our model's byte-file, we can predict and return our prediction with the help of a flask application file over APIs.

1. Building a web interface to collect user input
2. Processing the input (including encoding categorical variables)
3. Loading the serialized model
4. Making predictions
5. Returning results via an API