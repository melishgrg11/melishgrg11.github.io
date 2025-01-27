<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine?</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(to bottom, #ff5f6d, #ffc371);
      color: white;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
    }
    h1 {
      font-size: 3rem;
      margin-bottom: 20px;
    }
    p {
      font-size: 1.5rem;
      margin-bottom: 30px;
    }
    .button-container {
      display: flex;
      gap: 20px;
    }
    button {
      background-color: white;
      color: #ff5f6d;
      border: none;
      padding: 15px 30px;
      font-size: 1.2rem;
      font-weight: bold;
      border-radius: 8px;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    button:hover {
      background-color: #ff5f6d;
      color: white;
      transform: scale(1.1);
    }
    footer {
      position: absolute;
      bottom: 10px;
      font-size: 0.9rem;
    }
  </style>
</head>
<body>
  <h1>Hi Nikki,</h1>
  <p>Will you be my Valentine? 💖</p>
  <div class="button-container">
    <button onclick="sayYes()">YES 💕</button>
    <button onclick="sayNo()">NO 😢</button>
  </div>
  <footer>Made with ❤️ by [Your Name]</footer>

  <script>
    function sayYes() {
      alert("Yay! I love you, Nikki! 💖");
    }

    function sayNo() {
      alert("Oh no! But I still think you're amazing, Nikki! 😢");
    }
  </script>
</body>
</html>
