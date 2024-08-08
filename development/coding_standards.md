# 🌿 Ecolaura Coding Standards: Cultivating Clean Code



Welcome to Ecolaura's coding standards guide! Just as we curate sustainable products, we cultivate clean, efficient code. These standards ensure our codebase grows as harmoniously as a well-tended garden. Let's dig in! 🌱👩‍💻👨‍💻



## 🎯 Our Coding Philosophy



At Ecolaura, we believe code should be:

- As clean as the environment we're striving to protect

- As efficient as nature's most optimized processes

- As readable as a well-written book on sustainability



## 🌳 General Guidelines



1. **DRY (Don't Repeat Yourself)**: Reuse code like you'd reuse a shopping bag.

2. **KISS (Keep It Simple, Sustainable)**: Simple code is sustainable code.

3. **YAGNI (You Aren't Gonna Need It)**: Don't pollute the codebase with unnecessary features.

4. **Comment wisely**: Good code is self-documenting, but complex logic deserves explanation.



## 🍃 Naming Conventions



- **Variables**: Use descriptive, lowercase names with underscores for Python (snake_case) and camelCase for JavaScript.

 ```python

 user_email = "green@ecolaura.com"   # Python

 ```

```javascript

 let userEmail = "green@ecolaura.com";  // JavaScript

```



- **Functions/Methods**: Use verb phrases that describe the action.

```python

 def calculate_carbon_footprint(product):

```

```javascript

 function calculateCarbonFootprint(product) {

```



- **Classes**: Use PascalCase and noun phrases.

```python

 class SustainabilityScore:

```

```javascript

 class SustainabilityScore {

```



- **Constants**: Use uppercase with underscores.

 ```python

 MAX_PRODUCT_WEIGHT = 100 # kg

```

```javascript

 const MAX_PRODUCT_WEIGHT = 100; // kg

```



## 🌿 Language-Specific Guidelines



### Python (Django Backend)



1. Follow PEP 8 guidelines. It's the Python equivalent of ecological balance.

2. Use type hints. They're like labels on recycling bins – they make everything clearer.

```python

  def get_product_sustainability_score(product_id: int) -> float:

```

3. Use f-strings for string formatting. They're efficient and readable.

```python

  log.info(f"Calculated sustainability score for product {product_id}: {score}")

```



### JavaScript (React Frontend)



1. Use ES6+ features. They're the latest in code evolution.

2. Prefer const over let, and avoid var like single-use plastics.

3. Use async/await for asynchronous operations. Promises are good, but async/await is the future.

```javascript

  async function fetchSustainabilityScore(productId) {

   try {

    const response = await api.get(`/sustainability-score/${productId}`);

    return response.data;

   } catch (error) {

    console.error('Error fetching sustainability score:', error);

   }

  }

```



## 🧪 Testing



- Write tests like you're protecting endangered species – thoroughly and with care.

- Aim for at least 80% code coverage, but remember, quality over quantity.

- Test edge cases like you're preparing for climate extremes.



### Python Tests



Use pytest for its simplicity and power.



```python

def test_sustainability_score_calculation():

  product = Product(name="Eco Friendly Water Bottle", weight=0.5)

  score = calculate_sustainability_score(product)

  assert 0 <= score <= 100, "Sustainability score should be between 0 and 100"

```



### JavaScript Tests



Use Jest and React Testing Library for frontend tests.



```javascript

test('Sustainability score is displayed correctly', () => {

 render(<ProductCard product={mockProduct} />);

 const scoreElement = screen.getByTestId('sustainability-score');

 expect(scoreElement).toHaveTextContent('85');

});

```



## 📏 Code Formatting



- Use tools to automate formatting. It's like using renewable energy – effortless and consistent.

- For Python: Use Black. It's opinionated, like that one friend who always insists on using reusable bags.

- For JavaScript: Use Prettier. It makes your code pretty, like a well-designed eco-friendly product.



## 🌴 Git Commit Messages



Write commit messages like you're writing a micro-blog about saving the planet:



```

feat: Add carbon footprint calculator to product page



- Integrate with sustainability API

- Display result using an intuitive tree icon scale

- Add unit tests for calculation logic



Closes #123

```



- Start with a type: feat, fix, docs, style, refactor, test, chore

- Provide a concise summary in the present tense

- Add bullet points for multiple changes

- Reference issue numbers where applicable



## 🚀 Code Reviews



- Review code like you're inspecting products for our store – thoroughly and constructively.

- Use inline comments to suggest improvements or ask questions.

- Approve only when the code is as clean as we want our oceans to be.



## 🌱 Continuous Improvement



These standards, like our commitment to sustainability, are ever-evolving. If you have suggestions for improvements, let's discuss them. After all, sustainability is a collective effort!



Remember, every line of code we write is a step towards a more sustainable future. Let's make it count! 🌍💻🌱