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

## Commitment Decision Points

**Commitment Decision Points** are negotiated milestones in a buyer-supplier relationship. They define exactly when demand information transitions from a "forecast" to a "firm contractual obligation."

* These points are designed to prevent two common frustrations:
  * Supplier Risk: The supplier builds capacity or inventory based on plans, but the buyer fails to place the expected orders.
  * Buyer Risk: The buyer provides demand data, but the supplier fails to develop the necessary capacity to fulfill it.

### The Three Purchase Commitment Zones**

* By negotiating these decision points, organizations create three distinct zones that dictate the level of commitment:

|Zone|Definition|Level of Commitment|
|:---|:---|:---|
|**Frozen Zone**|The period inside the Firm Commitment Decision Point (e.g., Weeks 1–3).|Orders are treated as firm purchase orders. Both the volume and the specific delivery timing are fixed.|
|**Slushy Zone**|The period between the Firm and Volume Commitment Decision Points (e.g., Weeks 4–16).|The buyer is committed to the total volume, but retains the flexibility to shift priorities or timing.|
|**Liquid Zone**|The period beyond the Volume Commitment Decision Point (e.g., Month 5+).|Demand data is for guidance only. There is no contractual commitment to buy or produce.|

### Strategic Benefits

* **Bilateral Accountability**: A formal trading partner agreement specifies how demand info is communicated and what each party is obligated to do.
* **Transparency**: Suppliers feel comfortable committing to production schedules because they know which orders are guaranteed.
* **Flexibility vs. Stability**: It allows for a long-term focus while providing enough stability to maintain fairness for both parties.

### Placement of Decision Points

The exact location of these points is not fixed; they are negotiated at the executive level based on:

* Industry standards and market volatility.
* Supplier and buyer lead times.
* The desired balance between operational continuity and the ability to react to market changes.

## Time Fences for Material Requirements Planning

### Function and Purpose

While Master Scheduling manages end-items, MRP time fences manage the specific "ingredients" required to build those items.

* **Commitment**: They ensure that once materials are dedicated to a specific order, they are not "stolen" by other competing orders.
* **Lead Time Management**: They help manage the Cumulative Lead Time—the longest total time required to accomplish an activity, accounting for every path in the Bill of Material (BOM).

### The Two MRP Time Fences

In an MRP environment, the fences are typically defined by the status of the material:

* **Planning Time Fence**: Usually set at the moment the material is ordered or when production of the subcomponent begins.
* **Demand Time Fence**: Usually set when the material is received or when the production of that specific component is complete.

### Managing Complexity

For products with deep Bills of Material (like a ship or an aircraft), there may be multiple, overlapping time fences:

* **Early Stage**: A ship’s hull may have fences set months or years in advance.
* **Middle Stage**: The engines and mechanical systems have their own set of fences.
* **Late Stage**: Interior furnishings and cabin electronics have fences set much later in the production cycle.

### The Balance: Stability vs. Flexibility

The reading highlights a critical trade-off in using these fences:

|The Need for Stability|The Need for Flexibility|
|:--|:--|
|Late changes cause "nervousness" in the system, leading to extra setups, expediting costs, and overtime.|Customers may cancel orders or request last-minute changes.|
|Frequent rescheduling damages the perceived reliability of the master schedule.|Equipment failures, scrap/waste, or supplier delays may require a "pivot" in the plan.|

# Materials and Inventory
