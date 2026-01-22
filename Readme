Fmcg-Report
Problem Statement
This report helps the Stakeholder understand their customers better. It helps the stakeholder to know what product is doing well and the ones not doing well, the stock out duration and how to fix it, weather impact on sales, is promotion effective, does holiday affect sales, weekday or weekend which one generate more income. Through different report and visuals, they get to know their improvement area, & thus they can improve their services by identifying these area.

Steps followed
Step 1 : Load data into Power BI Desktop, from Microsoft sql server.
Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
Step 4 : It was observed that in none of the columns errors.
Step 5 : By default the supplier id is in numbers instead of been a unique id, so it is been fixed using power query.
Step 6 : I split the supplier id column by delimiter to separate the numbers from the zeros.
Step 7 : After the split I now have two column, I deleted the columns with zero.
Step 8 : Add a prefix of 's' to the other column with numbers and change the data type to text.
Step 9 : Save and close power query.
The entire report consist of 6 pages and each pages tells a unique business story

Step 10 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted & the title of the report was written.
Step 11 : Calculated column was created in which, Holiday status were grouped into various two groups(No holiday and holiday).
for creating new column following DAX expression was written;

Holiday Status = IF('fmcg_sales_3years_1M_rows'[is_holiday]=FALSE()," No Holiday","Holiday")

promo group = IF('fmcg_sales_3years_1M_rows'[discount_pct]=0,"No Discount", IF('fmcg_sales_3years_1M_rows'[discount_pct]<0.10,"Below 10%", IF('fmcg_sales_3years_1M_rows'[discount_pct]<0.20,"Below 20%", IF('fmcg_sales_3years_1M_rows'[discount_pct],"Below 30%"))))

promotion = IF('fmcg_sales_3years_1M_rows'[promo_flag]=FALSE(),"No Discount","Discount")

Rain grouping = IF( 'fmcg_sales_3years_1M_rows'[rain_mm]=0,"No rain", IF('fmcg_sales_3years_1M_rows'[rain_mm]<=0.99,"Very little" , IF('fmcg_sales_3years_1M_rows'[rain_mm]<=2.99,"little rain", IF('fmcg_sales_3years_1M_rows'[rain_mm]<=4.99,"Much rain", IF('fmcg_sales_3years_1M_rows'[rain_mm]<=5.99,"Heavy Rain", IF('fmcg_sales_3years_1M_rows'[rain_mm]<=8.99,"Slightly heavy", IF('fmcg_sales_3years_1M_rows'[rain_mm]>8.99,"Very heavy")

))))))

weekend vs weekday = IF('fmcg_sales_3years_1M_rows'[is_weekend]=TRUE(),"Weekends","Weekday")
Step 12: A new table was created and rename as measure table, it hold all the created measures used all through the report.
the measures are as follows

Average Margin(%) =
AVERAGE('fmcg_sales_3years_1M_rows'[margin_pct])

Avg lead time =
AVERAGE('fmcg_sales_3years_1M_rows'[lead_time_days])

Promo Lift % =
DIVIDE( CALCULATE(AVERAGE('fmcg_sales_3years_1M_rows'[units_sold]),'fmcg_sales_3years_1M_rows'[promo_flag]=TRUE())- CALCULATE(AVERAGE('fmcg_sales_3years_1M_rows'[units_sold]), 'fmcg_sales_3years_1M_rows'[promo_flag]=FALSE()), CALCULATE(AVERAGE('fmcg_sales_3years_1M_rows'[units_sold]), 'fmcg_sales_3years_1M_rows'[promo_flag]=FALSE()))

Stock Out Count =
CALCULATE( COUNTROWS('fmcg_sales_3years_1M_rows'), 'fmcg_sales_3years_1M_rows'[stock_out_flag]=TRUE())

Stockout Rate(%) = DIVIDE( COUNTROWS(FILTER('fmcg_sales_3years_1M_rows','fmcg_sales_3years_1M_rows'[stock_out_flag]=TRUE())),COUNTROWS('fmcg_sales_3years_1M_rows'))*100

Total Profit =

SUM('fmcg_sales_3years_1M_rows'[net_sales]) - SUMX('fmcg_sales_3years_1M_rows','fmcg_sales_3years_1M_rows'[purchase_cost] * 'fmcg_sales_3years_1M_rows'[units_sold])

7 . Total Sales = SUM(fmcg_sales_3years_1M_rows[net_sales] )

Total Unit Sold = SUM('fmcg_sales_3years_1M_rows'[units_sold])
