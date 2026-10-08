# Bank Customer Churn Analysis 

## Background

This project analyzes customer churn for a fictional bank using the **Bank Customer Churn dataset from Maven Analytics**. The goal was to understand which customer segments are more likely to leave and where the bank should focus its retention efforts. I built the analysis entirely in **Power BI**, focusing on customer segmentation, churn patterns, and business-focused recommendations.

## Executive Summary

The dataset contains **10,000 customers**, with **2,037 customers churned**, resulting in a **20.37% churn rate**. Germany stands out with a **32.44% churn rate**, roughly twice the rate of France and Spain. Customer characteristics also matter: **50–59-year-olds have a 56.04% churn rate**, while inactive customers churn at **26.85% compared with 14.27% for active customers**. The biggest volume opportunity is among **one-product customers**, who account for **1,409 churned customers, or 69.2% of all churned customers**.

## Insights Deep Dive

### 1. Churn is concentrated rather than evenly distributed

Out of 10,000 customers, **2,037 have exited**, giving the bank an overall churn rate of **20.37%**.

That means roughly **1 in every 5 customers** has left.

The more important question, however, is whether those 2,037 churned customers are spread evenly across the customer base. Looking at the segments shows that they are not.

---

### 2. Germany has a much higher churn rate than the other countries

| Geography | Customers | Churned Customers | Churn Rate |
| --------- | --------: | ----------------: | ---------: |
| Germany   |     2,509 |               814 | **32.44%** |
| Spain     |     2,477 |               413 |     16.67% |
| France    |     5,014 |               810 |     16.15% |

Germany immediately stood out to me.

Its **32.44% churn rate** is almost twice the rate seen in France and Spain. What's particularly interesting is that Germany has roughly half as many customers as France, yet produced almost the same number of churned customers: **814 versus 810**.

From a business point of view, Germany would be one of the first areas I'd investigate further.

The current dataset doesn't contain information about customer service, fees, complaints, or local market conditions, so I wouldn't claim that geography itself is causing churn. Instead, Germany is a clear signal that something about this customer population deserves further investigation.

---

### 3. Customers aged 50–59 have the highest observed churn risk

Age showed a much stronger difference than I initially expected.

| Age Group | Churn Rate |
| --------- | ---------: |
| 18–29     |      7.56% |
| 30–39     |     10.88% |
| 40–49     |     30.79% |
| **50–59** | **56.04%** |
| 60+       |     27.95% |

Customers aged **50–59 have a 56.04% churn rate**, compared with **20.37% overall**.

This is particularly interesting because the relationship isn't simply "older customers churn more." The churn rate peaks in the 50–59 group and then falls to **27.95%** among customers aged 60+.

That makes the 50–59 segment worth investigating rather than assuming age alone explains the difference.

---

### 4. Inactive customers are considerably more likely to churn

Customer engagement also showed a clear difference.

| Customer Status | Customers | Churn Rate |
| --------------- | --------: | ---------: |
| Active          |     5,151 | **14.27%** |
| Inactive        |     4,849 | **26.85%** |

Inactive customers churn at almost **twice the rate** of active customers.

They also make up **4,849 customers**, meaning this isn't a tiny segment that can simply be ignored.

This suggests that customer engagement could be useful as an early warning signal. However, the dataset only gives us the customer's active/inactive status at a point in time, so I would want historical engagement data before concluding that inactivity is the reason customers leave.

---

### 5. One-product customers create the largest churn volume

The number of products produced one of the most interesting patterns in the analysis.

| Number of Products | Customers |   Churned |  Churn Rate |
| -----------------: | --------: | --------: | ----------: |
|                  1 |     5,084 | **1,409** |      27.71% |
|                  2 |     4,590 |       348 |   **7.58%** |
|                  3 |       266 |       220 |  **82.71%** |
|                  4 |        60 |        60 | **100.00%** |

At first glance, the 3- and 4-product groups look like the biggest problem because their churn rates are extremely high.

But looking at **churn volume** changes the picture.

One-product customers account for **1,409 of the 2,037 churned customers**, or **69.2% of all churned customers**.

This is why I wouldn't look at churn rate alone. A small segment can have an extremely high churn rate without representing the largest business opportunity.

The 3- and 4-product groups should still be investigated, but their small populations mean I wouldn't immediately generalize the result or assume that having more products causes customers to leave.

---

### 6. The highest-risk segments become clearer when characteristics are combined

Looking at individual variables is useful, but combining characteristics gives a better picture of where risk is concentrated.

For example, **Germany + age 50–59 + inactive customers** has an observed churn rate of **86%**, with **126 of 146 customers** having exited.

Other combinations also show elevated churn, including:

* **Germany + 40–49 + inactive:** 52% churn
* **France + 50–59 + inactive:** 78% churn
* **Germany + 40–49 + active:** 37% churn

This suggests that churn isn't simply a "Germany problem" or an "age problem." The risk becomes more pronounced when multiple characteristics overlap.

At the same time, I would treat these combinations as **high-risk segments for investigation**, not proof that these characteristics cause churn.

---

### 7. Not every customer characteristic is equally useful

One of the lessons from this analysis was that not every variable needs to become a headline finding.

Some characteristics, such as **credit score, estimated salary, and tenure**, showed relatively small differences in churn compared with the stronger patterns found in geography, age, activity, and product count.

I therefore wouldn't give every available column equal attention in an executive dashboard.

The objective isn't to show everything in the dataset. It's to identify the patterns that can actually help management decide where to investigate.

## Recommendations

### 1. Investigate the German customer experience

Germany has a **32.44% churn rate**, compared with around **16–17% in France and Spain**.

The bank should investigate whether differences in customer experience, products, fees, service interactions, or other local factors could explain this gap.

The current dataset cannot identify the underlying reason, so this should be treated as an investigation rather than a confirmed cause.

### 2. Prioritize one-product customers for retention analysis

One-product customers account for **1,409 churned customers**, representing **69.2% of all churned customers**.

Rather than simply trying to sell these customers additional products, I would first investigate why their relationship with the bank remains limited and whether there are relevant products or services that genuinely improve their customer relationship.

### 3. Use inactivity as a potential early-warning signal

Inactive customers have a **26.85% churn rate**, compared with **14.27% for active customers**.

The bank could investigate whether declining customer activity can be used to identify customers who may need attention before they leave.

Historical login, transaction, product-usage, and interaction data would make this much more useful.

### 4. Investigate the extreme 3- and 4-product churn rates

The **82.71% churn rate among 3-product customers** and **100% among 4-product customers** are too unusual to ignore.

However, these groups contain only **266 and 60 customers**, respectively.

I wouldn't immediately recommend a broad retention strategy based on these numbers. Instead, I'd investigate the specific products, fees, customer journeys, and data quality behind these segments to understand why their churn is so high.

## Final Words

The main lesson from this project is that **churn rate alone doesn't tell the whole story**. The highest-risk segment isn't necessarily the biggest business opportunity. One-product customers have a much lower churn rate than the 3- and 4-product groups, but they account for **69.2% of all churned customers** because the segment is much larger.

For me, the most useful part of the analysis was moving from *"Who churned?"* to *"Where is churn concentrated, how large is the opportunity, and what should the business investigate next?"* The available data provides strong signals, but understanding the actual reasons behind churn would require additional customer behavior and experience data.
