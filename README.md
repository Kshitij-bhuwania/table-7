
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Table 7 - Menu</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; background: #f8f9fa; }
    h1 { color: #8e44ad; text-align: center; }
    .category-title { color: #8e44ad; border-bottom: 2px solid #8e44ad; padding-bottom: 5px; margin-top: 25px; }
    .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 15px; margin-top: 15px; }
    .card { background: white; border: 1px solid #ddd; padding: 12px; border-radius: 8px; text-align: center; box-shadow: 0 2px 4px rgba(0,0,0,0.05); }
    .card h4 { margin: 5px 0; font-size: 15px; }
    .price { color: #27ae60; font-weight: bold; margin: 8px 0; }
    button { padding: 6px 12px; border: none; border-radius: 4px; font-weight: bold; cursor: pointer; }
    .btn-add { background: #28a745; color: white; }
    .btn-add:disabled { background: #b2bec3; }
    .btn-remove { background: #dc3545; color: white; margin-left: 5px; }
    .nav-btn { display: block; width: max-content; margin: 30px auto; background: #8e44ad; color: white; text-decoration: none; padding: 12px 25px; border-radius: 6px; font-weight: bold; }
  </style>
</head>
<body>

  <h1>🟣 Table 7 - Select Items</h1>
  
  <div id="menuContainer"></div>

  <a href="https://kshitij-bhuwania.github.io/table-7-checkout/" class="nav-btn">View Table 7 Cart & Total (Page 7) &rarr;</a>

  <script>
    const TABLE_KEY = "cart_table_7";
    
    // Complete Menu Data Extracted from Menu Images
    const menuData = [
      {
        category: "TEA & COFFEE",
        items: [
          { id: 1, name: "Kadak Tea", price: 20 },
          { id: 2, name: "Ginger Tea", price: 25 },
          { id: 3, name: "Elaichi Tea", price: 25 },
          { id: 4, name: "Masala Tea", price: 25 },
          { id: 5, name: "Cloves Tea", price: 25 },
          { id: 6, name: "Coffee", price: 30 },
          { id: 7, name: "Chocolate Tea", price: 35 },
          { id: 8, name: "Honey Ginger Tea", price: 35 },
          { id: 9, name: "Chocolate Coffee", price: 50 },
          { id: 10, name: "Hot Chocolate", price: 60 }
        ]
      },
      {
        category: "MAGGI FOREST",
        items: [
          { id: 11, name: "Veggie Maggi", price: 50 },
          { id: 12, name: "Punjabi Tadka Maggi", price: 50 },
          { id: 13, name: "Chilli Garlic Maggi", price: 50 },
          { id: 14, name: "Tandoori Maggi", price: 65 },
          { id: 15, name: "Mexican Maggi", price: 65 },
          { id: 16, name: "Butter Maggi", price: 65 },
          { id: 17, name: "Creamy Maggi", price: 75 },
          { id: 18, name: "Schezwan Maggi", price: 80 },
          { id: 19, name: "Masala Maggi", price: 80 },
          { id: 20, name: "Corn & Cheese Maggi", price: 90 },
          { id: 21, name: "Cheese Chilli Maggi", price: 90 },
          { id: 22, name: "Veg Paneer Maggi", price: 100 },
          { id: 23, name: "Mushroom Maggi", price: 100 }
        ]
      },
      {
        category: "BURGER BOOK",
        items: [
          { id: 24, name: "Aloo Tikki Burger", price: 60 },
          { id: 25, name: "Schezwan Burger", price: 70 },
          { id: 26, name: "Coleslaw Burger", price: 70 },
          { id: 27, name: "Mexican Burger", price: 95 },
          { id: 28, name: "Creamy Burger", price: 110 },
          { id: 29, name: "Paneer Tikki Burger", price: 120 },
          { id: 30, name: "Double Decker Burger", price: 150 },
          { id: 31, name: "Crunchy Tikki Burger", price: 160 },
          { id: 32, name: "Veg Surprise Burger", price: 160 },
          { id: 33, name: "Maharaja Burger", price: 170 },
          { id: 34, name: "Veg Makhani Burger", price: 170 },
          { id: 35, name: "Crunchy Paneer", price: 195 }
        ]
      },
      {
        category: "PUCHKA BHAR KE (DRY)",
        items: [
          { id: 36, name: "Sev Puchka", price: 55 },
          { id: 37, name: "Masala Puchka", price: 60 },
          { id: 38, name: "Makka Puchka", price: 60 },
          { id: 39, name: "Dahi Puchka", price: 65 }
        ]
      },
      {
        category: "PUCHKA PANI (6 PIECES)",
        items: [
          { id: 40, name: "Regular", price: 45 },
          { id: 41, name: "Lasan", price: 50 },
          { id: 42, name: "Adrak", price: 50 },
          { id: 43, name: "Hajma", price: 50 },
          { id: 44, name: "Hing", price: 50 },
          { id: 45, name: "Jeera", price: 50 },
          { id: 46, name: "Khatta Meetha", price: 60 }
        ]
      },
      {
        category: "PIZZA STATE",
        items: [
          { id: 47, name: "Golden Corn Pizza", price: 170 },
          { id: 48, name: "Onion Tomato Pizza", price: 170 },
          { id: 49, name: "Paneer & Capsicum", price: 190 },
          { id: 50, name: "Spicy Veggie Pizza", price: 190 },
          { id: 51, name: "Double Cheese Pizza", price: 200 },
          { id: 52, name: "Corn & Cheese Pizza", price: 210 },
          { id: 53, name: "Green House Pizza", price: 210 },
          { id: 54, name: "Veg Loaded Pizza", price: 215 },
          { id: 55, name: "Kulhad Pizza Small", price: 230 },
          { id: 56, name: "Tandoori Paneer Pizza", price: 230 },
          { id: 57, name: "Country Feast Pizza", price: 250 },
          { id: 58, name: "Mexican Paneer Pizza", price: 250 },
          { id: 59, name: "Veggie Supreme Pizza", price: 250 },
          { id: 60, name: "Garlic Cheese Pizza", price: 250 },
          { id: 61, name: "Pasta Pizza", price: 250 },
          { id: 62, name: "Mushroom Pizza", price: 250 },
          { id: 63, name: "Cheesy Macaroni Veg", price: 250 },
          { id: 64, name: "Cheese Burst Pizza", price: 260 }
        ]
      },
      {
        category: "SANDWICH",
        items: [
          { id: 65, name: "Jam & Cheese", price: 70 },
          { id: 66, name: "Aloo Tikki Club", price: 80 },
          { id: 67, name: "Indori Masala", price: 80 },
          { id: 68, name: "Corn & Mayo", price: 90 },
          { id: 69, name: "Bombay Kaccha", price: 90 },
          { id: 70, name: "Cheese Chutney", price: 90 },
          { id: 71, name: "Chocolate Sandwich", price: 90 },
          { id: 72, name: "Jain Sandwich", price: 100 },
          { id: 73, name: "Cheese Peri Peri", price: 110 },
          { id: 74, name: "Open Cheese Toast", price: 110 },
          { id: 75, name: "Double Cheese Chutney", price: 125 },
          { id: 76, name: "Paneer Loaded", price: 140 },
          { id: 77, name: "Tandoori Paneer", price: 145 },
          { id: 78, name: "Chilli Cheese Toast", price: 150 },
          { id: 79, name: "Russian Sandwich", price: 150 },
          { id: 80, name: "Pizza Sandwich", price: 160 }
        ]
      },
      {
        category: "FRIES / NUGGETS",
        items: [
          { id: 81, name: "French Fries", price: 90 },
          { id: 82, name: "Crinkle Fries", price: 90 },
          { id: 83, name: "Masala Fries", price: 95 },
          { id: 84, name: "Peri Peri Fries", price: 100 },
          { id: 85, name: "Masala Cheese Fries", price: 110 },
          { id: 86, name: "Potato Nuggets", price: 120 },
          { id: 87, name: "Cheese Nuggets", price: 150 }
        ]
      },
      {
        category: "CHAAT KI CHARCHA",
        items: [
          { id: 88, name: "Masala Papdi Chaat", price: 80 },
          { id: 89, name: "Matar Chaat", price: 80 },
          { id: 90, name: "Aloo Tikki Chaat", price: 80 },
          { id: 91, name: "Dahi Bhalla", price: 80 },
          { id: 92, name: "Chole Chaat", price: 80 },
          { id: 93, name: "Delhi Papdi Chaat", price: 90 },
          { id: 94, name: "Aloo Tikki with Cheese", price: 95 },
          { id: 95, name: "Corn Chaat", price: 100 },
          { id: 96, name: "Samosa Chaat", price: 100 },
          { id: 97, name: "Hatka Jhatka Chaat", price: 120 }
        ]
      },
      {
        category: "PAV GARDEN",
        items: [
          { id: 98, name: "Vada Pav", price: 50 },
          { id: 99, name: "Masala Vada Pav", price: 70 },
          { id: 100, name: "Mumbai Vada Pav", price: 90 },
          { id: 101, name: "Pav Bhaji", price: 120 },
          { id: 102, name: "Cheese Pav Bhaji", price: 140 },
          { id: 103, name: "Extra Pav", price: 20 },
          { id: 104, name: "Chole Bhature", price: 150 }
        ]
      },
      {
        category: "BASKET CHAAT",
        items: [
          { id: 105, name: "Katori Chaat", price: 90 },
          { id: 106, name: "Triangle Chaat", price: 90 },
          { id: 107, name: "Tray Chaat", price: 90 },
          { id: 108, name: "Disco Chaat", price: 100 }
        ]
      },
      {
        category: "PIZZA CHAAT",
        items: [
          { id: 109, name: "Garlic Pizza Chaat", price: 125 },
          { id: 110, name: "Spicy Pizza Chaat", price: 125 },
          { id: 111, name: "Schezwan Pizza Chaat", price: 125 },
          { id: 112, name: "Italian Pizza Chaat", price: 135 },
          { id: 113, name: "Tandoori Pizza Chaat", price: 135 },
          { id: 114, name: "Mexican Pizza Chaat", price: 135 }
        ]
      },
      {
        category: "MOMOS",
        items: [
          { id: 115, name: "Veggie Lite Momos", price: 85 },
          { id: 116, name: "Cheese Corn Momos", price: 135 },
          { id: 117, name: "Paneer Momos", price: 140 }
        ]
      },
      {
        category: "GARLIC BREAD",
        items: [
          { id: 118, name: "Plain Garlic Bread", price: 70 },
          { id: 119, name: "Cheese Garlic Bread", price: 100 },
          { id: 120, name: "Exotic", price: 115 },
          { id: 121, name: "Supreme", price: 125 }
        ]
      },
      {
        category: "MAKKA MUG",
        items: [
          { id: 122, name: "Butter Salted", price: 70 },
          { id: 123, name: "Kali Mirch", price: 85 },
          { id: 124, name: "Tandoori Masala", price: 95 },
          { id: 125, name: "Cheese Makka", price: 120 },
          { id: 126, name: "Nachos with Dip", price: 130 }
        ]
      },
      {
        category: "CHAAT PUCHKA SPECIAL",
        items: [
          { id: 127, name: "Indori Poha", price: 90 },
          { id: 128, name: "Tandoori Spiral", price: 90 },
          { id: 129, name: "CP Special", price: 100 }
        ]
      },
      {
        category: "AKHRI PASTA",
        items: [
          { id: 130, name: "Macaroni White Sauce", price: 180 },
          { id: 131, name: "Mexican Pasta", price: 190 },
          { id: 132, name: "Macaroni Cheese Veg", price: 190 },
          { id: 133, name: "White Sauce Creamy Pasta", price: 195 },
          { id: 134, name: "Red Sauce Cheese Pasta", price: 200 }
        ]
      },
      {
        category: "ROLLS",
        items: [
          { id: 135, name: "Veg Roll", price: 80 },
          { id: 136, name: "Veggie Spicy Roll", price: 85 },
          { id: 137, name: "Paneer Roll", price: 110 },
          { id: 138, name: "Masala Pasta Roll", price: 120 },
          { id: 139, name: "Paneer Bhurji Roll", price: 140 },
          { id: 140, name: "Sweetcorn Masala Roll", price: 140 },
          { id: 141, name: "Mushroom Roll", price: 150 }
        ]
      },
      {
        category: "TORTILLA STUFFED",
        items: [
          { id: 142, name: "Tortilla Veg Stuffed", price: 70 },
          { id: 143, name: "Tortilla Paneer", price: 70 },
          { id: 144, name: "Tortilla Garlic", price: 85 },
          { id: 145, name: "Cheese Corn", price: 85 },
          { id: 146, name: "Tortilla Tandoori", price: 95 },
          { id: 147, name: "Cheese Mexican", price: 95 },
          { id: 148, name: "Tortilla Schezwan", price: 120 },
          { id: 149, name: "Cheese Mayo", price: 130 }
        ]
      },
      {
        category: "BREAK IN THIRST",
        items: [
          { id: 150, name: "Shikanji", price: 40 },
          { id: 151, name: "Butter Milk - Salted", price: 60 },
          { id: 152, name: "Butter Milk - Sweet", price: 60 },
          { id: 153, name: "Strawberry Lassi", price: 75 },
          { id: 154, name: "Masala Lemonade", price: 80 },
          { id: 155, name: "Mango Lassi", price: 85 }
        ]
      },
      {
        category: "MOJITO",
        items: [
          { id: 156, name: "Classic Virgin Mojito", price: 100 },
          { id: 157, name: "Sea Curacao Mojito", price: 115 },
          { id: 158, name: "Red Velvet Mojito", price: 120 },
          { id: 159, name: "Lychee Mojito", price: 125 },
          { id: 160, name: "Blueberry Mojito", price: 125 },
          { id: 161, name: "Black Currant Mojito", price: 125 }
        ]
      },
      {
        category: "SHAKES",
        items: [
          { id: 162, name: "Cold Coffee", price: 60 },
          { id: 163, name: "Badam Shake", price: 80 },
          { id: 164, name: "Thick Cold Coffee", price: 90 },
          { id: 165, name: "Chocolate Cold Coffee", price: 90 },
          { id: 166, name: "Vanilla Milkshake", price: 90 },
          { id: 167, name: "Dry Fruit Shake", price: 100 },
          { id: 168, name: "Butterscotch Milkshake", price: 100 },
          { id: 169, name: "Strawberry Shake", price: 110 },
          { id: 170, name: "Mango Shake", price: 115 },
          { id: 171, name: "Thick Chocolate Cold Coffee", price: 130 },
          { id: 172, name: "Fig Shake", price: 150 },
          { id: 173, name: "Kit-Kat Shake", price: 150 },
          { id: 174, name: "Chocolate Shake", price: 150 },
          { id: 175, name: "Oreo Shake", price: 150 },
          { id: 176, name: "Mix Milkshake", price: 150 },
          { id: 177, name: "Brownie Shake", price: 160 },
          { id: 178, name: "Ferrero Rocher Shake", price: 200 }
        ]
      }
    ];

    function getCart() { return JSON.parse(localStorage.getItem(TABLE_KEY)) || []; }

    function addToCart(id) {
      let cart = getCart();
      let allItems = menuData.flatMap(c => c.items.map(i => ({...i, category: c.category})));
      const item = allItems.find(i => i.id === id);
      if (!cart.some(i => i.id === id)) {
        cart.push(item);
        localStorage.setItem(TABLE_KEY, JSON.stringify(cart));
        render();
      }
    }

    function removeFromCart(id) {
      let cart = getCart().filter(i => i.id !== id);
      localStorage.setItem(TABLE_KEY, JSON.stringify(cart));
      render();
    }

    function render() {
      const cart = getCart();
      const container = document.getElementById("menuContainer");
      container.innerHTML = "";

      menuData.forEach(cat => {
        const catTitle = document.createElement("h2");
        catTitle.className = "category-title";
        catTitle.textContent = cat.category;
        container.appendChild(catTitle);

        const grid = document.createElement("div");
        grid.className = "grid";

        cat.items.forEach(item => {
          const inCart = cart.some(i => i.id === item.id);
          const card = document.createElement("div");
          card.className = "card";
          card.innerHTML = `
            <h4>${item.name}</h4>
            <div class="price">₹${item.price}</div>
            <button class="btn-add" onclick="addToCart(${item.id})" ${inCart ? 'disabled' : ''}>${inCart ? 'In Cart' : 'Add'}</button>
            ${inCart ? `<button class="btn-remove" onclick="removeFromCart(${item.id})">Remove</button>` : ''}
          `;
          grid.appendChild(card);
        });

        container.appendChild(grid);
      });
    }

    render();
  </script>
</body>
</html>
