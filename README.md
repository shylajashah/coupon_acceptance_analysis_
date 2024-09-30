# Analysis of the coupon acceptance rate
## Problem Statement 
The problem statement is to find out the characteristics of customers accepting a coupon delivered to them on their phone while they are driving in town, versus those customers not accepting. The analysis is based on data available from UCI Machine Learning repository that was collected via a survey on Amazon Mechanical Turk. 

## Data 
The data is from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes the likelihood of a driver choosing to accept a coupon offered to them. The coupons are of five different types - less expensive restaurants (under 20), coffee houses, carry out & take away, bar, and more expensive restaurants (20 - $50). Different driving scenarios are offered, including the destination, current time, weather, passenger, etc., and the survey then asked the person whether they will accept the coupon if they were the driver. Acceptance of coupon for use ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’. 

## Data Summary
- The dataset has 12684 rows and 26 columns. 
- The column "car" has over 99% of its values empty(null). This makes this column ineffective for analysis and is removed.
- 5 other columns have under 1% of their values. That is a small percent. These are also categorical attributes. So, replacing the nulls would mean filling with the most common category. That does not add much value. Hence, keeping the nulls as is.
- Numeric columns have values that are valid, and categorical entries match their individual group names.
- The only column name changed was to correct the spelling on "passenger" column.

## Exploratory Data Analysis 
Looking at the overall dataset, 57% of drivers accepted the offered coupons. The distribution of drivers by age is a normal distrbution (assuming 50plus is tail with multiple ages). Sunny weather increases the likelihood of accepting. While mid day is more popular in Sunny weather, morning is prefered in Snowy weather for saying a Yes. **More promotion should be done in Sunny weather**.<img width="593" alt="Screenshot 2024-09-30 at 11 16 51 AM" src="https://github.com/user-attachments/assets/52e36b6a-03dc-4d9a-b7d8-2ee72cd255b5">

Considering just coupons for Bar businesses, the following conclusions can be drawn. The acceptance rate for Bar coupons is lower than overall proportion (41% copared to 57%). If the drivers have greater than 3 visits per month to a bar, they are more likely to accept the coupon. **Focus on drivers who have higher visit to bar per month**. <img width="642" alt="Screenshot 2024-09-30 at 11 14 12 AM" src="https://github.com/user-attachments/assets/73b8f993-eb79-4c98-b0f0-a5a26968f575">

Drivers who go to a bar more than once a month and are above the age 25 also have higher rate of acceptance(71%) than under 25(65%). Especially, 21-30 year olds have the highest acceptance rate. - **Focus on drivers between 21 and 30 years**. 
<img width="640" alt="Screenshot 2024-09-30 at 11 12 52 AM" src="https://github.com/user-attachments/assets/716b0df7-626a-43d4-95fd-00ea71b779fe">

Drivers with no kids and not Widowed also have high acceptance rate 71% - **Focus on drivers when they are not traveling with their kids**. Considering the income level and preferance for other businesses, drivers who visit cheap restaurants more and have low income are very less likely to accept the coupon - **Focus on greater than 50k income and drivers who do not frequent cheap restaurants more than 4 times a month**. 


Similar to the analysis above for coupon for Bar, the driver attributes accepting coupons for "Carry out & Take away" was analyzed. The carry away behavior per month does not have any conclusive relation to driver behavior in accepting the coupon. Drivers with Less than 1 visit per month have the lowest acceptance, but their is no apparent trend on visits per month on acceptance. Acceptance rate for all Carry out & Take away coupons are higher than average in the late afternoon/evening times. Drivers with kids in the car are most likely to accept coupon around 6PM, followed by morning time. Lowest for this group is late nights. Drivers alone are more likely to accept coupon late evening/night or around 10AM, irrespective of expiration. They are least likely to accept early morning(7AM). **Target the time of day to late afternoon/evening unless they are traveling alone, in which case they are highly likely to accept in the morning.**
<img width="751" alt="Screenshot 2024-09-30 at 11 10 40 AM" src="https://github.com/user-attachments/assets/9eac8a16-84bd-4c9a-abfd-da2c8bf77a31">

Overall, there are a lot of factors that go into determining high acceptance rate of coupon. Sunny weather and late afternoon has highest acceptance overall. Higher income, tendency towards higher visits to a business type, improves chances of acceptance to that category. Age, passenger also are a factor. Further analysis needs to be done on dependency of distances from businesses and other demographics factors of the driver.
