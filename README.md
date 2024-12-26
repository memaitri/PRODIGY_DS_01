# PRODIGY_DS_01
Create a bar chart or histogram to visualize the distribution of a categorical or continuous variable, such as the distribution of ages or genders in a population.

import matplotlib.pyplot as plt
import pandas as pd

# Data for the visualization
data = {
    "Country": [
        "Afghanistan", "Albania", "Algeria", "American Samoa", "Andorra", "Angola", 
        "Argentina", "Armenia", "Australia", "Austria", "Azerbaijan", "Bangladesh", 
        "Belgium", "Bolivia", "Brazil", "Cambodia", "Cameroon", "Canada", "Chad", 
        "Chile", "China", "Colombia", "Congo, Dem. Rep.", "Denmark", "Ecuador", 
        "Egypt, Arab Rep.", "Ethiopia", "France", "Germany", "India", "Indonesia", 
        "Iran, Islamic Rep.", "Iraq", "Italy", "Japan", "Kenya", "Mexico", 
        "Nigeria", "Pakistan", "Philippines", "Russian Federation", "South Africa", 
        "Sudan", "Turkey", "United Kingdom", "United States", "Viet Nam", "World"
    ],
    "Population (Thousands)": [
        41454.76, 2745.97, 46164.22, 47.52, 80.86, 36749.91, 45538.4, 2990.9, 
        26658.95, 9131.76, 10153.96, 171466.99, 11787.42, 12244.16, 211140.73, 
        17423.88, 28372.69, 40097.76, 19319.06, 19658.83, 1410710.0, 52321.15, 
        105789.73, 5946.95, 17980.08, 114535.77, 128691.69, 68287.49, 83280.0, 
        1438069.6, 281190.07, 90608.71, 45074.05, 58993.47, 124516.65, 55339.0, 
        129739.76, 227882.95, 247504.49, 114891.2, 143826.13, 63212.38, 50042.79, 
        85325.96, 68350.0, 334914.9, 100352.19, 8061876.0
    ]
}

# Convert the data into a DataFrame for easier manipulation
df = pd.DataFrame(data)

# Sort the data for a cleaner visualization
df_sorted = df.sort_values(by="Population (Thousands)", ascending=False).head(10)

# Create the bar chart
plt.figure(figsize=(12, 8))
plt.bar(df_sorted["Country"], df_sorted["Population (Thousands)"], color="skyblue")
plt.xlabel("Country")
plt.ylabel("Population (Thousands)")
plt.title("Top 10 Countries by Population in 2023 (in Thousands)")
plt.xticks(rotation=45, ha="right")
plt.tight_layout()
plt.show()

