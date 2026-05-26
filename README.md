🛍️ Customer Behavior Analysis
A full-stack data analytics project uncovering shopping patterns, revenue drivers, and customer segments from real retail data
</div>

📌 Project Overview
This end-to-end data analytics project analyzes customer shopping behavior across 3 layers of the analytics stack — raw data cleaning in Python, business insight queries in SQL, and an interactive visual dashboard in Power BI.

Goal: Help a retail business understand who buys, what they buy, how discounts affect spending, and which customer segments drive the most revenue.


📊 Key Business Insights
💰 1. Revenue by Category

"Which product category makes the most money?"

CategoryInsight👗 ClothingHighest revenue contributor — largest product range drives volume👟 FootwearStrong performer — high avg. price per unit💍 AccessoriesHigh purchase frequency but lower unit price💻 ElectronicsLowest volume but highest avg. purchase amount🧥 OuterwearSeasonal demand limits total revenue
💡 Insight: Clothing dominates revenue due to volume, but Electronics has the highest revenue-per-transaction — a premium upsell opportunity.

🏷️ 2. Do Discounts Actually Increase Revenue?

"Are we losing money on discounts?"

Without Discount  ████████████████████  Higher total revenue
With Discount     ████████████████       Lower total revenue
💡 Insight: Discounted purchases generate less total revenue — discounts are attracting budget-conscious shoppers but not necessarily high spenders. Consider targeted discounts only for loyal/returning customers.

👥 3. Revenue by Gender
GenderRevenue Share🧑 MaleSlightly higher total spend👩 FemaleMarginally lower but more frequent purchases
💡 Insight: Gender split is nearly even — campaigns should not over-skew toward one demographic. Focus on behavior-based segmentation instead.

🎯 4. Customer Segmentation

Based on number of previous purchases

🆕 New Customers      (0 purchases)     → Acquisition focus
🔄 Returning Customers (1–15 purchases) → Retention & upsell
⭐ Loyal Customers    (15+ purchases)   → VIP rewards & referrals
💡 Insight: The majority of customers fall in the "Returning" bucket — a huge opportunity for subscription conversion and loyalty programs.

📦 5. Top & Bottom Rated Products
🏆 Top 5 (Highest Rated):

Products with consistent quality, likely Clothing & Accessories staples

⚠️ Bottom 5 (Lowest Rated):

Electronics & seasonal Outerwear items tend to score lower — quality reviews needed

💡 Insight: Low-rated products should be audited — poor reviews directly hurt repeat purchases and brand trust.

🚚 6. Shipping: Standard vs Express
Shipping TypeAvg. Purchase Amount🐢 StandardLower — budget shoppers choose this⚡ ExpressHigher — customers spending more are willing to pay for speed
💡 Insight: Customers who choose Express shipping spend more on average. Offering Express as a free perk above a purchase threshold could increase basket size.

💳 7. Subscribers vs Non-Subscribers
StatusAvg SpendTotal RevenueCustomer Count✅ SubscribedHigherSignificantly higherSmaller group❌ Not SubscribedLowerLowerLarger group
💡 Insight: Subscribed customers are more valuable per head. Growing the subscriber base is the single highest-ROI strategy — even a 10% increase in subscribers could meaningfully boost total revenue.

🔁 8. Repeat Buyers & Subscription Likelihood

Customers with more than 5 previous purchases...

💡 Insight: Repeat buyers are significantly more likely to hold a subscription. Targeting frequent shoppers with subscription upgrade prompts (especially around their 4th–5th purchase) could drive conversion.

👶👴 9. Revenue by Age Group
Age GroupRevenue Contribution20–40 (Young Adults)Highest — most active shoppers40–60 (Middle Aged)Second — stable spending power60+ (Senior Citizens)Lower volume but quality purchasesUnder 20Smallest — limited purchasing power
💡 Insight: Young adults (20–40) are the core customer base. Marketing and product decisions should be anchored to this segment's preferences.

🧹 Data Cleaning Pipeline
Raw CSV  →  Null Treatment  →  Deduplication  →  Normalization  →  cleaned_data.csv
StepActionCategory Mapping30+ items remapped to 5 correct categoriesSize NullsFilled by category logic (mode, "Free Size", "not available")Review Rating NullsFilled with per-product mean ratingPrevious Purchases NullsFilled with 0Purchase Amount NullsFilled with per-product meanDuplicatesIdentified and removed by Customer IDColumn NamesStandardized to snake_case lowercase

📁 Project Structure
customer-behavior-analysis/
│
├── 📓 notebooks/
│   └── customer_behavior_analysis.ipynb   ← Data cleaning & preprocessing (Python)
│
├── 🗄️ sql/
│   └── customer_behavior_analysis.sql     ← 12 business insight queries (MySQL)
│
├── 📊 powerbi/
│   └── customer_behaviour_analysis.pbix   ← Interactive dashboard
│
├── .gitignore
└── README.md

🗄️ SQL Business Questions (12 Total)
#QuestionTechnique Used1Highest revenue categoryGROUP BY + SUM2Discount impact on purchase valueGROUP BY + conditional3Revenue by genderGROUP BY + ORDER BY4Discount users above avg spendSubquery + WHERE5Top & bottom 5 rated productsORDER BY + LIMIT6Standard vs Express shipping spendWHERE IN + GROUP BY7Subscriber vs non-subscriber spendingGROUP BY + AVG + SUM8Top 5 discount-used productsCASE WHEN + percentage calc9Customer segmentation (New/Returning/Loyal)CASE WHEN + COUNT10Repeat buyers & subscription correlationWHERE + GROUP BY11Top 3 products per categoryWindow function (in progress)12Revenue by age groupCASE WHEN age ranges

🛠️ Tech Stack
ToolPurpose🐍 Python (Pandas)Data cleaning & preprocessing📓 Jupyter NotebookInteractive analysis environment🗄️ MySQLBusiness insight queries📊 Power BIData visualization & dashboard

🚀 How to Run
1. Python Notebook
bashpip install pandas
# Place customer_shopping_behavior.csv in /content/
# Run all cells → exports cleaned_data.csv
2. MySQL
sqlCREATE DATABASE CUSTOMERANALYSIS;
USE CUSTOMERANALYSIS;
-- Import cleaned_data.csv as table 'cleaned_data'
-- Then run queries from sql/customer_behavior_analysis.sql
3. Power BI
Open powerbi/customer_behaviour_analysis.pbix in Power BI Desktop
(Free download at powerbi.microsoft.com/desktop)

📈 Summary of Recommendations
PriorityActionImpact🔴 HighConvert repeat buyers (purchase 4+) to subscribersRevenue per customer ↑🔴 HighAudit low-rated products (bottom 5)Retention ↑🟡 MediumOffer Express shipping threshold incentiveBasket size ↑🟡 MediumTarget discount campaigns only at loyal segmentMargin ↑🟢 LowCreate age-specific campaigns for 20–40 groupAcquisition ↑

<div align="center">
Made with 🧠 Data • 🐍 Python • 🗄️ SQL • 📊 Power BI
Star ⭐ this repo if you found it useful!
