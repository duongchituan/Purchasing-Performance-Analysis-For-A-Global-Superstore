# 📊 Purchasing Performance Analysis For A Global Superstore (PowerBI)

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
 
This project aims to develop an Operations Dashboard in Power BI to support executive leadership in monitoring and optimizing procurement activities. As supply chain efficiency, accuracy, and cost control become increasingly critical, visualizing procurement data is essential to:

- Ensure goods are ordered at the right time, in the right quantities, and at optimal cost

- Track supplier performance and proactively identify risks such as delays or shortages

- Evaluate the procurement team's ability to meet sales demand across time and product categories

- Empower leadership to make timely, data-driven operational decisions

By delivering this dashboard, the organization will gain a modern, visual management tool that enhances supply chain efficiency and ensures sustainable business growth through informed decision-making.  

### 👤 Who is this project for?  

✔️ Purchasing Manager  

✔️ Board of Directors (BOD)  

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: Kaggle - Dataset of AdventureWorks    
- Format: .Pbix  

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
The dataset consists of 7 main tables used to build the purchasing dashboard:  
<details>
<summary><strong>Table 1: Purchasing_OrderDetail - Line-level order details</strong></summary>

| Column Name             | Description                                  |
|-------------------------|----------------------------------------------|
| `OrderQty`              | Quantity ordered                             |
| `ReceivedQty`           | Quantity received                            |
| `RejectedQty`           | Quantity rejected                            |
| `StockedQty`            | Quantity stocked                             |
| `LeadTime_Days`         | Lead time in days                            |
| `DelayDays`             | Number of delay days                         |
| `DueDate`, `OnTime`     | Delivery due date and on-time flag           |
| `IsBackorderedFlag`     | Indicates if the item was backordered        |
| `UnitPrice`             | Unit price of the item                       |
| `PurchaseOrderDetailID` | Line item identifier                         |
| `PurchaseOrderID`, `ProductID` | Foreign keys to orders and products     |

</details>
<details>
<summary><strong>Table 2: Product_Inventory – Current inventory levels</strong></summary>

| Column Name           | Description                                |
|------------------------|--------------------------------------------|
| `Quantity`             | Current inventory quantity                 |
| `Below Reorder Flag`   | Indicates if inventory is below reorder level |
| `BelowSafetyStock`     | Indicates stock is below safety threshold  |
| `OutOfStockProducts`   | Out of stock status                        |
| `ProductID`            | Foreign key to product                     |


</details>

<details>
<summary><strong>Table 3: Product_Product – Product master data</strong></summary>

| Column Name           | Description                                |
|------------------------|--------------------------------------------|
| `ProductID`            | Unique product identifier                  |
| `Name`, `Class`, `Style` | Product characteristics                   |
| `SafetyStockLevel`     | Safety stock value                         |
| `ReorderPoint`         | Reorder threshold                          |
| `ListPrice`, `StandardCost` | Price and cost info                  |
| `ProductSubcategoryID` | Product is a member of this product subcategory.            |
</details>  

<details>
<summary><strong>Table 4: Purchasing_OrderHeader – Order-level metadata</strong></summary>

| Column Name         | Description                                 |
|----------------------|---------------------------------------------|
| `PurchaseOrderID`    | Header-level order ID                       |
| `OrderDate`, `ShipDate` | Order creation and shipping date         |
| `VendorID`           | Foreign key to vendor                       |
| `TotalDue`, `Freight`, `SubTotal` | Order-level cost details      |
</details>  

<details>
<summary><strong>Table 5: Purchasing_Vendor – Companies from whom Adventure Works Cycles purchases parts or other goods</strong></summary>

| Column Name             | Description                            |
|--------------------------|----------------------------------------|
| `VendorID`               | Unique vendor ID                       |
| `Name`, `AccountNumber`  | Vendor info                            |
| `PreferredVendorLabel`   | Whether vendor is preferred            |
| `CreditRating`           | Vendor's credit rating                 |
</details>  

<details>
<summary><strong>Table 6: Purchasing_ProductVendor – Product_vendor mapping</strong></summary>

| Column Name           | Description                              |
|------------------------|------------------------------------------|
| `ProductID`            | Linked product                           |
| `VendorID`             | Linked vendor                            |
| `MinOrderQty`, `MaxOrderQty` | Order quantity boundaries        |
| `StandardPrice`        | Standard unit cost                       |
| `AverageLeadTime`      | Vendor delivery time in days             |
</details>  

<details>
<summary><strong>Table 7: Product_ProductTable – Product_vendor mapping</strong></summary>

| Column Name             | Description                         |
|--------------------------|-------------------------------------|
| `ProductID`              | Linked product                      |
| `ProductCategoryID`      | Category reference                  |
| `ProductSubcategoryID`   | Subcategory reference               |
| `Category`               | Product category name               |
| `Subcategory`            | Product subcategory name            |
</details>  

#### 2️⃣ Data Relationships:  

<img width="1140" height="763" alt="image" src="https://github.com/user-attachments/assets/0ee4b01b-45e6-4ab3-b2a9-b9cc73931b02" />

## 🧠 Design Thinking Process  

Explain the step-by-step approach taken to solve the problem.  

1️⃣ Empathize  

<img width="1322" height="742" alt="image" src="https://github.com/user-attachments/assets/e5592b4c-e405-48e7-b49d-2a26e6f1860b" />

<img width="1038" height="782" alt="image" src="https://github.com/user-attachments/assets/8ece6c98-33dc-428c-a356-ccd7728e35bb" />

2️⃣ Define point of view  

