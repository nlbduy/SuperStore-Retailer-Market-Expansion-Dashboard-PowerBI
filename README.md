# **SuperStore Retailer Market and Product Strategy Dashboard with Power BI**

<img width="2000" height="833" alt="Image" src="https://github.com/user-attachments/assets/13aaaf46-70db-4052-8c09-87f7883e5ec5" />

Author: Nguyen Luu Bao Duy

Tool Used: Power BI

# **📑 Table of Contents**

- [**📌 Project Overview**](#-----project-overview--)

- [**📂 Dataset**](#-----dataset--)

- [**🧠 Design Thinking Process**](#-----design-thinking-process--)
  
- [**📊 Key Insights & Visualizations**](#-----key-insights---visualizations--)

- [**🚀 Final Conclusions and Recommendations**](#-----final-conclusions-and-recommendations--)


# **📌 Project Overview**

## **🎯 Project Objectives**

This project uses the well-known ***Global SuperStore*** dataset to build a Power BI dashboard for the Executive Board to make data-informed strategic decisions of **market expansion**. Our main goals are:

- Gain a holistic **overview** of the company's business market over the years.
- Observe the **growth trends** of key performance indicators (KPIs).
- Understand the **profit mechanism** to formulate strategies for market improvement and expansion.

## **👥 Target audience**

- Sales & Marketing Team
- Product Team
- Analytics and Data Team
- Business Strategy & Management Team

# **📂 Dataset**

## **📝 Data Description**

- Context: Global SuperStore is **a fictional online retailer** that sells office supplies, furniture, and technology products globally.
- The dataset includes 3 tables: Orders, Returns, and People
- Size:
    - Orders: 51290 records
    - Returns: 1172 records
    - People: 13 records
- Format: CSV

## **⚙️ Data Structure & Relationships**

**1️⃣ Tables Used**

- **Orders (Fact Table) -** Contains information about detailed transactions
- **Returns (Fact Table)** – Contains information about returned orders.
- **People (Dim Table)** – Contains information about sales representatives.

**2️⃣ Table Schemas**

<details>
<summary><b>Orders Table</b></summary>

| Field Name | Type | Description |
| :--- | :--- | :--- |
| **Order ID** | `String` | A unique identifier for each order. |
| **Order Date** | `Date` | The date the order was placed. |
| **Ship Date** | `Date` | The date the order was shipped. |
| **Ship Mode** | `String` | The shipping method used. |
| **Customer ID** | `String` | A unique identifier for each customer. |
| **Customer Name** | `String` | The name of the customer. |
| **Segment** | `String` | The customer's market segment. |
| **City** | `String` | The customer's city. |
| **State** | `String` | The customer's state/province. |
| **Country** | `String` | The customer's country. |
| **Postal Code** | `String` | The customer's postal code. |
| **Market** | `String` | The geographical market. |
| **Region** | `String` | The geographical region. |
| **Product ID** | `String` | A unique identifier for each product. |
| **Category** | `String` | The main product category. |
| **Sub-Category** | `String` | The product's sub-category. |
| **Product Name** | `String` | The name of the product. |
| **Sales** | `Float` | The sales value of the transaction. |
| **Quantity** | `Integer` | The quantity of products sold. |
| **Profit** | `Float` | The profit from the transaction. |

</details>

<details>
<summary><b>Returns Table</b></summary>

| Field Name | Type | Description |
| :--- | :--- | :--- |
| **Returned** | `String` | A flag indicating if the order was returned. The value is typically 'Yes'. |
| **Order ID** | `String` | The unique identifier of the returned order. This field can be used to join with the `Orders` table. |
| **Region** | `String` | The geographical region where the return occurred. |

</details>

<details>
<summary><b>People Table</b></summary>

| Field Name | Type | Description |
| :--- | :--- | :--- |
| **Person** | `String` | The name of the sales person. |
| **Region** | `String` | The geographical region this person is responsible for. This field can be used to join with the `Orders` table to analyze sales by person. |

</details>

**3️⃣ Data Relationships**

<img width="2000" height="1412" alt="Image" src="https://github.com/user-attachments/assets/e8766583-5a94-4845-9521-4ffafd102acd" />

**Relationships between tables**
| From Table | Relationship | To Table | Join Keys |
| :--- | :--- | :--- | :--- |
| `Orders` | One-to-One | `Returns` | `Orders.Order ID` = `Returns.Order ID` |
| `Orders` | Many-to-One | `People` | `Orders.Region` = `People.Region` |


## **🗓️** Time Frame

- The dataset includes records spanning from 2011 to 2014.
- The analysis is conducted for the same period.

# **🧠 Design Thinking Process**

This analysis uses a process called “Design Thinking” to generate ideas and solve problems.

## **What is Design Thinking and Why it matters for BI projects?**

Design Thinking is a **human-centered, iterative approach to problem-solving** that emphasizes understanding users, redefining problems, and creating innovative solutions through rapid prototyping and testing.

It is built on 5 stages:

1. **Empathize** – deeply understand the needs, pain points, and goals of users.
2. **Define** – clearly articulate the problem statement.
3. **Ideate** – generate a wide range of creative solutions.
4. **Prototype** – build quick, tangible versions of the solution.
5. **Test** – validate with users, gather feedback, and refine.

Unlike linear methods, Design Thinking is flexible and iterative, allowing teams to circle back when new insights emerge. It balances **desirability (user needs)**, **feasibility (technical capabilities)**, and **viability (business goals)**.

Business Intelligence (BI) initiatives often struggle when they focus too much on **tools, data models, and dashboards** while overlooking **actual user needs**. Design Thinking ensures BI solutions are not just technically correct but **practically impactful**.

Key reasons:

- **User-centric dashboards & reports**: BI outputs directly address decision-makers’ real challenges rather than overwhelming them with unused metrics.
- **Alignment with business goals**: Encourages defining the “why” behind every visualization or KPI, preventing data for data’s sake.
- **Collaboration across roles**: Breaks silos between business users, analysts, and IT by co-creating solutions.
- **Faster iteration**: Prototyping dashboards early helps validate insights before heavy data engineering investment.
- **Higher adoption**: When end-users are involved from the start, BI solutions are more intuitive, actionable, and widely adopted.

👉 In short, Design Thinking makes BI projects move from **“just reporting”** to **“strategic decision support”** by combining data with empathy, creativity, and business context.

## 1️⃣ Stage 1: Empathize

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/76bc3740-c881-48b9-a17d-fa2acc550b82" />

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/9fae003e-dc75-466e-a573-47f3ca258d75" />

## 2️⃣ Stage 2: Define Point Of View

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/995abc1c-e468-46f9-84e4-3fa9fa312469" />

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/fe4b4baa-96ea-4cb5-81da-1504f266a627" />

## 3️⃣ Stage 3: Ideate

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/93884e9d-f105-4a4c-b20c-b229e9d56c1c" />

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/ae5abd19-beae-42a2-b5b7-41754b3827f7" />

## 4️⃣ Prototype and review

This part is in the dashboard

# **📊 Key Insights & Visualizations**

## **🔍 Dashboard Preview**

**1️⃣ Business Overview**

<img width="2000" height="1142" alt="Image" src="https://github.com/user-attachments/assets/a3472560-5349-402a-afd8-0ed7ea4f443a" />

**📌 Key Findings**

- **Revenue and Profit Trajectory**: Revenue and profit have shown consistent growth over the years, reaching their peak in 2014 at **$4.3M in sales and $0.5M in profit**. However, profitability efficiency slightly declined, with profit margin dropping by **0.22 percentage points** between 2013 and 2014.
- **Market-Level Performance**:
    - **APAC and EU** are the strongest markets, contributing the highest profits (**$486K and $373K**, respectively).
    - **US and LATAM** deliver moderate profit contributions with average margins.
    - **Africa and EMEA** show weak performance with very low profitability.
    - Notably, **Canada** generates the lowest profit (~$18K) but records an exceptionally high profit margin (**26.62%**), indicating a niche high-margin segment possibility.
- **Country-Level Contribution**:
    - **Top-performing countries**: United States (**$286K**), China (**$150K**), and India (**$129K**).
    - **Second-tier contributors**: Several European countries (France, Germany, Austria, Belgium, Switzerland) and Australia, each contributing **$103K–112K**.
    - **Low contributors**: Most remaining countries generate less than **$55K** profit.
    - **Underperforming countries**: Some markets even record **negative profits**, highlighting inefficiencies or unfavorable business conditions.
    - Based on two key dimensions - **growth momentum** and **business profitability** - the countries are categorized into **5 distinct performance groups**:
      
      1. **Profit Growing**: Countries with a positive profit margin and positive YoY growth. This group represents **strong and sustainable performers** - they are both profitable and expanding, signaling solid market positions and effective business operations.
  
      2. **Profit Declining**: Countries with a positive profit margin but negative YoY growth. These markets **remain profitable**, but **their growth momentum is slowing down**. They are at risk of eroding profitability if the declining trend continues.
  
      3. **Loss Narrowing**: Countries with a negative profit margin but positive YoY growth. These are **recovering markets**. Despite current losses, they show early signs of improvement and have the potential to return to profitability if the positive trend persists.
  
      4. **Loss Widening**: Countries with a negative profit margin and negative YoY growth. These represent **high-risk markets**, where operations are both unprofitable and worsening. They may require restructuring, scaling down, or even exit decisions if no turnaround plan is viable.
  
      5. **New - Reactivated**: Countries with **newly established operations** or with **inconsistent profit history**. These markets are emerging or unstable, requiring close monitoring. While they may present growth opportunities, the lack of consistent profitability makes them riskier to rely on in the short term.

- **Product Category Performance**: **Technology** is the primary profit driver (**$664K**), while **Furniture** delivers the lowest profit contribution. **Office Supplies** remains in the middle, offering room for selective growth opportunities.
- **Return Rate Trends**:
    - **APAC and LATAM** show an improving trend with declining return rates over time.
    - Conversely, **EU and US** face rising return rates, signaling potential risks to profitability and operational efficiency if not addressed.

**2️⃣ Trend Analysis**

<img width="2000" height="1142" alt="Image" src="https://github.com/user-attachments/assets/820cf724-e474-4052-b326-7f0684aea084" />

**📌 Key Findings**

- **Revenue & Sales Growth**
    - Total sales doubled within four years, increasing steadily from **$2.26M in 2011 to $4.30M in 2014**.
    - This demonstrates strong scalability and consistent market expansion.
- **Profit Growth**
    - Net profit grew in parallel, from **$249K in 2011 to $504K in 2014**.
    - The fact that profit scaled with revenue indicates that growth is backed by real profitability, not solely by volume expansion.
- **Profitability Efficiency (Profit Margin)**
    - Profit margin improved from **11.02% in 2011 to a peak of 11.95% in 2013**, before slightly declining to **11.73% in 2014**.
    - This suggests rising operational or product-related costs that began to erode efficiency, even as profit continued to grow.
- **Return Rate**
    - Return rate initially increased from **4.71% in 2011 to 4.83% in 2012**, but then improved steadily to **4.55% in 2014**.
    - This positive trend indicates better control over product quality, fulfillment, or customer satisfaction.
- **Unprofitable Orders (Loss Order Rate)**
    - Roughly **30% of all orders have been consistently unprofitable** over the 4-year period, fluctuating only slightly between 29–31%.
    - This represents an **issue in pricing, discounting, or product portfolio strategy**, rather than a temporary fluctuation.
    - Without intervention, such a high share of unprofitable orders risks undermining overall business scalability.
- A clear **seasonal pattern** emerges, with **sales**, **orders**, and **profit** consistently peaking in **Q4** each year. This surge is typically followed by a decline or slight correction in Q1 of the following year. Such dynamics strongly suggest a **holiday-driven** or **year-end sales** effect.

**3️⃣ Profit Analysis**

<img width="2000" height="1142" alt="Image" src="https://github.com/user-attachments/assets/ea64440d-7ccd-4ed8-8c73-c74d65bf04c6" />

**📌 Key Findings**

- **Profit Drivers vs. Volume**
  - High sales volume does not always translate into profitability. Product performance can be grouped into **4 clusters**:
    - **Stars** - High growth, high margin. True **growth drivers** that deliver both revenue and efficiency, deserving top priority.
    - **Profit Protectors** - Low growth, stable margins. **Reliable contributors** that should be maintained for stability.
    - **Volume Traps** - High growth but low/negative margin. Increased sales amplify losses as costs outweigh revenue; require s**trict cost control** or **pricing adjustments**.
    - **Underperformers** - Low growth, low/negative margin. Candidates for **rationalization** or **elimination**.
  - Strategic focus should balance growth and efficiency, ensuring resources are allocated to products that generate both revenue and sustainable profitability.
- **Market Profitability vs. Risk Exposure**
    - **APAC and EU** are the largest profit contributors.
    - However, **APAC carries the highest unprofitable-order rate (≈37%)**, suggesting that while it is profitable, **growth comes with the elevated risk of loss-making orders**.
- **High and Persistent Unprofitable-Order Rates**
    - Market-level unprofitable-order rates remain structurally high: **Africa 21.4% | US 26.3% | EU 30.2% | EMEA 30.4% | LATAM 31.4% | APAC 37.0%**.
    - This means that in several key markets, **1 in 3 orders results in a loss**, highlighting a **systemic issue in pricing, discounting, or product mix**, not just year-to-year variance.
- **Profit Margin Spread Across Geographies**
    - Smaller markets like **Canada deliver exceptionally high profit margins despite limited sales volume**, positioning them as **niche, high-margin opportunities**.
    - In contrast, large-volume markets (e.g., **LATAM, EMEA**) generate lower margins, raising questions about sustainability and operational efficiency.
- **Year-over-Year Profit Growth vs. Margin Stability**
    - While total profit has consistently grown, **profit margins have fluctuated**.
    - This indicates that the business is scaling, but **the quality of growth is uneven** - profitability is being partially offset by **unprofitable orders, high returns, or suboptimal pricing strategies**.

# **🚀 Final Conclusions and Recommendations**

### **🌍 Market Expansion Opportunities**

### **🏯 APAC Market**

- **Potential Countries**: China, India, Australia
- **Strategic Product Focus**: Technology (Copiers, Phones)
- **Key Insights**:
    - Strong and consistent growth in both revenue and profit, with stable margins.
    - Return Rate is generally under control but shows an upward trend in 2014, particularly in China.
    - Loss Order Rate remains high across the region (avg. ~21.3%), with Australia being a critical outlier (41.4%).
- **Strategic Recommendations**:
    - Expand Technology products, especially Copiers and Phones, leveraging high demand.
    - **Australia**: implement cost-control initiatives to address high Loss Order Rate.
    - **China**: focus on reducing Return Rate by improving product quality and customer communication.
    - **India**: leverage strong growth potential with targeted promotions in Technology, while closely monitoring cost structures.


### **🏰 EU Market**

- **Potential Countries**: United Kingdom, France, Germany
- **Strategic Product Focus**: Technology and Office Supplies
- **Key Insights**:
    - Stable revenue and profit growth, though profit margin has shown volatility across years.
    - Return Rate has increased in recent years, eroding profitability.
    - Loss Order Rate remains elevated (23.4%).
- **Strategic Recommendations**:
    - Focus on scaling **Technology (Phones, Copiers)** and **Office Supplies (Appliances, Storage, Art)**.
    - **UK & Germany**: prioritize Technology and Office Supplies as growth drivers.
    - **France**: emphasize Office Supplies to balance portfolio risk.
    - Strengthen cost management initiatives to stabilize margins and reduce Loss Order Rate.


### **🗽 US Market**

- **Potential Country**: United States
- **Strategic Product Focus**: Technology and Office Supplies
- **Key Insights**:
    - Revenue and profit show steady growth; however, profit margin has been gradually declining.
    - Return Rate is trending upwards, indicating quality or customer satisfaction concerns.
    - Loss Order Rate was under control previously, but has risen again since 2014.
- **Strategic Recommendations**:
    - Expand **Technology (Copiers, Phones, Accessories)** and **Office Supplies (Paper, Binders, Storage, Appliances)**.
    - Strengthen existing initiatives to reduce both Loss Order Rate and Return Rate.
    - Improve cost efficiency and enhance margin through pricing optimization and supply chain improvements.


### Market–Product Strategic Focus Matrix

| Market          | Technology                                                                 | Office Supplies                                           |
|-----------------|----------------------------------------------------------------------------|----------------------------------------------------------|
| **APAC**        | 🔥 High Growth Potential <br> 📌 Focus: Copiers, Phones <br> 🎯 Reduce Loss Order Rate (AU), Improve Returns (CN) | ⚠️ Secondary Focus <br> Keep under watch                 |
| **Europe (EU)** | 🔥 Growth Driver <br> 📌 Focus: Phones, Copiers <br> 🎯 Stabilize margins, cut Loss Order Rate | 🟢 Portfolio Stabilizer <br> 📌 Focus: Appliances, Storage, Art |
| **United States** | 🔥 Core Revenue Base <br> 📌 Focus: Copiers, Phones, Accessories <br> 🎯 Pricing & supply chain optimization | 🟢 Complementary Focus <br> 📌 Paper, Binders, Storage, Appliances |


- 🔥 = Growth/Expansion Priority
- 🟢 = Portfolio Stabilizer
- ⚠️ = Secondary or Watchlist


### **💡Cross-Market Strategic Priorities**

**💰 Profit Margin Optimization**

- Implement value-based pricing to align prices with perceived customer value.
- Reduce procurement costs through supplier negotiations and economies of scale.
- Optimize production and operational efficiency to lower cost per unit.
- Drive higher sales volume via targeted marketing and bundling strategies.

**🛑 Loss Order Rate Reduction**

- Diagnose root causes: logistics costs, procurement expenses, discounting policies, and inventory management.
- Optimize cost drivers across the supply chain.
- Consider discontinuing consistently unprofitable products unless they present strategic potential.

**🛡️ Return Rate Management**

- Improve product quality assurance and customer experience.
- Provide accurate, transparent product information to align customer expectations.
- Enhance after-sales support and streamline return handling to improve customer satisfaction while reducing costs.


### **🔮 Strategic Outlook**

By prioritizing **APAC (China, India, Australia), EU (UK, France, Germany), and the US** with a clear focus on **Technology and Office Supplies**, the company can pursue a **balanced growth strategy**.

- **Technology** will serve as the primary profit driver across all markets, leveraging high-margin categories such as Copiers and Phones.
- **Office Supplies** will act as a stabilizer, offering consistent demand and complementing Technology sales.
- A dual approach—**expansion into high-growth markets** while **resolving cost inefficiencies and structural profitability issues**—will ensure sustainable growth and improved shareholder value.
