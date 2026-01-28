<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>❤️ Pergunta Especial</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        .container {
            text-align: center;
            background: white;
            padding: 50px;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
            z-index: 10;
            position: relative;
        }

        h1 {
            font-size: 2.5em;
            color: #333;
            margin-bottom: 40px;
            animation: pulse 2s infinite;
        }

        .buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
        }

        button {
            padding: 20px 40px;
            font-size: 1.5em;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.2s;
            font-weight: bold;
        }

        button:hover {
            transform: scale(1.1);
        }

        .btn-sim {
            background: #ff6b6b;
            color: white;
        }

        .btn-nao {
            background: #4ecdc4;
            color: white;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
        }

        .emoji {
            position: fixed;
            font-size: 3em;
            animation: float-up 3s ease-out forwards;
            pointer-events: none;
            z-index: 1000;
        }

        @keyframes float-up {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Que namora comigo?</h1>
        <div class="buttons">
            <button class="btn-sim" onclick="responderSim()">Sim ❤️</button>
            <button class="btn-nao" onclick="responderNao()">Não</button>
        </div>
    </div>

    <script>
        function createFloatingEmoji(emoji, count) {
            for (let i = 0; i < count; i++) {
                setTimeout(() => {
                    const emojiElement = document.createElement('div');
                    emojiElement.className = 'emoji';
                    emojiElement.textContent = emoji;
                    
                    // Posição aleatória horizontal
                    emojiElement.style.left = Math.random() * 100 + '%';
                    emojiElement.style.bottom = '-50px';
                    
                    // Duração aleatória da animação
                    const duration = 2 + Math.random() * 2;
                    emojiElement.style.animationDuration = duration + 's';
                    
                    document.body.appendChild(emojiElement);
                    
                    // Remove o elemento depois da animação
                    setTimeout(() => {
                        emojiElement.remove();
                    }, duration * 1000);
                }, i * 100);
            }
        }

        function responderSim() {
            createFloatingEmoji('❤️', 30);
            
            setTimeout(() => {
                alert('Yay! ❤️❤️❤️');
            }, 500);
        }

        function responderNao() {
            createFloatingEmoji('bruh', 25);
            
            setTimeout(() => {
                alert('bruh... 😢');
            }, 500);
        }
    </script>
</body>
</html>

