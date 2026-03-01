# 🛒 Online Store

A full-featured e-commerce web application built with Django. 
Users can browse products,
filter by category, brand,
price and rating,
add items to a cart,
and complete purchases.
Authenticated users can also leave reviews with star ratings.

> This project was built as a final assignment for a web development course.

---

## 📸 Features

- **Product Listing** — Browse all products displayed as cards with image, name, price, and rating
- **Search & Filter** — Filter by category, brand, price range, and minimum rating
- **Product Detail Page** — View full product info with tabbed layout (Details / Reviews) and image gallery
- **Shopping Cart** — Add, update quantity, and remove items; total price calculated automatically
- **Purchase Flow** — Buy all cart items at once with automatic stock management
- **Reviews & Ratings** — Authenticated users can leave star ratings and text reviews via a modal
- **User Authentication** — Register, login, and logout functionality
- **Admin Panel** — Full Django admin support for managing products, categories, brands

---

## 🛠 Tech Stack

| Technology | Why it's used |
|------------|--------------|
| **Python** | Main programming language |
| **Django** | Web framework — handles URLs, views, database, and authentication |
| **SQLite3** | Database — stores all products, users, carts, and reviews |
| **HTML/CSS** | Frontend — structure and styling of all pages |
| **JavaScript** | Makes tabs, modal, and star selector interactive |
| **Pillow** | Python library needed for uploading and handling product images |

---



## 📁 Project Structure
```
mysite/
├── conf/                   # Project configuration (settings, main URLs)
│   ├── settings.py         # All Django settings (database, apps, timezone...)
│   └── urls.py             # Main URL router — sends requests to store/urls.py
│
├── store/                  # The main app — all logic lives here
│   ├── migrations/         # Database change history (auto-generated)
│   ├── static/store/
│   │   └── style.css       # All CSS styles for every page
│   ├── templates/store/
│   │   ├── base.html       # Base template — navbar, messages (all pages extend this)
│   │   ├── index.html      # Home page — product grid + filters
│   │   ├── product_detail.html  # Product page — tabs, modal, gallery
│   │   ├── cart.html       # Cart page — items, quantity, buy button
│   │   ├── login.html      # Login form
│   │   └── register.html   # Register form
│   ├── models.py           # Database models — defines all tables
│   ├── views.py            # Business logic — what happens on each page
│   ├── urls.py             # URL patterns for the store app
│   ├── admin.py            # Admin panel configuration
│   └── context_processors.py  # Cart count — available on every page
│
├── media/                  # Uploaded product images (not included in repo)
├── db.sqlite3              # The database file
├── manage.py               # Django command-line tool
└── requirements.txt        # List of required Python packages
```

---

## 📦 Models (Database Tables)

| Model | What it stores |
|-------|---------------|
| `Category` | Product categories — e.g. Phones, Laptops, Watches |
| `Brand` | Product brands — e.g. Apple, Samsung, Google |
| `Product` | The product itself — name, price, stock, image, category, brand |
| `ProductImage` | Extra images for a product (one product can have many images) |
| `Review` | A user's review — full name, star rating, comment |
| `Cart` | One cart per user (automatically created on first add) |
| `CartItem` | One row per product in the cart — stores product + quantity |

---

## 🔐 Admin Panel

Access at `http://127.0.0.1:8000/admin/`

From the admin panel you can:
- Add, edit, and delete products (with multiple images in one form)
- Manage categories and brands
- View all carts, cart items, and reviews

---

## 🔄 How It Works (Simple Flow)
```
User visits a page
      ↓
conf/urls.py receives the request
      ↓
store/urls.py matches the URL to a View
      ↓
views.py runs the logic (reads/writes database via models.py)
      ↓
A template (HTML file) is filled with data and sent back
      ↓
User sees the page (styled by style.css)
```


## 👤 Author

**Giorgi Ugrekhelidze**
