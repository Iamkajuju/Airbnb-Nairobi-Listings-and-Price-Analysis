# Airbnb-Nairobi-Listings-and-Price-Analysis
## Table of content
 - [Description](#description)
 - [Tools](#tools)
 - [Skills Demonstrated](#skills-demonstrated)
 - [Dataset](dataset)
 - [Project Aim](#project-aim)
 - [Business Questions](#business-questions)
 - [Processes](#processes)
 - [Key Findings](#key-findings)
 - [Insights](#insights)
 - [Recommendations](#recommendations)
 - [Limitations](#limitations)

### Description
This project was built as a hands-on opportunity to practice the full range of Excel-based analysis: data cleaning, exploratory analysis, PivotTable construction, KPI design, and dashboard building. I worked with Inside Airbnb's Nairobi dataset.Beyond the mechanics, the project became a case study in why reputation, not price, tends to predict booking success, and in the importance of questioning outliers rather than letting them quietly skew the story.

### Tools
Microsoft Excel (Power Query, PivotTables, PivotCharts, Conditional Formatting, Formulas, Box & Whisker Charts, Histogram)

### Skills demonstrated
- Data cleaning & validation
- Handling missing/incomplete data
- Outlier detection & investigation
- Exploratory data analysis (EDA)
- PivotTable & KPI development
- Data visualization & dashboard design
- Data-driven storytelling & documentation

### Dataset
Source:[Inside Airbnb](https://insideairbnb.com/get-the-data/)

Listings.csv - Nairobi listings data on Airbnb as of June 2026
 - Fields: 79
 - Rows: 22008

### Project Aim
This project aims to identify what actually drives Airbnb listing performance in Nairobi — specifically, whether price, location, host reputation, or reviews best predict booking success, measured through estimated annual revenue. It also aims to demonstrate a complete, disciplined analyst workflow in Excel, from data cleaning and validation through to a clear, insight-driven dashboard.

### Business Questions
- Does Superhost status drive higher revenue, and if so, is it through pricing power or booking volume? 
- Do guest reviews meaningfully impact a listing's earning potential? 
- Which neighborhoods show genuine, reliable pricing power versus small-sample noise? 
- How much does outlier pricing distort the market's reported average, and what's the true typical price?

### Processes
Step 1: Data Preparation & Cleaning
   
Tools: Microsoft Excel — Power Query, Tables, Conditional Formatting, Formulas, Box & Whisker Plot
   
Activities:
- Loaded the raw Inside Airbnb Nairobi dataset (June 2026 scrape) via Power Query and reviewed its structure and variables.
- Created a separate working dataset from the raw data to preserve source integrity.
- Confirmed row count (22,008) and checked for duplicate listing IDs using Conditional Formatting.
-	Checked for blank/missing values across all columns using Conditional Formatting and COUNTBLANK.
-	Removed 13 columns found to be entirely blank across all listings.
-	Investigated partial blanks in bathrooms, recovering values from bathrooms_text using a formula-based extraction; confirmed remaining gaps had no reliable     source and were left blank.
-	Investigated blank values in price, price_quote_total_price, and price_quote_per_night, confirming they occurred on the same 314 rows and reflected incomplete scrape data rather than inactive listings.
- Determined bedrooms had no reliable backup column and left missing values blank rather than estimating them. 
- Checked data types to ensure price and other numeric fields were stored correctly (not as text). 
- Reviewed and cross-referenced neighbourhood and neighbourhood_cleansed, confirming the cleansed field was the appropriate standardized column for location-based analysis. 
- Examined the price variable for outliers using MAX/LARGE functions and a Box & Whisker plot. 
-  Manually investigated the highest-priced listings and confirmed extreme values (e.g., 3,399,795 KES) were pricing anomalies rather than genuine rates, based on inconsistent listing details and minimal booking history. 
- Flagged listings priced above 100,000 KES (99 listings, 0.46% of data) as outliers rather than removing them, preserving them for non-price analysis. 
- Confirmed the cleaned dataset contained no remaining duplicates or unexplained blanks requiring further correction.

Step 2: Exploratory Data Analysis (EDA)
   
Tools: Microsoft Excel — PivotTables, Formulas
   
Activities:
-	Created PivotTables to examine average pricing and listing volume by neighborhood and room type.
-	Calculated average price, estimated annual revenue, and listing share by Superhost status to compare regular hosts against Superhosts.
-	Created a helper field to classify listings as "Has Reviews" or "No Reviews," then compared pricing, revenue, and rating outcomes between the two groups.
-	Calculated the percentage of listings with no reviews to assess market maturity.
-	Built a location-based PivotTable combining listing count, average price, and average reviews per month to distinguish high-volume neighborhoods from high-activity ones.
-	Compared average price with and without flagged outliers to quantify their impact on summary statistics.
- Identified patterns showing that host reputation and review activity were more strongly associated with revenue than price positioning.

Step 3: Data Visualization
   
Tools: Microsoft Excel — Charts, KPIs, Dashboard
   
Activities:
- Selected chart types suited to each finding, including combo charts (bar + line) for metrics requiring both value and sample-size context.
-	Created charts to visualize pricing by neighborhood, pricing by room type, Superhost performance, review impact, price distribution, and neighborhood-level booking activity.
-	Created KPI cards for: Total Listings, Average Price of normal price and outliers, % of Listings Reviewed, and Superhost Revenue Multiple.
-	Designed an Excel dashboard combining all KPIs and charts into a single, cohesive view of the market.

### Key Findings
Pricing & Market Structure
- Nairobi's Airbnb prices are heavily right-skewed: the median price (6,147 KES) sits well below the average (9,715 KES), with most listings falling between 4,000–13,000 KES per night.
- A small number of pricing anomalies distort the market average — removing 99 flagged outlier listings (0.46% of data) lowers the average price from 9,715 KES to 8,076 KES.
- Kilimani is the dominant neighborhood by volume (43% of priced listings) with a moderate, reliable average price (11,419 KES). High averages in low-volume neighborhoods (e.g., Kamukunji, 63 listings) are unreliable and should be interpreted with caution.
- Entire home/apt (85.1%) and Private room (14.5%) dominate the market and are priced surprisingly close to each other (~2.5% apart) — unlike more mature markets, where entire homes typically command a larger premium.

Host Reputation & Revenue
- Superhosts represent only 14% of listings but earn nearly 10x the average estimated annual revenue of regular hosts (418,207 KES vs 43,036 KES), despite pricing 15% lower on average.
- Listings with guest reviews earn substantially more (233,455 KES average estimated revenue) than listings with none (0 KES), even though unreviewed listings are priced 24% higher on average.
- Across both Superhost status and review activity, trust and reputation — not price — appear to be the strongest drivers of booking success in this market.

Market Maturity
-	59% of Nairobi listings have never received a review, indicating a young, rapidly growing market with significant unproven supply.
-	Booking activity (reviews per month) does not always track listing volume or price — Dagoretti and Kibra show the highest average booking activity, despite smaller listing counts and lower prices than Kilimani or Westlands.

### Insights
-	Across every angle of this analysis — host status, review activity, and even neighborhood-level demand — the same pattern holds: reputation outperforms price as the strongest signal of booking success in Nairobi's Airbnb market. Superhosts and reviewed listings consistently earn dramatically more than their unreviewed or non-Superhost counterparts, even while charging less — suggesting that guests are optimizing for trust and proof of quality over cost savings. This has a direct practical implication: a new host entering this market is likely better served by pricing competitively to build an early review history than by pricing at or above the market average from day one.
-	The data also points to a market that is still young and unevenly developed. With 59% of listings unreviewed and booking activity concentrated in neighborhoods that aren't necessarily the largest or priciest (Dagoretti and Kibra outperforming Kilimani and Westlands on reviews per month), there appears to be real, unmet guest demand outside the most saturated areas — a signal worth further investigation for hosts or investors considering where to enter the market.
-	Finally, the outlier investigation reinforced a broader analytical lesson: headline averages can be misleading. A handful of anomalous listings (less than 0.5% of the dataset) inflated the reported average price by nearly 17%, underscoring the importance of validating summary statistics — not just calculating them — before drawing conclusions from them.

### Recommendations
For Hosts
- New listings should prioritize competitive pricing over premium positioning in the early stages — the data shows unreviewed listings often price higher than reviewed ones, yet earn substantially less. Lowering initial rates to attract first bookings and reviews appears to be a more effective strategy for building long-term revenue.
-	Pursuing Superhost status should be treated as a revenue strategy, not just a reputation badge — the near 10x revenue gap suggests the operational effort required (responsiveness, low cancellations, guest satisfaction) delivers a measurable return.
  
For Investors
- Kilimani and Westlands remain the safest, most established markets by volume and reliable pricing, but they may also be the most saturated — evidenced by comparatively lower booking activity per listing.
-	Dagoretti and Kibra show stronger relative guest demand despite smaller listing counts and lower prices, suggesting these neighborhoods may be undersupplied relative to demand and worth further investigation as emerging opportunities.
  
For Platform/Market Development
-	With 59% of listings still unreviewed, targeted support for new hosts (e.g., guidance on early pricing strategy, review-building incentives) could meaningfully accelerate market maturity.
-	Given how easily a handful of listings distorted the average price city-wide, platform-level pricing anomaly detection (flagging implausible rates) would improve the accuracy of any market reporting drawn from this data.
  
For Future Analysis
-	Extend this analysis with a full correlation study between review scores and price (started but not completed here) to test whether guest satisfaction predicts pricing power.
-	Revisit this dataset in 6–12 months to track how quickly the "no reviews" segment converts into active, reviewed listings — a useful indicator of market maturity over time.

### Limitations
- This dataset reflects a single scrape date (June 2026) and does not capture 
  seasonal pricing or booking trends over time.
- Revenue and occupancy figures are Airbnb-estimated, not confirmed booking data.
- Some fields (bedrooms, host response metrics) had no reliable way to recover 
  missing values and were left blank rather than estimated.
- As one of Inside Airbnb's newest markets, Nairobi's dataset may be less 
  complete or consistent than more established cities' datasets.

### Acknowledgements
Data provided by [Inside Airbnb](https://insideairbnb.com), an independent, 
non-commercial project supporting research on short-term rentals worldwide.

## About Me
**Hilda Kajuju**  
📧 kajujumurithi1@gmail.com





