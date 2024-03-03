# Minimim Cost Flow

To Run, launch a jupyter notebook and open `Minimum Cost Flow for Transportation Lanes.ipynb`.

## About Minimum Cost Flow Models 

What does this model do?  In summary, the model chooses transportation lanes from a number of options.  In practice, the data for these options is changing at least on a quarterly basis due to the following reasons.

* Contracts with the suppliers that manufacture these products expire and require periodic renegotiation. 
* Transportation costs from third party logistics (3PLs) fluctuate depending on fuel prices and other costs, but also due to shifting demand and supply.  One example is when a truck delivers products to an area where there is not also product to load upon a return trip.  When the 3PL can't coordinate for the truck to be highly utilized, such as in this situation, the truck is being paid to "deadhead" back empty or at other times at less than a Full TruckLoad (FTL).  These cost differences account for the increase in price for the quote you receive, compared to other destinations.

Additional python formulations of Minimum Cost Flow models can be found at: 
* [COIN-OR / PuLP (github) - American Steel Problem](https://github.com/coin-or/pulp/blob/master/examples/AmericanSteelProblem.py)
* [github-alerera - MCNF Timespace Problem](https://github.com/alerera/logistics-opt-python/blob/master/pulp/mcnf_timespace.py)
* [Gurobi-github - General Landing Page for Multiple Problems ](https://gurobi.github.io/modeling-examples/)

## Result

The resulting model shows the minimum cost flow solution among Origins and Destination.
* i.e. The Origins with the lowest cost are chosen to satisfy the demand for each Destination

![Min Cost Flow](https://github.com/wpbSabi/python_optimization/blob/main/minimum_cost_flow/images/folium_map.png)

