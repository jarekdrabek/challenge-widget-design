# challenge-widget-design

Given the data below
![](img/widgets_data.png)

Create a basic system description and document a normalized schema from widgets data above
1) what you think this system would do 
2) what you feel would be a reasonable database structure for the data and a reasonable architecture for the system 
3) any questions or concerns you have regarding this dataset/system that might need to be answered before establishing an ideal database/solution for such a system.

Ad 1. 

It can be that the table is the view for the business to businnes feeding platform that displays **customers** hot deals from **suppliers** .
What specific fields mean:
- **widget** is a product name or offer name
- **packaging** shows the information about the quantity of products in one package
- **price** shows the price of a package
- **cost** shows the delivery costs (depends on the warehouse and size of a products)
- **warehouse** the localization of warehouse 
- **qty** shows the number of packages in the given warehouse
- **min_qty** shows the minimal number of products that needs to be order in order to have a deal 


Ad2. 

Given low data volume and low numbers of users (3 customers and 3 suppliers) I assume that the application will be small or at least is at its early stage.
Therefore we are not in good position to predict sweet spots in the system architecture or even where the application will go further from the business point of view.

Taking the above into consideration I would choose ligthweight technology that will allow to biuld the system quickly and if possibly amend DB schema quickly and easily.
I would go for SQL database and Django Framework for building Model and UI. It allows to build UI quickly and thanks to migrations it allows to make a Database schema 
amendments painless.


If the decision is to go to SQL database the schema would be as follows<br>
**_SQL Schema_**

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



Ad. 3 

