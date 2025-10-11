# Infosys Springboard Food Brand – Understanding Customer Trends Project

## Project Overview
This project analyzes survey, review, and social media data to understand customer preferences, sentiment, and product-level performance for a food brand. The goal is to deliver actionable business insights via interactive Power BI dashboards and custom DAX measures that combine operational, sentiment, and revenue metrics.

## Under the Guidance:
- Pavithra Kannan mam

## All work is delivered by Team 5: 
- Samvedita Bisariya
- Udit Mathur
- Hema Latha
- Dipa Majumder

## Team Collaboration & Contribution

Our team adopted a highly collaborative and flexible working model. Instead of assigning fixed roles, all members contributed to every milestone based on their skills and interests. This dynamic approach fostered shared ownership and continuous learning, ensuring each stage of the project was a product of our collective effort, open communication, and mutual feedback.

## Contents

### PPT_Files
- Milestone-1-PPT.pptx — Project setup, data sources, initial EDA and plan.
- Milestone-2-PPT.pptx — Feature engineering, modeling approach, intermediate visuals.
- Milestone-3-PPT.pptx — Final dashboard walkthrough, measures, insights and recommendations.
- Milestone-4-PPT.pptx — Advanced persona segmentation, age group analytics, and business value visualizations.

### Dataset
restaurant_customer_satisfaction.csv — Raw dataset used for analysis.

### Dashboard.pbix

### Documentation
- Food Brand Understand Customer Trends_Infosys.pdf — Project brief and dataset documentation provided by Infosys.
- Milestone 1 Report
- Milestone 2 Report

## Evaluation Criteria (Milestone-Based):
- Milestone 1 (Week 2): Cleaned and standardized data from surveys, social media, and reviews. Unified data model validated.
- Milestone 2 (Week 4): Sentiment analysis implemented. Dashboard includes sentiment trends and keyword-based feedback themes.
- Milestone 3 (Week 6): Product-level dashboards with category comparisons and sentiment correlation completed.
- Milestone 4 (Week 8): Segmentation and user personas visualized across region and age filters.
- Milestone 5 (Week 10): Final strategy dashboard with trend keywords, sentiment shifts, and actionable recommendations.

## Project Methodology & Modules Implemented

Our team implemented the project through a structured, milestone-based approach, developing distinct analytical modules.

#### Module 1: Data Collection & Cleaning
- Loaded and integrated the `restaurant_customer_satisfaction.csv` dataset.
- Performed data cleaning and preparation using Power Query to ensure data quality.
- Established a star schema data model by creating `DimCustomer` and `DimProduct` dimension tables for robust analysis.

#### Module 2: Sentiment Analysis Module
- Developed a dual-method sentiment analysis engine:
    1.  Rule-Based Classification: Created a `SentimentCategory` column in Power Query based on numerical ratings (e.g., Rating >= 4 is "Positive").
    2.  AI/NLP Classification: Integrated a Python script with the **VADER** library to perform sentiment analysis on generated feedback text, creating `SentimentScore_AI` and `SentimentCategory_AI` columns.
- Enriched the dataset by creating a `DynamicFeedback` column that synthetically generates contextual review text.

#### Module 3: Product Insights Module
- Developed a suite of advanced DAX measures to evaluate sales, revenue, and customer ratings at a granular level.
- Compared product categories by average ratings for Food, Service, and Ambiance.
- Performed correlation analysis between key metrics like `Sales vs. Sentiment` and `Spend vs. Rating` using DAX.

#### Module 4: Customer Segmentation
- Identified and created actionable behavioral personas using DAX based on a customer's sentiment and visit frequency[cite: 367]. Key personas include:
    - Loyal Promoters
    - New/Occasional Positives
    - Casual Neutrals
    - High-Value Dissatisfied
    - At-Risk Customers
- Segmented customers into demographic `AgeGroup` categories (e.g., Teen, Adult, Senior) for deeper analysis.

## Key Technical Features & Deliverables

#### Interactive Power BI Dashboards
Four distinct dashboards were created to visualize insights from each milestone, featuring:
- KPI Cards: Tracking `Total Revenue`, `Total Visits`, `Average Rating`, `Average Sentiment Score`, and more.
- Comparative Analysis: Grouped bar charts to compare average Food, Service, and Ambiance ratings across cuisines.
- Correlation Plots: A scatter plot visualizing the relationship between customer sentiment and total sales by cuisine.
- Sentiment Breakdowns: Stacked bar charts showing the proportion of positive, neutral, and negative reviews for each cuisine.
- Persona Distribution: Donut and area charts illustrating the share of each customer persona and their distribution by visit frequency.

#### Advanced DAX & Power Query Implementation
- Custom DAX Measures:
    - `Total Revenue` = `SUM('SalesData'[SalesAmount])` 
    - `Product Feature Score` = `DIVIDE([Avg Food Rating] + [Avg Service Rating] + [Avg Ambiance Rating], 3)` 
    - `Corr_Spend_Rating` & `Corr_Sentiment_Sales` to mathematically calculate correlation 
    - `Loyalty %` to measure the percentage of visits from loyalty members 
    - `Revenue Rank` = `RANKX( ALLSELECTED('SalesData'[Cuisine]), [Total Revenue], , DESC, DENSE )` 
- Calculated Columns for Segmentation:
    - `AgeGroup`: Created using a `SWITCH(TRUE(), ...)` statement to classify customers by age.
    - `Persona`: Built with a `SWITCH(TRUE(), ...)` statement combining `SentimentCategory` and `FrequencyCategory` to define personas.

## Key Business Insights & Recommendations:
- Target `At-Risk` Customers for Retention: A significant portion of the customer base falls into the "At-Risk" and "High-Value Dissatisfied" personas. The business should prioritize these segments with targeted promotions and service recovery campaigns to prevent churn.
- Optimize Operations to Reduce `Wait Times`: The dashboard highlights variations in `Average Wait Time` across different cuisines. Focusing on improving efficiency for cuisines with longer wait times can directly enhance customer satisfaction and ratings.
- Leverage Strengths in `Top-Performing Cuisines`: Cuisines like Chinese and Mexican consistently receive higher ratings. These can be promoted more heavily, and their successful elements (e.g., specific dishes, service style) can be analyzed and potentially replicated across other offerings.
- Personalize Marketing Using `Personas`: The detailed persona and age group segmentation enables highly personalized marketing. "Loyal Promoters" can be enrolled in exclusive reward programs, while "New/Occasional Positives" can be targeted with offers to increase their visit frequency.

## Repository Contents & How to Use
- PPT_Files: Contains all milestone presentations detailing our process, findings, and analysis.
- Dataset: Includes the raw `restaurant_customer_satisfaction.csv` file used for the project.
- `Dashboard.pbix`: The final Power BI project file containing all data models, DAX measures, and interactive dashboards.
- `/Documentation/`: Contains the original project brief from Infosys and milestone reports.

## To Explore:
- Interactive Dashboard: Download and open `Dashboard.pbix` in Microsoft Power BI Desktop.
- Project Journey: Review the presentations in the `PPT_Files` directory for a step-by-step overview of our work.
