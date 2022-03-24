# CeFr

## Introduction

CeFr is an automated python pipeline for plate reader data analysis. It is designed to work on SynergyH1 and Cytation3 plate readers. The final output is a dataframe containing a background-corrected, triplicate-averaged columns. It outputs a raw data plot as well as the triplicated averaged plot. One can chose to execute the different functions independently or all together by calling the main function. 

## Implementation

Cefr is available in 2 different formats : python and jupyter notebook. To import it one should download the python file in its working directory or it root python packages folder. One can also dowload directly the notebook containing an example.

## Explaination of the different functions

### 1. Main 
  - Automatic anaysis of yout plate reader data
  - Imputs : 'Name of the file or the path to the file **.xlsx**,the gain you want to use, the number of row you want for the plot, the number of columns for the plot, how the triplicates were done options : 'col' for column (e.g : E2,F2,G2) ; 'line' for in line (e.g E2,E3,E4); 'no' for anything else or if you don't want the wells collapsed ,the location of your control !synthax is as follow : **['E22', 'F22', 'G22']**, wether you want to plot every triplicate in one plot or each triplicate in different plot : 'YES' or 'NO' 

### 2. excelreader:
   - Function to open the **excel** file of the results 
   - Imputs : name of the file **.xlsx** , the gain you want to use (from 50 to 100),  if you want the correction to go back to FITC equivalent type 'Yes' or 'YES'  if you don't want the correction type "NO" 
  
### 3. plot_raw_data:
   - Function to plot the raw data
   - Imputs : the data you want to use (you can call it using the excelreader output) , the number of row for display, the number of columns for display (if the number of conditions is odd you can add one and add a row or a column, it will create a blank plot)
   
### 4. collapse: 
   - Function to collapse the triplicate into one column
   - Imputs : the data (dataframe) , how you made the triplicate either 'line' 'col' or if you did not do triplicate 'no', the position of the control well with only H2O in this synthax : **['I2','I3','I4']**
   
### 5. plot_triplicates
   - Function to plot the mean of all the triplicate 
   - Imputs : the collapsed dataset, if you want the plots in the same axis or not ("YES" or "NO")

### Example of synthax

*main(r'C:/Users/nessl/Documents/M1/S2/Lab 1/Logic gate/cell free/11.03.22 cell free.xlsx',75,"YES",6,8,'col',['E22', 'F22', 'G22'],"YES")*
