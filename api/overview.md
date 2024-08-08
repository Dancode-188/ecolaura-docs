# 🌿 Ecolaura API: Powering Sustainable E-Commerce



Welcome to the Ecolaura API - the green engine behind our revolutionary sustainable e-commerce platform. This API is designed to be intuitive, powerful, and as eco-friendly as the products we sell. Let's dive into the world of sustainable API design! 🌍🚀



## 🔑 Authentication



We use JWT (JSON Web Tokens) for secure, stateless authentication. It's like a reusable shopping bag for your credentials - efficient and eco-friendly!



To authenticate:



1. Send a POST request to `/api/auth/login/` with your credentials.

2. Receive a JWT token.

3. Include this token in the Authorization header of subsequent requests:

```

  Authorization: Bearer <your_token_here>

```



Remember, sharing is caring, but not when it comes to API tokens! 🙅‍♂️



## 🌱 API Endpoints



Our API endpoints are organized like a well-tended garden. Here's a overview of our main areas:



### 🛍️ Products



- `GET /api/products/`: Fetch a list of sustainable products

- `GET /api/products/{id}/`: Get details of a specific product

- `GET /api/products/categories/`: List product categories



### 👤 Users



- `POST /api/users/`: Register a new eco-warrior

- `GET /api/users/me/`: Retrieve the logged-in user's profile

- `PUT /api/users/me/`: Update user profile



### 🛒 Orders



- `POST /api/orders/`: Place a new order

- `GET /api/orders/`: List user's orders

- `GET /api/orders/{id}/`: Get details of a specific order



### 🌡️ Sustainability



- `GET /api/sustainability/score/{product_id}/`: Get sustainability score for a product

- `GET /api/sustainability/impact/`: Get user's environmental impact



### 🤖 AI Consultant



- `POST /api/ai-consultant/chat/`: Send a message to the AI consultant

- `GET /api/ai-consultant/recommendations/`: Get personalized eco-friendly recommendations



### 🔄 Trade-In



- `POST /api/trade-in/request/`: Submit a trade-in request

- `GET /api/trade-in/estimate/{product_id}/`: Get trade-in value estimate



## 📊 Response Format



Our API responses are as clean and green as our products:


```json

{

 "status": "success",

 "data": {

  // Relevant data here

 },

 "meta": {

  "pagination": {

   "page": 1,

   "per_page": 20,

   "total": 100

  }

 }

}

```



In case of errors, we keep it real:



```json

{

 "status": "error",

 "message": "Oops! Something went wrong.",

 "errors": [

  {

   "field": "email",

   "message": "Please provide a valid email address."

  }

 ]

}

```



## 🌈 Pagination



We paginate list responses to keep things lightweight and efficient. It's like using a reusable water bottle instead of buying plastic ones!



Use `page` and `per_page` query parameters to control pagination:



```

GET /api/products/?page=2&per_page=20

```



## 🚦 Rate Limiting



To keep our servers as green as possible, we implement rate limiting:



- 1000 requests per hour for authenticated users

- 100 requests per hour for unauthenticated requests



Don't worry, we'll let you know how many requests you have left in the response headers.



## 🌱 Versioning



We version our API to ensure smooth sailing as we grow. Include the version in the URL:



```

https://api.ecolaura.com/v1/products/

```



## 🍃 Best Practices



1. **Be Gentle**: Our servers run on renewable energy. The less work they do, the better for the planet!

2. **Cache Wisely**: Save responses when you can. It's like using a reusable shopping bag!

3. **Compress**: Send `Accept-Encoding: gzip` header to receive compressed responses.

4. **Be Specific**: Use fields parameter to request only the data you need:


```

  GET /api/products?fields=id,name,price

```



## 🌿 Grow With Us



Our API is constantly evolving, just like our ecosystem. Check out our [changelog](../release_notes/changelog.md) to stay up-to-date with the latest features and improvements.



Got ideas to make our API even greener? We're all ears! Open an issue or submit a pull request. Together, we can code a more sustainable future! 🌍💻



Remember, every API call you make is a step towards a more sustainable world. Happy coding, eco-warriors! 🚀🌱