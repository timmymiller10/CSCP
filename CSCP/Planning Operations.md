# Planning Operations

## Planning Operations Road Map


**Manufacturing Planning and Control (MPC)** process - This system is designed to balance demand-side requirements with supply-side capabilities through a series of integrated steps.

### Demand-Side Activities

* This section focuses on identifying and managing customer requirements:
  * **Forecasting**: Predicting future demand to guide long-term planning.
  * **Demand Management**: Balancing supply and demand while managing customer expectations.
  * **Distribution Requirements Planning (DRP)**: Determining the need for finished goods at distribution centers (DCs) and pulling orders upward through the system.

### Priority Planning (The "What" and "When")

* These activities determine which products should be made and in what order:
  * **Sales and Operations Planning (S&OP)**: A collaborative process that creates a production plan at the aggregate level (product families).
  * **Master Scheduling (MS)**: Disaggregates the S&OP plan into a Master Production Schedule (MPS), committing to specific units and dates.
  * **Material Requirements Planning (MRP)**: Calculates the specific components and raw materials needed to fulfill the MPS.

### Supply-Side (Capacity) Planning

* Every priority plan must be validated against available resources to ensure feasibility:
  * **Resource Planning (RP)**: Checks the aggregate production plan against long-term, high-level resources (e.g., new facilities or major equipment).
  * **Rough-Cut Capacity Planning (RCCP)**: Verifies that the Master Production Schedule is achievable with current labor and machinery.
  * **Capacity Requirements Planning (CRP)**: A detailed check at the MRP level to ensure specific work centers can handle the load.

### Production Activity Control (PAC)

* This is the execution phase on the shop floor:
  * **Scheduling**: Detailed planning of specific jobs and sequences.
  * **Implementation**: Executing the work orders.
  * **Capacity Control**: Monitoring the actual output and adjusting resources as needed to stay on track.

### Purchasing

The final link in the chain, responsible for acquiring the materials and services identified during the MRP and PAC phases.

### The "Capacity Check" Hierarchy

The text emphasizes that planning is an iterative process. If a capacity check fails at any level, the plan must be revised or capacity must be increased.

|Planning Level|Associated Capacity Check|
|:---|:---|
|**S&OP (Aggregate)**|Resource Planning|
|**Master Scheduling (Unit)**|Rough-Cut Capacity Planning|
|**MRP (Component)**|Capacity Requirements Planning|
|**Execution (Job)**|Capacity Control|

## Master Scheduling (MS)

Process of disaggregating the high-level data from the Sales and Operations Plan (S&OP) into specific units and dates. While S&OP works with product families, Master Scheduling focuses on individual part numbers deemed critical to the operation.

The core output is the **Master Production Schedule (MPS)**, which acts as a "contract" between sales and operations.

### The Master Scheduling Grid

* The process is typically managed via an ERP system using a grid that tracks several key variables across a planning horizon:
  * **Forecast**: The projected demand for the item.
  * **Customer Orders**: Actual orders received that have "consumed" the forecast.
  * **Projected Available Balance (PAB)**: The expected inventory at the end of a period.
  * **Available-to-Promise (ATP)**: The portion of uncommitted inventory and planned production that sales can promise to customers for delivery.
  * **Master Production Schedule (MPS)**: The actual build plan (often based on a specific Lot Size).

### Time Fences and Zones

* To balance the need for stability with the need for flexibility, the master schedule is divided into three zones using "fences":
  * **Frozen Zone (Inside the Demand Time Fence)**: Capacity and materials are committed to specific orders. Changes are generally prohibited or require high-level approval because they are costly and disruptive.
  * **Slushy Zone (Between the DTF and Planning Time Fence)**: The master scheduler has more trade-off authority. Changes to the "mix" of products are possible, but the overall volume is usually protected.
  * **Liquid Zone (Outside the Planning Time Fence)**: This is the most flexible area where the schedule can be easily changed by the computer's planning logic to meet new forecasts.

### Key Calculations

* The logic used to calculate the Projected Available Balance (PAB) changes depending on where you are in relation to the Demand Time Fence (DTF):
  * **Before the DTF**: The calculation uses only **Customer Orders**, as these are "frozen" and certain.
  * **After the DTF**: The calculation uses the **higher of Forecast or Customer Orders** to ensure the plan accounts for the most likely demand.

### Benefits of the MPS

* **For Sales**: Provides a clear "Available-to-Promise" figure to make reliable delivery commitments.
* **For Operations**: Provides stability by preventing "nervousness" in the schedule and ensuring efficient use of labor and equipment.
* **For the Company**: Minimizes inventory holding costs and reduces the risk of stockouts.

# Materials and Inventory
