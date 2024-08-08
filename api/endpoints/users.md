# 👤 Ecolaura API: User Endpoints



Welcome to the user section of Ecolaura's API! These endpoints are the foundation of our eco-friendly community, allowing users to join, engage, and grow in their sustainability journey. Let's dive into how we nurture our user ecosystem! 🌱👥



## 📋 Endpoints Overview



- [Register User](#register-user)

- [Login User](#login-user)

- [Logout User](#logout-user)

- [Get User Profile](#get-user-profile)

- [Update User Profile](#update-user-profile)

- [Change Password](#change-password)

- [Request Password Reset](#request-password-reset)

- [Reset Password](#reset-password)

- [Get User Sustainability Impact](#get-user-sustainability-impact)

- [Get User Order History](#get-user-order-history)

- [Update User Preferences](#update-user-preferences)



## 🔐 Authentication



All endpoints require authentication unless specified otherwise. Include the JWT token in the Authorization header:

```

Authorization: Bearer <your_token_here>

```



## 📁 Endpoints



### Register User



Plant a new seed in our eco-community! 🌱



```

POST /api/v1/users/register

```



Request Body:

```json

{

 "email": "green_warrior@example.com",

 "password": "EcoFriendly123!",

 "first_name": "Green",

 "last_name": "Warrior"

}

```



Response:

```json

{

 "message": "User registered successfully",

 "user_id": "user_123abc"

}

```



### Login User



Water your account with authentication! 💧



```

POST /api/v1/users/login

```



Request Body:

```json

{

 "email": "green_warrior@example.com",

 "password": "EcoFriendly123!"

}

```



Response:

```json

{

 "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",

 "user": {

  "id": "user_123abc",

  "email": "green_warrior@example.com",

  "first_name": "Green",

  "last_name": "Warrior"

 }

}

```



### Logout User



Time to rest and photosynthesize! 🌞



```

POST /api/v1/users/logout

```



Response:

```json

{

 "message": "Logged out successfully"

}

```



### Get User Profile



Check on your growing eco-impact! 🌿



```

GET /api/v1/users/profile

```



Response:

```json

{

 "id": "user_123abc",

 "email": "green_warrior@example.com",

 "first_name": "Green",

 "last_name": "Warrior",

 "joined_date": "2023-01-15T00:00:00Z",

 "sustainability_score": 85

}

```



### Update User Profile



Prune and shape your profile! ✂️🌳



```

PUT /api/v1/users/profile

```



Request Body:

```json

{

 "first_name": "Super",

 "last_name": "Green Warrior"

}

```



Response:

```json

{

 "message": "Profile updated successfully",

 "user": {

  "id": "user_123abc",

  "email": "green_warrior@example.com",

  "first_name": "Super",

  "last_name": "Green Warrior"

 }

}

```



### Change Password



Fortify your eco-fortress! 🏰



```

PUT /api/v1/users/change-password

```



Request Body:

```json

{

 "current_password": "EcoFriendly123!",

 "new_password": "SuperEcoFriendly456!"

}

```



Response:

```json

{

 "message": "Password changed successfully"

}

```



### Request Password Reset



Forgot your key to the green kingdom? Let's grow a new one! 🔑🌱



```

POST /api/v1/users/request-password-reset

```



Request Body:

```json

{

 "email": "green_warrior@example.com"

}

```



Response:

```json

{

 "message": "Password reset instructions sent to your email"

}

```



### Reset Password



Replant your password with a fresh, strong seedling! 🌱💪



```

POST /api/v1/users/reset-password

```



Request Body:

```json

{

 "token": "reset_token_received_via_email",

 "new_password": "NewEcoPassword789!"

}

```



Response:

```json

{

 "message": "Password reset successfully"

}

```



### Get User Sustainability Impact



Measure the size of your green footprint! 👣🌍



```

GET /api/v1/users/sustainability-impact

```



Response:

```json

{

 "user_id": "user_123abc",

 "total_green_points": 1500,

 "trees_saved": 5,

 "co2_reduced": 100,

 "plastic_saved": 50,

 "top_badge": "Eco Warrior"

}

```



### Get User Order History



Revisit your journey through the eco-marketplace! 🛒🌿



```

GET /api/v1/users/orders

```



Query Parameters:

- `page`: Page number (default: 1)

- `per_page`: Items per page (default: 10)



Response:

```json

{

 "orders": [

  {

   "id": "order_789xyz",

   "date": "2023-05-20T14:30:00Z",

   "total_amount": 150.00,

   "status": "delivered",

   "items": [

    {

     "product_id": "prod_456def",

     "name": "Bamboo Toothbrush Set",

     "quantity": 2,

     "price": 25.00

    }

   ]

  }

 ],

 "pagination": {

  "current_page": 1,

  "total_pages": 5,

  "total_items": 47

 }

}

```



### Update User Preferences



Customize your eco-journey! 🎨🌿



```

PUT /api/v1/users/preferences

```



Request Body:

```json

{

 "newsletter_subscription": true,

 "preferred_categories": ["zero-waste", "organic-food"],

 "sustainability_goal": "reduce_plastic"

}

```



Response:

```json

{

 "message": "Preferences updated successfully",

 "preferences": {

  "newsletter_subscription": true,

  "preferred_categories": ["zero-waste", "organic-food"],

  "sustainability_goal": "reduce_plastic"

 }

}

```



## 🌿 Best Practices



1. Always validate and sanitize user input

2. Use HTTPS for all API calls to ensure data privacy

3. Implement rate limiting to prevent abuse

4. Keep authentication tokens secure and implement token refresh mechanism

5. Provide clear error messages for better user experience



## 🐛 Error Handling



Our API serves eco-friendly error responses:



```json

{

 "error": {

  "code": "INVALID_INPUT",

  "message": "The provided email is not valid. Please check and try again."

 }

}

```



Common HTTP status codes:

- 400: Bad Request

- 401: Unauthorized

- 403: Forbidden

- 404: Not Found

- 429: Too Many Requests

- 500: Internal Server Error



## 🌱 Future Growth



We're constantly evolving our user API, like a thriving ecosystem:



1. Social authentication (Google, Facebook)

2. Two-factor authentication for enhanced security

3. User activity feed endpoint

4. Expanded sustainability impact metrics

5. Integration with external carbon footprint calculators



Remember, every API call is nurturing our growing community of eco-warriors. Let's code for a greener future! 🌍💻🌱