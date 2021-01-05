# python_optimization
Models utilizing python optimization packages

# What is in the python_optimization project and what are they? 

Currently there is one model in the python_optimization project: 
PuLP_OregonCongressionalApportionment.ipynb

This model is a knapsack optimization problem with the goal to assign 36 Oregon counties to 6 congressional districts based on population. This process is part of congressional apportionment after each US Census that occurs at the start of a decade.

This is a complex problem, and enhancements will be periodically added to the model.  

Utilize jupyter notebook to open the ".ipynb" file.  There are more details inside the notebook about the formulation, assumptions, and future model enhancements planned.

# Why/History

The main purpose of this model is to explore non-partisan ways of Oregon congressional districting after the congressional apportionment of 2021.  Since it is likely that Oregon will receive one additional congressional district this time, the changes to the districts will likely be greater than in most decades.  

The objective and constraints will not include any partisan data, such as voter registration by political party offiliation or details down to the census tract.  Instead, the model will be based on population data alone and counties- which each have a county elections board- will be kept as whole as possible to simplify elections reporting.  Although this model is intended to drive the high-level conversation before getting deep into census tract discussions, there are many complexities to appreciate at the high level.  And one can argue that the most value of non-partisan conversations can be had at the high level.

While complex mathematical models developed by researchers to fairly (or alternatively partisanly) define congressional districts exist, those models are not easy to utilize for the average discussion.

Brown University researchers have made public the complex python code of a fair model that is not gerrymandered for the political gain of any particular political party. However, this model does not retain county borders and may not be an easy sell due to the large amount of change that creates.  (http://district.cs.brown.edu/)

Partisan models are typically not made public.


## Want to know more or see a quick summary?

A PDF summary will be created soon, after some additional model enhancements.

Census.gov webpage with information on the congressional apportionment after the 2010 censuse: 
https://www.census.gov/data/tables/2010/dec/2010-apportionment-data.html


# How do I run the code?

Utilize a jupyter notebook to open the ".ipynb" file.  There are more details inside the notebook about the formulation, assumptions, and future model enhancements planned.