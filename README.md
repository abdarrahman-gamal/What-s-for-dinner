# What's for dinner?

A single-page recipe browser built with vanilla JavaScript and Bootstrap 5. It cycles through dinner ideas with prep times, ingredient checklists, cooking steps, and nutritional breakdowns.

[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-7952B3?logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## Overview

The app serves as a quick recipe picker. Instead of scrolling through long food blogs, users can click through a collection of meals, check total prep and cook times, switch between ingredients and directions, and check nutritional macros per serving.

It runs entirely in the browser using plain JavaScript and static assets, with no framework dependencies or build tools.

## How it works

- **Recipe cycling:** An internal index tracks the current recipe in an array of objects. Clicking the discovery button increments the counter and loops back to the start when reaching the end of the list, updating the DOM fields in place.
- **Tabbed recipe details:** Bootstrap tabs organize meal information into four separate views:
  - Ingredients: listed items with exact portions.
  - Directions: step-by-step cooking instructions.
  - Nutrition: calories, protein, carbs, fats, fiber, and sodium per serving.
  - Chef tips: notes on heat control, browning, and common ingredient swaps.
- **Cooking time flags:** An alert banner appears automatically if a recipe has `extendedTime: true` (meals taking over 45 minutes), helping users spot slow-cook dishes right away.
- **Two-pane responsive layout:** On mobile screens, the page stacks into a single scrollable card. On wider screens, it expands into a split view with the dish photo on the left and an independently scrollable details panel on the right.

## Tech stack

| Layer | Tool |
| :--- | :--- |
| Markup | Semantic HTML5 |
| Styles | Bootstrap 5.3 and custom CSS variables |
| Icons | FontAwesome 6 |
| Scripting | Vanilla JavaScript (ES6+) |

## Project files

```text
├── css/
│   ├── all.min.css           # FontAwesome
│   ├── bootstrap.min.css     # Bootstrap 5
│   └── style.css             # Custom styles, gradients, and scrollbars
├── js/
│   ├── all.min.js             # FontAwesome runtime
│   ├── bootstrap.bundle.min.js# Bootstrap tab components
│   └── main.js               # Recipe dataset and DOM update logic
├── img/                      # Recipe dish photography
├── index.html                # Base layout and tab markup
└── README.md
```

## Recipe object structure

All recipes are stored inside a data array in `main.js`:

```javascript
{
  name: "Creamy Tuscan Garlic Chicken",
  description: "Pan-seared chicken breasts simmered in a garlic, spinach, and sun-dried tomato cream sauce.",
  image: "img/1.png",
  rating: "4.8",
  reviews: "(445 reviews)",
  prepTime: "20 min",
  cookTime: "15 min",
  servings: "2 people",
  difficulty: "Easy",
  category: "Italian",
  extendedTime: false,
  ingredients: ["2 boneless chicken breasts", "1 cup heavy cream", "..."],
  instructions: ["Season chicken breasts with salt and pepper...", "..."],
  nutrition: {
    calories: "520",
    protein: "42g",
    carbs: "12g",
    fat: "34g",
    fiber: "3g",
    sodium: "620mg"
  },
  tips: ["Pat chicken dry with paper towels before searing to get a better crust."]
}
```