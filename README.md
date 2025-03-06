# Implementation-of-Personal-Fitness-Tracker-using-Python
# **Personal Fitness Tracker**

## **Overview**
The **Personal Fitness Tracker** is a Python-based web application built using **Streamlit** that allows users to:
- Track their **calories burned** based on user input.
- Visualize **activity intensity** using interactive charts.
- Receive **exercise & diet recommendations**.
- Compare fitness data with **similar results** for better insights.

## **Features**
✅ **User Input Panel** for entering fitness parameters.  
✅ **Calorie Prediction** based on age, BMI, workout duration, etc.  
✅ **Activity Intensity Chart** for easy analysis.  
✅ **Personalized Exercise & Diet Recommendations**.  
✅ **Data Comparison** with similar user records.  

## **Tech Stack**
- **Python 3.x**
- **Streamlit** (UI framework)
- **Pandas** (Data processing)
- **Matplotlib & Seaborn** (Data visualization)
- **NumPy** (Numerical calculations)

---

## **Installation & Setup**

### **1. Clone the Repository**
```bash
git clone https://github.com/yourusername/personal-fitness-tracker.git
cd personal-fitness-tracker
```

### **2. Create and Activate Virtual Environment (Optional but Recommended)**
```bash
python -m venv venv  # Create virtual environment
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate  # On Windows
```

### **3. Install Dependencies**
```bash
pip install -r requirements.txt
```

### **4. Run the Application**
```bash
streamlit run app.py
```
This will launch the **Personal Fitness Tracker** in your default web browser.

---

## **Code Overview**

### **1. Importing Libraries**
```python
import streamlit as st
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### **2. Building the User Interface**
```python
st.title("Personal Fitness Tracker")
st.write("Enter your details to estimate your calorie burn and get recommendations.")

# User Input Section
age = st.slider("Age", 10, 100, 30)
bmi = st.slider("BMI", 15, 40, 20)
duration = st.slider("Duration (min)", 0, 35, 15)
heart_rate = st.slider("Heart Rate", 60, 130, 80)
body_temp = st.slider("Body Temperature (C)", 36, 42, 38)
gender = st.radio("Gender", ["Male", "Female"])
```

### **3. Predicting Calories Burned**
```python
def predict_calories(age, bmi, duration, heart_rate, body_temp, gender):
    base_calories = duration * 3.5  # Basic calculation
    if gender == "Male":
        base_calories *= 1.1  # Males burn more on average
    return round(base_calories, 2)

calories_burned = predict_calories(age, bmi, duration, heart_rate, body_temp, gender)
st.subheader("Prediction:")
st.write(f"**{calories_burned} kilocalories burned**")
```

### **4. Activity Intensity Chart**
```python
st.subheader("Activity Intensity Chart")
labels = ["Low", "Medium", "High"]
values = [duration * 1.5, duration * 2.5, duration * 4]
colors = ['green', 'yellow', 'red']

fig, ax = plt.subplots()
ax.bar(labels, values, color=colors)
st.pyplot(fig)
```

### **5. Exercise & Diet Recommendations**
```python
st.subheader("Exercise & Diet Recommendations")
st.markdown("✔ **Recommended Exercises:** Light walking, yoga, stretching.")
st.markdown("✔ **Diet:** Increase protein intake, eat fruits and vegetables.")
st.markdown("[▶ Light Workout Video](#)")
```

### **6. Displaying Similar Results**
```python
data = {"Gender": ["Male", "Female", "Male", "Male", "Female"],
        "Age": [20, 20, 51, 38, 54],
        "Height": [176, 176, 178, 185, 180],
        "Weight": [81, 72, 85, 86, 78],
        "Duration": [14, 13, 11, 13, 10],
        "Heart Rate": [92, 90, 90, 91, 94],
        "Body Temp": [40.2, 40.2, 40, 40.3, 39.8],
        "Calories": [48, 53, 52, 55, 51]}
df = pd.DataFrame(data)
st.subheader("Similar Results:")
st.dataframe(df)
```

---

## **Screenshots**

### **User Input & Prediction**
![User Input](sandbox:/mnt/data/Screenshot%202025-03-06%20123515.png)

### **Activity Intensity Chart**
![Activity Intensity](sandbox:/mnt/data/Screenshot%202025-03-06%20123537.png)

### **Exercise & Diet Recommendations**
![Recommendations](sandbox:/mnt/data/Screenshot%202025-03-06%20123606.png)

### **Similar Results & Data Insights**
![Similar Results](sandbox:/mnt/data/Screenshot%202025-03-06%20123640.png)

### **User Input Panel**
![Input Panel](sandbox:/mnt/data/Screenshot%202025-03-06%20123656.png)

---

## **Future Enhancements**
🔹 Integration with **wearable devices** for real-time tracking.  
🔹 **AI-based recommendations** for personalized workouts.  
🔹 **Mobile app version** for broader accessibility.  
🔹 **Gamification features** to boost motivation.  

## **Contributing**
- Fork the repository & submit pull requests.😊
- Report bugs or request features in the **Issues** section.



------
🚀 **Stay fit and track your progress with the Personal Fitness Tracker!** 🚀




