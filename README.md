# Mortgage-calculator
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Mortgage Calculator</title>

  <style>
    body {
      font-family: Arial;
      background: #f4f4f4;
      text-align: center;
      padding: 20px;
    }

    .box {
      background: white;
      padding: 20px;
      max-width: 400px;
      margin: auto;
      border-radius: 10px;
    }

    input, button {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
    }

    button {
      background: #0078D4;
      color: white;
      border: none;
      cursor: pointer;
    }
  </style>
</head>

<body>

  <div class="box">
    <h2>Mortgage Calculator</h2>

    <input type="number" id="amount" placeholder="Loan Amount (£)">
    <input type="number" id="rate" placeholder="Interest Rate (%)">
    <input type="number" id="years" placeholder="Years">

    <button onclick="calculate()">Calculate</button>

    <h3 id="result"></h3>
  </div>

  <script>
    function calculate() {
      let P = document.getElementById("amount").value;
      let r = document.getElementById("rate").value / 100 / 12;
      let n = document.getElementById("years").value * 12;

      if (!P || !r || !n) {
        document.getElementById("result").innerText = "Please fill all fields";
        return;
      }

      let M = P * (r * Math.pow(1 + r, n)) / (Math.pow(1 + r, n) - 1);

      document.getElementById("result").innerText =
        "Monthly Payment: £" + M.toFixed(2);
    }
  </script>

</body>
</html>
