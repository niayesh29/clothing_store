# clothing_store
فروشگاه م<!DOCTYPE html>
<html lang="fa">
<head>
  <meta charset="UTF-8">
  <title>فروشگاه لباس آنلاین</title>
  <link href="https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Vazirmatn', sans-serif;
      direction: rtl;
      background: #f6f6f9;
      padding: 20px;
      color: #333;
    }

    h1 {
      text-align: center;
      color: #5c3d99;
    }

    input[type="search"] {
      padding: 10px;
      width: 100%;
      max-width: 400px;
      margin: 20px auto;
      display: block;
      border: 1px solid #ccc;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }

    .category {
      margin-top: 40px;
    }

    .category h2 {
      color: #444;
      border-bottom: 2px solid #ccc;
      padding-bottom: 5px;
    }

    .item {
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 3px 6px rgba(0,0,0,0.05);
      padding: 15px;
      margin: 15px 0;
      transition: transform 0.3s;
    }

    .item:hover {
      transform: translateY(-5px);
    }

    button {
      background-color: #7e57c2;
      color: white;
      border: none;
      padding: 10px 15px;
      border-radius: 6px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #673ab7;
    }

    .cart {
      background: #fff;
      padding: 20px;
      margin-top: 40px;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      font-size: 18px;
      text-align: center;
      color: #333;
    }
  </style>
</head>
<body>
  <h1>فروشگاه لباس آنلاین</h1>
  <input type="search" id="search" placeholder="جستجو در محصولات..." oninput="searchItems()">

  <div class="category" id="women">
    <h2>لباس زنانه</h2>
    <div class="item" data-title="مانتو تابستانی">
      <p>مانتو تابستانی</p>
      <p>قیمت: ۳۲۰٬۰۰۰ تومان</p>
      <button onclick="addToCart(320000)">افزودن به سبد خرید</button>
    </div>
    <div class="item" data-title="پیراهن مجلسی">
      <p>پیراهن مجلسی</p>
      <p>قیمت: ۵۸۰٬۰۰۰ تومان</p>
      <button onclick="addToCart(580000)">افزودن به سبد خرید</button>
    </div>
  </div>

  <div class="category" id="men">
    <h2>لباس مردانه</h2>
    <div class="item" data-title="کت تک مردانه">
      <p>کت تک مردانه</p>
      <p>قیمت: ۶۹۰٬۰۰۰ تومان</p>
      <button onclick="addToCart(690000)">افزودن به سبد خرید</button>
    </div>
    <div class="item" data-title="شلوار جین">
      <p>شلوار جین</p>
      <p>قیمت: ۳۴۰٬۰۰۰ تومان</p>
      <button onclick="addToCart(340000)">افزودن به سبد خرید</button>
    </div>
  </div>

  <div class="category" id="kids">
    <h2>لباس بچگانه</h2>
    <div class="item" data-title="تی‌شرت کودک">
      <p>تی‌شرت کودک</p>
      <p>قیمت: ۱۴۰٬۰۰۰ تومان</p>
      <button onclick="addToCart(140000)">افزودن به سبد خرید</button>
    </div>
    <div class="item" data-title="لباس نوزادی">
      <p>لباس نوزادی</p>
      <p>قیمت: ۱۲۰٬۰۰۰ تومان</p>
      <button onclick="addToCart(120000)">افزودن به سبد خرید</button>
    </div>
  </div>

  <div class="cart">
    مجموع قیمت: <span id="total">۰</span> تومان
  </div>

  <script>
    let total = 0;
    function addToCart(price) {
      total += price;
      document.getElementById('total').innerText = total.toLocaleString();
    }

    function searchItems() {
      const query = document.getElementById('search').value.toLowerCase();
      const items = document.querySelectorAll('.item');
      items.forEach(item => {
        const title = item.getAttribute('data-title').toLowerCase();
        item.style.display = title.includes(query) ? 'block' : 'none';
      });
    }
  </script>
</body>
</html>
