# Fitting Poisson  distribution
# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Experiment :

![image](https://user-images.githubusercontent.com/103921593/230282876-f4a5afbf-cac1-4648-a1b0-c78840638a8e.png)

# Program :

import math

from scipy.stats import chi2


x = [0, 1, 2, 3, 4, 5, 6, 7]  # Observed values (x)

obs_freq = [10, 8, 7, 6, 5, 3, 1, 0]  # Observed frequency

exp_freq = [10.43, 8.78, 7.39, 6.22, 5.23, 4.39, 3.66, 3.56]  # Expected frequency



chi_square = sum([(o - e) ** 2 / e for o, e in zip(obs_freq, exp_freq)])

print(f"Calculated Chi-square value: {chi_square:.2f}")

df = len(x) - 1  # Degrees of freedom

critical_value = chi2.ppf(0.99, df)

print(f"Critical Chi-square value (1% LOS, df={df}): {critical_value:.2f}")

if chi_square < critical_value:
 
    print("The given data can be fitted in Poisson Distribution at 1% LOS.")

else:

    print("The given data cannot be fitted in Poisson Distribution at 1% LOS.")
 

# Output : 

Calculated Chi-square value: 6.06

Critical Chi-square value (1% LOS, df=7): 18.48

The given data can be fitted in Poisson Distribution at 1% LOS.

# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
