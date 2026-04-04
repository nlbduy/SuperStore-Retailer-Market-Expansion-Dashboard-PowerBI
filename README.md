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

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/057b4fd7-d5c3-492f-92b5-784d3172c7e7" />

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/a6055719-fdb8-4763-9736-fe2da8b94a1e" />

## 2️⃣ Stage 2: Define Point Of View

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/422461ef-97b4-40b6-8c2b-dabb2aeaafa1" />

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/d86bfdf3-19c1-4a1a-a792-f30633f73769" />

## 3️⃣ Stage 3: Ideate

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/ca37076a-dc08-48b7-83c8-2c6f6a49045a" />

<img width="2000" height="1125" alt="Image" src="https://github.com/user-attachments/assets/958a035c-4f3a-47e8-8c08-97597da2bf85" />

## 4️⃣ Prototype and review

This part is in the dashboard

# **📊 Key Insights & Visualizations**

## **🔍 Dashboard Preview**

**1️⃣ Business Overview**

<img width="2000" height="1139" alt="Image" src="https://github.com/user-attachments/assets/7cede1cc-cabc-412d-a105-c1b79e97b2c7" />

To identify key **growth drivers** and **execution bottlenecks**, this page conducts a multi-dimensional analysis across four core pillars: Time, Market, Segment, and Category.

Concurrently, the **Market Health Classification** model is applied to categorize nations into four groups based on the correlation between **Current Profit** and **LY Profit Growth Rate**:
- **Profit Growing**: Ideal markets with positive profits and robust expansion momentum.
- **Profit Declining**: "Alert" markets; currently profitable but experiencing decelerating growth — a sign of saturation or intense competition.
- **Loss Narrowing**: Underperforming markets showing recovery; deficits are shrinking through optimization efforts.
- **Loss Widening**: High-risk markets with deepening losses and negative growth, requiring urgent intervention or restructuring.


**📌 Key Findings**
- **Overall Growth and Performance**: The business maintains impressive revenue momentum (+24.4% YoY), reaching the $11.82M threshold. However, net profit margins show a slight decline (-4.83%), indicating that aggressive expansion promotions or market entry costs are beginning to impact net profitability.

- **Market Health**
  - **Strategic Backing**: APAC and EU remain the primary revenue pillars, serving as the essential "profit engines" to fund global expansion plans.
  - **Saturation Signals**: A critical risk is emerging as major profit drivers — specifically the US and China (APAC) — have transitioned into the **Profit Declining** group. This confirms that traditional core markets are hitting growth ceilings.
  - **Stability Buffers**: While some countries in EU and LATAM show declining profits, their small contribution weight ensures overall regional stability. These regions act as vital "safety buffers" during the resource shift toward new market penetration.

- **Customer Segment Structure**
  -  **Consumer**: Acts as the "Backbone" of the business, **contributing over 51% of total profit** and ensuring consistent cash flow for the entire system.
  -	**Home Office**: Despite having the smallest revenue share, this segment boasts the most optimized profit margin (11.88%). This highlights significant niche market potential with a highly efficient ROI (Return on Investment).
- **Product Portfolio Structure**
  - **Technology (The Lead)**: Maintains its dominant position with the highest revenue and a leading profit margin (13.7%). It remains the primary catalyst for market-wide growth.
  - **Furniture (Operational Red Flag)**: Despite being the second-largest revenue contributor, its profit margin is a mere 6.8% (less than half of Technology). This underperformance is a primary factor dragging down the company's overall consolidated margin.
  - **Office Supplies (The Balanced Performer)**: This category demonstrates the best equilibrium between cost management and profitability.

**2️⃣ Market Potential Analysis**

<img width="2000" height="1139" alt="Image" src="https://github.com/user-attachments/assets/7f743bb2-e890-4f22-bd2a-552d120ef524" />

**The Profit Margin Paradox and Growth Headroom**

Canada currently stands as the market with the lowest revenue contribution, yet it boasts a record-breaking profit margin of 26.62% — double that of mature markets such as APAC and the EU. This identifies Canada as a high-quality "Greenfield" market, where product value has remained intact and hasn't been eroded by aggressive price wars.

