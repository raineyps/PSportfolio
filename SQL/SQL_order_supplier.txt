select *
into OS
from dbo.orders
left join dbo.[product-supplier] on orders.[Orders_Product ID] = [product-supplier].[Supplier_Product ID]

select OS.[Customer ID],
		LOWER(OS.[Customer Status]) AS Customer_Status,
		OS.[Date Order was placed],
		OS.[Delivery Date],
		OS.[Order ID],
		OS.[Orders_Product ID],
		OS.[Quantity Ordered],
		OS.[Total Retail Price for This Order],
		OS.[Cost Price Per Unit],
		OS.[Product Line],
		OS.[Product Category],
		OS.[Product Group],
		OS.[Product Name],
		OS.[Supplier Country],
		OS.[Supplier Name],
		OS.[Supplier ID]
into order_supplier
from dbo.OS
