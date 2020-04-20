## Lesson 05 - Constraints:
1. Check
2. Default
3. Auto increment

## Class task:
Create the following tables with this constraints:
1. In `Customer` CustomerId must be primary key. 
2. In `Order` OrderId must be primary key. 
3. In `Order` CustomerId must be foreign key to CustomerId in `Customer`
4. In `Customer` Phone must be a string data type (it can start with 0)
5. In `Order` ShipPostalCode must be auto-increment
6. In `Customer` default value for `Reigon` will be `US`
7. In `Order` use CHECK to ensure ShipPostalCode is above 0. 
8. In `Customer` use NOT NULL for Address
9. In `Customer` make Phone Unique 
10. In `Order` default value for ShipVia is `Amazon`

<img width="500px" src="http://www.binaryintellect.net/articles/content/Images/T_MVCViewsViaAjax_03.png"/>
