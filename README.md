# Big_Data_GutMeal

## Problem Statement
In recent years, the connection between gut microbiome composition, dietary habits, and overall health has gained significant attention. Personalized nutrition, especially meal planning based on gut health indicators and lifestyle factors, offers a promising path toward improving metabolic, digestive, and inflammatory conditions.

The goal of this project is to develop a scalable machine learning model that can predict personalized meal plans based on a user's gut microbiome profile, dietary intake (protein, fiber, carbohydrate, fat), demographic details (age, gender), and allergy information. The system is designed to handle large-scale data in a distributed environment using PySpark and Spark MLlib, and integrates interpretable visualizations without compromising scalability.

By accurately predicting suitable meal plans, this solution aims to support:

Clinically relevant dietary guidance for individuals with specific gut conditions or food sensitivities
Commercial wellness applications offering precision nutrition at scale
Actionable insights into the relationship between microbial patterns and nutritional needs


## Data slection
Source:  American Gut Project, a study on food habits and lifestyle
Data:
	Microbiome Indicators:
	- Bacteroides
	- Firmicutes
	- Lactobacillus etc.
	Demographic Indicators:
	- Age
	- Gender
 	- BMI
	Nutrient Intake:
	- Protein Intake
	- Fiber Intake
	- Carbohydrate Intake etc
 
![image](https://github.com/user-attachments/assets/3c9d1f8e-a04e-4fa3-89ce-d2ee3ee4288e)

![image](https://github.com/user-attachments/assets/4d5e8469-7a10-4ccb-afb5-0b96bb4dd458)


## Exploratory data analysis
Majority of the participants consume medium amount of moderate amount of protein
Meal plan recommendations are imbalanced, skewing towards Eco-Friendly Low Sugar diets
Each meal plan is distinct recommendation based on age and BMI
Challenges:
Imbalanced classes in target variable
![image](https://github.com/user-attachments/assets/c8b78876-1a55-4137-9626-edcf5d0f5ac4)
![image](https://github.com/user-attachments/assets/b81fb764-2c04-4453-8384-c11eefd36e2b)
![image](https://github.com/user-attachments/assets/ff4b55a3-f7d1-409b-8408-ba589379d78b)


## Model Selection
### Logistic Regression (Base Model)
Simple and interpretable
Good baseline model for classification
Performs reasonably well, but limited in capturing complex relationships

### Decision Tree (Increment 1)
Easy to visualize and explain
Overfits on smaller or imbalanced data

### Random Forest (Increment 2)
Combines multiple trees for better stability
Improved performance over single tree

### Gradient Boosted Trees with One vs Rest (Increment 3)
Handle multi-class meal plan prediction
GBT captures complex relationships by sequentially improving decision trees
One-vs-Rest enables GBT to work with multiple classes by training a separate model for each


## Data Preperation 
Translated Diet and Allergy Information
Converted terms like “High Protein” or “Dairy Allergy” into a format the system can understand and learn from.

### Balanced the Meal Categories
Method 1: Upscale all classes to reduce imbalance, and bias
Method 2: Merge classes with low records, upscale the new class to reduce bias and imbalance

### Why It Matters
High-quality data means more accurate and trustworthy meal 	recommendations for users — essential for scaling and clinical 	relevance.


## Feature Selection
### Method 1
Correlation Matrix to assess the independence of each numerical variable
![image](https://github.com/user-attachments/assets/c5077e1a-6997-4b9c-8fd7-e244316d1545)

### Method 2
Chi Square test to select the categorical features
Correlation matrix to assess the independence of each numerical variable
![image](https://github.com/user-attachments/assets/b9bc7258-dab0-4acb-ab28-45ec127cb5f9)


## Model Selection
![image](https://github.com/user-attachments/assets/d06ff81a-577b-4d89-960d-bc85ec46a412)


## Random Forest (chosen model)
### Overview
Builds upon the performance Logistic Regression and Random Forrest, while avoiding the pitfalls of Gradient Boosting
The model achieved strong classification accuracy, especially in predicting commonly recommended plans like Mediterranean Gut Boost and Low-Carb Balanced. 
Accuracy: The model demonstrated high accuracy , indicating most predictions were correct.
Precision & Recall: Both were strong for common meal plans, confirming low false positive and false negative rates.
F1 Score: Balanced and high, showing reliable performance across the dataset.
Confusion Matrix: Minimal misclassifications, especially for well-represented meal plans.

### Business Insights
Enables scalable, personalized meal planning for apps or services.
Increases efficiency for dietitians by automating routine suggestions.
Adds competitive value to health and fitness platforms.
Boosts customer satisfaction and retention with tailored recommendations.

### Real-Life Implications
Supports better health outcomes with safe, informed meal choices.
Reduces allergy risks through intelligent filtering.
Empowers users to follow healthier diets easily.
Helps healthcare and insurers promote preventive care.

## Conclusion 
This project validates the use of a Random Forest classifier for recommending meal plans based on microbiome and lifestyle data. The model delivers robust performance across diverse dietary profiles by effectively capturing complex, non-linear relationships in the data. While predictions for common plans are accurate, there remains room to enhance sensitivity for specialized meal plans with limited representation.

Clinically, the system reflects real-world dietary science by aligning specific gut microbiome patterns—such as elevated Proteobacteria or low Firmicutes—with dietary needs like fiber boosting or inflammation reduction. This enables practical application in scenarios such as managing metabolic conditions, gut dysbiosis, and food sensitivities.

Commercially, it demonstrates strong potential for scalable, personalized nutrition platforms that integrate health data and technology.



























