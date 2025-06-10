# ☕ Coffee Sales Data Analysis Project Using Python

In this project, I analyzed **1,133 coffee sales transactions** using **Python, Pandas, Seaborn, and Matplotlib**, uncovering insights into customer purchasing behavior and revenue trends. Here's a detailed breakdown with key statistics and Python functions used:  

### **🔹 Data Preprocessing & Cleaning**  
- Checked for missing values using `data.isnull().sum()`, revealing **89 missing entries** in the `card` column.  
- Converted date and datetime columns to proper formats using:  
  ```python
  data['date'] = pd.to_datetime(data['date'])
  data['datetime'] = pd.to_datetime(data['datetime'])
  ```
- Created new time-based features: `month`, `day`, and `hour` using `.dt.strftime()` to facilitate deeper analysis.  

### **🔹 Revenue & Sales Trends**  
- The dataset's total revenue from coffee sales was:  
  ```python
  total_revenue = data['money'].sum()
  print(f'Total Revenue: {total_revenue}')
  ```
  **₹37,492.50**, with an **average price of ₹33.11 per coffee**.  
- Using `.groupby()` and `.sum()`, identified **Americano with Milk** as the highest-selling coffee with **268 purchases**.  

### **🔹 Customer Payment Preferences**  
- **92.14% of transactions** were card-based:  
  ```python
  data['cash_type'].value_counts(normalize=True) * 100
  ```
- **All missing card values were cash transactions**, as confirmed with:  
  ```python
  data[data['card'].isnull()]['cash_type'].value_counts()
  ```

### **🔹 Time-Based Sales Analysis**  
- **Peak Sales Days:** Weekday analysis using `.groupby(['day']).count()` revealed **Friday had the highest transactions**.  
- **Hourly Demand Patterns:**  
  ```python
  hourly_sales = data.groupby(['hour']).count()['date'].reset_index().rename(columns={'date':'count'})
  ```
  Sales peaked between **10 AM to 1 PM**, aligning with morning coffee cravings.  

### **🔹 Visualizing Insights**  
Using **Seaborn & Matplotlib**, I created various plots for intuitive analysis:  
- **Bar Chart** showing total revenue per coffee type:  
  ```python
  sns.barplot(data=revenue_data, x='money', y='coffee_name', color='steelblue')
  ```
- **Time Series Trends** depicting monthly fluctuations in coffee sales:  
  ```python
  sns.lineplot(data=monthly_sales)
  ```

### **🔹 Key Business Takeaways**  
✅ Focused marketing efforts on **Americano with Milk**, the most popular choice.  
✅ Optimized staff scheduling for peak hours (**10 AM - 1 PM**).  
✅ Considered discounts on slower-selling coffee types.  

This analysis provides **actionable insights for revenue optimization, demand forecasting, and business strategy refinement**. Excited to connect with fellow data enthusiasts and share more learnings! 🚀  

#DataScience #Python #Visualization #CoffeeTrends #Analytics  

Does this level of detail align with what you're looking for? Let me know if you'd like further refinements! 📊🔥  
