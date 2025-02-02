# rageeeeeeee.github.io
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Julia ❤️</title>
    <style>
        body {
            background-color: #ffe6f0;
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            text-align: center;
        }
        h1 {
            color: #d10050;
            font-size: 3rem;
            margin: 20px;
        }
        p {
            font-size: 2rem;
            color: #600020;
            margin: 10px;
        }
        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff69b4;
            transform: rotate(45deg);
            animation: float 5s infinite;
        }
        .heart::before,
        .heart::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff69b4;
            border-radius: 50%;
        }
        .heart::before {
            top: -10px;
            left: 0;
        }
        .heart::after {
            left: 10px;
            top: 0;
        }
        @keyframes float {
            0% {
                transform: translateY(0) rotate(45deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(45deg);
                opacity: 0;
            }
        }
        button {
            background-color: #d10050;
            color: white;
            border: none;
            padding: 15px 25px;
            font-size: 1.5rem;
            border-radius: 10px;
            cursor: pointer;
            margin: 20px;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #a0003d;
        }
        .hidden {
            display: none;
        }
        #loveMessage {
            font-size: 4rem;
            color: #d10050;
            margin-top: 20px;
        }
        #pigEmoji {
            font-size: 5rem;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <h1>Julia</h1>
    <div id="initialText">
        <p>Desde que te he conocido, cada día ha sido especial.</p>
        <p>Ya mismo es San Valentín y quiero preguntarte algo importante...</p>
    </div>
    <button id="revealButton">Haz clic aquí</button>

    <div id="question" class="hidden">
        <p style="font-size: 3rem;">¿Quieres ser mi San Valentín?</p>
        <button onclick="respond(true)">Sí ❤️</button>
        <button onclick="respond(false)">No 💔</button>
    </div>

    <p id="loveMessage" class="hidden">¡Te quiero! 💖</p>
    <div id="pigEmoji" class="hidden">🐷💩</div>

    <script>
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 2 + 3 + 's';
            document.body.appendChild(heart);
            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        document.getElementById('revealButton').addEventListener('click', () => {
            document.getElementById('initialText').classList.add('hidden');
            document.getElementById('revealButton').classList.add('hidden');
            document.getElementById('question').classList.remove('hidden');
            setInterval(createHeart, 300);
        });

        function respond(isYes) {
            const loveMessage = document.getElementById('loveMessage');
            const pigEmoji = document.getElementById('pigEmoji');
            if (isYes) {
                loveMessage.classList.remove('hidden');
            } else {
                pigEmoji.classList.remove('hidden');
            }
            document.getElementById('question').classList.add('hidden');
        }
    </script>

</body>
</html>
