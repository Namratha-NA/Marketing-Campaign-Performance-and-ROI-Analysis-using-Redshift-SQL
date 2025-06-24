# Marketing Campaign Performance and ROI Analysis using Redshift SQL
This project analyzes multi-channel marketing campaigns (Google Ads, Facebook, LinkedIn, Email) using Amazon Redshift and SQL. It covers Python-based preprocessing, simulated ad spend and revenue, schema design, S3 ingestion, and SQL analysis of ROI, attribution models (first-touch, last-touch), and customer funnels to identify top-performing channels and optimize marketing budgets.

## Objectives
- Measure and compare ROI across marketing channels
- Analyze first-touch and last-touch attribution
- Visualize funnel performance from impressions to conversions
- Identify drop-off points and optimize campaign spend

## Tech Stack
- **Data Warehouse**: Amazon Redshift
- **Data Storage**: Amazon S3
- **Data Processing**: Python (Pandas, NumPy)
- **Data Ingestion**: Redshift COPY Command
- **Analysis**: SQL
- **Visualization**: Power BI

## Dataset Structure
Data is normalized into 3 tables:
- `campaigns`: `ad_id`, `ad_platform`, `ad_type`, `ad_spend`, `revenue`, `roi`
- `users`: `user_id`, `age`, `gender`, `location`, `interests`, `device_type`
- `customer_journey`: `user_id`, `ad_id`, `impressions`, `clicks`, `conversion`, `engagement_score`

## Workflow

1. **Data Preprocessing**
   - Cleaned raw social media ad dataset using Python
   - Simulated ad spend and revenue per conversion
   - Calculated ROI for each campaign

2. **Data Normalization**
   - Split into 3 tables: `campaigns`, `users`, `customer_journey`
   - Saved as CSVs for Redshift ingestion

3. **Redshift Setup**
   - Uploaded CSVs to S3
   - Created staging tables in Redshift
   - Used `COPY` to ingest data

4. **SQL Analysis**
   - ROI per channel/campaign
   - Attribution modeling (first-touch, last-touch)
   - Funnel analysis (impressions → clicks → conversions)

## Insights
- LinkedIn campaigns yielded **3.5x ROI**, outperforming other platforms
- **65% drop-off** observed at the click stage in most campaigns
- Email campaigns showed high conversion rates but lower engagement
