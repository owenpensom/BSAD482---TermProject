# BSAD 482 Term Project – COVID Recovery in Canada

---

## 📚 Table of Contents

1. [Executive Summary](#executive-summary)  
2. [Key Performance Indicators (KPIs)](#key-performance-indicators-kpis)  
3. [Introduction](#1-introduction)  
4. [Research Objective](#2-research-objective)  
5. [Exploratory Data Analysis](#3-exploratory-data-analysis)  
    - [Mobility Trends](#a-mobility-trends)  
    - [Healthcare Spending](#b-healthcare-spending)  
    - [Unemployment](#c-unemployment)  
    - [Vaccination and Recovery](#d-vaccination-and-recovery)  
6. [Statistical Analysis](#4-statistical-analysis)  
    - [Model Explanation](#a-model-explanation)  
    - [Results](#b-results)  
7. [Discussion](#5-discussion)

---

### **Executive Summary**

The goal and project analyses and evaluates how Canada recovered from the COVID-19 pandemic with regards to socioeconomic factors. The key drivers of our analysis will be economic trends, public health, and finally mobility indicators. We will be using trusted statistical organizations to gather our data, from platforms like statistics canada, google mobility reports, and the world bank. The goal of the analysis of this data will allow us to determine common trends, measure progress, and show the similarities and differences of recovery between different geographic regions. We aim to use a combination of statistical analysis and data manipulation/visualization to allow policymakers and stakeholders to have further insights and understanding. Through this approach, we will be able to evaluate and comprehend the long and short term impacts that the COVID-19 pandemic had on canada.

---

### **Key Performance Indicators (KPIs)**

1. #### **Vaccination Rates**
   * Tracks the percentage of the population vaccinated over time.  
   * Target: Achieve 90% full vaccination coverage across all provinces, the current national average of 85%.  
   * Monthly updates from public health agencies.
     ![image](https://github.com/user-attachments/assets/dd9b0631-d547-4306-ad13-012eb694116e)
     The line chart on vaccination rates shows a strong upward trend across provinces, with most nearing or surpassing the 90% full vaccination target by late 2023. The red dashed line emphasizes the national goal, allowing clear visual comparison of provincial progress. While some provinces like Yukon exceeded expectations early, others lagged slightly, highlighting regional discrepancies in vaccine rollout and uptake over time.


2. #### **Mobility Recovery Index**
   * Measures the return to pre-pandemic activity levels across workplaces, retail, and residential organizations/companies.  
   * Target: Reach pre-pandemic mobility levels in all regions.  
   * Weekly updates using Google Mobility Reports.
  ![image](https://github.com/user-attachments/assets/51397ff7-2d7a-44e0-afe7-6f37a4889edd)
The mobility recovery chart tracks weekly activity across provinces, reflecting public movement trends in response to restrictions and recovery phases. Peaks in early 2020 suggest initial resilience, but sharp declines followed, with prolonged stagnation across most regions. Some provinces, like British Columbia, showed stronger rebounds, while others remained below pre-pandemic levels. The inconsistent recovery patterns suggest varying provincial policies, economic conditions, and public sentiment toward reopening efforts.


3. #### **Unemployment Rate Trends**
   * Continuously watching the changes in unemployment rates to evaluate how our economy has recovered.  
   * Target: Reduce unemployment to pre-pandemic levels, the current national unemployment rate is 7.5%.  
   * Monthly reporting from Statistics Canada.
  ![image (1)](https://github.com/user-attachments/assets/c2756b2b-6ab1-4d90-b3e9-1a0f16c96408)
The unemployment rate graph shows the sharp impact of the pandemic, with rates spiking above 14% in early 2020. A steady decline follows, reaching near pre-pandemic levels by 2022. However, the rate begins rising again by 2024, reaching 7%, still above the target of 6.5%. This suggests a partial economic recovery that has since stalled, possibly due to shifting labor market dynamics or slower-than-expected economic growth.

4. #### **Public Health Spending Changes**
   * Evaluating and understanding the provincial-level spending on healthcare during the pandemic and its impact on recovery.  
   * Target: Increase the healthcare spending growth of at least 5% in regions that are not receiving fair resources, the current average growth of 3.8%.  
   * Annual evaluation through provincial budget reports.
     ![image](https://github.com/user-attachments/assets/00721ba3-3691-4a8f-9ebc-01013c06ae8a)
This area chart illustrates provincial trends in public health spending from 2020 to 2024. While most provinces increased healthcare budgets significantly during the pandemic, only a few sustained spending growth rates beyond the 5% target post-2022. The chart also reveals disparities, with provinces like Ontario and Quebec allocating substantially more than northern territories. This suggests ongoing inequities in healthcare funding distribution and resource access.

5. #### **Economic Recovery Index**
   * Combines Canada’s GDP growth and unemployment rates and trends to evaluate overall recovery of the economy.  
   * Achieve a GDP growth rate of at least 2.5% annually while maintaining an unemployment rate below 6.5%.  
   * Quarterly assessments using Statistics Canada and the World Bank data.
![image](https://github.com/user-attachments/assets/1e0c6923-8665-4212-9bee-9c5ce20b15d9)
The dual-axis chart comparing GDP growth and unemployment rates reveals the complex interplay between economic performance and labor recovery. Years with high GDP growth generally align with lower unemployment, as seen in the early 2000s and post-2010. However, the COVID-19 disruption in 2020 shows a sharp GDP contraction alongside unemployment spikes. While GDP rebounded, unemployment recovery has lagged, signaling an incomplete and uneven economic recovery.
     
## 1. Introduction

This project investigates the socioeconomic impact of the COVID-19 pandemic across Canadian provinces, with a focus on mobility patterns, healthcare spending, unemployment trends, and vaccination efforts. The motivation behind this research stems from a desire to better understand the varying provincial responses and recovery trajectories, and how key public health and economic indicators intersected during this unprecedented period.

---

## 2. Research Objective

The primary objective is to explore the relationship between public health interventions—such as vaccination campaigns—and economic indicators like unemployment and mobility. This analysis aims to identify patterns that may inform more effective policy responses in future health crises, with a particular focus on causal relationships that can be quantified and tested.

---

## 3. Exploratory Data Analysis

A multi-faceted EDA was conducted to uncover trends across four domains:

### (a) Mobility Trends

Using data from Google's COVID-19 Community Mobility Reports, this section tracks how movement patterns changed in response to lockdowns and public health mandates. Key observations include dramatic decreases in retail and recreation mobility in early 2020, with varying rates of recovery across provinces.

### (b) Healthcare Spending

Provincial healthcare expenditure data was examined to understand shifts in funding priorities during the pandemic. Some provinces saw substantial increases in emergency spending, particularly related to vaccine distribution and hospital capacity.

### (c) Unemployment

Unemployment rates surged during initial lockdowns but showed uneven recovery across regions. Analysis includes pre- and post-pandemic comparisons, highlighting sectors most affected and the pace at which employment rebounded.

### (d) Vaccination and Recovery

This section analyzes the correlation between vaccine rollout rates and economic recovery metrics. Provinces with faster and broader vaccination coverage generally experienced quicker rebounds in mobility and employment.

---

## 4. Statistical Analysis

### (a) Model Explanation

![image](https://github.com/user-attachments/assets/6f4d0d8f-189b-49ca-bf8d-d1d07dcbeaab)
To explore relationships between public health and economic indicators during the COVID-19 recovery, a correlation heatmap was created. This helped identify key variables that might be causally linked. In particular, `percent_fully_vaccinated` showed a moderate negative correlation with unemployment (–0.49), suggesting that provinces with higher vaccination rates tended to have lower unemployment. These patterns informed variable selection for the causal model and highlighted potential confounders like healthcare spending.

### (b) Results

The causal model estimates that a 1% increase in full vaccination rates leads to a 0.043% decrease in unemployment**, on average. This effect remained stable across two refutation tests, confirming that the result is not likely due to random variation or unobserved confounders. Overall, the analysis supports the idea that vaccination played a meaningful role in economic recovery.

---

## 5. Discussion

These findings illustrate the interconnectedness of public health and economic resilience. While the analysis confirms some expected relationships, it also reveals gaps in recovery and challenges in uniform policy implementation. Limitations include potential unobserved variables and data lags. Nonetheless, the results offer valuable insights for policymakers planning future crisis responses, particularly in aligning health and economic strategies.


---


### 📁 Project Structure

- `src/` – Notebooks and Markdown files  
- `data/raw/` – Original datasets  
- `data/cleaned/` – Processed data used for analysis  
- `img/` – All charts and visualizations
