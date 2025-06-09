# Car_Sales_Analysis
Car Sales Insights with SQL
# Introduction
Project Title: "Car Sales Insights with SQL"

Tools Used: MySQL

Objectives:
Analyze price trends
Compare car conditions and their impact on pricing
Determine feature popularity

Deliverables:
SQL script
______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

##Car Dataset Unedited
![UNCORRECTED COLUMN NAMES](https://github.com/user-attachments/assets/d3eed5b3-968b-4b2e-93a2-252fee0928a8)

## 1. Correct column names
ALTER TABLE updated_car_sales_data
CHANGE `Car Make` car_make VARCHAR (100),
CHANGE `Car Model` car_model VARCHAR (100),
CHANGE `Fuel Type` fuel_type VARCHAR (100),
CHANGE `Options/Features` options_features VARCHAR (100);

![script for change of column names](https://github.com/user-attachments/assets/f94ff61b-9b33-4fdb-949a-e9b681ae7869)

![CORRECTED COLUMNS](https://github.com/user-attachments/assets/ed9e1527-88a8-4118-b4e4-9801d076573e)

## 2. Top 10 Car Makes by Number of Sales
SELECT car_make, COUNT(*) AS total_sales
FROM updated_car_sales_data
GROUP BY car_make
ORDER BY total_sales DESC
LIMIT 10;

![Top 10 Car Makes by Number of Sales](https://github.com/user-attachments/assets/0c45f214-b37e-49fc-997e-bf6c8e58135d)

## 3. Average Price by Car Make
SELECT car_make, ROUND(AVG(price), 2) AS avg_price
FROM updated_car_sales_data
GROUP BY car_make
ORDER BY avg_price DESC;

![Average Price by Car Make](https://github.com/user-attachments/assets/2b1b1648-8d51-42e5-8a26-a62d48f3c1b6)

## 4. Most Common Fuel Types
SELECT fuel_type, COUNT(*) AS count
FROM updated_car_sales_data
GROUP BY fuel_type
ORDER BY count DESC;

![Most Common Fuel Types](https://github.com/user-attachments/assets/f34358bd-1d61-4c9f-a793-49f9b13c5013)

## 5. Distribution of Car Conditions
SELECT `condition`, COUNT(*) AS count
FROM updated_car_sales_data
GROUP BY `condition`
ORDER BY count DESC;

![Distribution of Car Conditions](https://github.com/user-attachments/assets/4e0c2e7f-06ec-44aa-89fb-a2e01f35ad21)

## 6. Average Price by Condition
SELECT `condition`, ROUND(AVG(price), 2) AS avg_price
FROM updated_car_sales_data
GROUP BY `condition`
ORDER BY avg_price DESC;

![Average Price by Condition](https://github.com/user-attachments/assets/a9aa22e5-dd39-4fb1-8d39-97020b3fd106)

## 7. Sales Over the Years
SELECT year, COUNT(*) AS total_sales
FROM updated_car_sales_data
GROUP BY year
ORDER BY year;

![Sales Over the Years](https://github.com/user-attachments/assets/8898782b-6c25-4526-9c09-03e7280e6779)

## 8. Accident History Impact on Pricing
SELECT accident, ROUND(AVG(price), 2) AS avg_price, COUNT(*) AS count
FROM updated_car_sales_data
GROUP BY accident;
![Accident History Impact on Pricing](https://github.com/user-attachments/assets/10f3c72f-ebce-4bca-a4eb-64abde627864)


## 9. Average Mileage by Car Make
SELECT car_make, ROUND(AVG(mileage), 2) AS avg_mileage
FROM updated_car_sales_data
GROUP BY car_make
ORDER BY avg_mileage DESC;
