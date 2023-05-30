# CodeAlpha_Temperature_Converter
#HTML CODE
<!DOCTYPE html>
<html>
<head>
  <title>Temperature Converter</title>
  <link rel="stylesheet" href="temp.css">
</head>
<body>
  <h1>Temperature Converter</h1>
  <div class="container">
    <div class="form-group">
      <label for="celsius">Celsius</label>
      <input type="number" id="celsius" placeholder="Enter temperature in Celsius">
    </div>
    <div class="form-group">
      <label for="fahrenheit">Fahrenheit</label>
      <input type="number" id="fahrenheit" placeholder="Enter temperature in Fahrenheit">
    </div>
    <div class="form-group">
      <label for="kelvin">Kelvin</label>
      <input type="number" id="kelvin" placeholder="Enter temperature in Kelvin">
    </div>
    <button class="btn" onclick="convertTemperature()">Convert</button>
    <div class="result">
      <p id="result"></p>
    </div>
  </div>

  <script>
    function convertTemperature() {
      var celsiusInput = document.getElementById("celsius");
      var fahrenheitInput = document.getElementById("fahrenheit");
      var kelvinInput = document.getElementById("kelvin");
      var resultElement = document.getElementById("result");

      if (celsiusInput.value !== "") {
        var celsius = parseFloat(celsiusInput.value);
        var fahrenheit = (celsius * 9 / 5) + 32;
        var kelvin = celsius + 273.15;
        resultElement.textContent = celsius + " degrees Celsius = " + fahrenheit.toFixed(2) + " degrees Fahrenheit = " + kelvin.toFixed(2) + " Kelvin";
      } else if (fahrenheitInput.value !== "") {
        var fahrenheit = parseFloat(fahrenheitInput.value);
        var celsius = (fahrenheit - 32) * 5 / 9;
        var kelvin = celsius + 273.15;
        resultElement.textContent = fahrenheit + " degrees Fahrenheit = " + celsius.toFixed(2) + " degrees Celsius = " + kelvin.toFixed(2) + " Kelvin";
      }  else if (kelvinInput.value !== "") {
        var kelvin = parseFloat(kelvinInput.value);
        var celsius = kelvin - 273.15;
        var fahrenheit = (celsius * 9 / 5) + 32;
        resultElement.textContent = kelvin + " Kelvin = " + celsius.toFixed(2) + " degrees Celsius = " + fahrenheit.toFixed(2) + " degrees Fahrenheit";
      } else {
        resultElement.textContent = "Please enter a temperature.";
      }
    }
  </script>
</body>
</html>

