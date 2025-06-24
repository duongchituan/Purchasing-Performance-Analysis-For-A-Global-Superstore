# 📊 Purchasing Performance | Power BI

---
![ChatGPT Image 02_07_08 24 thg 6, 2025](https://github.com/user-attachments/assets/eda03e9e-dc15-4842-8ce5-babab120cc21)



Author: Duong Chi Tuan  
Date: May 2025  
Tools Used: Power BI  

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations & Recommendations](#-key-insights--visualizations)  

---

## 📌 Background & Overview  

### Objective:
### 📖 What is this project about? 
 
This project provides a Power BI dashboard to support strategic decision-making. The objective is:  

- Understand company-wide sales performance

- Identify top products & regions for market expansion

- Support senior management in selecting strategic products 

### 👤 Who is this project for?  

✔️ Senior managers & business decision-makers  

✔️ Strategy teams exploring market expansion  

✔️ Product managers evaluating performance  

✔️ Data analysts supporting executive insights  

###  ❓Business Questions:  
✔️ Which products generate the most revenue and profit?  

✔️ What are the top-performing regions or markets?  

✔️ Which customer segments are the most valuable?  

✔️ Are there markets with growth potential we haven’t tapped into yet?  

✔️ What trends can inform our product and market expansion strategies?  

### 🎯Project Outcome:  
✔️ Profit Margin Decline in 2014:
Despite a strong revenue increase (+24% vs. 2013), the company experienced a slight drop in overall profit margin (from 11.97% to 11.51%) due to rising operational costs.

✔️ Shift Toward Costly Shipping Methods:
There was an increase in order volume using high-cost shipping methods, especially First Class (+33%) and Same Day (+25%), which led to faster growth in shipping expenses than in gross profit.

✔️ Suboptimal Product Mix Impacting Margins:
The surge in Office Supplies orders—typically low-margin products—combined with costly shipping methods, contributed to the margin decline.

✔️ Return Rate Remained Stable:
Return rates in key markets (APAC, EU, US) remained steady (around 5–7%) and were not a major driver of profit decline.

✔️ High-Margin Niche Market Identified:
Canada, though a small market (Revenue: 0.05M), achieved the highest profit margin (27.59%), with Copiers contributing 38% of total profit—highlighting a highly efficient product-market fit.

✔️ Expansion Opportunity Identified:
Recommend a targeted expansion into Canada, focusing on high-margin products like Copiers, while avoiding scale-up of low-margin categories such as Office Supplies.  

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: Kaggle  
- Size:
  - The Orders table contains 51,290 records
  - The People table contains 13 records
  - The Returns table contains 1,172 records  
- Format: .csv  

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
The dataset consists of three tables:  
- Orders – Contains detailed transaction and customer information
<details>
<summary><strong>📊 Table 1: Orders</strong></summary>

| Column Name     | Data Type | Description                                         |
|-----------------|-----------|-----------------------------------------------------|
| Order ID        | VARCHAR   | Unique identifier for each order.                  |
| Order Date      | DATE      | Date when the order was placed.                   |
| Ship Date       | DATE      | Date when the order was shipped.                  |
| Ship Mode       | VARCHAR   | Shipping method used for delivery.                |
| Customer ID     | VARCHAR   | Unique identifier for each customer.              |
| Customer Name   | VARCHAR   | Full name of the customer.                        |
| Segment         | VARCHAR   | Customer segment (e.g., Consumer, Corporate).     |
| City            | VARCHAR   | City where the order was placed.                  |
| State           | VARCHAR   | State where the order was placed.                 |
| Country         | VARCHAR   | Country where the order was placed.               |
| Postal Code     | VARCHAR   | Postal code of the shipping address.              |
| Market          | VARCHAR   | Market region (e.g., APAC, EMEA).                 |
| Region          | VARCHAR   | Geographical region of the order.                 |
| Product ID      | VARCHAR   | Unique identifier for each product.               |
| Category        | VARCHAR   | Product category (e.g., Furniture, Office Supplies). |
| Sub-Category    | VARCHAR   | Sub-category of the product.                      |
| Product Name    | VARCHAR   | Name of the product ordered.                      |
| Sales           | DECIMAL   | Revenue generated from the order.                 |
| Quantity        | INT       | Number of items ordered.                          |
| Profit          | DECIMAL   | Profit earned from the order.                     |

</details>
- Returns – Stores data on returned orders.  
<details>
<summary><strong>📦 Table 2: Returns</strong></summary>

| Column Name | Data Type | Description                                           |
|-------------|-----------|-------------------------------------------------------|
| Returned    | VARCHAR   | Indicates whether the order was returned (e.g., 'Yes' or 'No'). |
| Order ID    | VARCHAR   | Unique identifier for each order.                    |

</details>

- People – Holds information about sales representatives.
<details>
<summary><strong>🧑‍💼 Table 3: People</strong></summary>

| Column Name | Data Type | Description                                           |
|-------------|-----------|-------------------------------------------------------|
| Person      | VARCHAR   | Name of the salesperson.                             |
| Region      | VARCHAR   | Geographic region where the salesperson operates.    |

</details>

#### 2️⃣ Data Relationships:  

![image](https://github.com/user-attachments/assets/e16fece0-207e-48c9-81f4-ce7f92fc9958)


## 🧠 Design Thinking Process  

Explain the step-by-step approach taken to solve the problem.  

👉🏻 Insert a screenshot of the Design Thinking steps (Screenshot your Excel design thinking tables for better presentation).  

1️⃣ Empathize  

![image](https://github.com/user-attachments/assets/f39364a6-ff80-4983-b91c-39a670497b71)

![image](https://github.com/user-attachments/assets/8003b524-207e-41ee-b958-cc31c17ef806)
  
2️⃣ Define point of view  

![image](https://github.com/user-attachments/assets/5658d28f-af43-4772-8017-5255f01d774d)

3️⃣ Ideate  

![image](https://github.com/user-attachments/assets/cf222246-e7ae-4d5c-bbf9-9d3a418b5225)

4️⃣ Prototype and review  

This part is in the dashboard

---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Overview 

![image](https://github.com/user-attachments/assets/ad0862a1-f30d-459d-8344-fa3a65757af8)  

From 2011 to 2014, the company maintained a strong growth trajectory in both revenue and profit. In 2014 alone, revenue grew significantly (+24% vs. 2013). However, profit margin showed a slight decline across all three key markets (APAC, EU, and US), indicating some underlying issues with profitability efficiency.  

![1](https://github.com/user-attachments/assets/be44600c-98c9-47d7-9c5d-aa8d50263cfc)


📌 Analysis:  

 📈 Revenue increased, but profit didn't keep up
Profit margin peaked in 2013 (11.97%), not in 2014 when revenue was highest. This suggests that as revenue grew, costs also rose—implying the company may be trading margin for scale.

🚚 Increase in high-cost shipping methods
In 2014, there was a notable rise in orders using expensive shipping methods such as First Class and Same Day. This shift significantly raised logistics costs, which outpaced gross profit growth and eroded overall profitability.

🛍️ Higher share of low-margin product categories
In particular, Office Supplies—a category with relatively low profit margins—experienced a surge in order volume. This shifted the product mix toward less profitable items, reducing the company's overall margin efficiency.  

![2](https://github.com/user-attachments/assets/826e0533-f500-446f-8e68-1987362e13d3)

🔁 Slight increase in return rate in APAC and US
Compared to 2013, the return rate rose in key markets like APAC (4.99% → 5.04%) and US (5.90% → 6.12%) in 2014. While the change is small, when combined with expensive shipping and a weak product mix, it added to costs and reduced net revenue.  

![3](https://github.com/user-attachments/assets/9509d04d-c6b4-4c28-bca9-6d7f80448e78)

⚠️ Three factors combined to reduce profit margin
The margin drop in 2014 was not caused by a single issue, but by a combination of:

(1) increased use of high-cost shipping,
(2) a rise in low-margin product share,
(3) higher return rates.
→ These factors together exerted cost pressure and squeezed profitability.

🌍 EU – High revenue but also the highest return rate (6.18%)
Although EU is one of the top contributors in both revenue and profit, it also has the highest return rate among all regions. This signals potential issues with product quality, after-sales service, or customer experience—and could hurt long-term margins if not addressed.

🪑 Furniture – Underperforming product category
Among the three main categories (Technology, Office Supplies, Furniture), Furniture generated the lowest profit. It may exist for catalog diversity, but in reality, it's dragging down the company's overall performance.  

💡 Recommendation:  

- Review shipping policies, especially for orders using First Class and Same Day. Consider applying minimum order thresholds or extra fees to manage logistics costs.

- Restructure the product mix to reduce dependency on low-margin items (like Office Supplies) and promote cross-selling with higher-performing products.

- Investigate product quality and customer experience in the EU region, where the return rate is highest. Prioritize after-sales improvements or redesign return policies to limit loss.

- Reassess or scale down the Furniture category if it continues to underperform in upcoming periods.

- Track profit per order more closely, not just overall revenue or profit, to quickly detect operational inefficiencies.

#### 2️⃣ Dashboard 2 Preview  

![image](https://github.com/user-attachments/assets/57c30008-b5d0-49ba-ae73-cf41a7478857)

📌 Analysis:   

🇨🇦 Canada – Small market with exceptionally high margin
Despite contributing only $0.05M in revenue and $0.01M in profit, Canada recorded the highest profit margin (27.59%) in the entire dataset.
⚠️ However, due to the small sample size, just a few large transactions could create an inflated margin.
→ Further validation at the SKU/product level is needed to confirm its potential.

🌍 Africa – A small but surprisingly efficient market
With $0.59M in revenue and $0.07M in profit, Africa reached a profit margin of 11.48%, aligning with the company average.
→ This suggests potential for niche market expansion with controlled cost and focused targeting.  

🖨️ Copiers – Key profit driver in Canada
Copiers contributed 38% of total profit in Canada, making it a standout product for scaling efforts in this market.

📱 Phones – High revenue, modest efficiency
While it generated the highest revenue ($1.37M) across all SKUs, its profit margin is only 13.07%.
→ A reassessment is needed to investigate operational or pricing inefficiencies.

📄 Paper & Labels – Low-volume, high-margin SKUs
Although small in revenue, these SKUs deliver 25%+ profit margins, suggesting strong potential if scaled carefully.

💡 Recommendation:  

- Scale up operations in Canada, focusing on high-margin categories such as Copiers, Office Supplies, and Technology.
→ A lean, margin-driven strategy could prove highly effective here.

- Explore niche expansion in Africa with selective investment in high-margin SKUs. Prioritize low-risk, cost-effective channels to test the waters.

- Re-evaluate the overall SKU mix to reduce dependency on high-revenue but low-margin products like Phones, and shift toward smaller, high-efficiency items such as Paper and Labels.


---


