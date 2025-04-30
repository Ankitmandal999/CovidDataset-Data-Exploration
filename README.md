# COVID 19 Data Exploration using SQL

## Project Overview
This project involves SQL-based analysis for COVID-19 data exploration. It includes setting up a database with COVID-19 data, performing CRUD operations, and executing advanced SQL queries. The goal is to analyze trends, track cases, and extract insights from the data to understand the pandemic's impact.

```sql

Select*
from PortfolioProject..CovidDeaths
order by 3,4

--Select data that we are going to use

Select location,date,total_cases,new_cases,total_deaths,population
from PortfolioProject..CovidDeaths
order by 1,2

--looking at total cases Vs total deaths
--shows likelihood of dying if you are living in India

Select location,date,total_cases,total_deaths,(total_deaths/total_cases)*100 as DeathPercentage
from PortfolioProject..CovidDeaths
where location like '%India%'
order by 1,2

--Looking at toal cases vs population
--Shows what % of people got Covid

Select location,date,total_cases,population,(total_cases/population)*100 as Infection_Percentage
from PortfolioProject..CovidDeaths
where location like '%India%'
order by 1,2
