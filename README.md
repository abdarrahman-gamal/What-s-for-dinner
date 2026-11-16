# 🍽️ What's For Dinner? — Dynamic Recipe Discovery Platform

> A lightweight, state-driven client-side web application designed to eliminate mealtime decision fatigue through dynamic DOM manipulation and responsive UI architecture. Built with pure Vanilla JavaScript (ES6+), Bootstrap 5, and modern modular CSS.

---

## 📌 Executive Summary

Every day, millions of people experience decision paralysis over a simple question: *"What should I cook tonight?"* 

**What's For Dinner** solves this by delivering an interactive, distraction-free discovery engine. With a single click, users can cycle through curated, chef-crafted recipes with complete nutritional intelligence, step-by-step preparation workflows, contextual cooking alerts, and pro culinary tips—all rendered in real-time with zero runtime framework dependencies.

---

## ⚡ Core Technical Features

- **Dynamic DOM Rendering Pipeline:** Decoupled data layer from presentation logic. The application ingests a structured JavaScript object schema and declaratively hydrates the DOM elements without full-page reloads.
- **State-Driven Navigation (Circular Buffer):** Implements an index-based pointer state that cycles seamlessly across the recipe dataset with automatic bounds reset (`O(1)` state transition).
- **Context-Aware Alert Engine:** Evaluates recipe metadata dynamically (e.g., `extendedTime: true` for meals requiring >45 mins) and conditionally injects warning banners to prevent unexpected prep delays.
- **Micro-Tabbed Detail Dashboard:** Modular Bootstrap 5 tab system seamlessly switching between:
  - **Ingredients List:** Quantified items with custom numbered badge styling.
  - **Culinary Execution:** Chronological cooking steps with high-contrast sequence markers.
  - **Nutritional Analytics:** 6-metric breakdown (Calories, Protein, Carbs, Fat, Fiber, Sodium).
  - **Pro Chef Tips:** Curated conditional advice tailored to recipe edge-cases.
- **Modern Design System & Token Architecture:** Built on CSS Custom Properties (`:root`), utilizing modern `oklch` color spaces for smooth gradients, clamp-based fluid typography, and consistent spacing units.
- **Fully Responsive & Accessible:** Fluid grid switching effortlessly from a stacked mobile view to a dual-pane desktop card with independent scrollable panels.

---

## 🛠️ Tech Stack & Architecture

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Core Logic** | Vanilla JavaScript (ES6+) | State tracking, dynamic DOM generation, conditional styling logic |
| **Structure** | Semantic HTML5 | Accessible, SEO-friendly layout structure |
| **Styling** | Modern CSS3 & Design Tokens | Custom properties, fluid typography, OKLCH gradient schemes |
| **Grid & Components** | Bootstrap 5.3 | Responsive flexbox grid, navigation bar, and tabbed panes |
| **Iconography** | FontAwesome 6 (Free) | Visual cues for metrics, timings, and interaction elements |

---

## 📂 Project Structure

```bash
├── css/
│   ├── all.min.css           # FontAwesome icon library stylesheet
│   ├── bootstrap.min.css     # Bootstrap 5 layout & utility framework
│   └── style.css             # Custom design tokens, scroll containers & micro-animations
├── js/
│   ├── all.min.js            # FontAwesome SVG/JS engine
│   ├── bootstrap.bundle.min.js # Bootstrap component interactions (Tabs, Navbar)
│   └── main.js               # Recipe data model, state logic & DOM hydration
├── img/                      # Optimized recipe photography & assets
│   ├── 1.png - 6.png         # Recipe hero visuals
│   └── avatar-1.jpg          # User interface profile placeholder
├── index.html                # Semantic entry point and UI skeleton
└── README.md                 # Project technical documentation
```

---

## 📊 Data Schema Definition

Each recipe entity adheres to the following structured JavaScript object model:

```javascript
{
  name: String,            // Title of the dish
  description: String,     // Brief culinary overview
  image: String,           // Relative asset path
  rating: String,          // Community score (e.g., "4.8")
  reviews: String,         // Formatted review count (e.g., "(445 reviews)")
  prepTime: String,        // Preparation duration (e.g., "20 min")
  cookTime: String,        // Active cooking duration (e.g., "15 min")
  servings: String,        // Yield count (e.g., "2 people")
  difficulty: String,      // "Easy" | "Intermediate" | "Hard" (drives dynamic badge color)
  category: String,        // Regional cuisine (Asian, Mediterranean, Egyptian, etc.)
  extendedTime: Boolean,   // Flag triggering the duration warning banner
  ingredients: Array<String>, // List of ingredients with quantities
  instructions: Array<String>,// Step-by-step cooking procedure
  nutrition: {             // Nutritional breakdown per serving
    calories: String,
    protein: String,
    carbs: String,
    fat: String,
    fiber: String,
    sodium: String
  },
  tips: Array<String>      // Edge-case culinary recommendations
}
```

---

## 🚀 Getting Started

### Prerequisites
No build steps, package managers, or server installations required. This project runs directly in any modern web browser.

### Quick Run
1. Clone or download the repository:
   ```bash
   git clone https://github.com/your-username/whats-for-dinner.git
   ```
2. Navigate into the project directory:
   ```bash
   cd whats-for-dinner
   ```
3. Open `index.html` in your browser:
   - On Windows:
     ```powershell
     Start-Process index.html
     ```
   - Or run with a lightweight local server (e.g., VS Code Live Server / `npx serve`).

---

## 🔮 Scalability & Future Roadmap

- [ ] **State Persistence:** Cache bookmarked/favorite recipes into browser `localStorage`.
- [ ] **External API Integration:** Connect to Spoonacular / TheMealDB API for infinite recipe streaming.
- [ ] **Dietary & Allergen Filtering:** Implement multi-filter criteria (Keto, Vegan, High-Protein, Under 30 Mins).
- [ ] **Interactive Portion Scaler:** Dynamically recalculate ingredient quantities based on user-selected serving sizes.

---

## 👨‍💻 Author

**Abdarrahman Gamal**  
Frontend Developer & Web Engineering Enthusiast  
- **LinkedIn:** [Abdarrahman Gamal](https://linkedin.com)  
- **GitHub:** [@your-github](https://github.com)

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
