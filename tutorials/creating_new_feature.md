# 🌱 Creating a New Feature for Ecolaura



Welcome, eco-innovator! This guide will walk you through the process of adding a new feature to Ecolaura. Just as every new plant contributes to the biodiversity of an ecosystem, your feature will enhance our sustainable e-commerce platform. Let's grow something amazing together! 🌿💻



## 🎯 Overview



Adding a new feature to Ecolaura involves these key steps:

1. Planning and Proposal

2. Environment Setup

3. Implementation

4. Testing

5. Documentation

6. Pull Request

7. Review and Iteration

8. Merge and Deploy



## 🌳 Step 1: Planning and Proposal



Before writing any code, it's crucial to plan your feature:



1. **Identify the Need**: Clearly define the problem your feature solves.

2. **Outline the Solution**: Sketch out how your feature will work.

3. **Discuss with the Team**: Share your idea in our #feature-ideas Slack channel.

4. **Create a Proposal**: Submit a Feature Proposal Issue on GitHub.



Example Feature Proposal:



```markdown

Title: Add Carbon Footprint Calculator for Products



Description:

This feature will calculate and display the carbon footprint for each product, 

helping users make more informed, eco-friendly choices.



Implementation Details:

- Add a `carbon_footprint` field to the Product model

- Create an algorithm to calculate carbon footprint based on materials, 

 manufacturing process, and shipping

- Display carbon footprint on product pages

- Add a filter option for carbon footprint in product search



Endpoints to Add/Modify:

- GET /api/v1/products/{id}/carbon-footprint

- Update GET /api/v1/products to include carbon footprint



Frontend Changes:

- Add carbon footprint display to ProductCard and ProductDetail components

- Add carbon footprint filter to ProductSearch component



Estimated Time: 2 weeks

```



## 🛠️ Step 2: Environment Setup



Ensure your development environment is ready:



1. Fork the Ecolaura repository if you haven't already.

2. Clone your fork:

```

  git clone https://github.com/Dancode-188/ecolaura.git

```

3. Set up your local environment following our [setup guide](setting_up_local_environment.md).

4. Create a new branch for your feature:

```

  git checkout -b feature/carbon-footprint-calculator

```



## 💻 Step 3: Implementation



Now it's time to bring your feature to life!



### Backend Implementation:



1. Add necessary models:



```python

# products/models.py

class Product(models.Model):

  # ... existing fields ...

  carbon_footprint = models.FloatField(null=True, blank=True)



  def calculate_carbon_footprint(self):

    # Implementation of carbon footprint calculation

    pass

```



2. Create or update API endpoints:



```python

# products/views.py

from rest_framework.decorators import api_view

from rest_framework.response import Response



@api_view(['GET'])

def product_carbon_footprint(request, product_id):

  product = get_object_or_404(Product, id=product_id)

  carbon_footprint = product.calculate_carbon_footprint()

  return Response({'carbon_footprint': carbon_footprint})

```



### Frontend Implementation:



1. Update React components:



```jsx

// src/components/ProductCard.js

import React from 'react';



const ProductCard = ({ product }) => (

 <div className="product-card">

  <h2>{product.name}</h2>

  <p>Price: ${product.price}</p>

  <p>Carbon Footprint: {product.carbonFootprint} kg CO2</p>

 </div>

);



export default ProductCard;

```



2. Add new features to existing pages:



```jsx

// src/pages/ProductSearch.js

import React, { useState } from 'react';



const ProductSearch = () => {

 const [carbonFootprintFilter, setCarbonFootprintFilter] = useState(null);



 // ... existing code ...



 return (

  <div>

   {/* ... existing JSX ... */}

   <select onChange={(e) => setCarbonFootprintFilter(e.target.value)}>

    <option value="">All</option>

    <option value="low">Low Carbon Footprint</option>

    <option value="medium">Medium Carbon Footprint</option>

    <option value="high">High Carbon Footprint</option>

   </select>

   {/* ... product list rendering ... */}

  </div>

 );

};

```



## 🧪 Step 4: Testing



Ensure your feature works as expected and doesn't break existing functionality:



1. Write unit tests:



```python

# products/tests.py

from django.test import TestCase

from .models import Product



class ProductCarbonFootprintTest(TestCase):

  def test_carbon_footprint_calculation(self):

    product = Product.objects.create(name="Eco Bottle", price=20.00)

    self.assertIsNotNone(product.calculate_carbon_footprint())

```



2. Write integration tests:



```python

# products/tests.py

from django.test import TestCase

from django.urls import reverse



class ProductAPITest(TestCase):

  def test_carbon_footprint_api(self):

    product = Product.objects.create(name="Eco Bottle", price=20.00)

    response = self.client.get(reverse('product-carbon-footprint', args=[product.id]))

    self.assertEqual(response.status_code, 200)

    self.assertIn('carbon_footprint', response.data)

```



3. Run all tests:

```

  python manage.py test

```



## 📝 Step 5: Documentation



Update relevant documentation:



1. Add API endpoint documentation in `api/endpoints/products.md`

2. Update the product model documentation in `architecture/database_schema.md`

3. Add user-facing feature documentation in `features/carbon_footprint.md`



## 🚀 Step 6: Pull Request



Time to submit your work for review:



1. Commit your changes:

```

  git add .

  git commit -m "Add carbon footprint calculator for products"

```

2. Push to your fork:

```

  git push origin feature/carbon-footprint-calculator

```

3. Open a Pull Request on GitHub, providing a detailed description of your changes.



## 👀 Step 7: Review and Iteration



Work with reviewers to refine your feature:



1. Respond to comments and questions promptly.

2. Make requested changes and push new commits.

3. Ensure all CI checks are passing.



## 🎉 Step 8: Merge and Deploy



Once approved, your feature will be merged:



1. The maintainer will merge your PR into the main branch.

2. Your feature will be deployed in the next release cycle.

3. Monitor the feature in production for any issues.



## 🌱 Best Practices



- Keep your feature focused and avoid scope creep.

- Follow our [coding standards](../development/coding_standards.md).

- Write clear, concise commit messages.

- Keep your PR as small as possible for easier review.

- Be open to feedback and willing to iterate on your design.



## 🤝 Need Help?



If you're stuck or have questions:



1. Check our [FAQ](../troubleshooting/faq.md) for common issues.

2. Ask for help in the #dev-help Slack channel.

3. Reach out to a mentor or senior developer for guidance.



Remember, every great feature starts as a seed of an idea. With care and cultivation, your contribution will help Ecolaura flourish and make a positive impact on the world. Happy coding, eco-warrior! 🌿💻🌍