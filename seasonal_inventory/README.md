# Seasonal Inventory Model with OR-Tools

This [medium article](https://towardsdatascience.com/a-python-or-tools-model-for-seasonal-inventory-planning-483aaf5aa8b) on the seasonal inventory planning model provides an overview of how to use and build the model with ortools in python.


## How do I run the code?

The models are written in python using jupyter notebook.  
* At the top of the python code is the import for the libraries, which you may need to install if you haven't already.
* Utilize a jupyter notebook to open the `.ipynb` file. There are more details inside the notebook about the formulation, assumptions, and future model enhancements planned.

## Background for the model purpose

Manufacturing facilities may not have the capacity to produce seasonal products within that season. Building additional inventory prior to the season can often be less expensive than buying additional tooling and space.  Here's a few scenarios where that could be the case: 
* If this seasonal product is a substantial part of the manufacturer's business, then scheduling production during the offseason enables leveling out of resources over a longer period of time; this enables the facility to staff full-time workers rather than to rely on a seasonal workforce.  
* Even if the facilities can surge capacity to meet demand, that may result in additional overhead costs, including overtime pay.  The cost of storing prebuilt product in inventory may be less than this added cost.  

When taking the building-before-season approach, there's a few questions to answer:
* What is the quantity of the product to prebuild into inventory before the season starts?
* Assuming the prebuilt inventory will build up over time with a smoothed production plan, when does manufacturing need to start for the prebuild? 

Although a simple model such as this example could be worked out with pen and paper, this model provides a scalable framework to build upon for multiple products amid competing capacity constraints.  

Tags
* Multi-Period-Inventory-Model
* Python
* Optimization
* Google OR-Tools / ortools