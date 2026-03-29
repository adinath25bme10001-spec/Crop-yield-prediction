# Crop Yield Prediction System

A simple Machine learning based system built in python that predicts the crop yield based on the field conditions. This project compares the predicted field condition against actual field conditions and gives the difference between them and also give the difference using a bar chart.
This project uses a basic mathematical approach to estimate crop yield based on environment and agricultural factors.

# Project Description

This project is a simple crop yield prediction system where users can input different field conditions like rainfall, temperature, humidity, fertilizer usage, soil pH, sunlight, and irrigation levels.

The idea is to estimate how much crop yield we might get based on these inputs. Along with that, the system also lets users compare what they expected versus what actually happened in the field.

So basically, you can:

Enter predicted conditions (what you think will happen)
Enter actual conditions (what really happened later)
See both results side by side
And check the difference visually using a graph

# How It Works

Historical Data — Sample data on past seasonal field conditions, e.g., rainfall, temperature, humidity, etc., are used for training, and weights are calculated.
---
2. Weight Calculation — For each of the 7 factors, weights are calculated by averaging "yield/feature" across all historical data.

3. Prediction Phase — The user inputs their predicted field conditions, and each field condition is multiplied by its corresponding weight and summed up to get the predicted yield.

4. Actual Phase — The user inputs their actual field conditions, and the formula is used again to get the actual yield.

5. Comparison — The actual and predicted yields are compared, and their difference is calculated.

6.Visualization — A bar chart is plotted, showing actual and predicted yields side by side, with their difference annotated on the chart.


# Dataset

Each row in the database represent the past sectional field conditions.


Each record contains 8 columns:


Rainfall (mm)	Temp (°C)	Humidity (%)	Fertilizer     (kg/ha)	Soil pH	Sunlight (hours)	Irrigation (0–10)	
Yield (tons/ha)

1000	41	60	58	8.5	10.4	9	4.2
2200	38	65	45	7.2	9.8	8	5.8
4000	35	85	38	6.2	8.4	4	8.9
5000	29	90	30	6.5	7.6	2	9.5
2800	38	75	49	7.0	9.0	7	6.0

Note:

This dataset is completely imaginary / sample data. This is only for understanding that how the prediction works.

# Input Features


Here total 7 parameters are used


Rainfall (mm)

Temperature (°C)

Humidity (%)

Fertilizer (kg/ha)

Soil pH

Sunlight (hours)

Irrigation level (0–10)


# Outputs Features

Predicted Crop Yield (tons/ha)

Actual Crop Yield (tons/ha)

Difference between predicted and actual

Bar graph showing comparison



# Graph Output

The system generates a bar chart:

X-axis → Type (Actual vs Predicted)
Y-axis → Yield (tons/ha)

Displays difference value on graph



 # Prediction Logic


weight[i] = average(yield / feature[i])   for each of the 7 features

predicted_yield = Σ (input[i] × weight[i])  / 10


Weights are derived from past data.
The final yield is divided by 10 to scale so that the result to be a realistic range.
The result is rounded to 2 decimal places.


The same is also applied for the actual inputs also


# Difference Calculation

difference = actual_yield - predicted_yield

This gives a rough measure of prediction accuracy. A value close to 0 means the prediction was accurate.




# Technologies Used

 Technology                      Purpose

 Python                 Core programming  language
 matplotlib                Graph/chart plotting



# How to Run

1.Make sure Python is installed on your system.

2.Install the required library:

 pip install matplotlib

3.Run the script:

bash   python crop_yield_prediction.py

4.Enter your predicted field conditions when prompted.

5.Enter your actual field conditions when prompted.

6.View the printed results and the bar chart that appears.



# Example Interaction



Enter the following values for prediction:

Rainfall (mm): 3000
Temperature (C): 33
Humidity (%): 78
Fertilizer (kg/ha): 40
Soil pH: 6.8
Sunlight (hours): 8.5
Irrigation level (0-10): 6

Predicted Crop Yield (tons/ha): 7.43

Now enter ACTUAL field conditions:

Actual Rainfall (mm): 3200
...
...

Actual Crop Yield (tons/ha): 7.89

Difference (Actual - Predicted): 0.46



# Limitations

The dataset used is imaginary and not based on real agricultural research.
The weight calculation is a simplified custom formula and not a standard ML algorithm (e.g., Linear Regression, Random Forest).
The model does not account for crop type, region, season, or pest/disease effects.
Accuracy depends heavily on how realistic the input values are.



# Conclusion

This project demonstrates how basic mathematical logic can be used to a simple crop yield prediction system. It helps in understanding how input factors influence output and introduces fundamental ML concepts in a simple way.
