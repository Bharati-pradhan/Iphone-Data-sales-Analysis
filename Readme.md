# iPhone Sales Data Analysis

This project analyzes iPhone product ratings and sales data using Python, Pandas, Plotly, and Matplotlib. The dataset includes information about different iPhone products listed on Flipkart, including star ratings, number of reviews, and other details. The goal of this analysis is to identify the top-rated iPhone products and visualize their rating distribution.

## Features

- **Data Preprocessing**: Load, clean, and inspect the iPhone sales dataset.
- **Top 10 Highest Rated iPhones**: Extract the top 10 iPhone products with the highest ratings from the dataset.
- **Bar Chart Visualization**: Use both Plotly and Matplotlib to visualize the number of ratings for the highest-rated iPhones.

## Prerequisites

Before running the code, ensure you have the following libraries installed:

```bash
pip install pandas numpy matplotlib plotly
```

## Dataset

The dataset (`apple_products.csv`) contains information on various iPhone products on Flipkart, including:
- Product Name
- Star Rating
- Number of Ratings
- Other product details

## How to Run the Code

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Bharati-pradhan/Breast-Cancer-Prediction.git
   ```

2. **Navigate to the Project Folder**:
   ```bash
   cd iPhone-Sales-Data-Analysis
   ```

3. **Install Dependencies**:
   Install the required Python libraries if not already installed:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Analysis**:
   Open the Jupyter notebook or Python file where the code is implemented and run the cells to view the analysis and visualizations.

## Code Overview

### 1. Data Loading

The data is loaded from the `apple_products.csv` file:

```python
import pandas as pd

data = pd.read_csv("apple_products.csv")
```

### 2. Data Inspection

Basic inspections, including checking for missing values and a statistical description of the dataset:

```python
data.isnull().sum()  # Check for missing values
data.describe()      # Get basic statistical details
```

### 3. Finding the Top 10 Highest Rated iPhones

Sort the dataset based on the "Star Rating" to find the highest-rated iPhones:

```python
highest_rated = data.sort_values(by=["Star Rating"], ascending=False).head(10)
print(highest_rated['Product Name'])  # Display top 10 products
```

### 4. Visualizing the Data

#### Plotly Bar Chart

Plotly is used to create an interactive bar chart that shows the number of ratings for each iPhone product:

```python
import plotly.express as px

figure = px.bar(x=highest_rated['Product Name'], y=highest_rated['Number Of Ratings'], 
                labels={'x': 'Product Name', 'y': 'Number of Ratings'})
figure.show()
```

#### Matplotlib Bar Chart

Alternatively, Matplotlib is used to create a static bar chart of the same data:

```python
import matplotlib.pyplot as plt

plt.bar(highest_rated['Product Name'], highest_rated['Number Of Ratings'], color='skyblue')
plt.xlabel('Product Name')
plt.ylabel('Number of Ratings')
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

## Conclusion

This project analyzes iPhone products on Flipkart