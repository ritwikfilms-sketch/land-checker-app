<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI Land Checker</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      color: white;
      text-align: center;
      padding: 40px;
    }

    .box {
      background: rgba(255,255,255,0.1);
      padding: 30px;
      border-radius: 15px;
      max-width: 400px;
      margin: auto;
    }

    input {
      width: 90%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 8px;
      border: none;
    }

    button {
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      background: #00ffcc;
      font-weight: bold;
    }

    #result {
      margin-top: 20px;
      font-size: 18px;
    }
  </style>
</head>

<body>

  <div class="box">
    <h1>🌍 AI Land Checker</h1>

    <input type="number" id="size" placeholder="Land Size (sqft)">
    <input type="number" id="price" placeholder="Expected Price">

    <button onclick="checkLand()">Analyze</button>

    <div id="result"></div>
  </div>

  <script>
    function checkLand() {
      let size = document.getElementById("size").value;
      let price = document.getElementById("price").value;

      if(size === "" || price === "") {
        document.getElementById("result").innerHTML = "⚠️ Please fill all fields.";
        return;
      }

      let rate = price / size;
      let result = "";

      if(rate < 500) {
        result = "🔥 Great Deal! Good Investment Opportunity.";
      } else if(rate < 1000) {
        result = "⚖️ Average Market Value.";
      } else {
        result = "⚠️ Overpriced Property. Reconsider.";
      }

      document.getElementById("result").innerHTML = result;
    }
  </script>

</body>
</html>
