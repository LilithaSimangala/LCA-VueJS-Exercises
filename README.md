# Cooking Masterclass Checkout (Vue.js)

## 📌 Project Overview
This project is a Vue.js checkout simulation for Cooking Masterclass.  
It allows users to browse cooking courses, add them to a cart, adjust quantities, and view live pricing updates including tax and totals.

The goal of this project is to demonstrate component-based architecture, props, events, computed properties, and basic state management in Vue 3.

---

## 🚀 Features

- Browse cooking courses (catalogue)
- Add courses to cart
- Increase and decrease item quantities
- Remove items from cart
- Sold-out course handling
- Live subtotal, tax (15%), and grand total calculation
- Empty cart message
- Responsive layout (desktop & mobile)

---

## 🧩 Components Structure

- `App.vue` → Main state management (courses, cart, totals)
- `CourseCatalogue.vue` → Displays list of courses
- `CourseCard.vue` → Individual course display
- `ShoppingCart.vue` → Cart overview + totals
- `CartItem.vue` → Individual cart item controls

---

## ⚙️ Installation & Setup

2. Run development server
npm run dev
3. Open in browser
http://localhost:5173/
🛠️ Tech Stack
Vue 3
Vite
JavaScript
HTML/CSS
📸 Screenshot

 <img width="1920" height="1080" alt="Screenshot (444)" src="https://github.com/user-attachments/assets/fec11122-7cdd-46b1-9984-e25a3a3c397f" />

📂 Project Structure
src/
 ├── components/
 │    ├── CourseCatalogue.vue
 │    ├── CourseCard.vue
 │    ├── ShoppingCart.vue
 │    └── CartItem.vue
 ├── App.vue
 ├── main.js
 └── style.css



### 1. Install dependencies
```bash
npm install
