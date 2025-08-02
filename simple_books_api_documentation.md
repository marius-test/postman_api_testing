# Simple Books API

**Base URL:** `https://simple-books-api.click`  
This API allows you to **check book availability** and **place orders**.

---

## API Status

**GET** `/status`  
Check if the API is working.

---

## List Books

**GET** `/books`  
Returns a list of available books.

**Optional query parameters:**

- `type`: `fiction` or `non-fiction`
- `limit`: A number between `1` and `20`

**Example:**
```
GET /books?type=fiction&limit=5
```

---

## Get Book Details

**GET** `/books/:bookId`  
Retrieve detailed information about a specific book.

**Example:**
```
GET /books/1
```

---

## Submit an Order _(Authentication Required)_

**POST** `/orders`  
Place a new order.

**Headers:**
```
Authorization: Bearer <YOUR TOKEN>
```

**Request Body (JSON):**
```json
{
  "bookId": 1,
  "customerName": "John"
}
```

**Response:**  
Returns the order ID.

---

## Get All Orders _(Authentication Required)_

**GET** `/orders`  
View a list of all orders.

**Headers:**
```
Authorization: Bearer <YOUR TOKEN>
```

---

## Get a Single Order _(Authentication Required)_

**GET** `/orders/:orderId`  
View details for a specific order.

**Headers:**
```
Authorization: Bearer <YOUR TOKEN>
```

---

## Update an Order _(Authentication Required)_

**PATCH** `/orders/:orderId`  
Update customer name on an existing order.

**Headers:**
```
Authorization: Bearer <YOUR TOKEN>
```

**Request Body (JSON):**
```json
{
  "customerName": "John"
}
```

---

## Delete an Order _(Authentication Required)_

**DELETE** `/orders/:orderId`  
Delete an existing order.

**Headers:**
```
Authorization: Bearer <YOUR TOKEN>
```

**Request Body:** *(Must be empty)*

---

## API Authentication

To use any order-related endpoints, you must register your API client and get a token.

**POST** `/api-clients/`  

**Request Body (JSON):**
```json
{
  "clientName": "YourApp",
  "clientEmail": "you@example.com"
}
```

**Response:**  
Returns an **access token** (valid for 7 days).

**Error 409:**  
API client already registered. Use a different `clientName` or `clientEmail`.

---
