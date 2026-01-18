# Car sales Report

### Report Link : https://app.powerbi.com/groups/me/reports/2a545714-9cc5-4f3d-bd5b-6ff663048476/02b64ffeadd52599ec0d?experience=power-bi

## Report insight

The Report consists of 3 pages(Business overview, Dealer Performance, Customer Performance)

## THE BUSINESS  OVERVIEW INSIGHT
- The revenue performance reflects a strong, volume-driven growth trajectory supported by consistent pricing and broad market demand. Total revenue of $671.5M from 23,905 vehicles sold indicates that growth is being achieved through scale rather than price inflation, with the average selling price remaining stable at approximately $28K.
- Year-over-year revenue shows a clear upward trend, with revenue increasing from roughly $300M in 2022 to $371M in 2023, demonstrating sustained demand momentum and effective sales execution.
- Brand performance is concentrated among mass-market manufacturers such as Chevrolet, Ford, and Dodge, confirming that accessibility and product availability drive higher revenue contribution compared to premium positioning alone. This same pattern is visible at the customer and dealer levels, where revenue leadership is driven by repeat purchasing and high transaction volume, not isolated high-value sales.
- Regionally, revenue is strongest in markets like Austin and Janesville, highlighting the impact of population density and active buyer participation. These regions outperform others without relying on higher pricing, reinforcing that demand scale is the primary revenue lever.
- Product mix analysis shows SUVs and Hatchbacks contributing nearly half of total revenue, reflecting customer preference for versatile and practical vehicle types. Similarly, neutral and popular color choices such as Pale White and Black dominate sales, indicating demand alignment rather than trend-driven volatility.    

## THE DEALER PERFORMRANCE INSIGHT 
- This analysis reinforces a consistent theme across the business: dealer performance is primarily volume-driven rather than price-driven.
- Despite noticeable differences in total revenue among top-performing dealers, the average selling price remains tightly clustered around ~$28K. Dealers such as Progressive Shippers Cooperative, Rabun Used Car Sales, and Saab-Belle Dodge generate materially higher revenue and unit sales without materially higher pricing. This confirms that revenue leadership is achieved through higher transaction volume and customer throughput, not premium pricing.
- The left visual shows that even when average selling price fluctuates slightly, it does not materially alter total revenue rankings among top dealers. Similarly, the right visual demonstrates that dealers selling more cars do so without increasing price, further validating that demand scale and operational efficiency—not pricing leverage—are the dominant performance drivers.
- The relatively stable Income-to-Price ratio (~29–30) across dealers suggests pricing is well aligned with customer affordability, reducing elasticity risk and supporting sustained demand.        

## CUSTOMER PERFORMANCE INSIGHT
- The dashboard highlights a strong revenue-driven performance fueled primarily by volume rather than premium pricing, with clear opportunities to sharpen customer segmentation and pricing strategy.
- Overall performance is solid, generating $671.5M in total revenue from 23,905 vehicles sold, with an average selling price of ~$28.1K. This indicates a healthy mid-market positioning rather than a luxury-led model. However, revenue per dealer mirrors total revenue, suggesting revenue concentration across a limited dealer base, which could pose scalability or risk-exposure concerns.
- From a customer performance perspective, revenue is highly skewed toward a small group of repeat buyers. Customers like Aaron and Aaliyah demonstrate high purchase frequency and outsized revenue contribution, reinforcing the importance of relationship-driven sales and retention programs. At the same time, the wide spread in income-to-price ratios reveals that many customers are purchasing well below their affordability threshold, signaling untapped upsell and cross-sell potential, particularly for higher-trim or premium models.
- The vehicle mix analysis shows that brands with moderate average selling prices (e.g., Chevrolet, Ford, Toyota) generate the highest total revenue, confirming that volume efficiency outweighs premium pricing in overall revenue impact. Luxury brands exhibit higher prices but lower volume, limiting their total contribution.
- Regionally, the “people-driven” markets outperform price-driven ones, meaning customer density and demand matter more than pricing power. Regions like Austin and Scottsdale represent growth anchors, whereas lower-density regions may require pricing incentives or localized marketing strategies to improve performance.
- Finally, the average customer income vs. cars sold analysis indicates a misalignment between customer earning power and vehicle pricing, particularly in mid-income segments. This presents a clear opportunity to reposition higher-margin vehicles to customers already capable of affording them, without relying on discounts.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present .
- Step 5 : New	 calculated measures was created.
- Step 6 : Visual filters (Slicers) were added for four fields named "Model", "Engine", "Transmission" & "Gender" it is sync to all page in the report.                                                                                                                                                                                                                                                                                        
- Step 7 : Five card visuals were added to the canvas, representing total revenue, total car sold, average selling price, year over year revenue growth, and previous year revenue.
- Step 8 : A line chart ,Column chart, two Bar chart, a treemap chart donut chart and pie chart was also added to the report design area representing sales trend by year, top 5 car brand, top 5 by customer, top 5 dealer, revenue by region, revenue by car style, revenue by car colour.
- Step 9 Two more pages was created named
- Step 10 : Calculated column was created in which, income  were grouped into various groups.
for creating new column following DAX expression was written;
       
       Income range = IF('car_sales_date_corrected'[Annual Income]<= 100000,"Below 100k",
                IF('car_sales_date_corrected'[Annual Income]<=500000,"100k - 500k",
                IF('car_sales_date_corrected'[Annual Income]<=1000000,"500k - 1m",
                IF('car_sales_date_corrected'[Annual Income]<=5000000,"1m - 5m","Over 5m"
                ))))        




