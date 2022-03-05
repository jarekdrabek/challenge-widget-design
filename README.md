# challenge-widget-design

Given the data below
![](img/widgets_data.png)


1) Create a basic system description and document a normalized schema from widgets data above.  
2) what you think this system would do 
3) what you feel would be a reasonable database structure for the data and a reasonable architecture for the system 
4) any questions or concerns you have regarding this dataset/system that might need to be answered before establishing an ideal database/solution for such a system.

Ad 1&2. It can be that the table is the view for the business to businnes feeding platform that displays **customers** hot deals from **suppliers**.

What specific fields means:
- **widget** is a product name or offer name
- **packaging** shows the information about the quantity of products in one package
- **price** shows the price of a package
- **cost** shows the delivery costs (depends on the warehouse and size of a products)
- **warehouse** the localization of warehouse 
- **qty** shows the number of packages in the given warehouse
- **min_qty** shows the minimal number of products that needs to be order in order to have a deal 


**_Schema_**

TABLE **warehouse**<br>
warehouse_id<br>
warehoouse<br>

TABLE **customer**<br>
customer_id<br>
customer<br>

TABLE **supplier**<br>
supplier_id<br>
supplier<br>

TABLE **product**<br>
product_id<br>
product<br>
packaging<br>
<br>

TABLE **delivery_cost**<br>
product_id<br>
warehouse_id<br>
cost<br>

TABLE **special_offers**<br>
supplier_id<br>
product_id<br>
customer_id<br>
warehouse_id<br>
price<br>
min_qty<br>




Ad 2. 
