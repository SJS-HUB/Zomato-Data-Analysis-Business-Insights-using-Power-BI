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
IF('Zomato India Data'[CountryCode] IN {1, 162, 166, 184, 191, 204, 208, 214}, "Asia",
IF('Zomato India Data'[CountryCode] IN {14, 148}, "Australia",
IF('Zomato India Data'[CountryCode] IN {37, 94, 216}, "North America", 
IF('Zomato India Data'[CountryCode] = 30, "South America",
IF('Zomato India Data'[CountryCode] = 189, "Africa",
IF('Zomato India Data'[CountryCode] = 215, "Europe", BLANK()
))))))
```

## **Measures**

### 1. Cuisine Count
```DAX
Cuisine Count = COUNT('Zomato India Data'[Count])
```

### 2. Restaurant Count
```DAX
Restaurant count = COUNT('Zomato India Data'[RestaurantID])
```

### Additional Features
- Conditional coloring applied to the ratings column for better visualization.


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

