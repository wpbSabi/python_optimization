# Facility Location Model

Sabi Horvat, March 2021

## Overview

The model chooses N facilities from a set of available facility locations to minimize total cost and allocates products to customers from those facilities.

## Model Formulation 

### Decision Variables

- $\text{open_DC}_{d} \in [0,1]$: Whether the Distribution Center [ d ] is opened, or whether space within an existing Distribution Center is contracted.  Either way, there is a fixed cost to the decision.   

- $\text{allocation}_{d,c} \in \mathbb{N}_{0}$: The non-negative amount of units that are planned to flow from Distribution Center [ d ] to Customer [ c ]

### Objective Function

- **Minimize the planned cost**.  Planned cost includes the fixed cost of setup and the variable cost of shipping products from the Distribution Center to Customers.

\begin{equation}
\text{Minimize} \quad Z = \sum_{(d,c) \in \text{Distribution Centers} \times \text{Customers}}({\text{shipping_cost}_{d,c}} * {\text{allocation}_{d,c}}) +  ({\text{fixed_cost}_{d}} * {\text{open_DC}_{d}})
\end{equation}

### Constraints

- **Fulfill Customer Demand**: Customers to receive allocation from the distribution centers in the amount of the planned demand.

\begin{equation}
\sum_{d \in \text{Distribution Centers}}{\text{allocation}_{d,c}} \geq \text{Demand}_{c} \quad  \forall c \in \text{Customers}
\end{equation}

- **Only allocate products to Open Distribution Centers**: A modeling constraint to ensure closed distribution centers do not ship products.  The big M is set to the sum of all customer demand.

\begin{equation}
\ {\text{allocation}_{d,c}} \leq M * \text{open_DC}_{d} \quad  \forall c \in \text{Customers, } d \in \text{Distributions}
\end{equation}

- **Distribution Centers Capacity**: Each Distribution Center has a limited capacity based on these planning decisions.

\begin{equation}
\sum_{c \in \text{Customers}}{\text{allocation}_{d,c}} \leq \text{Capacity}_{d} \quad \forall d \in \text{Distribution Centers}
\end{equation}
 