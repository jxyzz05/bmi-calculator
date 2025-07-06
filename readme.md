# bmi-calculator
first simple project
## bmi-calculator

First simple project

### BMI Calculator Code

```html
<!DOCTYPE html>
<html>
<head>
  <title>BMI Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }
    input, button {
      padding: 10px;
      margin: 5px;
    }
  </style>
</head>
<body>

  <h2>BMI Calculator</h2>

  <input type="number" id="weight" placeholder="Weight (kg)">
  <input type="number" id="height" placeholder="Height (cm)">
  <br>
  <button onclick="calculateBMI()">Calculate</button>

  <p id="result"></p>

  <script>
    function calculateBMI() {
      const weight = parseFloat(document.getElementById("weight").value);
      const height = parseFloat(document.getElementById("height").value) / 100;

      if (!weight || !height) {
        document.getElementById("result").innerText = "Please enter valid values.";
        return;
      }

      const bmi = (weight / (height * height)).toFixed(2);
      let category = "";

      if (bmi < 18.5) category = "Underweight";
      else if (bmi < 24.9) category = "Normal";
      else if (bmi < 29.9) category = "Overweight";
      else category = "Obese";

      document.getElementById("result").innerText = `BMI: ${bmi} (${category})`;
    }
  </script>

</body>
</html>
