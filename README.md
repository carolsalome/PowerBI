Dashboard created during the Alura school challenge to develop skills involving Power BI.
During the development of this dashboard, several data treatments were carried out and new metrics were created using DAX language.

ACTIVITY DETAILS
Table Name: Tabelas - Produtos
Table Description: Product details table
Table columns: Categoria Produto (product category), preço(price)
Data processing: The [Product Category] column was a concatenation of the product code and the product category description. In order to create a relationship between this table and the other tables, it was necessary to break this column into two. One called [Product ID] which is the product code (this field was used as the primary key) and the [Product Category] column was kept with only the name of the category.

Table Name: Tabelas - Estoque
Table Description: Control of product stock quantity by date
Table columns: ID Produto (product ID), data atualização(update date), quantidade (amount)
Data processing: The [updated date] column was not configured as a date field. To make it possible to calculate delivery times, I transformed this field into a date.

Table Name: Tabelas - Pedidos
Table Description: Control of all orders placed
Table columns: ID Produto (product ID), ID Pedido(order ID), ID Veículo (vehicle ID), data de compra(purchase date), data de entrega(delivery date), data previsão(expected delivery date), latitude, longitude, quantidade (amount), Status do pedido (order status), UF de entrega (delivery state)
Data processing: The field [Date of purchase] was as a String with a date in American standard, so that it could be used in the metrics it needed to be changed to Date and Time format and changed to Brazilian standard.
The [Latitude] and [Longitude] fields had to be changed to decimal and manipulated so that they could reflect real latitudes and longitudes
The [Vehicle ID] field needed to be changed so that it was possible to connect to the primary key [Vehicle ID] of the Vehicle Tables Table, so the prefix VEH was added to all lines in this column.
In addition, new measures were created using variables to determine whether the order was delivered on time and how long the order took to be delivered after purchase.

Table Name: Tabelas - Veículos
Table Description: Vehicles details table
Table columns: ID Veículo (vehicle ID), Tipo (type), Status
Data processing: I only changed the [Type] column so that the names had the first letter capitalized because it looks more visually beautiful.


DASHBOARD
Total Orders, Orders delivered on time, Orders delivered after the deadline, Orders by State in map view, Vehicles available, Vehicles in Use, Fleet of vehicles by type, Average delivery time over time, Average inventory per year
![dashboard pronto](https://github.com/user-attachments/assets/71886e71-fc4e-44eb-bc66-ab252d893bde)
