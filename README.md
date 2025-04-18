<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Амико ты бот</title>
  <style>
    body {
      background-color: #ff0000;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      overflow: hidden;
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }
    .main-message {
      font-size: 40px;
      z-index: 10;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
    .click-message {
      position: absolute;
      font-size: 20px;
      animation: pop-up 0.5s ease;
      pointer-events: none;
    }
    @keyframes pop-up {
      0% { opacity: 0; transform: scale(0.5); }
      100% { opacity: 1; transform: scale(1); }
    }
  </style>
</head>
<body>
  <div class="main-message">НИКАКОГО ИНЕТА ТЕБЕ</div>
  <script>
    // При клике выводим "Амико ты бот" в точке нажатия
    document.body.addEventListener("click", (event) => {
      const message = document.createElement("div");
      message.textContent = "Амико ты бот";
      message.classList.add("click-message");

      // Позиция клика
      message.style.left = `${event.clientX}px`;
      message.style.top = `${event.clientY}px`;

      // Добавление и удаление
      document.body.appendChild(message);
      setTimeout(() => message.remove(), 2000);
    });
  </script>
</body>
</html>
