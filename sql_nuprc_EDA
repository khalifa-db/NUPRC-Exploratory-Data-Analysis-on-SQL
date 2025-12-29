-- Dataset: NUPRC Monthly Gas Production (2025)
-- Author: Dahiru Bashir

--Which month had the highest gas flaring?--
SELECT 
    top 1 months,
    "total gas flared (mmscf)" total_gas_flared
FROM dbo.nuprcdata01
ORDER BY 2 DESC;

--Total gas flared (wasted) vs utilized--
SELECT
    SUM("total gas flared (mmscf)") AS total_flared_mmscf,
    SUM("total gas utilised (mmscf)") AS total_utilised_mmscf
FROM portfolioproject.dbo.nuprcdata01;

--Total gas emissions factor (total gas flared * flared co2 per metric tonne)--
SELECT distinct
    months,
    "total gas flared (mmscf)",
    "total gas flared (mmscf)" * 53.3 AS co2_emissions_tons
FROM portfolioproject.dbo.nuprcdata01
order by 3 desc;

--Total annual emission for the year 2025--
SELECT
    SUM("total gas flared (mmscf)" * 53.3) AS total_co2_emissions_tons
FROM portfolioproject.dbo.nuprcdata01;

--Which month had the best gas utilization performance--
SELECT
    top 1 months,
    "total gas utilised (mmscf)"
FROM PortfolioProject.dbo.nuprcdata01
ORDER BY "total gas utilised (mmscf)" DESC;


--What percentage of produced gas is actually used? Gas utilized to gas produced ratio--
SELECT
    months,
    ("total gas utilised (mmscf)" / "total gas production (mmscf)") * 100 
        AS recalculated_utilisation_percent
FROM portfolioproject.dbo.nuprcdata01
ORDER BY 2 desc;

--Value of gas flared per month (USD)--
SELECT
    months,
   "total gas flared (mmscf)",
    "total gas flared (mmscf)" * 4070 AS value_of_gas_flared_usd
FROM PortfolioProject.dbo.nuprcdata01
ORDER BY 3 desc;

--Total value of gas flared for the year--
SELECT 
      SUM("total gas flared (mmscf)") * 4070 as total_value_of_gas_flared
      FROM PortfolioProject.dbo.nuprcdata01

 --Value of gas shrinkage per month (USD)--
SELECT
    months,
   "GAS SHRINKAGE" AS value_of_gas_shrinkage
FROM PortfolioProject.dbo.nuprcdata01
ORDER BY 2 desc;


--Total value of gas shrinkage for the year--
SELECT
   sum("GAS SHRINKAGE") * 4070 AS total_value_of_gas_shrinkage
FROM PortfolioProject.dbo.nuprcdata01;