**Decoding Customer Behavior**

- **Stable Average Order Value (AOV)**: At **$326**, Canada’s AOV is comparable to other emerging markets like Africa and EMEA. This confirms that the local customer base possesses significant purchasing power.
- **The Loyalty Gap**: There is a record-low **Revenue per Customer ($370)**, driven primarily by an **Order Frequency of only 1.03** (averaging roughly one order per customer).
- **Key Insight**: Current Canadian customers are largely "transient" or one-time buyers. The data suggests that Canada does not have a spending power issue, but rather **a structural loyalty challenge**. The primary hurdle is not a "refusal to spend," but the absence of an effective **Retention Strategy**.

**Competitive Advantage: "Discount Resilience"**

A standout finding is that Canada operates with **0% discounting**. While other territories must rely on "Heavy Discounts" for over 20% of their orders to sustain volume, Canada achieves organic growth at full retail price. This demonstrates a unique capacity to absorb products based on actual value rather than price incentives.

**🍁STRATEGIC CONCLUSION: WHY CANADA?🍁**

We have identified Canada as the primary target for expansion based on three pillars:
- **Scalability Potential**: With a customer base representing only **3.7%** of our global footprint, the headroom for market penetration is immense.
- **Financial Resilience**: The superior profit margin provides a robust **"safety buffer"** to absorb the initial Marketing and Logistics costs inherent in North American expansion.
- **LTV Optimization Opportunity**: Based on our Growth Formula (Revenue = Customers x Frequency x AOV), if we can successfully drive engagement and **raise the Order Frequency from 1.03 to 1.5** (the benchmark for other emerging markets), **revenue in Canada could see a breakthrough surge of ~45%** without needing to alter the price structure or incur heavy new customer acquisition costs.


**3️⃣ Product Strategy Analysis**

<img width="2000" height="1139" alt="Image" src="https://github.com/user-attachments/assets/8a1c5c26-75f5-41dd-b78b-41e2a1950610" />

**Global Portfolio Overview & Financial Performance**

A comprehensive review of the corporate product portfolio reveals three distinct categories with unique financial and operational profiles:
- **Technology & Office Supplies (Core Drivers)**: These serve as the primary pillars of revenue, maintaining consistent and healthy profit margins.
- **Furniture (The Profit Paradox)**: Despite ranking second in revenue (slightly ahead of Office Supplies), this category yields **the lowest actual profit** among the three groups.

**Decoding the Profit Erosion in Furniture**
The underperformance of the Furniture category is not rooted in mispricing or operational inefficiency, but rather in the discounting strategy:
- **Stable Cost Structure**: The COGS-to-Gross Revenue ratio for Furniture is only approximately **2%** higher than the other two categories, while Shipping Costs remain well-controlled at comparable levels (**~11.45%**).
- **Heavy Discounting Impact**: Furniture has the highest proportion of discounted products, with **nearly 55% of items sold under promotion**. Specifically, medium-to-heavy discounts (20% or higher) account for nearly 43% of sales.
- **Margin Depletion**: Data shows that **discounts erode 18.56% of Furniture's gross revenue**. Given that gross margins for this category are naturally slimmer, this heavy discounting significantly compromises net profitability.
  
  <img width="300" height="240" alt="Image" src="https://github.com/user-attachments/assets/84bc13e3-75a1-42c3-b430-c2bfe88efd43" />
  
- **Return Risk**: Furniture also records a **high Return Rate** with significant return values. Due to the bulky nature of these items, returns result in substantial losses through reverse logistics costs and potential product damage.

**Operational Dynamics: AOV vs. Quantity**
There is a clear strategic divergence in customer engagement between the Technology and Office Supplies categories:
- **Technology (Value-Driven)**: Characterized by high Average Order Value (AOV) but lower sales volume. These products typically have a long lifecycle, leading to a naturally lower organic repurchase rate.
- **Office Supplies (Volume-Driven)**: Characterized by high transaction volume with lower AOV. As essential, fast-moving consumables for office environments, this category maintains the highest retention and repurchase rates.

