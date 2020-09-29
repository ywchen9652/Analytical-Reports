# Solar Energy Analysis
Solar Energy Analysis

Case Overview

Develop and analyze a simulation model of solar power generation and electricity costs.
Recall that one way to view analytics is in terms of three broad categories: preparation,
description/prediction, and prescription. This case involves all three categories, though the data
preparation element is relatively minor.

The goal is to reinforce your skills in (1) developing predictive models from data, (2) designing and
implementing a relatively complex simulation model, (3) conducting analysis of your model to identify
prescriptions (i.e., guidance for a decision maker). The case assignment can be divided into three main
steps. 

1. Predictive models of kWh demand and production.

a. Demand model. In general, the demand model (to be estimated from the data) specifies the
probability distribution of kWh demand for each hour in a year. But it is not reasonable to define
a different probability distribution for each of the 8760 hours in a year. Instead, your team will
conduct two-level hierarchical clustering: clustering days within a year, then clustering hours
within a day. Your predictive demand model will specify a probability distribution of demand for
each cluster.

In order keep time requirements of this case assignment reasonable, the top-level clusters are
specified for you: each cluster is a month and each month has a demand factor to be
estimated/predicted. The demand factor for a month (aka, seasonal index) is the predicted average
24-hour demand in a month as a percent of the “average” month. For example, a month with a
demand factor of 1.2 means that daily demand in the month averages 20% more than demand in
the “average” month. To be correct, the average of the 12 monthly demand factors should equal
1.0.

b. Production model. In general, the production model (to be estimated from the data) specifies the
probability distribution of solar panel kWh production for each hour in a year. kWh production is
a straight-forward function of number of solar panels, capacity per panel under full sunlight, and
fraction of full sunlight in an hour. The capacity is provided by the solar panel vendor and the
number of panels is a value that you may specify and experiment with. The only predictive
element of the production model pertains to fraction of full sunlight in an hour. For example,
suppose the solar panel capacity is 0.2 kWh. There is no solar production during nighttime hours,
an hour of full sun generates 0.2 kWh, and to keep things simple, you may assume that the panel
generates 0.08 kWh under 60% cloud cover (i.e., 0.40  0.20 = 0.08) (and no power is generated
under 100% cloud cover).
Similar to the demand model, you will identify the probability distribution of fraction of full
sunlight in an hour for different clusters, though in this case, the clusters are fully specified so
that you may spend time on other aspects of the project (12 clusters corresponding to months).
Data on daylight hours and Phoenix area cloud cover over a year are available. Additional detail
on production model clusters are provided in Section 3 below. 

2. Measure of performance.

Your team will develop a cost model. This model that maps kWh demand,
number of solar panels, kWh solar production, and electricity rate structure into cost. You will use
this model to estimate the probability distribution of annual electricity cost under different scenarios
(e.g., number of solar panels, rate structure), which serves as the foundation for prescriptive analysis
described below.
The electricity rate structure includes both charges and credits. A credit accrues when kWh
production is greater than demand (i.e., known as net metering). A charge occurs when kWh demand
is greater than production, which is offset by any accumulated credit. Your model is designed to
accommodate a multi-rate structure that arises in practice. In particular, your model allows up to five
charge rates (i.e., on-peak-winter, on-peak summer, off-peak winter, off-peak summer, super off-peak
winter). By designing your model to include parameters that define when each rate category applies,
you will have the flexibility cover fewer than five rate categories as well as different time intervals
when a particular rate category applies. (APS is known to periodically change the rate structures, and
you can easily examine the effect of a change.) 

3. Prescriptive analysis of your model.

Limit your model to a one-year time frame. The overall goal of your
analysis is to gain an understanding of the relationship between various inputs (e.g., number of solar
panels, how the credit rate compares to the charge rates, how the clusters of low, mid, and high
demand compare to the time intervals that different charge rates are in effect) and a key output: 
probability distribution of the percentage reduction in annual electricity bill from solar panels, and
especially its associated summary statistics – mean and standard deviation.




