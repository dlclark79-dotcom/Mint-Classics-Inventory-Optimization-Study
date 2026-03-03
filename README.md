# Mint Classics Inventory Optimization Study
# Goal: Identify opportunities to close one warehouse by reducing overstocked inventory.
## Project Overview 
To improve operational efficiency, Mint Classics sought to identify opportunities to close one of its four storage facilities. This analysis utilized MySQL Workbench to evaluate the relationship between inventory levels, warehouse utilization, and sales performance across the company’s entire product line. It was discovered that warehouses have stagnant capital and underutilized capacity, warranting redistribution and liquidation. 

## Key Insights
Underutilized Capacity: The South Warehouse currently holds the lowest volume of inventory (79,380 items). Analysis suggests that the North and West facilities have sufficient combined "headroom" to absorb this stock without reaching full capacity. 
Stagnant Capital: A significant portion of the inventory is overstocked. In several product lines, the quantity in stock vastly exceeds annual sales volume, indicating that capital is being tied up in slow-moving goods. 
Product Performance: While all products have recorded sales, a subset of items shows an extremely low Inventory Turnover Ratio. 
Strategic Recommendations
Facility Closure: Proceed with the closure of the South Warehouse. Its inventory should be redistributed to the North and West facilities to maximize space utilization. 
Inventory Liquidation: Implement a targeted promotional campaign to reduce "excess stock" identified in Figure 2. This will free up physical space and improve cash flow. 
Procurement Adjustment: Pause or reduce production on high-stock/low-turnover items until inventory levels align with historical sales trends. 

## Business Task
Mint Classics Company, a retailer of classic model cars and other vehicles, is looking at closing one of their storage facilities. To support a data-based business decision, they are looking for suggestions and recommendations for reorganizing or reducing inventory, while still maintaining timely service to their customers. I have been asked to use MySQL Workbench to familiarize myself with the general business by examining the current data. 
These are the business questions I am tasked with answering:
1) Where are items stored and if they were rearranged, could a warehouse be eliminated? 
2) How are inventory numbers related to sales figures? Do the inventory counts seem appropriate for each item? 
3) Are we storing items that are not moving? Are any items candidates for being dropped from the product line? 
The answers to questions like those should help you to formulate suggestions and recommendations for reducing inventory with the goal of closing one of the storage facilities. 


## Project Objectives
1) Explore products currently in inventory. 
2) Determine important factors that may influence inventory reorganization/reduction. 
3) Provide analytic insights and data-driven recommendations. 


## Cleaning
Table relationships were mapped by creating a new EER diagram (Figure 1). Scripts were then run in MySQL Workbench to check each table for nulls. It looks as though the Nulls do not affect any of the fields needed for this analysis, so no additional measures were taken. However, this should be remembered for future analyses. 

<img width="993" height="812" alt="Mint Classics EER" src="https://github.com/user-attachments/assets/88d47e31-182b-451b-a299-66f52f18c387" />
Figure 1.  



## Reasoning
1) Where are items stored and if they were rearranged, could a warehouse be eliminated? 


| stock | warehouseName |
| --- | --- |
| 131,688 | North |
| 219,183 | East |
| 79,380 | South |
| 124,880 | West |



Find out which products and product lines are stored in each warehouse. The east warehouse has over 200,000 items, I will hypothesize this is filled to capacity. However, the north and west warehouses have a little over half this many items (131,688 and 124,880), and could easily absorb stock stored in the south warehouse (79,380). If redistributing the stock is possible, the contents of the south warehouse could be moved to the north and west warehouses. 


2) How are inventory numbers related to sales figures? Do the inventory counts seem appropriate for each item? 

![Inventory and Orders](https://github.com/user-attachments/assets/c939f8fa-c293-4d14-8539-3066fb76b68b)
Figure 2.  

The stock of each item was compared with  its sales. After summing quantityOrdered, grouped by productName it’s clear that for many products stock greatly outweighs sales, resulting in thousands of excess stock sitting in warehouses after sales (Figure 2). The above analysis also reveals some products in which order count exceeds quantity in stock. While this information is not relevant to the current project, it may still be worth noting. 


3) Are we storing items that are not moving? Are any items candidates for being dropped from the product line? 
Figure 2 also reveals that, although many more products are in stock than what are being ordered, all products are being ordered. None should be dropped from production. However, pausing production on the overstocked items and enacting a promotional event to help clear the overstock would be advised. 
Recommendations
If possible, redistribute the stock from the south warehouse to the north and west warehouses. This should empty the south warehouse allowing it to be closed. However, additional questions remain regarding this recommendation which cannot be answered by the dataset provided.  Such as: 1)Does the south warehouse serve a specific region? If you close it, will shipping costs to southern customers skyrocket, canceling out the storage savings? 2)Does the south warehouse hold a specific product line? If so, do the north and west warehouses have the right equipment to handle them? 
Additionally, the stock of many products greatly exceeds sales, resulting in thousands of items sitting in warehouses. A targeted reduction in this overstock should further facilitate redistributing stock. 