**Market Spotlight: Canada Expansion Insights**

<img width="2000" height="1139" alt="Image" src="https://github.com/user-attachments/assets/482fd83b-8a23-4d31-b4de-f43852ecfc0c" />

Comparing global trends against the Canadian market reveals a highly "clean" financial landscape:
- **Premium Profit Margins**: By operating with **0% discounts**, all product categories in Canada achieve ideal profit margins ranging from **24% to 27%**.
- **Technology Dominance**: Canadian customers demonstrate a high willingness to pay for Technology products, yielding the highest AOV — nearly double that of the Furniture category.
- **Operational Note**: While returns have not yet been recorded, Canada's COGS currently trends higher than the global average (ranging from **61% to 64%**). This is a critical metric to monitor as the market scales.


# **🚀 Final Conclusions and Recommendations**

**1. The Strategic Verdict: Why Canada?** 🍁

Based on a multi-dimensional analysis of financial performance and customer behavior, Canada has been designated as the primary target for market scaling due to three absolute competitive advantages:

- 💰**Premium Profitability**💰 : A record-breaking **26.62% profit margin** (double that of mature markets). This serves as a strategic financial "buffer" to absorb operational costs and initial market entry risks.

- 🛡️**Price Integrity**🛡️: The only market maintaining **0% discounting**. This validates the organic appeal of the product and the ability to protect brand value without succumbing to price wars.

- 🌱**Untapped Potential**🌱: With a current customer base representing only **3.71%** of the total footprint, Canada is a high-quality **"Greenfield"** market with immense expansion headroom.

**2. Core Growth Strategy: Closing the Loyalty Gap** 🔗

Analysis indicates that the challenge in Canada is not purchasing power (AOV is stable at ~$326) but rather the **systemic nature of loyalty** (Order Frequency is stagnant at 1.03).

**Strategic Objective**: Prioritize **Retention** optimization before aggressively expanding the customer base. Scaling on a platform lacking engagement leads to inefficient Customer Acquisition Costs (CAC). The goal is to shift Order Frequency from **1.03 to 1.5** (regional benchmark), driving a breakthrough **~45%** revenue surge purely through the existing customer base.

**3. Action Plan: The Two-Phase Roadmap** 🗺️

🏗️ **Phase 1: Foundation & Retention-First (Plugging the "Loyalty Leak")**

Focus on building the infrastructure to transform transient buyers into loyal advocates.

- **Core Category**: Office Supplies (Essential, fast-moving consumables).

- **Tactics**:

  - Implement **Subscription models** (recurring orders) and **Loyalty programs** tailored to repurchase behavior.

  - Establish **Post-purchase Engagement** workflows to create regular brand touchpoints, converting one-time shoppers into repeat customers.

- **Expected Outcome**: A stabilized recurring revenue stream and a high-trust platform for high-value product penetration.

🚀 **Phase 2: Acquisition & Scaling (Revenue Acceleration)**

Once the retention engine is stabilized, the focus shifts toward market share capture and profit maximization.

- **Core Categories**: Synergistic focus on Office Supplies & Technology.

- **Tactics**:

  - **Office Supplies**: Aggressively scale marketing acquisition to capture new users, leveraging the automated retention systems from Phase 1.

  - **Technology**: Capitalize on established brand trust to Cross-sell high-AOV tech products, maximizing total revenue per customer.

🔒 **Operational Safeguards: Risk Mitigation**

- **Maintain No-discount Policy**: Prevent margin erosion (discounting impacts other regions by up to 18.56%).

- **Quality & Logistics Control**: Tighten inspection protocols to mitigate return risks and high-cost reverse logistics for bulky items.

**4. Financial Outlook** 💎

The focus on Canada represents a strategic shift from "growth at any cost" to **"Sustainable Profit Optimization"**. By integrating customer retention with full-price integrity, the enterprise is positioned to achieve rapid top-line growth with the lowest possible risk to net margins.
