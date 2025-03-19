# Implied Spot FX Analysis Tool
## Overview
This project entails the creation of a currency analysis tool centered on purchasing power parity (PPP) and implied exchange rates. The tool utilizes financial data from Bloomberg to examine currency trends and inflation differentials between countries.

## Key Features
### Data Retrieval: 
Utilizes Bloomberg APIs to fetch FX and inflation data.

### Implicit FX Rate Calculation: 
Calculates implied FX rates based on inflation differentials.

### Data Management: 
Employs a structured class-based approach to manage currency data and calculations.

### Visualization and Analysis: 
Generates summary statistics and visualizations to compare real spot FX rates with implied rates.

![thumbnail](https://github.com/user-attachments/assets/ef92f9aa-3f7e-4146-a065-d3548fd515dd)

![image](https://github.com/user-attachments/assets/b6c93630-badd-4968-a734-3bacb1b03eea)
Beyond calculating the implied PPP spot rate, one can derive the opportunity cost and likelihood of realizing a return investing in the local short term rate over the short term US rate (overnight) given the deviation of the current realized spot FX rate relative to its implied value.

### Flexibility: 
Offers flexible date range selection and grouping options.

## Technical Details
### Libraries Used: 
The project relies on Python libraries such as pandas, numpy, and xbbg for data manipulation and Bloomberg API interactions.

### Data Processing: 
Handles data resampling, percentage change calculations, and cumulative product computations for inflation indices.

### Error Handling: 
Includes error handling for unsupported currencies.

### Project Structure:
The tool is organized around a core class that encapsulates currency data and implicit FX rate calculations. It also includes functions for data retrieval, inflation index construction, and comparison of real and implied FX rates.

