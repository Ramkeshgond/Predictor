<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Future Predictor</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #0f172a, #1e293b);
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .card {
      background: #020617;
      padding: 30px;
      border-radius: 12px;
      width: 320px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.4);
    }
    h1 {
      text-align: center;
      margin-bottom: 20px;
    }
    label {
      display: block;
      margin-top: 10px;
      font-size: 14px;
    }
    input {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      border-radius: 6px;
      border: none;
      outline: none;
    }
    button {
      width: 100%;
      margin-top: 20px;
      padding: 10px;
      border: none;
      border-radius: 8px;
      background: #38bdf8;
      font-weight: bold;
      cursor: pointer;
    }
    button:hover {
      background: #0ea5e9;
    }
    .result {
      margin-top: 20px;
      padding: 10px;
      background: #020617;
      border-radius: 8px;
      text-align: center;
      min-height: 40px;
    }
  </style>
</head>
<body>
  <div class="card">
    <h1>Future Predictor 🔮</h1>

    <label for="name">Your Name</label>
    <input type="text" id="name" placeholder="Enter your name" />

    <label for="date">Select a Date</label>
    <input type="date" id="date" />

    <button onclick="predictFuture()">Predict</button>

    <div class="result" id="result"></div>
  </div>

  <script>
    function predictFuture() {
      const name = document.getElementById('name').value.trim();
      const date = document.getElementById('date').value;
      const resultDiv = document.getElementById('result');

      if (!name || !date) {
        resultDiv.textContent = "Please enter both name and date.";
        return;
      }

      const predictions = [
        "Tumhara kuch nhee ho shakta Mere Dost ,
        "Bhadwe muh uthaa ke kyo chal aate ho",
        "Ak kaam kro B-tech karna chhod do Tuhara iss field me kuch nhee ho shakta",
        "Tumhara Future to door door dikhai nhee de rhaa 🌱",
        "Mai kya btaawoo tumhara future dikh hee nhee rhaa ⏳",
        "Ladki aur Paise  ke alwa sab kuch hoga tumhari jindegi me 🤝",
        "Future to kuch nhee dikh rhaa per agar laundiyabazi band kar do to saayed dikh jaaye 🎯"
      ];

      // Simple deterministic hash using name + date
      let hash = 0;
      const input = name + date;
      for (let i = 0; i < input.length; i++) {
        hash += input.charCodeAt(i);
      }

      const prediction = predictions[hash % predictions.length];
      resultDiv.textContent = `${name}, your future says: ${prediction}`;
    }
  </script>
</body>
</html>

