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

To ensure consistency in our analysis, we performed the following modifications to the CSV files:

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

### **Trends Over Time:**
- **Daily Screen Time:** Fluctuated between **100 and 600+ minutes**, with some outliers indicating very high usage days.
- **Daily Active Energy:** Varied from less than **100 kcal** (low activity/rest days) to over **400 kcal** on active days.

### **Patterns:**
- No strong weekly cycles in screen time or active energy.
- Minor increases in screen time during weekends, though not always accompanied by increased activity.

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

