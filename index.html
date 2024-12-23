<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>24h Key Generator</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            background: rgba(255, 255, 255, 0.95);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            width: 100%;
            max-width: 500px;
            text-align: center;
        }

        h1 {
            color: #1a237e;
            font-size: 2em;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        .key-box {
            background: #f5f6fa;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            border: 2px solid #e8eaf6;
        }

        .key {
            font-family: monospace;
            font-size: 24px;
            color: #303f9f;
            letter-spacing: 2px;
            word-break: break-all;
            padding: 10px;
            background: white;
            border-radius: 10px;
            border: 2px dashed #3f51b5;
            margin: 10px 0;
        }

        .time-remaining {
            color: #5c6bc0;
            font-size: 1.1em;
            margin: 20px 0;
            padding: 10px;
            background: #e8eaf6;
            border-radius: 10px;
            display: inline-block;
        }

        .created-time {
            color: #666;
            font-size: 0.9em;
            margin-top: 10px;
        }

        .button {
            background: #3f51b5;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 1.1em;
            cursor: pointer;
            transition: all 0.3s ease;
            margin: 10px;
        }

        .button:hover {
            background: #303f9f;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .button:active {
            transform: translateY(0);
        }

        #copyMessage {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 25px;
            background: #4caf50;
            color: white;
            border-radius: 10px;
            opacity: 0;
            transition: opacity 0.3s ease;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            pointer-events: none;
        }

        #copyMessage.show {
            opacity: 1;
        }

        @media (max-width: 480px) {
            .container {
                padding: 20px;
            }

            h1 {
                font-size: 1.5em;
            }

            .key {
                font-size: 18px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🔑 24h Key Generator</h1>
        <div class="key-box">
            <div class="key" id="currentKey">Generazione...</div>
            <div class="time-remaining" id="timeRemaining">Calcolo tempo rimanente...</div>
            <div class="created-time" id="createdTime"></div>
        </div>
        <button class="button" id="copyButton">Copia Key</button>
        <button class="button" id="newKeyButton">Genera Nuova Key</button>
    </div>
    <div id="copyMessage">Key copiata! ✅</div>

    <script>
        // Variabili globali in memoria
        let currentKey = null;
        let creationTime = null;

        // Funzione per generare caratteri casuali
        function generateRandomString(length) {
            const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
            let result = '';
            for (let i = 0; i < length; i++) {
                result += characters.charAt(Math.floor(Math.random() * characters.length));
            }
            return result;
        }

        // Generazione della key
        function generateKey() {
            currentKey = 'KEY_' + generateRandomString(16);
            creationTime = Date.now();
            updateUI();
            return currentKey;
        }

        // Formattazione del numero con zero iniziale
        function padNumber(num) {
            return num.toString().padStart(2, '0');
        }

        // Aggiornamento dell'interfaccia
        function updateUI() {
            if (!currentKey || !creationTime) return;

            document.getElementById('currentKey').textContent = currentKey;
            const date = new Date(creationTime);
            document.getElementById('createdTime').textContent = 
                Creata il: ${date.toLocaleString('it-IT')};
        }

        // Aggiornamento del timer
        function updateTimer() {
            if (!creationTime) return;

            const now = Date.now();
            const timeLeft = (creationTime + 24*60*60*1000) - now;

            if (timeLeft <= 0) {
                generateKey();
                return;
            }

            const hours = Math.floor(timeLeft / (1000 * 60 * 60));
            const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);

            document.getElementById('timeRemaining').textContent = 
                ⏳ Scade tra: ${padNumber(hours)}h ${padNumber(minutes)}m ${padNumber(seconds)}s;
        }

        // Funzione per copiare la key
        function copyKey() {
            if (!currentKey) return;

            const el = document.createElement('textarea');
            el.value = currentKey;
            el.setAttribute('readonly', '');
            el.style.position = 'absolute';
            el.style.left = '-9999px';
            document.body.appendChild(el);
            el.select();
            document.execCommand('copy');
            document.body.removeChild(el);

            const message = document.getElementById('copyMessage');
            message.classList.add('show');
            setTimeout(() => message.classList.remove('show'), 2000);
        }

        // Event listeners
        document.getElementById('copyButton').addEventListener('click', copyKey);
        document.getElementById('newKeyButton').addEventListener('click', generateKey);

        // Inizializzazione
        generateKey();
        setInterval(updateTimer, 1000);
    </script>
</body>
</html>
