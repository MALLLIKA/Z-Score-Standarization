# Import packages
import numpy as np
import pandas as pd
from scipy import stats
# Import matplotlib pyplot
from matplotlib import pyplot as plt

# Read in housing data
brooklyn_one_bed = pd.read_csv('brooklyn-one-bed.csv')
brooklyn_price = brooklyn_one_bed['rent']

manhattan_one_bed = pd.read_csv('manhattan-one-bed.csv')
manhattan_price = manhattan_one_bed['rent']

queens_one_bed = pd.read_csv('queens-one-bed.csv')
queens_price = queens_one_bed['rent']

# Add mean calculations below 
brooklyn_mean=np.average(brooklyn_price)
manhattan_mean=np.average(manhattan_price)
queens_mean=np.average(queens_price)
# Add median calculations below
brooklyn_median=np.median(brooklyn_price)
manhattan_median=np.median(manhattan_price)
queens_median=np.median(queens_price)


# Add mode calculations below


brooklyn_mode=stats.mode(brooklyn_price)
manhattan_mode=stats.mode(manhattan_price)
queens_mode=stats.mode(queens_price)


# Mean
try:
    print("The mean price in Brooklyn is " + str(round(brooklyn_mean, 2)))
except NameError:
    print("The mean price in Brooklyn is not yet defined.")
try:
    print("The mean price in Manhattan is " + str(round(manhattan_mean, 2)))
except NameError:
    print("The mean in Manhattan is not yet defined.")
try:
    print("The mean price in Queens is " + str(round(queens_mean, 2)))
except NameError:
    print("The mean price in Queens is not yet defined.")
    
    
# Median
try:
    print("The median price in Brooklyn is " + str(brooklyn_median))
except NameError:
    print("The median price in Brooklyn is not yet defined.")
try:
    print("The median price in Manhattan is " + str(manhattan_median))
except NameError:
    print("The median price in Manhattan is not yet defined.")
try:
    print("The median price in Queens is " + str(queens_median))
except NameError:
    print("The median price in Queens is not yet defined.")
    
    
#Mode
try:
    print("The mode price in Brooklyn is " + str(brooklyn_mode[0][0]) + " and it appears " + str(brooklyn_mode[1][0]) + " times out of " + str(len(brooklyn_price)))
except NameError:
    print("The mode price in Brooklyn is not yet defined.")
try:
    print("The mode price in Manhattan is " + str(manhattan_mode[0][0]) + " and it appears " + str(manhattan_mode[1][0]) + " times out of " + str(len(manhattan_price)))
except NameError:
    print("The mode price in Manhattan is not yet defined.")
try:
    print("The mode price in Queens is " + str(queens_mode[0][0]) + " and it appears " + str(queens_mode[1][0]) + " times out of " + str(len(queens_price)))
except NameError:
    print("The mode price in Queens is not yet defined.")
#Histogram for Manhattan
plt.hist(brooklyn_price, range=(1000, 8000),   bins=14,  edgecolor='black')
plt.title("Brroklyn 1BHK prices at NYC")
plt.xlabel("brooklyn_price")
plt.ylabel("Count")
plt.axvline(brooklyn_mean, color='r', linestyle='solid', linewidth=3, label="Mean")
plt.axvline(brooklyn_median, color='y', linestyle='dotted', linewidth=3, label="Median")
#plt.axvline(brooklyn_mode, color='orange', #linestyle='dashed', linewidth=3, #label="Mode")
plt.legend()
 
plt.show()

![](images/github-histogram.png)
