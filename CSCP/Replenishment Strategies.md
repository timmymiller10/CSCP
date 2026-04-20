# Replenishment Strategies

## Inventory Control & Order Quantities

Inventory control aims to balance **customer service levels** against **carrying, ordering, and setup costs**. There are two primary disciplined models for determining how much to order:

* **Lot-for-Lot (L4L)**: Orders exactly what is needed for a specific period (net requirements). Used in **JIT (Just-in-Time)** environments and for **"A" items** in ABC analysis.

* **Fixed Order Quantity (FOQ)**: Orders a predetermined, fixed amount (e.g., a full pallet or container) whenever a replenishment is triggered.

    * **Economic Order Quantity (EOQ)**: A specific type of FOQ that minimizes the sum of annual carrying and ordering costs.

**The EOQ Formula & Assumptions**

The EOQ is found where 
$Carrying \, Costs = Ordering \, Costs$

**Key Assumptions**: 
* Demand and lead time are constant/known
* Items arrive all at once
* No quantity discounts 
* Only carrying and ordering costs are considered.

## Ordering Systems (When to Order)


| System | Mechanics | Key Characteristic |
| :--- | :--- | :--- |
| Order Point | Order placed when inventory hits a specific level. | Quantity is fixed; intervals vary. |
| Periodic Review | Inventory is reviewed at fixed intervals (e.g., every Monday). | Intervals are fixed; quantity varies. |
| Min-Max | Orders placed when below "Min" to reach "Max." | Both timing and quantity can vary. |
| Time-Phased (TPOP) | MRP-like logic using forecasts for independent demand. | Good for "lumpy" demand or slow movers. |
| Demand-Driven MRP | Uses strategic inventory buffers to decouple supply/demand. | Reduces bullwhip effect without safety stock. |

Order Point Formula:$$\text{Order Point} = (\text{Average Demand during Lead Time}) + \text{Safety Stock}$$


## Safety Stock & Safety Lead Time

Both are buffers against uncertainty, but they function differently:

**Safety Stock (Quantity Buffer)**
Extra units held to protect against fluctuations in demand or supply.

* **Risk**: Stockout risk is highest at the **time of replenishment**.

* **Diminishing Returns**: Increasing service levels (e.g., from 95% to 98%) requires a **disproportionately large increase in safety stock**.

**Safety Lead Time (Time Buffer)**

Orders are placed **earlier than the normal lead time** requires.

* Used primarily for **slow-moving items** where carrying extra physical units (safety stock) would be too expensive.

* **Risk:** Can lead to overstocks if orders consistently arrive earlier than needed.

## Key Takeaways

* **EOQ Robustness**: Even if cost estimates are slightly off, the EOQ tends to stay within a small, useful range.
* **Periodic Review Use Case**: Best for retailers/supermarkets to consolidate deliveries into truckloads from a single source.
* **Inventory Decoupling**: Safety stock acts as a "buffer" to decouple supply from demand, ensuring the flow of goods isn't interrupted by minor hiccups.