<img width="899" height="739" alt="image" src="https://github.com/user-attachments/assets/0ee48465-1574-4abf-ab3b-bb056f1a4547" />

3️⃣ Ideate  

<img width="902" height="434" alt="image" src="https://github.com/user-attachments/assets/62349837-b35f-4fe7-84ac-ea94c5e2b67e" />

<img width="919" height="343" alt="image" src="https://github.com/user-attachments/assets/39a807ec-83ff-4da7-a70e-6b916f5ead03" />

---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Product 

<img width="1315" height="727" alt="image" src="https://github.com/user-attachments/assets/b9be3f5b-02a3-4e0b-8488-10e79aa04350" />

📌 Analysis:  

1️⃣ Overall performance:  

- Revenue reached **$3.21M** (+24.41% compared to 2013), and profit was **$369.74K** (+19.56%), showing strong revenue growth but slower profit growth.

- ROI decreased to **13%** (↓4.41%), reflecting rising costs or shrinking profit margins.

- The **return rate** decreased to **13.74%** (**↓21.22% vs. 2013**), suggesting **improvements in product quality** or **customer experience**, helping to **reduce logistics costs** and **improve profitability**.

2️⃣ Time trend:  

- Revenue increased consistently from 2011 to 2014.
  
- Profit margin remained around **10–12%**, indicating revenue growth did not translate into higher profitability.

3️⃣ Regional performance:  

- **Central**: largest revenue (**$2.07M**) and highest profit (**$212K**), lowest return rate (**22.38%**), ROI **11.45%**.
  
- **South**: second-highest revenue (**$1.18M**), solid profit (**$99.5K**), good return rate (**36%**), ROI **9.24%**.
  
- **North**: high profit and ROI (**$148K**, **18.83%**), acceptable return rate (**49.81%**).
  
- **North Asia**: highest ROI (**24%**) and strong profit (**$122K**), but very high return rate (**101.91%**), indicating major risks.
  
- Other regions (West, Oceania, EMEA, Africa, Southeast Asia, East) show high return rates (**50–84%**) and average or low ROI → not efficient for expansion at this stage.
  
- **Caribbean, Central Asia, Canada**: extremely high return rates (**114–583%**) with low revenue → not suitable for expansion.

💡 Recommendation:  

🔵 **Prioritize expansion in:**
- **Central**: most stable market, largest scale, lowest return risk → continue investing, focus on improving ROI through cost optimization.
  
- **South**: large market size, moderate return rate, low ROI but potential for increased efficiency with better cost control.
  
- **North**: high profit and ROI, acceptable return rate → suitable for simultaneous expansion with Central and South.

🟡 **Consider conditional expansion in:**
- **North Asia**: expand only after addressing causes of extremely high return rates, as ROI and profit margins are promising.

🔴 **Do not expand now in:**
- West, Oceania, EMEA, Africa, Southeast Asia, East: high return rates and insufficient ROI.
  
- Caribbean, Central Asia, Canada: extremely high return rates and low revenue; investigate causes before any expansion.

#### 2️⃣ Product  

![Uploading image.png…]()

📌 Analysis:   

- Top revenue-generating products include Phones ($1.38M), Copiers ($1.25M), and Chairs/Bookcases (each $1.20M). In terms of profitability, Copiers lead with $0.22M, followed by Phones ($0.18M) and Bookcases ($0.13M). These products not only deliver high revenue but also maintain solid profit margins, indicating strong potential for long-term sustainability and further expansion.  

- However, several product lines are experiencing unusually high return rates, such as Tables (174.15%), Fasteners (152.01%), and Labels (135.18%). These figures point to serious risks related to product quality or after-sales service processes. In contrast, Phones (44.24%), Chairs (52.36%), and Bookcases (60.54%) show relatively low return rates, suggesting these are more stable and reliable products, less likely to incur extra return or customer service costs.  

- Products positioned in the "high revenue – high profit" quadrant — such as Copiers, Phones, Bookcases, and Chairs — are strategic lines that should continue to be prioritized and strengthened. On the other hand, product lines like Fasteners, Supplies, Furnishings, and Labels, which fall into the "low revenue – low profit" zone, should be carefully reviewed for optimization or even removal if necessary.  

- Although smartphones top the revenue chart, they suffer from an extremely high return rate (over 2000%), significantly impacting their actual profitability. Meanwhile, underperforming items such as Avery Binder Labels, Push Pins, and Eureka Bags are experiencing severe losses with return rates as high as 117,200%, indicating no remaining business value and should be considered for elimination.  

💡 Recommendation:  

1. Prioritize Strategic Product Lines
Focus on investing in and expanding high-performing products such as 🖨️ **Copiers**, 📱 **Phones**, 📚 **Bookcases**, and 🪑 **Chairs**.. These products significantly contribute to both **revenue** and **profit** while maintaining relatively **low and stable return rates**.

2. Improve Product Quality and After-Sales Processes
For products with ⚠️ **high return rates** such as **Tables**, **Fasteners**, and **Labels**, it's crucial to re-evaluate **product quality**, **packaging**, **product descriptions**, and **return policies** to reduce financial risks caused by excessive returns.

3. Optimize Product Portfolio
Products that fall into the 💸 **“low revenue – low profit”** zone, such as **Fasteners**, **Supplies**, and **Furnishings**, should be gradually phased out or repositioned in the market. This helps the company focus its resources on more profitable lines.

4. Warning on Phone Category
Although the 📱 **Phone category** generates the highest revenue, its extremely high return rate is significantly eroding actual profit. Stricter quality control, sourcing from more reputable suppliers, or improving after-sales service are necessary steps to prevent avoidable financial losses.


---


