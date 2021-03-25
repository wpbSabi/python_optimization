
# Oregon Congressional Districting based on the 2020 Census

*-Updates will be made after the 2020 Census is released.  The model is currently based on 2018 estimates*

Oregon might receive a new Congressional District after the 2020 US Census.  Pew Research Center wrote an [article](https://www.pewresearch.org/fact-tank/2018/05/31/u-s-population-keeps-growing-but-house-of-representatives-is-same-size-as-in-taft-era/) which visualized that Oregon was one of the states closest to adding a district in 2010.  Since then Oregon's population grew by an estimated 9%, outpacing the US population's 6% growth, it is likely that the 2020s will be the decade that Oregon receives the new district.

![Pew Research Center Image](https://github.com/wpbSabi/python_optimization/blob/main/oregon_districts/FT_18.05.18_RepresentationRatios_states.png)

It's been about 50 years since Oregon has had a change in its number of districts ([Wikipedia](https://en.wikipedia.org/wiki/Oregon's_congressional_districts)), and it's interesting to ponder what a new district would look like. Will the new district significantly impact the current district shapes or rather be absorbed without significant changes to the existing districts?

This model will answer the following questions through mathematical modeling and geo-visualizations.
* How has the population changed over the past decade since the previous census in 2010? 
* How might the Congressional District map be redrawn?


## The Optimization Model

The goal of the model is to assign 36 Oregon counties to 6 congressional districts based on population. This process is part of congressional apportionment, which occurs at the start of each decade after the US Census.

To open the python model, utilize Jupyter Notebook to read the ".ipynb" the code and additional explanations.  There are more details inside the notebook about the formulation, assumptions, and any future model enhancements planned.

The optimization model's decision variables assign counties to districts and then allocate county populations to those districts.  This ensures that all counties (and population) are assigned to districts mathematically.  This also enables objectives and constraints that will formulate solutions based on population, district contiguity, and preservation of county boundaries. 

![decision_variables_objective](https://github.com/wpbSabi/house_ducks/blob/master/dv_obj.png)
![constraints](https://github.com/wpbSabi/house_ducks/blob/master/constr.png)


## Exploratory Data Analysis

The exploratory data analysis explores the population growth in Oregon to better understand whether the change was distributed evenly among counties or whether certain regions experienced more growth than other regions.

![Population 2018](https://github.com/wpbSabi/python_optimization/blob/main/oregon_districts/images/Population2018.png)

Oregon's five most populated counties contain 60% of the state population:
1. Multnomah County contains the largest city (Portland) and 4th largest city (Gresham) in the east Portland metro.
2. Washington County contains the 5th (Hillsboro) and 6th (Beaverton) largest cities in the west Portland metro.
3. Clackamas County holds much of its population in the southeast Portland metro.
4. Lane County contains Oregon's 3rd largest city (Eugene).
5. Marion County contains Oregon's 2nd largest city and capital (Salem).

![Population Change](https://github.com/wpbSabi/python_optimization/blob/main/oregon_districts/images/PopulationChange.png)

The largest population changes by county occurred in the most populous counties.  In addition the previously named counties, Deschutes County (7th most populous), experience the 4th highest gain in population. Jackson County in southern Oregon also experienced notable growth.


## Model Results 

Before exploring the model results, let's review the current Oregon District map, which contains five districts.

![Oregon's 5 Districts](https://github.com/wpbSabi/python_optimization/blob/main/oregon_districts/Oregon_Congressional_Districts%2C_113th.png)

The first model results:
* Create a 6th district in the grey region below.  The grey region contains populous counties that were split into two districts each, while also creating a 6th district.
* Chooses two districts along the Pacific Ocean coast instead of three.
* Shifts the distric that is no longer borders the coast to include Deschutes county, a growing county on the east side of the Cascade Mountain Range.

![Model Result Population Label](https://github.com/wpbSabi/python_optimization/blob/main/oregon_districts/images/SecondPass.png)

![Model Result County Label](https://github.com/wpbSabi/python_optimization/blob/main/oregon_districts/images/SecondPassCountyLabels.png)

Further models will be created soon, utilizing different seeds and another open source solver.
* Running the model with the GLPK solver rather than the CBC solver did find a one of the other optimial solutions (which chooses the minimum number of assignements), but the result was very similar to the CBC solver.
* TBD : tightening the population difference constraint among counties


## Want to know more about Congressional Apportionment?

Census.gov webpage with information on the congressional apportionment after the 2010 censuse: 
https://www.census.gov/data/tables/2010/dec/2010-apportionment-data.html


## When will the 2020 Census data be available?

As of March 2021, it is projected that the 2020 Census data will be available in September or October of 2021.


## How do I run the code?

Utilize a jupyter notebook to open the ".ipynb" file.  There are more details inside the notebook about the formulation, assumptions, and future model enhancements planned.
