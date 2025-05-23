<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>BOGO Offer</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #fff;
      padding: 20px;
      color: #333;
    }
    .container {
      max-width: 400px;
      margin: auto;
      border: 1px solid #eee;
      padding: 20px;
      border-radius: 10px;
    }
    h2 {
      text-align: center;
      color: #f48fb1;
    }
    .option {
      border: 2px solid #eee;
      padding: 15px;
      margin-bottom: 10px;
      border-radius: 10px;
      position: relative;
    }
    .option input[type="radio"] {
      margin-right: 10px;
    }
    .option .tag {
      background: #f48fb1;
      color: white;
      font-size: 12px;
      padding: 3px 8px;
      border-radius: 5px;
      position: absolute;
      top: -10px;
      right: -10px;
    }
    .sizes, .colors {
      display: flex;
      gap: 10px;
      margin-top: 10px;
    }
    select {
      padding: 5px;
      margin-top: 5px;
    }
    .price {
      font-weight: bold;
      margin-top: 5px;
    }
    .free-delivery {
      text-align: center;
      color: green;
      margin: 10px 0;
    }
    button {
      background: #f48fb1;
      color: white;
      padding: 12px;
      width: 100%;
      border: none;
      font-size: 16px;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>YAY! It's BOGO</h2>
    
    <div class="option">
      <input type="radio" name="bundle" value="1" checked onchange="updatePrice(1)">
      1 Unit <span class="tag">10% Off</span>
      <div class="price">$10.00 USD <s>$24.00 USD</s></div>
    </div>

    <div class="option">
      <input type="radio" name="bundle" value="2" onchange="updatePrice(2)">
      2 Unit <span class="tag">MOST POPULAR</span>
      <span class="tag" style="top: 20px;">20% Off</span>
      <div class="sizes">
        <label>#1 Size:
          <select><option>S</option><option>M</option><option>L</option></select>
        </label>
        <label>Color:
          <select><option>Black</option><option>White</option></select>
        </label>
      </div>
      <div class="sizes">
        <label>#2 Size:
          <select><option>S</option><option>M</option><option>L</option></select>
        </label>
        <label>Color:
          <select><option>Black</option><option>White</option></select>
        </label>
      </div>
      <div class="price">$18.00 USD <s>$48.00 USD</s></div>
    </div>

    <div class="option">
      <input type="radio" name="bundle" value="3" onchange="updatePrice(3)">
      3 Unit <span class="tag">30% Off</span>
      <div class="price">$24.00 USD <s>$72.00 USD</s></div>
    </div>

    <div class="free-delivery" id="freeDelivery" style="display: none;">Free Delivery</div>
    <div class="price">Total: <span id="totalPrice">$10.00 USD</span></div>

    <button>Add to Cart</button>
  </div>

  <script>
    function updatePrice(units) {
      let price = 0;
      let freeDelivery = false;

      if (units == 1) price = 10;
      else if (units == 2) price = 18;
      else if (units == 3) {
        price = 24;
        freeDelivery = true;
      }

      document.getElementById("totalPrice").innerText = `$${price.toFixed(2)} USD`;
      document.getElementById("freeDelivery").style.display = freeDelivery ? 'block' : 'none';
    }
  </script>
</body>
</html>
