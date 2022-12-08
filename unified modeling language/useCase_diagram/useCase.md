# "Use Case" Diagram

we started the proccess of creating the use case digram after reading the specification document and understanding the probleme.
We are going to create the following components :

1. The requirements table.

1. The regroupement table.

1. The actors diagram.

1. The Diagram it self.

1. The detailed description.

## 1. The Requirements Table

|Reference|Requirement|
|:--------|:----------|
|R1|Optimized responsive design for the following devices: mobile, tablet, and desktop|
|R2|View products|
|R3|Search products|
|R4|Filter products|
|R5|Make purchases with Stripe|
|R6|View shopping cart|
|R7|Add items to cart|
|R8|Update cart before purchasing|
|R9|Allow users to register an account|
|R10|Allow customers to login to their account|
|R11|Save payment credentials for future use|
|R12|Allow for creation of categories|
|R13|Allow for updating of categories|
|R14|Allow for viewing of categories|
|R15|Allow for deleting of categories|
|R16|Each category should have a name|
|R17|Allow for creation of products|
|R18|Allow for deleting of products|
|R19|Allow for updating of products|
|R20|Allow for viewing of products|
|R21|Each product should have multiple images, a title, a category, a short and long description, a price, a discount, and available stock|
|R22|Customers can add multiple products to their cart|
|R23|On each product page, display a random selection of products from the same category|
|R24|Allow for creation of engineers|
|R25|Allow for updating of engineers|
|R26|Allow for viewing of engineers|
|R27|Allow for deleting of engineers|
|R28|Each engineer should have a first and last name, a birthday, an ID number, two addresses, a city, an email, and a phone number|
|R29|Allow for creation of customers|
|R30|Allow for updating of customers|
|R31|Allow for viewing of customers|
|R32|Allow for deleting of customers|
|R33|Track orders|
|R34|Allow for order management, including the ability to associate each order with a customer, a set of products, a total price, a quantity for each product, and an engineer. Track whether each order has been executed or not.|

## 2. Actors Diagram

// TODO: ADD THE ACTORS DIAGRAM 
![]()

## 3. The regroupment table

|Reference|Requirement|intentions|Actor|
|:-|:-|:-|:-|
|Ref1|R2,R3,R4|Browse Products|customer|
|Ref2|R5|Make Purchases|Customer|
|Ref3|R6, R7, R8|Manage Cart|Customer|
|Ref4|R8, R9|Auth|customer/admin|
|Ref5|R11,R12,R13,R14|Managing categories|admin|
|Ref5|R16,R17,R18,R19|Managing products|admin|
|Ref5|R23,R24,R25,R26|Managing engineers|admin|
|Ref5|R29,R30,R31,R32|Managing customers|admin|
|Ref5|R33|Managing orders|admin| 


# 4. The digram itself

// TODO: ADD THE Use case DIAGRAM 

# 5. The Description

|Name|Auth|
|:-|:-|
|Created by|Choaib Mouhrach|
|Date created|December 8, 2022|
|Description|This use case refers to authentication and to achive that the actor should be authenticated through login or register|
|Include use cases|null|
|Extend use cases|display errors|
|primary actors|admin\customer|
|secondary actors|null|
|preconditions|The actor should insert he's login credentials and get verified|
|postconditions|The actor will be authenticated|
|main flow|1. The actor visit the login page.<br/>2. The system displays the login register form.<br/>3. The actor fills the form and submit.<br/>4. The system Verify's The credentials.<br/>5. The system Authenticate the actor.<br/>|
|alternative flow|1a: The actor visits the register page:<br/> 1. The system displays the register page|
|exception conditions|4a: The system find's an error in the request : <br/> 1. The system shows authentication errors|
|Name|Browse Products|
|Created by|Choaib Mouhrach|
|Date created|December 8, 2022|
|Description|The use case refers to "Seeing the products", "Browsing them", "Filtering and searching through them"|
|Include use cases|null|
|Extend use cases|null|
|primary actors|Customer|
|secondary actors|null|
|preconditions|To access This use case the actor must visit the products page|
|postconditions|The Actor will get an idea about what products are in the store|
|main flow|1. The actor visits the products page<br/> 2. The system Displays the available products with a pagination in the end and a panel in the left so the actor can filter the products and a search bar in the top<br/>3. The Actor Types in the search bar<br/>4. The System filters the products by title and description then display the filtered products<br/>5. The Actor changes the filter options in the left panel<br/>6. The system shows the filterd products<br/>7. The Actor change the page by clicking on the pagination<br/>8. The system shows the requested page of products|
|alternative flow|null|
|exception conditions|4a: The system does not find any products to display:<br/> 1. The system shows a pragraph "Product Not found"<br/> 2. The system hide's the pagination|
|Name|Manage Cart|
|:--|:--|
|Created by|Choaib Mouhrach|
|Date created|December 8, 2022|
|Description|This use case refers to "adding products to cart" , "Browsing The cart items", "Update and delete cart items"|
|Include use cases|Browse Products|
|Extend use cases|null|
|primary actors|Customer|
|secondary actors|null|
|preconditions|The Actor should browse the availble products before adding any product to the cart|
|postconditions|The cart will have only wanted items|
|main flow|1. The actor adds the wanted items to the cart <br />2. The cart get filled with the wanted items<br/>3. The Actor updates the cart item quantity<br/>4. The system updates the quantity of the product<br/>5. The Actor deletes an item<br/>6. The system deletes the specified product from the cart|
|alternative flow|null|
|exception conditions|2a, 5a:The system does not find the specififed product<br/>1. The system displays an alert with the error "Product Not found"|
|Name|Make Purchase|
|Created by|Choaib Mouhrach|
|Date created|December 8, 2022|
|Description|This use case referse to paying for the items in the cart where the actor can pay for the items if the cart has at leaset one item in it|
|Include use cases|Manage cart|
|Extend use cases|null|
|primary actors|Customer|
|secondary actors|null|
|preconditions|The cart should have at least one item and the payment credentials should be valid|
|postconditions|The cart will reset its items and place an order in the orders section|
|main flow|1. The user clicks on the checkout button<br />2. The System displays The form for the actor to insert his credentials<br />3. The System validates the payment process.<br/>4. The system makes the cart empty|
|alternative flow|null|
|exception conditions|3a: The system finds the credentials unvalid:<br />1. The system displays an alert with the error "The credentials are not valied"|
|Name|Manage products|
|Created by|Choaib Mouhrach|
|Date created|December 8, 2022|
|Description|This use case refers to 'creating new products', "updating existing products", "deleting existing products", "viewing existing products"|
|Include use cases|Auth|
|Extend use cases|null|
|primary actors|admin|
|secondary actors|null|
|preconditions|The actor should be authenticated and authorized to do trigger this use case|
|postconditions|The Products list will be mutated|
|main flow|1. The actor visits the products page in the dashboard<br/>2. The system displays the products and the search bar in the top and the filter in the left along side the pagination and the update and delete button at the end of every row.<br/>3. The actor types in the search bar<br/>The system shows the required products|
|alternative flow|2a: The actor changes in the filter options:<br />1. The system displays the filtered products<br />2b: The actor changes the pagination<br/>1. The system displays the filtered products<br/>2c:The actor clicks on the delete button<br/>1. The system displays a prompt asking the actor if they want to proceed with the operation.<br/>2. The Actor chooses on of the displayed choices.<br/>The System deletes the product if the prompt returns true<br />2d: The Actor clicks on the update button<br />1. The System displays a form in a modal<br/>2. The Actor changes in the form<br />3. The system validated the form and updated the product|
|exception conditions|null|



