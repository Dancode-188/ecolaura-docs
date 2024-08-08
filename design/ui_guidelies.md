# 🎨 Ecolaura UI Guidelines: Designing for Sustainability



Welcome to Ecolaura's UI Guidelines! Just as nature thrives on harmony and balance, our user interface embodies these principles to create a seamless, intuitive, and visually appealing experience. Let's dive into the elements that make our design as sustainable as our products! 🌿💻



## 🌍 Design Philosophy



Our design philosophy is rooted in three core principles:



1. **Sustainability**: Our UI reflects our commitment to the environment.

2. **Simplicity**: Clean, intuitive interfaces that don't overwhelm the user.

3. *\Accessibility**: Designs that are inclusive and usable for all.



## 🎨 Color Palette



Our colors are inspired by nature, creating a calming and eco-friendly atmosphere.



### Primary Colors



- **Leaf Green**: `#4CAF50` - Used for primary actions and key UI elements

- **Sky Blue**: `#03A9F4` - Used for secondary actions and accents

- **Earth Brown**: `#795548` - Used for grounding elements and text



### Secondary Colors



- **Sunflower Yellow**: `#FFC107` - Used for warnings and highlights

- **Coral Red**: `#FF5722` - Used sparingly for critical actions or errors



### Neutrals



- **Off-White**: `#FAFAFA` - Primary background color

- **Light Gray**: `#E0E0E0` - Secondary background, borders

- **Dark Gray**: `#616161` - Primary text color



### Usage



```css

:root {

 --color-primary: #4CAF50;

 --color-secondary: #03A9F4;

 --color-tertiary: #795548;

 --color-warning: #FFC107;

 --color-error: #FF5722;

 --color-background: #FAFAFA;

 --color-background-secondary: #E0E0E0;

 --color-text: #616161;

}

```



## 🖋 Typography



We use a combination of serif and sans-serif fonts to create a natural, readable interface.



- **Headings**: Playfair Display (serif)

- **Body Text**: Open Sans (sans-serif)



```css

@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&family=Playfair+Display:wght@700&display=swap');



body {

 font-family: 'Open Sans', sans-serif;

 font-size: 16px;

 line-height: 1.5;

 color: var(--color-text);

}



h1, h2, h3, h4, h5, h6 {

 font-family: 'Playfair Display', serif;

 font-weight: 700;

}

```



## 📏 Layout and Grid System



We use a 12-column grid system for flexible and consistent layouts across devices.



```css

.container {

 display: grid;

 grid-template-columns: repeat(12, 1fr);

 gap: 20px;

}

```



## 🧩 Component Library



Our component library is like a well-balanced ecosystem. Here are some key components:



### Buttons



```html

<button class="btn btn-primary">Primary Action</button>

<button class="btn btn-secondary">Secondary Action</button>

```



```css

.btn {

 padding: 10px 20px;

 border-radius: 5px;

 font-weight: 600;

 text-transform: uppercase;

}



.btn-primary {

 background-color: var(--color-primary);

 color: white;

}



.btn-secondary {

 background-color: var(--color-secondary);

 color: white;

}

```



### Cards



```html

<div class="card">

 <img src="product-image.jpg" alt="Eco-friendly Product">

 <div class="card-content">

  <h3>Product Name</h3>

  <p>Product description goes here.</p>

  <button class="btn btn-primary">Add to Cart</button>

 </div>

</div>

```



```css

.card {

 background-color: white;

 border-radius: 8px;

 box-shadow: 0 2px 4px rgba(0,0,0,0.1);

 overflow: hidden;

}



.card-content {

 padding: 20px;

}

```



## 🖼 Iconography



We use a custom icon set inspired by nature and sustainability. Icons should be simple, recognizable, and consistent in style.



```html

<span class="icon icon-leaf"></span>

<span class="icon icon-recycle"></span>

```



```css

.icon {

 display: inline-block;

 width: 24px;

 height: 24px;

 background-size: contain;

 background-repeat: no-repeat;

 background-position: center;

}



.icon-leaf {

 background-image: url('path/to/leaf-icon.svg');

}



.icon-recycle {

 background-image: url('path/to/recycle-icon.svg');

}

```



## ♿ Accessibility Guidelines



1. Maintain a color contrast ratio of at least 4.5:1 for normal text and 3:1 for large text.

2. Use semantic HTML elements (`<nav>`, `<header>`, `<main>`, etc.).

3. Provide alternative text for images and icons.

4. Ensure keyboard navigation for all interactive elements.

5. Use ARIA labels where necessary.



## 📱 Responsive Design Principles



1. Mobile-first approach

2. Flexible grids and layouts

3. Responsive images

4. Touch-friendly tap targets (minimum 44x44 pixels)



```css

@media (max-width: 768px) {

 .container {

  grid-template-columns: repeat(6, 1fr);

 }

}



@media (max-width: 480px) {

 .container {

  grid-template-columns: repeat(4, 1fr);

 }

}

```



## ✅ Do's and Don'ts



### Do's

- Use the defined color palette consistently

- Maintain ample white space for clarity

- Use icons to enhance understanding

- Ensure all interactive elements have clear hover and focus states



### Don'ts

- Don't use colors not defined in the palette

- Avoid cluttered layouts

- Don't use low-contrast text-background combinations

- Avoid using all-caps for body text



## 🌱 Sustainability in Design



Remember, sustainable design goes beyond aesthetics:

1. Optimize images and assets to reduce data transfer

2. Design with performance in mind to reduce energy consumption

3. Create interfaces that encourage sustainable user behaviors



## 🔄 Continuous Improvement



Our UI guidelines, like nature, are ever-evolving. We encourage feedback and suggestions to make our design system more efficient, accessible, and sustainable.



Remember, good design is like a thriving ecosystem - balanced, harmonious, and nurturing for all its users. Happy designing, eco-warriors! 🎨🌿🌍