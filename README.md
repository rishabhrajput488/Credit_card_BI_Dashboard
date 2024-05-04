# Credit_card_BI_Dashboard
Power BI Credit Card Transaction and Customer Details Dashboard : This repository houses a dynamic Power BI dashboard that provides valuable insights into credit card transactions and customer data. 
Credit Card Transaction Report Key Features:
    Metrics at a Glance: Discover the big numbers—$57M in revenue, $8 M in interest earned, and a 656K total transactions.
    Granular Breakdowns: Dive deeper with breakdowns by card category (Blue, Silver, Gold, Platinum), expenditure type (bills, entertainment, fuel, grocery, food, travel), education level, and job type.
    Quarterly Trends: Visualize revenue and transaction patterns across Q1 to Q4, helping you spot seasonal trends.
    User-Friendly Design: Intuitive bar graphs, tables, and clean visuals make data exploration a breeze. 
Csutomer Report Key Features:
    Comprehensive Analytics: Tracks over 10.3K cardholders, with insights into acquisition costs, credit scores, and delinquencies.
    Revenue Insights: Presents revenue trends by year, quarter, month, day, and gender through an interactive line graph.
    Customer Demographics: Analyzes transactions by age and income groups, offering a deep dive into customer spending behavior.
    Geographic Distribution: Showcases credit card holder statistics by state, providing a geographic perspective on card usage.

DAX Queries used in creating Measures:

    Revenue = SUMX(credit_card, credit_card[Annual_Fees] + credit_card[Interest_Earned] + credit_card[Total_Trans_Amt])
    
    Prev Week Revenue =  CALCULATE([Revenue], 
                            FILTER(ALL('credit_card'),
                                'credit_card'[Week_Start_Date] = MAX('credit_card'[Week_Start_Date]) - 7))
                                
    W/W revenue change = DIVIDE(([Revenue]-[Prev Week Revenue]), [Prev Week Revenue])
