# 🥗 Big_Data_GutMeal – AI-Powered Personalized Nutrition


## 📌 Problem Statement

In recent years, the connection between **gut microbiome composition**, **dietary habits**, and **overall health** has gained significant attention. Personalized nutrition—especially meal planning based on gut health indicators and lifestyle factors—offers a promising path toward improving **metabolic**, **digestive**, and **inflammatory conditions**.

The goal of this project is to develop a **scalable machine learning model** that can predict **personalized meal plans** based on:
- Gut microbiome profile (e.g., Bacteroides, Firmicutes)
- Dietary intake (protein, fiber, carbohydrate, fat)
- Demographic features (age, gender, BMI)
- Food allergy data

The system is built using **PySpark and Spark MLlib**, optimized for **big data environments**, with interpretable visualizations and clinically relevant outcomes.


## 📂 Data Selection

**Source**: American Gut Project and lifestyle survey data

**Data Features**:
- **Microbiome Indicators**: Bacteroides, Firmicutes, Lactobacillus, etc.
- **Demographics**: Age, Gender, BMI
- **Nutrient Intake**: Protein, Fiber, Carbohydrates, Fat
- **Allergies**: Dairy, Gluten, Nuts
 
![image](https://github.com/user-attachments/assets/4d5e8469-7a10-4ccb-afb5-0b96bb4dd458)

![image](https://github.com/user-attachments/assets/edf7ba60-a764-4192-8f90-7c6ab51d5f8b)


## 📊 Exploratory Data Analysis (EDA)

- Most users consume **moderate levels** of protein and fiber.
- **Meal plan labels are imbalanced**, heavily skewed toward a few diets.
- Age and BMI trends vary across plans, suggesting feature relevance.

**Challenges Identified**:
- Significant **class imbalance** in target labels.
  
![image](https://github.com/user-attachments/assets/c8b78876-1a55-4137-9626-edcf5d0f5ac4)

![image](https://github.com/user-attachments/assets/b81fb764-2c04-4453-8384-c11eefd36e2b)

![image](https://github.com/user-attachments/assets/ff4b55a3-f7d1-409b-8408-ba589379d78b)


## 🧠 Model Selection

### 1. Logistic Regression (Baseline)
- Interpretable and fast
- Limited in handling non-linear relationships

### 2. Decision Tree
- Easy to interpret
- Prone to overfitting with class imbalance

### 3. Random Forest ✅ *(Chosen Model)*
- Handles non-linearity and mixed feature types
- Reduced overfitting; better overall performance

### 4. Gradient Boosted Trees (GBT) + One-vs-Rest
- High potential for accuracy
- More resource intensive and complex to tune


## 🛠️ Data Preparation

- **Categorical Encoding**: Converted text labels like “High Protein” into numeric indices
- **Allergy Normalization**: Cleaned inconsistent allergy formats
- **Class Balancing**:
  - Method 1: Upsample minority classes
  - Method 2: Merge similar rare classes and resample


## 📌 Feature Selection

### Method 1: Correlation Matrix
- Assessed relationships between numeric variables

![image](https://github.com/user-attachments/assets/c5077e1a-6997-4b9c-8fd7-e244316d1545)

### Method 2
- Chi Square test to select the categorical features
- Correlation matrix to assess the independence of each numerical variable
  
![image](https://github.com/user-attachments/assets/b9bc7258-dab0-4acb-ab28-45ec127cb5f9)


## Model Results

![image](https://github.com/user-attachments/assets/d06ff81a-577b-4d89-960d-bc85ec46a412)


## 🤖 Final Model – Random Forest

### 🔍 Performance Overview
- Achieved **74% accuracy**
- High **precision and recall** for frequent meal plans
- Low misclassification on common categories
- Strong **F1 Score**, indicating balanced performance

### 💼 Business Insights
- Enables **scalable meal planning** in wellness apps
- Automates basic nutrition logic for dietitians
- Adds differentiation to health tech platforms

### 🏥 Real-Life Impact
- Supports better health decisions with informed recommendations
- Reduces allergy risk with built-in constraints
- Promotes preventive care via smart meal suggestions


## ✅ Conclusion

This project validates the use of a **Random Forest classifier** for recommending meal plans based on gut microbiome and lifestyle data. The model demonstrated strong predictive performance, especially for common diet plans, by learning complex patterns in user microbiome and intake profiles.

**Clinically**, it aligns with evidence-based nutritional science—for example, matching high *Proteobacteria* with fiber-boosting plans, or recommending low-sugar plans for higher BMI users.

**Commercially**, the system offers a scalable, AI-powered foundation for personalized nutrition platforms and wellness solutions.


























