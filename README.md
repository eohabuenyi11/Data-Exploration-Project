# Data-Exploration-Project
Final Project on SQL as Part of Data Analysis class with Udacity/Masterschool 
/*
--CREATING VIEW
*/
CREATE VIEW deforestaion AS (
  SELECT f.country_code, f.year,  f.forest_area_sqkm, l.country_name, l.total_area_sq_mi,   	l.total_area_sq_mi*2.59 AS total_area_sqkm, r.region, r.income_group,  f.forest_area_sqkm/(l.total_area_sq_mi*2.59)*100  AS  land_forest_area_per 
    FROM forest_area f
    JOIN land_area l
    ON f.country_code = l.country_code AND f.year = l.year
    JOIN regions r 
    ON f.country_code = r.country_code);
