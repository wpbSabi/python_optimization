# Facility Location Model

Sabi Horvat, March 2021

## Overview

The model chooses N facilities from a set of available facility locations to minimize total cost and allocates products to customers from those facilities.

## Data

The data in the model currently is simple.  Three customer nodes and seven potential distribution center nodes.  Each node also has geographic data which is not shown here for brevity.

![customers](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/Customers.png)

![DCs](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/Distribution_Centers.png)

## Model Formulation 

### Decision Variables

![dvs](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/decision_variables.png)

### Objective Function

- **Minimize the planned cost**.  Planned cost includes the fixed cost of setup and the variable cost of shipping products from the Distribution Center to Customers.

![obj](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/objective.png)

### Constraints

- **Fulfill Customer Demand**: Customers to receive allocation from the distribution centers in the amount of the planned demand.

![c1](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/constraint1.png)

- **Only allocate products to Open Distribution Centers**: A modeling constraint to ensure closed distribution centers do not ship products.  The big M is set to the sum of all customer demand.

![c2](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/constraint2.png)

- **Distribution Centers Capacity**: Each Distribution Center has a limited capacity based on these planning decisions.
![c3](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/constraint3.png)

### Results

The results show that the three customers were allocated to four distribution centers, based on the capacity available and shipping costs (in this case the shipping cost was directly related to straight-line distance).

![results_table](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/results_table.png)

This map is created with Folium and is interactive within the notebook, although all current features are visible in the image. 

![results_map](https://github.com/wpbSabi/python_optimization/blob/main/facility_location/images/Result.png)

