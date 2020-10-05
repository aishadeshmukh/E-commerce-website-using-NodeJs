# E-commerce-website-using-NodeJs


### Download the repository

`git clone`

### Running the application using postman

Install postman desktop application to tests the steps of sign up/sign in and sign out of users and admin. The authentication provided to admin can also be tested here.

#### Sign up
- Execute a post query with URL - http://localhost:8000/api/signup
- Insert header Content-Type with value application/json
- In the body field, select raw radio button and insert below sample code to sign up a user

` {
    "name": "John",
    "lastname": "Doe",
    "email": "john@exp.com",
    "password": "12345"
}`


#### Sign in
- Execute a post query with URL - http://localhost:8000/api/signin
- Insert header Content-Type with value application/json
- In the body field, select raw radio button and insert below sample code to sign up a user

`{
    "email":"john@exp.com",
    "password": "12345"
}
`

#### Creating Categories of the product
- The categories can be created by the admin alone.
- The admin will first need to login through above sign in instructions.
- After signning in the token and id of the admin will appear in the result section.
- Execute a post query with URL - http://localhost:8000/api/category/create/userId
  Here userId is the id of the admin which appears when signed in.
- Insert header Content-Type with value application/json.
- In the header, one more field needs to be added as Authorization. The value for it will be Bearer token (Here token is the same token generated after admin sign in).
- In the body section, in raw field, insert below code with the category name you want to insert.

`
{
    "name": "Delete this"
}
`


#### Creating product
- The categories can be created by the admin alone.
- The admin will first need to login through above sign in instructions.
- After signning in the token and id of the admin will appear in the result section.
- Execute a post query with URL - http://localhost:8000/api/product/create/userId
  Here userId is the id of the admin which appears when signed in.
- In the header, one more field needs to be added as Authorization. The value for it will be Bearer token (Here token is the same token generated after admin sign in).
- In the body section, select form-data radio button to insert the attributes of the product in the form of key value pair
 
 | KEY       |     VALUE     |
 |   -----   |      -----    |
name         |  Abstract Tshirt
description  | New Summer collection with abstract print
price        |  500
stock        |  40
category     |  categoryId
photo        |   image.jpg


- The categoryId above should be taken from the id when the category was created.
- In the photo key section, make sure to select file in the drop down. The value section gives you a button to select the image from your device. Make sure you are have updated setting of postman to allow it to select files outside the working directory.




#### Deletion and Updation of category/product
- The admin alone can delete/update the category/product.
- Execute a delete query with URLs below for deletion of respective entity -
   - http://localhost:8000/api/product/productId/userId
   - http://localhost:8000/api/category/categoryId/userId
   Here, userId is the id of the admin when he is signed in.
- Similarly, a put query can be executed to update a specific category/product.



#### Creating orders
- The user can create an order by adding products.
  - Execute a post query with URL - http://localhost:8000/api/order/create/:userId
    Here userId is the id of the signed in user.



#### Viewing all orders of a particular user
The admin can view all order of a user, check the status of the order and update it.
  - Get query to display all orders of a user URL - http://localhost:8000/api/order/all/:userId
  - Get query to display status of the order of a user URL - http://localhost:8000/api/order/status/:userId
  - Post query to update the status of an order of the user URL - http://localhost:8000/api/order/:orderId/status/:userId


#### Viewing all products and categories
- The admin can view all the products and unique categories by exceuting below get requests.
 - URL - http://localhost:8000/api/product
 - URL - http://localhost:8000/api/product/categories
 
 


### Robo3T for Database
- The database is created in MongoDB.
- Establish a new connection in Robo3T.
- Create a database on your mongoDB terminal using below - 

    ` use tshirt 
    `

- After each CRUD operation, you can find you saved database for the particular entity in Robo3T under the Collections folder of tshirt database.
- Each attribute is visible which can further edited or deleted as required.








