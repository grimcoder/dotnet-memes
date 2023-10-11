### **LocalEats API Physical Design**

---

#### **Base URL**: 
`https://api.localeats.com/v1/`

#### **Authentication**: 
- **Bearer Token Authentication**: Every API request must have an `Authorization` header with a valid JWT token.
  
---

#### **1. User Management**

- **Endpoint**: `/users`

  - **GET** `/users/{id}`: Retrieve user by ID
    - **Response**: User details JSON

  - **POST** `/users/register`: Register a new user
    - **Request**: User details JSON (Username, Email, Password, etc.)
    - **Response**: Success status and User ID
  
  - **POST** `/users/login`: User login
    - **Request**: Credentials JSON (Username/Email and Password)
    - **Response**: JWT Token and User details
  
  - **PUT** `/users/{id}`: Update user details
    - **Request**: User details to be updated in JSON format
    - **Response**: Success status

---

#### **2. Restaurants Management**

- **Endpoint**: `/restaurants`

  - **GET** `/restaurants`: Retrieve a list of all restaurants
    - **Response**: List of restaurant details JSON
  
  - **GET** `/restaurants/{id}`: Retrieve specific restaurant by ID
    - **Response**: Restaurant details JSON

  - **POST** `/restaurants`: Add a new restaurant
    - **Request**: Restaurant details JSON
    - **Response**: Success status and Restaurant ID
  
  - **PUT** `/restaurants/{id}`: Update restaurant details
    - **Request**: Restaurant details JSON
    - **Response**: Success status
  
  - **DELETE** `/restaurants/{id}`: Delete a restaurant
    - **Response**: Success status

---

#### **3. Menu Management**

- **Endpoint**: `/menu`

  - **GET** `/menu/{restaurantId}`: Retrieve menu items for a restaurant
    - **Response**: List of menu items in JSON

  - **POST** `/menu/{restaurantId}`: Add a menu item for a restaurant
    - **Request**: Menu item details JSON
    - **Response**: Success status and Menu item ID

  - **PUT** `/menu/{itemId}`: Update menu item details
    - **Request**: Menu item details JSON
    - **Response**: Success status

  - **DELETE** `/menu/{itemId}`: Delete a menu item
    - **Response**: Success status

---

#### **4. Order Management**

- **Endpoint**: `/orders`

  - **GET** `/orders/{userId}`: Retrieve all orders for a user
    - **Response**: List of order details in JSON

  - **POST** `/orders`: Place a new order
    - **Request**: Order details (items, quantities, delivery address, etc.) in JSON
    - **Response**: Success status and Order ID
  
  - **PUT** `/orders/{orderId}`: Update order status/details
    - **Request**: Order status or any other details to be updated in JSON
    - **Response**: Success status

---

#### **5. Reviews Management**

- **Endpoint**: `/reviews`

  - **GET** `/reviews/{restaurantId}`: Retrieve all reviews for a restaurant
    - **Response**: List of reviews in JSON
  
  - **POST** `/reviews`: Add a new review
    - **Request**: Review details JSON
    - **Response**: Success status and Review ID
