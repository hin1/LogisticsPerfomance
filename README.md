# Shopee Code League 2020: Logistics

## Introduction

This is a submission for the Logistics competition hosted by Shopee Code League 2020 on Kaggle. 

## How it works

### Input
* `delivery_orders_march.csv` -  Shows order details such as ID, pickup and delivery locations and dates by logistics providers.
* `SLA_matrix.xlsx` - A matrix that shows the stipulated number of working days required by the Service Level Agreement (SLA) to be delivered.

### Output
* `output.csv` - Two columns with the order IDs and if their corresponding orders were late.

### Details

#### Working days
Working days exclude Sundays and a given set of public holidays. This part was greatly simplified by the `busdays_count()` function in Numpy, in calculating the number of actual working days taken for the range of dates between pickup to the first delivery dates, or between dates.

#### Delivery attempts
A maximum of two delivery attempts are given for each order, in case the first delivery attempt did not go through. The required number of working days is 3 for the second delivery attempt.

#### Late condition
An order is considered late when either the first or second delivery (if it exists) is late.