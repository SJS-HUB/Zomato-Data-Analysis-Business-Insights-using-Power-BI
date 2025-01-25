# Zomato Power BI Project

## 📜 Overview
Zomato is a leading restaurant aggregation and meal delivery service operating globally. This project creates an interactive and consolidated **Power BI Dashboard** to help Zomato analyze its business performance and uncover irregularities in its data.

## 🎯 Project Goals
1. Analyze the **total number of restaurants** worldwide (by continents, countries, and cities).  
2. Provide a **global view** with drill-down capabilities.  
3. Identify **top-rated restaurants** and those with **lowest costs**.  
4. Allow filtering by:
   - Geographical location (continent, country, city).  
   - Services provided (online ordering, reservation services).  
   - Rating slabs with color-coded visuals.  
5. Highlight restaurants with the **most cuisines served**.  
6. Design a **multi-page Power BI report** aligned with Zomato's theme.  
7. Ensure compatibility with **web browsers** and **mobile devices**.

---

## 🚀 Features
- **Global Overview:** Interactive map with drill-down capabilities from continents to cities.  
- **Performance Insights:** Identify top-rated and lowest-cost restaurants.  
- **Filtering Options:** Easy-to-use filters for location, services, and ratings.  
- **Cuisine Analysis:** Find restaurants with the most cuisines.  
- **User-Friendly Design:** Zomato-themed multi-page layout with smooth navigation.  
- **Cross-Device Compatibility:** Optimized for web and mobile use.

---

## 📂 Data Preparation
1. **Data Import:** Consolidated multiple Excel files containing restaurant data by continent.  
2. **City Name Corrections:**  
   - Standardized names (e.g., "Sí£o Paulo" → "São Paulo", "ÛÁstanbul" → "Istanbul").  
   - Removed ambiguities (e.g., "Cedar Rapids/Iowa City" → "Cedar Rapids").  
3. **Column Optimization:** Removed unused columns to streamline the dataset.  
4. **Restaurant Details:** Added columns for:
   - Restaurant Name  
   - Restaurant Address  
5. **Cuisine Table:** Created a separate dimension table listing cuisines for each restaurant.  
6. **Country-Code Table:** Ensured unique, non-blank values and added a "Continent" column.

---

## 📊 DAX Calculations
This document contains all the DAX formulas used in the Power BI Zomato project, including calculated columns and measures.

## **Calculated Columns**

### 1. Continent
```DAX
Continent = 
SWITCH(
    TRUE(),
    'Table'[Country] IN {"India", "Pakistan", "Bangladesh"}, "Asia",
    'Table'[Country] IN {"USA", "Canada"}, "North America",
    'Table'[Country] IN {"Germany", "UK", "France"}, "Europe",
    'Table'[Country] IN {"Australia"}, "Australia",
    'Table'[Country] IN {"Brazil", "Argentina"}, "South America",
    'Table'[Country] IN {"South Africa", "Nigeria"}, "Africa",
    "Other"
)
```

### 2. Cuisine Count
```DAX
Cuisine Count = 
COUNTROWS(
    DISTINCT('Table'[Cuisines])
)
```

## **Measures**

### 1. Restaurant Count
```DAX
Restaurant Count = 
DISTINCTCOUNT('Table'[Restaurant Name])
```

### 2. Average Cost for Two
```DAX
Average Cost = 
AVERAGE('Table'[Cost for Two])
```

### 3. Average Rating
```DAX
Average Rating = 
AVERAGE('Table'[Aggregate Rating])
```

### 4. Total Votes
```DAX
Total Votes = 
SUM('Table'[Votes])
```

### 5. Top City by Restaurants
```DAX
Top City = 
TOPN(1, VALUES('Table'[City]), [Restaurant Count], DESC)
```

### 6. Total Number of Chains
```DAX
Total Chains = 
COUNTROWS(
    DISTINCT('Table'[Restaurant Name])
)
```

### 7. Rating Bucket
```DAX
Rating Bucket = 
SWITCH(
    TRUE(),
    'Table'[Aggregate Rating] >= 4.5, "Excellent",
    'Table'[Aggregate Rating] >= 4.0, "Very Good",
    'Table'[Aggregate Rating] >= 3.5, "Good",
    'Table'[Aggregate Rating] >= 3.0, "Average",
    "Below Average"
)
```

### 8. Revenue Estimation
```DAX
Revenue = 
[Average Cost] * [Restaurant Count]
```


## 🎨 Dashboard Design
- **Multi-Page Layout:**  
  - Global Overview  
  - Restaurant Insights (Ratings, Costs)  
  - Cuisine Analysis  
- **Filters:**  
  - By Continent, Country, and City  
  - By Services (Online ordering, Reservations)  
  - By Ratings (Color-coded slabs)  
- **Theme:** Designed with Zomato's branding for consistency.  

---

## 🔧 How to Use
1. Clone or download the repository.  
2. Open the Power BI file in **Power BI Desktop**.  
3. Interact with the dashboard:  
   - Use filters to refine data.  
   - Navigate across pages for detailed analysis.  
   - Drill down from global to city-level data.  

---

## 📈 Key Outcomes
- Comprehensive insights into Zomato's global restaurant operations.  
- Easy identification of top-performing restaurants and improvement areas.  
- Enhanced decision-making through actionable data visualization.  

---

## 🖥️ Tools & Technologies
- **Power BI** for dashboard creation and data visualization.  
- **DAX** for calculated columns and measures.  
- **Excel** for data preprocessing.  

---

## 🤝 Contributions
Contributions are welcome! Feel free to open issues or submit pull requests to improve the project.

---

## 📧 Contact
For queries or suggestions, feel free to reach out:  
**Sharada Sonaje** - [LinkedIn](http://www.linkedin.com/in/sharada-s-83b958273) | [Email](sharadasonaje25@gmail.com)

