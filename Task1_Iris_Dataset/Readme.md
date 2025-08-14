# **Iris Dataset Analysis**

## **Objective**
Learn how to load, inspect, and visualize a dataset to understand data trends and distributions.

---

## **Dataset**
**Iris Dataset** (CSV format, can be loaded via Seaborn or downloaded manually)

---

## **Skills Demonstrated**
- **Data loading and inspection** using Pandas  
- **Descriptive statistics** and data exploration  
- **Basic plotting and visualization** with Seaborn and Matplotlib  

---

## **Steps Performed**

### **1. Load the Dataset**
- Used `seaborn.load_dataset('iris')` to load the dataset directly.

### **2. Data Inspection**
- Printed dataset **shape**, **column names**, and first five rows using `.head()`.
- Used `.info()` to view column data types and null value counts.
- Used `.describe()` for summary statistics.

### **3. Data Visualization**
- **Scatter Plot**: To show the relationship between Sepal Length and Sepal Width.
- **Histograms**: To display the value distribution of each numerical column.
- **Box Plots**: To identify outliers in the dataset.
- **Pair Plot**: To visualize relationships between all feature pairs, grouped by species.

---

## **Code**
The complete Python code for this analysis is available in [`Task1_Iris_Datset.ipynb`](Task1_Iris_Datset.ipynb).

---

## **Output Examples**
### Scatter Plot
Shows how Sepal Length and Sepal Width vary for different species.

### Histograms
Reveal the frequency distribution for each feature.

### Box Plots
Help detect outliers and spread of data.

### Pair Plot
Provides a comprehensive look at feature relationships and clustering by species.

---

## **Conclusion**
The Iris dataset provides a clear example for practicing data loading, inspection, and visualization techniques.  
By using Pandas, Matplotlib, and Seaborn, we can gain insights into trends, distributions, and relationships in the data.
