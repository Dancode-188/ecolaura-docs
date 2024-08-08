# 🌿 Ecolaura API: Product Endpoints



Welcome to the product section of Ecolaura's API! These endpoints are the backbone of our eco-friendly e-commerce platform, allowing you to interact with our sustainable product catalog. Let's dive into the green goodness! 🌍🛒



## 📋 Endpoints Overview



- [List Product](#list-products)

- [Get Product Details](#get-product-details)

- [Create Product](#create-product)

- [Update Product](#update-product)

- [Delete Product](#delete-product)

- [Get Product Sustainability Score](#get-product-sustainability-score)



## 🔐 Authentication



All endpoints require authentication unless specified otherwise. Include the JWT token in the Authorization header:



```

Authorization: Bearer <your_token_here>

```



## 📊 Rate Limiting



To keep our servers as green as our products, we implement rate limiting:

- 1000 requests per hour for authenticated users

- 100 requests per hour for unauthenticated requests (applicable only to public endpoints)



## 📁 Endpoints



### List Products



Retrieve a list of eco-friendly products. It's like window shopping, but for saving the planet!



```

GET /api/v1/products

```



#### Query Parameters



| **Parameter** | **Type** | **Description** |

|-----------|------|-------------|

| page | integer | Page number for pagination. Default is 1. |

| per_page | integer | Number of items per page. Default is 20, max is 100. |

| category | string | Filter by product category. |

| min_score | float | Minimum sustainability score (0-100). |

| sort | string | Sort by: 'price', 'score', 'name'. Prefix with '-' for descending order. |



#### Response



```json

{

 "status": "success",

 "data": [

  {

   "id": "prod_123abc",

   "name": "Eco-Friendly Water Bottle",

   "description": "Stay hydrated while saving the planet!",

   "price": 19.99,

   "sustainability_score": 95,

   "category": "Kitchen",

   "image_url": "https://ecolaura.com/images/water-bottle.jpg"

  },

  // ... more products

 ],

 "meta": {

  "pagination": {

   "current_page": 1,

   "per_page": 20,

   "total_pages": 5,

   "total_items": 100

  }

 }

}

```



### Get Product Details



Dive deep into the eco-credentials of a specific product.



```

GET /api/v1/products/{product_id}

```



#### Response



```json

{

 "status": "success",

 "data": {

  "id": "prod_123abc",

  "name": "Eco-Friendly Water Bottle",

  "description": "Stay hydrated while saving the planet!",

  "price": 19.99,

  "sustainability_score": 95,

  "category": "Kitchen",

  "image_url": "https://ecolaura.com/images/water-bottle.jpg",

  "materials": ["Recycled Stainless Steel", "Bamboo"],

  "features": [

   "BPA-free",

   "Insulated",

   "Dishwasher safe"

  ],

  "manufacturer": "GreenGoods Inc.",

  "stock_quantity": 500

 }

}

```



### Create Product



Plant a new product in our eco-friendly forest! (Admin only)



```

POST /api/v1/products

```



#### Request Body



```json

{

 "name": "Bamboo Toothbrush Set",

 "description": "Brush away plastic waste!",

 "price": 12.99,

 "category": "Bathroom",

 "materials": ["Bamboo", "Nylon"],

 "features": [

  "Biodegradable handle",

  "Soft bristles",

  "Pack of 4"

 ],

 "manufacturer": "EcoBrush Co.",

 "stock_quantity": 1000

}

```



#### Response



```json

{

 "status": "success",

 "data": {

  "id": "prod_456def",

  "name": "Bamboo Toothbrush Set",

  "description": "Brush away plastic waste!",

  "price": 12.99,

  "sustainability_score": 90,

  "category": "Bathroom",

  "image_url": null,

  "materials": ["Bamboo", "Nylon"],

  "features": [

   "Biodegradable handle",

   "Soft bristles",

   "Pack of 4"

  ],

  "manufacturer": "EcoBrush Co.",

  "stock_quantity": 1000

 }

}

```



### Update Product



Give our products an eco-friendly makeover! (Admin only)



```

PUT /api/v1/products/{product_id}

```



#### Request Body



```json

{

 "price": 11.99,

 "stock_quantity": 1500

}

```



#### Response



```json

{

 "status": "success",

 "data": {

  "id": "prod_456def",

  "name": "Bamboo Toothbrush Set",

  "description": "Brush away plastic waste!",

  "price": 11.99,

  "sustainability_score": 90,

  "category": "Bathroom",

  "image_url": null,

  "materials": ["Bamboo", "Nylon"],

  "features": [

   "Biodegradable handle",

   "Soft bristles",

   "Pack of 4"

  ],

  "manufacturer": "EcoBrush Co.",

  "stock_quantity": 1500

 }

}

```



### Delete Product



Retire a product (but never our commitment to the environment)! (Admin only)



```

DELETE /api/v1/products/{product_id}

```



#### Response



```json

{

 "status": "success",

 "message": "Product successfully deleted"

}

```



### Get Product Sustainability Score



Unveil the eco-friendliness of a product!



```

GET /api/v1/products/{product_id}/sustainability-score

```



#### Response



```json

{

 "status": "success",

 "data": {

  "overall_score": 90,

  "breakdown": {

   "materials": 95,

   "production": 85,

   "packaging": 90,

   "transportation": 80,

   "end_of_life": 100

  }

 }

}

```



## 🐛 Error Handling



Our API serves errors as organically as we serve eco-products:



```json

{

 "status": "error",

 "message": "Oops! Something went wrong.",

 "errors": [

  {

   "field": "price",

   "message": "Price must be a positive number."

  }

 ]

}

```



Common HTTP status codes:

- 400: Bad Request

- 401: Unauthorized

- 403: Forbidden

- 404: Not Found

- 429: Too Many Requests

- 500: Internal Server Error



## 🌱 Best Practices



1. **Pagination**: Always use pagination for list endpoints to keep response times swift and our servers happy.

2. **Filtering**: Utilize query parameters to filter products and reduce unnecessary data transfer.

3. **Error Handling**: Always check for and handle potential errors in your applications.

4. **Caching**: Cache product data where appropriate to reduce API calls and save energy!



## 🔮 Future Enhancements



We're constantly growing our API, like a well-tended garden. Here's what's on our eco-friendly roadmap:



1. GraphQL support for more flexible querying

2. Real-time stock updates via WebSockets

3. Enhanced filtering options (e.g., by multiple categories, price range)

4. Bulk operations for creating and updating products



Remember, every API call is a step towards a more sustainable e-commerce ecosystem. Happy coding, eco-warriors! 🌿💻🌍