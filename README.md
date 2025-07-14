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

Based on the data presented in the dashboard, the procurement activities for raw materials, goods, and semi-finished products during the reviewed period can be assessed as follows:

- Order fulfillment and product quality are at optimal levels: Both the Fulfillment Rate and Defect Rate are at 100% and 0% respectively, indicating a highly efficient procurement and inbound logistics process.

- Significant supply disruption from August onwards: Received quantity and procurement value dropped sharply in August and completely halted by September. This signals potential disruption in the supply chain, possibly due to order delays, halted production schedules, budget constraints, or bottlenecks in internal approval processes.

- Overstocking across multiple items: Numerous products show excessive inventory levels far exceeding their Reorder Points and Safety Stock thresholds, posing risks of inventory obsolescence, increased storage costs, and inefficient capital utilization.

- Poor performance in certain products: Lock Washer 4, 5 and Lock Nut 5, 6 exhibit high defect/return rates (above 9%), while Sport-100 Helmet shows an extremely low fulfillment rate (6.67%). This could directly impact production continuity if these are critical components.

💡 Recommendation:  

Based on the findings above, the following actions are recommended:

- Investigate supply chain disruption from August onwards: Review open purchase orders, procurement schedules, and supplier delivery status. Verify that there are no internal bottlenecks in the approval or payment process.

- Re-evaluate inventory policies: Adjust Safety Stock and Reorder Points, especially for overstocked items. Prioritize consumption of existing stock and implement stock alerts within Power BI to prevent over-ordering.

- Reassess suppliers with poor performance: Perform a vendor performance review focused on suppliers linked to high defect rates and low fulfillment. Consider negotiating revised SLAs or sourcing alternative vendors if required.

- Implement continuous monitoring systems: Develop a real-time dashboard to track key metrics such as inventory levels, open POs, delivery timelines, and defect rates. Set up automated alerts for early detection of abnormal trends.
  
#### 2️⃣ Vendor  

<img width="1315" height="727" alt="image" src="https://github.com/user-attachments/assets/37116bd9-2c69-4d25-97d0-654a25834eea" />

📌 Analysis:   

1. Overall Procurement Performance
- The dashboard indicates that the overall procurement performance is currently strong. The Order Fulfillment Rate and Fulfillment by Quantity have both reached 100% in the most recent month, suggesting that all orders were delivered in full and on time by the vendors.

- The Defect or Return Rate stands at 0.00%, which means there were no returned or defective items this month. While this is a positive sign, it is important to remember that in previous months, defective or returned items still existed and must not be overlooked in long-term evaluations.

- The Average Purchase Price is currently $3.40, showing no month-over-month change and indicating price stability in procurement.

2. Vendor Performance
- Looking at individual vendors, many show relatively high defect or return rates, ranging from approximately 4.4% to 4.9%. The vendors with the highest defect rates include Anderson’s Custom Bikes, Bicycle Specialists, and SUPERSALES INC. This level of defect rate is considered high, especially for components or raw materials used in production.

- Additionally, the Order Fulfillment Rates for these vendors are also low, mostly ranging between 75% and 77%. This suggests that not only is product quality inconsistent, but these vendors are also not reliably meeting delivery commitments.

- Some vendors also have significantly higher prices compared to others—such as Crowley Sport and Greenwood Athletic Company—yet they still report relatively high defect rates. This raises questions about the cost-effectiveness of continuing partnerships with those suppliers.

3. Performance Trends Over Time
- Monthly trend data shows that Fulfillment by Quantity has steadily improved over the year, increasing from around 98.9% in January to 100% in September. This is a positive trend indicating enhanced delivery performance.

- However, the Average Lead Time presents a serious concern. While it remained stable at around 9 days for the first eight months of the year, there was a sharp and sudden spike to 25 days in September. This is nearly three times longer than the normal lead time and suggests a major disruption, potentially in logistics, vendor capacity, or supply chain processes.

- Although this delay has not yet affected order fulfillment rates, it poses a serious risk if the trend continues, particularly for just-in-time or time-sensitive production operations.  

💡 Recommendation:  

1. Reevaluate Vendor Performance
Vendors with high defect rates and low fulfillment performance should be thoroughly reviewed—especially those with defect rates above 4.5% and fulfillment rates below 77%. These metrics indicate underlying issues in quality control or capacity management. If no improvement is seen after discussions and corrective actions, alternative vendors with better reliability and quality assurance should be considered.

2. Strengthen Quality Control Measures
Despite a 0% defect rate this month, historical data shows consistent quality issues across several vendors. It is recommended to enhance inbound quality inspections, particularly for suppliers with a history of defective deliveries. This will help catch problems before they affect production.

3. Address the Spike in Lead Time
The sudden increase in average lead time to 25 days in September is alarming and should be investigated immediately. The cause could be due to transportation issues, raw material shortages, vendor-side delays, or internal purchasing process changes. Affected vendors should be contacted to identify root causes and take corrective actions. If not resolved, this could disrupt production schedules in the near term.

4. Optimize Purchasing Costs
Some vendors are charging high prices without delivering corresponding value or quality. Procurement teams should reevaluate the cost-to-benefit ratio and renegotiate pricing where applicable. If vendors are unable to meet cost-efficiency benchmarks, switching to more competitive suppliers should be considered.

---


