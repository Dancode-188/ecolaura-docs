# 🖋️ Ecolaura Typography: Cultivating Clarity in Communication



Welcome to Ecolaura's Typography guide! Just as different plants in a forest contribute to its biodiversity, our carefully selected typefaces work together to create a harmonious and effective communication ecosystem. Let's explore the letterforms that bring our sustainable message to life! 🌿📚



## 🌍 Overview



Our typography choices are rooted in our commitment to clarity, accessibility, and sustainability. We've selected fonts that are:

- Easy to read across various devices and screen sizes

- Reflective of our eco-friendly brand identity

- Versatile enough to convey both professionalism and warmth

- Optimized for digital environments to reduce data usage



## 🌳 Our Type System



### Primary Font: Roboto



Roboto is our primary workhorse, used for body text and most interface elements. Its clean, modern lines and excellent readability make it perfect for our digital forest.



```css

font-family: 'Roboto', sans-serif;

```



### Secondary Font: Playfair Display



Playfair Display adds a touch of elegance and nature-inspired flourish to our headings and special text elements.



```css

font-family: 'Playfair Display', serif;

```



## 📏 Font Sizes and Hierarchy



We use a modular scale with a base size of 16px and a ratio of 1.25 to create a harmonious hierarchy:



| Element          | Size | Weight | Font Family      |

|------------------|------|--------|------------------|

| Body Text        | 16px | 400    | Roboto           |

| H1               | 39px | 700    | Playfair Display |

| H2               | 31px | 700    | Playfair Display |

| H3               | 25px | 600    | Roboto           |

| H4               | 20px | 600    | Roboto           |

| Small/Caption    | 13px | 400    | Roboto           |



```css

/* Example CSS */

body {

 font-family: 'Roboto', sans-serif;

 font-size: 16px;

 line-height: 1.5;

}



h1 {

 font-family: 'Playfair Display', serif;

 font-size: 2.441rem;

 font-weight: 700;

}



/* ... other heading styles ... */

```



## 🌿 Font Weights and Styles



- **Roboto**: We primarily use Regular (400) and Semi-Bold (600)

- **Playfair Display**: We use Bold (700) for impactful headings



Italic styles are used sparingly, primarily for emphasis or to denote scientific names of plants.



## 📐 Line Heights and Letter Spacing



- Body text: 1.5 times the font size

- Headings: 1.2 times the font size

- Letter spacing: -0.5px for headings, normal for body text



```css

p {

 line-height: 1.5;

}



h1, h2, h3, h4, h5, h6 {

 line-height: 1.2;

 letter-spacing: -0.5px;

}

```



## ♿ Accessibility Considerations



- Maintain a minimum body text size of 16px

- Ensure sufficient contrast between text and background colors

- Use real text instead of text within images

- Avoid all-caps text for long passages

- Implement proper heading structure for screen readers



## 🌻 Typography in Context



### Product Titles

```html

<h2 class="product-title">Eco-Friendly Water Bottle</h2>

```

```css

.product-title {

 font-family: 'Playfair Display', serif;

 font-size: 1.953rem;

 font-weight: 700;

 color: #4CAF50; /* Eco Green */

}

```



### Call-to-Action Buttons

```html

<button class="cta-button">Shop Now</button>

```

```css

.cta-button {

 font-family: 'Roboto', sans-serif;

 font-size: 1rem;

 font-weight: 600;

 text-transform: uppercase;

 letter-spacing: 1px;

}

```



## ✅ Do's and Don'ts



Do's:

- Use the appropriate font family for each context (Roboto for body, Playfair Display for featured headings)

- Maintain consistent font sizes and weights across similar elements

- Use proper semantic HTML tags (`<h1>`, `<h2>`, `<p>`, etc.) for correct document structure

- Optimize font loading for performance (e.g., use font-display: swap)



Don'ts:

- Don't mix too many font sizes or weights in a single design

- Avoid using Playfair Display for long blocks of text

- Don't use font sizes smaller than 13px

- Avoid relying solely on color to convey meaning in text



## 🌱 Reflecting Our Brand and Values



Our typography choices embody Ecolaura's core values:



- **Roboto**: Its clean, efficient design reflects our commitment to sustainability and no-waste practices

- **Playfair Display**: The organic, slightly playful serifs echo the natural world we're working to protect

- **Size Hierarchy**: Our clear, structured approach to size represents our organized efforts towards a sustainable future

- **Readability Focus**: Prioritizing legibility demonstrates our commitment to clear communication and transparency



By consistently applying these typography guidelines, we create a reading experience that's as refreshing and harmonious as a walk through a well-tended forest. Our words become the leaves and branches that form our digital canopy, inviting users to explore and engage with our sustainable vision.



Remember, good typography is like a healthy ecosystem – each element has its place, and together they create a balanced, thriving whole. Let's use our fonts wisely to grow a more sustainable future! 🌿📝🌍