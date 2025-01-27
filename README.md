<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine?</title>
  <style>
    /* General Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #ffafcc, #ffc3a0);
      background-size: 400% 400%;
      animation: gradientShift 10s ease infinite;
      color: #fff;
      overflow: hidden;
    }

    .container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      height: 100vh;
      padding: 1rem;
    }

    h1 {
      font-size: 2.5rem;
      font-weight: bold;
      margin-bottom: 1rem;
      overflow: hidden;
      white-space: nowrap;
      border-right: 2px solid white;
      animation: typing 4s steps(30) forwards, blink 0.5s step-end infinite;
    }

    h2 {
      font-size: 1.5rem;
      margin-bottom: 2rem;
      animation: fadeIn 3s ease-in-out;
    }

    .heart-button {
      display: inline-block;
      padding: 1rem 2rem;
      font-size: 1.2rem;
      font-weight: bold;
      color: #ffafcc;
      background: #fff;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      text-decoration: none;
      transition: background 0.3s ease, transform 0.2s ease;
      animation: fadeIn 4s ease-in-out;
    }

    .heart-button:hover {
      background: #ffe5ec;
      transform: scale(1.1);
      box-shadow: 0 0 15px rgba(255, 255, 255, 0.8);
    }

    .hearts {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
    }

    .heart {
      width: 20px;
      height: 20px;
      background-color: #fff;
      position: absolute;
      clip-path: polygon(50% 0%, 100% 35%, 82% 100%, 50% 82%, 18% 100%, 0% 35%);
      animation: float 5s infinite ease-in-out;
      opacity: 0.7;
    }

    /* Rotating Heart */
    .rotating-heart {
      position: absolute;
      width: 150px;
      height: 150px;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      clip-path: polygon(50% 0%, 100% 35%, 82% 100%, 50% 82%, 18% 100%, 0% 35%);
      background: rgba(255, 255, 255, 0.2);
      animation: rotateHeart 10s linear infinite;
    }

    /* Animations */
    @keyframes typing {
      from {
        width: 0;
      }
      to {
        width: 100%;
      }
    }

    @keyframes blink {
      from, to {
        border-color: transparent;
      }
      50% {
        border-color: white;
      }
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }

    @keyframes float {
      0% {
        transform: translateY(0) rotate(0deg);
      }
      50% {
        transform: translateY(-50px) rotate(45deg);
      }
      100% {
        transform: translateY(0) rotate(90deg);
      }
    }

    @keyframes gradientShift {
      0% {
        background-position: 0% 50%;
      }
      50% {
        background-position: 100% 50%;
      }
      100% {
        background-position: 0% 50%;
      }
    }

    @keyframes rotateHeart {
      0% {
        transform: translate(-50%, -50%) rotate(0deg);
      }
      100% {
        transform: translate(-50%, -50%) rotate(360deg);
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Hi Nikki ❤️</h1>
    <h2>Will you be my Valentine?</h2>
    <a href="#" class="heart-button">Yes, of course! 💌</a>
  </div>

  <div class="rotating-heart"></div>
  <div class="hearts"></div>

  <script>
    // Floating Hearts
    const heartsContainer = document.querySelector('.hearts');

    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');

      const size = Math.random() * 20 + 10; // Random size for hearts
      heart.style.width = `${size}px`;
      heart.style.height = `${size}px`;

      heart.style.left = Math.random() * 100 + '%'; // Random position
      heart.style.animationDuration = Math.random() * 3 + 2 + 's'; // Random float duration
      heart.style.animationDelay = Math.random() * 5 + 's'; // Random delay

      heartsContainer.appendChild(heart);

      // Remove the heart after animation ends
      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    // Generate hearts every 500ms
    setInterval(createHeart, 500);

    // Confetti Explosion on Button Click
    document.querySelector('.heart-button').addEventListener('click', (e) => {
      e.preventDefault();
      const confettiCount = 100;
      const confettiColors = ['#ffafcc', '#ffc3a0', '#fff'];

      for (let i = 0; i < confettiCount; i++) {
        const confetti = document.createElement('div');
        confetti.style.position = 'absolute';
        confetti.style.width = '10px';
        confetti.style.height = '10px';
        confetti.style.backgroundColor =
          confettiColors[Math.floor(Math.random() * confettiColors.length)];
        confetti.style.top = `${e.clientY}px`;
        confetti.style.left = `${e.clientX}px`;
        confetti.style.animation = `confetti 1s ease-out forwards`;
        document.body.appendChild(confetti);

        setTimeout(() => confetti.remove(), 1000);
      }
    });

    const style = document.createElement('style');
    style.textContent = `
      @keyframes confetti {
        0% {
          transform: scale(1);
        }
        100% {
          transform: translate(${Math.random() * 400 - 200}px, ${Math.random() * 400 - 200}px) scale(0);
          opacity: 0;
        }
      }
    `;
    document.head.appendChild(style);
  </script>
</body>
</html>
