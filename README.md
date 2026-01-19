# ideal-fortnight
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Mini App</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body {
            font-family: sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: var(--tg-theme-bg-color, #ffffff);
            color: var(--tg-theme-text-color, #000000);
        }
        button {
            padding: 10px 20px;
            background-color: var(--tg-theme-button-color, #2481cc);
            color: var(--tg-theme-button-text-color, #ffffff);
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Namaste!</h1>
    <p id="user-name">Dost</p>
    <button id="main-btn">Click Me</button>

    <script>
        // Telegram Web App initialize karna
        const tg = window.Telegram.WebApp;
        tg.expand(); // App ko full screen kholne ke liye

        // User ka naam dikhane ke liye
        if (tg.initDataUnsafe && tg.initDataUnsafe.user) {
            document.getElementById('user-name').innerText = `Hello, ${tg.initDataUnsafe.user.first_name}!`;
        }

        // Button click event
        document.getElementById('main-btn').addEventListener('click', () => {
            tg.showAlert("Aapne button dabaya!");
        });
    </script>
</body>
</html>
