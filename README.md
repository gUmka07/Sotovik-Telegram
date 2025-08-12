<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Telegram WebApp Menu</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #0e1621;
      color: #fff;
      display: flex;
      flex-direction: column;
      height: 100vh;
    }

    .menu-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 8px;
      padding: 10px;
      overflow-y: auto;
      flex: 1;
    }

    .menu-item {
      background-color: #17212b;
      padding: 10px;
      border-radius: 8px;
      text-align: center;
      font-size: 14px;
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border: 1px solid rgba(255,255,255,0.1);
      transition: background-color 0.2s;
    }

    .menu-item:hover {
      background-color: #1c2938;
    }

    .menu-item span {
      margin-top: 5px;
    }

    .bottom-bar {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      background-color: #17212b;
      display: flex;
      justify-content: space-around;
      padding: 10px;
      border-top: 1px solid rgba(255,255,255,0.1);
    }

    .bottom-bar button {
      background: #2b5278;
      border: none;
      color: white;
      padding: 8px 16px;
      border-radius: 6px;
      font-size: 14px;
      cursor: pointer;
    }

    .bottom-bar button:hover {
      background: #3c6fa0;
    }
  </style>
</head>
<body>

  <div class="menu-grid">
    <div class="menu-item">🔧<span>Аксессуары</span></div>
    <div class="menu-item">🎧<span>Наушники</span></div>
    <div class="menu-item">⌚<span>Apple Watch</span></div>
    <div class="menu-item">🍏<span>iPad</span></div>
    <div class="menu-item">🍏<span>MacBook</span></div>
    <div class="menu-item">🍏<span>iPhone</span></div>
    <div class="menu-item">🍏<span>iPhone 16</span></div>
    <div class="menu-item">📱<span>Samsung</span></div>
    <div class="menu-item">📱<span>Xiaomi</span></div>
    <div class="menu-item">📱<span>Poco</span></div>
    <div class="menu-item">📱<span>Google</span></div>
    <div class="menu-item">📱<span>OnePlus</span></div>
    <div class="menu-item">📱<span>Honor/Huawei</span></div>
    <div class="menu-item">📱<span>Nothing Phone</span></div>
    <div class="menu-item">📱<span>Nubia</span></div>
    <div class="menu-item">✨<span>Dyson</span></div>
    <div class="menu-item">📷<span>Камеры/Приставки/Колонки</span></div>
    <div class="menu-item">🏢<span>Б/У Устройства/Обменки</span></div>
    <div class="menu-item">💬<span>Заказать</span></div>
    <div class="menu-item">📍<span>Наши контакты</span></div>
  </div>

  <div class="bottom-bar">
    <button>🏠 Главная</button>
    <button>📦 Корзина</button>
    <button>📞 Контакты</button>
  </div>

  <script src="https://telegram.org/js/telegram-web-app.js"></script>
  <script>
    const tg = window.Telegram.WebApp;
    tg.expand(); // Разворачиваем WebApp на весь экран

    document.querySelectorAll('.menu-item').forEach(item => {
      item.addEventListener('click', () => {
        const name = item.innerText.trim();
        tg.sendData(name); // Отправка данных боту
      });
    });
  </script>
</body>
</html>
