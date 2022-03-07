# challenge-widget-design

Given the data below
![](img/widgets_data.png)

Create a basic system description and document a normalized schema from widgets data above
1) what you think this system would do 
2) what you feel would be a reasonable database structure for the data and a reasonable architecture for the system 
3) any questions or concerns you have regarding this dataset/system that might need to be answered before establishing an ideal database/solution for such a system.

**Ad 1.** 

It can be that the table is the view for the business to businnes feeding platform that displays hot deals to the **customers**. The deals are added by **suppliers** .

What specific fields mean:
- **widget** is a product name / offer name
- **packaging** shows the information about the quantity of products in one package
- **price** shows the price of a package
- **cost** shows the delivery costs (depends on the warehouse and size of a products)
- **warehouse** the localization of warehouse 
- **qty** shows the number of packages in the given warehouse
- **min_qty** shows the minimal number of products that needs to be order in order to have a deal 


**Ad2.** 

Given low data volume and low numbers of users (3 customers and 3 suppliers) I assume that the application will be small or at least it is at its early development stage.
Therefore we are not in good position to predict sweet spots in the system architecture or even where the application will go further from the business point of view.

Taking the above into consideration I would choose ligthweight technology that will allow to biuld the system quickly and if possibly amend DB schema quickly and easily.
I would go for SQL database and Django Framework for building Model and UI. It allows to build UI quickly and thanks to migrations it allows to make a Database schema 
amendments painless.



**_SQL Schema_**

TABLE **warehouse**<br>
warehouse_id(PK)<br>
warehoouse<br>

TABLE **customer**<br>
customer_id(PK)<br>
customer<br>

TABLE **supplier**<br>
supplier_id(PK)<br>
supplier<br>

TABLE **product**<br>
product_id(PK)<br>
product<br>
packaging<br>
<br>

TABLE **delivery_cost**<br>
product_id(FK)<br>
warehouse_id(FK)<br>
cost<br>

TABLE **special_offers**<br>
supplier_id(FK)<br>
product_id(FK)<br>
customer_id(FK)<br>
warehouse_id(FK)<br>
price<br>
min_qty<br>



**Ad. 3**

In my opinion it is impossible to establish an ideal DB fo future at early stage of any appliactions, but at least we should take into consideration following questions:
* How many users we anticipate. how many customers (reads) and how many suppliers (writes)?
* Who are our users? Are they technical or not? How often they will use the app? how they will possibly use the application (mobile? desktop? tablet? All)
* Is the latency critical part of the system? It can be the case when the offer will be very attractive and restricted in time.



