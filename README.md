# Car_Sales_Analysis
Car Sales Insights with SQL
## 1. Correct column names
ALTER TABLE updated_car_sales_data
CHANGE `Car Make` car_make VARCHAR (100),
CHANGE `Car Model` car_model VARCHAR (100),
CHANGE `Fuel Type` fuel_type VARCHAR (100),
CHANGE `Options/Features` options_features VARCHAR (100);

## 2. Top 10 Car Makes by Number of Sales
SELECT car_make, COUNT(*) AS total_sales
FROM updated_car_sales_data
GROUP BY car_make
ORDER BY total_sales DESC
LIMIT 10;

## 3. Average Price by Car Make
SELECT car_make, ROUND(AVG(price), 2) AS avg_price
FROM updated_car_sales_data
GROUP BY car_make
ORDER BY avg_price DESC;

## 4. Most Common Fuel Types
SELECT fuel_type, COUNT(*) AS count
FROM updated_car_sales_data
GROUP BY fuel_type
ORDER BY count DESC;

## 5. Distribution of Car Conditions
SELECT `condition`, COUNT(*) AS count
FROM updated_car_sales_data
GROUP BY `condition`
ORDER BY count DESC;

## 6. Average Price by Condition
SELECT `condition`, ROUND(AVG(price), 2) AS avg_price
FROM updated_car_sales_data
GROUP BY `condition`
ORDER BY avg_price DESC;

## 7. Sales Over the Years
SELECT year, COUNT(*) AS total_sales
FROM updated_car_sales_data
GROUP BY year
ORDER BY year;

## 8. Accident History Impact on Pricing
SELECT accident, ROUND(AVG(price), 2) AS avg_price, COUNT(*) AS count
FROM updated_car_sales_data
GROUP BY accident;

## 9. Average Mileage by Car Make
SELECT car_make, ROUND(AVG(mileage), 2) AS avg_mileage
FROM updated_car_sales_data
GROUP BY car_make
ORDER BY avg_mileage DESC;
