# 🌱 Ecolaura Unit Testing: Nurturing Code Quality



Welcome to Ecolaura's Unit Testing guide! Just as a healthy ecosystem relies on the well-being of its smallest organisms, our codebase thrives on well-crafted unit tests. Let's explore how we ensure the robustness of our sustainable e-commerce platform, one test at a time! 🌿🧪



## 🌳 Why Unit Testing Matters



Unit testing is the foundation of our code quality ecosystem:

- Catches bugs early in the development cycle

- Facilitates refactoring and improvements

- Serves as living documentation for code behavior

- Enhances confidence in code changes



Like nurturing seedlings, investing time in unit tests helps our codebase grow strong and resilient.



## 🛠️ Tools of the Trade



We use different testing frameworks for our frontend and backend, each chosen for its efficiency and ecosystem compatibility:



### Frontend: Jest + React Testing Library

```javascript

import React from 'react';

import { render, screen } from '@testing-library/react';

import SustainabilityScore from './SustainabilityScore';



test('renders sustainability score correctly', () => {

 render(<SustainabilityScore score={85} />);

 const scoreElement = screen.getByText(/85/i);

 expect(scoreElement).toBeInTheDocument();

});

```



### Backend: pytest

```python

import pytest

from ecolaura.models import Product

from ecolaura.services import calculate_sustainability_score



def test_sustainability_score_calculation():

  product = Product(name="Eco-Friendly Water Bottle", materials=["recycled plastic"])

  score = calculate_sustainability_score(product)

  assert 80 <= score <= 100, "Eco-friendly products should have high sustainability scores"

```



## 🌿 Best Practices for Unit Testing



1. **Test One Thing at a Time**: Like isolating variables in an experiment, each test should focus on a single behavior.



2. **Use Descriptive Test Names**: Your test names should read like a forest trail guide, clearly describing the path of execution.



3. **Arrange-Act-Assert**: Structure your tests like the growth cycle of a plant:

  - Arrange: Set up the test conditions

  - Act: Perform the action being tested

  - Assert: Verify the results



4. **Keep Tests Independent**: Each test should be like a self-contained ecosystem, not relying on other tests to run.



5. **Mock External Dependencies**: Use mocking to simulate external systems, like creating a controlled environment for an experiment.



6. **Test Edge Cases**: Don't just test the sunny day scenarios; consider drought and flood conditions too!



7. **Maintain Test Hygiene**: Regularly review and refactor tests to keep them clean and efficient.



## 🌻 Examples of Ecolaura Unit Tests



### Testing Product Sustainability Score (Backend)

```python

import pytest

from ecolaura.models import Product

from ecolaura.services import sustainability_service



def test_product_sustainability_score():

  # Arrange

  product = Product(

    name="Bamboo Toothbrush",

    materials=["bamboo", "nylon bristles"],

    packaging="recyclable paper"

  )

  # Act

  score = sustainability_service.calculate_score(product)

  # Assert

  assert 75 <= score <= 100, f"Expected high sustainability score, got {score}"

@pytest.mark.parametrize("materials,expected_range", [

  (["plastic"], (0, 50)),

  (["recycled plastic"], (50, 75)),

  (["bamboo"], (75, 100))

])

def test_sustainability_score_materials(materials, expected_range):

  product = Product(name="Test Product", materials=materials)

  score = sustainability_service.calculate_score(product)

  assert expected_range[0] <= score <= expected_range[1], \

    f"Score {score} not in expected range {expected_range} for materials {materials}"

```



### Testing Shopping Cart Component (Frontend)

```javascript

import React from 'react';

import { render, fireEvent, screen } from '@testing-library/react';

import ShoppingCart from './ShoppingCart';



test('adding item increases quantity', () => {

 // Arrange

 render(<ShoppingCart />);

 const addButton = screen.getByText('+');

 const quantityDisplay = screen.getByTestId('quantity');



 // Act

 fireEvent.click(addButton);



 // Assert

 expect(quantityDisplay).toHaveTextContent('1');

});



test('removing item decreases quantity', () => {

 // Arrange

 render(<ShoppingCart initialQuantity={2} />);

 const removeButton = screen.getByText('-');

 const quantityDisplay = screen.getByTestId('quantity');



 // Act

 fireEvent.click(removeButton);



 // Assert

 expect(quantityDisplay).toHaveTextContent('1');

});

```



## 🏃‍♂️ Running Unit Tests



### Frontend (React)

```bash

npm test

```



### Backend (Django)

```bash

python manage.py test

```



Interpret results like reading the health of an ecosystem. Green passes are thriving areas, while red failures indicate spots needing attention.



## 🔄 CI/CD Integration



Our CI/CD pipeline runs unit tests automatically on every push:



1. Tests run in parallel to speed up the process

2. Failed tests block merging to protect our main branch ecosystem

3. Test coverage reports are generated to identify untested areas



## 🌱 Cultivating a Testing Culture



Remember, a robust test suite is like a thriving forest – it takes time to grow but provides immense value. Encourage your fellow developers to contribute to this ecosystem by:



- Writing tests for new features

- Adding tests when fixing bugs

- Celebrating high test coverage



By nurturing our unit tests, we ensure that Ecolaura remains a resilient, sustainable platform. Happy testing, eco-developers! 🌿🧪🌍