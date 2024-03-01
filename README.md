# Car Dealership- Dashboard


## Background

Chuck Peterson Dealership is a car dealership that sells various car models. To effectively track and analyse our sales performance, we need a comprehensive Car Sales Dashboard in Power BI. 

## Problem Statement

The dashboard should provide real-time insights into key performance indicators (KPIs) related to our sales data. This will enable us to make informed decisions, monitor our progress, and identify trends and opportunities for growth. 

#### Sales Overview: 
1. Year-to-Date (YTD) Total Sales 
2. Month-to-Date (MTD) Total Sales 
3. Year-over-Year (YOY) Growth in Total Sales 
4. Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales 

#### Average Price Analysis: 
1. YTD Average Price 
2. MTD Average Price 
3. YOY Growth in Average Price 
4. Difference between YTD Average Price and PTYD Average Price 

### Cars Sold Metrics: 
1. YTD Cars Sold 
2. MTD Cars Sold 
3. YOY Growth in Cars Sold 


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Checked the default settings of all the columns
- Step 4 : Created a new Table named 'Calender' and set relationship between Calender Table and the Car_data table. 
- Step 5 : The Calender Table was created to be utilised during creation of Time intellegence functions.
- Step 6 : The Car_Data table contains car_id, Customer details, model deatils , date of purchase, dealer details and the price of the car. 
- Step 7 : Follwoing Dax Functions were used to create our First KPI Sales Overview :
   
        Total YTD Sales = TOTALYTD(SUM(car_data[Price ($)]),'Calender   Table'[Date])
       
        Previous YTD total sales = CALCULATE(SUM(car_data[Price ($)]),SAMEPERIODLASTYEAR('Calender Table'[Date]))

        Sales difference = [Total YTD Sales] - [Previous YTD total sales]

        YOY sales = ([Sales difference]/[Previous YTD total sales])*100

        Total MTD KPI = CONCATENATE("Total MTD : ",FORMAT([Total MTD]/1000000,"$0.00"))


![Capture](https://github.com/paso2004/Sales/assets/161154534/71200b97-2697-4766-a3bf-0d3d8ef5baaf)

- Step 8 : Follwoing Dax Functions were used to create our Second KPI Average Sales :
   
        Average YTD sales = TOTALYTD([Average Sales],'Calender Table'[Date])
       
        Averqage PYTD sales = CALCULATE([Average Sales],SAMEPERIODLASTYEAR('Calender Table'[Date]))

        Average Difference = [Average YTD sales]-[Averqage PYTD sales]

        YOY Average = [Average Difference]/[Averqage PYTD sales]

        Average MTD kpi = CONCATENATE("Average MTD : ",FORMAT([Average MTD]/1000,"$0.00"))


![Capture](https://github.com/paso2004/Sales/assets/161154534/f559e7a5-cec3-4a1a-8b68-e9bde5bb8669)

- Step 9 : Total Car Sales KPI was created using similar DAX functions but with COUNT() command.
Snap of Sales Over View KPI
![Capture2](https://github.com/paso2004/Sales/assets/161154534/0f8aefc4-cf66-44d6-9e5e-d2f23ff1c97f)
- Step 10 : An area map was created for Sales analysis over weekly matrix. 
- Step 11 : Donut chart was selected to represent YTD sales based on Car Body Style.

- Step 12 : To represent the Average YTD on the colour of cars sold A donut chart was again created .
- Step 13 : A map plot was selected to represent the sales based on dealer region.
- Step 14 : No dashboard is complete without filters . So slicers were added to filter the dashboard based on : Body Style, Dealer Name , Transmission , Engine.
- Step 15 : We created a seconf page with all the details in atabular format that includes : Card Id, Date, Customer Name , Company , Model , Colour , Total Sales(Price)


# Snapshot of Dashboard (Power BI DESKTOP)

![capture3](https://github.com/paso2004/Sales/assets/161154534/0404e60e-c851-4edb-a160-4dae40aedce0)

 
 # Deatils Snapshot (Power BI DESKTOP)

 
![Capture4](https://github.com/paso2004/Sales/assets/161154534/dc8acef1-26ce-483b-9edd-dd75514c1056)
