# **DSA210-Project**

## **Project Description**

This project investigates the relationship between daily screen time and active energy expenditure. The goal is to evaluate whether there is a correlation between the two, using data collected from personal devices.

### **Hypotheses:**

- **Null Hypothesis (H₀):** There is no correlation between daily screen time and active energy expenditure.
- **Alternative Hypothesis (H₁):** There is a significant correlation between daily screen time and active energy expenditure.

In a digital world where screen time has become a central part of daily life, understanding its potential impact on physical activity can provide valuable insights for maintaining a balanced and healthy lifestyle.

---

## **Dataset**

### **Screen Time Data**
- **Source:** Extracted using the [ScreenTime2CSV tool](https://github.com/FelixKohlhas/ScreenTime2CSV).
- **Metrics:** Daily total screen time in minutes, aggregated from iOS/macOS Screen Time logs.

### **Active Energy Data**
- **Source:** iOS Health App.
- **Metrics:** Calories burned during active movement (excluding basal metabolic rate).

---

## **Data Cleaning and Preprocessing**

To ensure consistency in our analysis, I performed the following modifications to the CSV files:

1. **Screen Time CSV:**
   - Kept only the `date` and `total_screen_time_minutes` columns, removing unnecessary fields.
   - Converted timestamps to `datetime` format for consistency.

2. **Active Energy CSV:**
   - Retained only the `date` and `active_energy_kcal` columns.
   - Addressed missing values and formatting issues before merging datasets.

3. **Merging the Datasets:**
   - Merged both datasets on the `date` column to create a unified DataFrame for analysis.

---

## **Exploratory Data Analysis (EDA)**

To better understand the relationship between screen time and active energy, I performed the following visualizations:

### **1. Daily Trends Over Time:**
- **Screen Time Plot:** A line plot showing daily total screen time (in minutes). This highlighted daily fluctuations, with values ranging from **100 to 600+ minutes**. Peaks indicated potential "binge" usage days.
- **Active Energy Plot:** A line plot for daily active energy (in kcal). This revealed rest days with **less than 100 kcal burned** and active days with **over 400 kcal**.
- **Insights:** While both metrics fluctuated over time, there were no immediately obvious cyclical patterns.

### **2. Scatter Plot: Screen Time vs. Active Energy:**
- A scatter plot was used to visualize the relationship between screen time and active energy for each day.
- **Insights:** There was no clear trend or strong clustering in the plot. The points were widely scattered, suggesting only a weak relationship.

### **3. Correlation Coefficient Calculation:**
- Both **Pearson** (linear) and **Spearman** (monotonic) correlation coefficients were computed.
- Results indicated a **weak negative correlation** with high p-values, meaning the correlations were **not statistically significant**.

### **4. Weekly Averages:**
- To smooth out daily fluctuations, the data was resampled to compute weekly averages.
- A line plot showed that **screen time** was relatively high during the last week of December, while **active energy** dipped during the same period.

### **5. Workday vs. Weekend Comparison:**
- A bar chart was plotted to compare average screen time and active energy during workdays vs. weekends.
- **Insights:** There was minimal difference between workdays and weekends in terms of screen time and active energy, suggesting consistent digital habits throughout the week.

---

## **Hypothesis Testing**

### **Overall Correlation:**
- **Pearson Correlation:** `-0.167`, p-value: `0.385` (not statistically significant).
- **Spearman Correlation:** `-0.251`, p-value: `0.189` (not statistically significant).

### **Workdays vs. Weekends:**
- **Workdays Correlation:**
  - Pearson: `-0.152`, p-value: `0.510` (no significant correlation).
  - Spearman: `-0.235`, p-value: `0.305` (no significant correlation).
  
- **Weekends Correlation:**
  - Pearson: `-0.243`, p-value: `0.563` (no significant correlation).
  - Spearman: `-0.048`, p-value: `0.910` (no significant correlation).

---

## **Key Findings**

1. **Overall Relationship:**
   - No significant correlation between daily screen time and active energy expenditure.
   - The weak negative trend suggests that high screen time may coincide with slightly lower physical activity, but this relationship is not strong or consistent.

2. **Workday vs. Weekend Patterns:**
   - No meaningful difference in correlation strength between workdays and weekends.
   - Screen time and active energy expenditure appeared relatively independent of the type of day.

---

## **Conclusion and Insights**

- **Conclusion:** 
  The null hypothesis cannot be rejected, indicating no significant correlation between screen time and active energy expenditure in the dataset.
  
- **Implications:** 
  Other lifestyle factors (e.g., sleep duration, exercise habits) may influence the patterns observed.

- **Future Research Directions:**
  - **Subgroup Analysis:** Examine specific time periods (e.g., morning vs. evening) to uncover more granular trends.
  - **Larger Sample Size:** Collect data over a longer period to increase the reliability of the analysis.
  - **Additional Metrics:** Include variables such as step count, workout logs, or heart rate data for deeper insights.

---
