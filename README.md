<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>24h Key Generator</title>
    <style>
        /* Stili esistenti (rimangono invariati) */
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
        .key-box, .button, .key, .time-remaining, .created-time {
            /* Mantieni stili esistenti */
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
        <button class="button" id="newKeyButton">Genera Nuova Key</button>
    </div>

    <script>
        let currentKey = null;
        let creationTime = null;

        // Genera una chiave casuale
        function generateRandomString(length) {
            const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
            let result = '';
            for (let i = 0; i < length; i++) {
                result += characters.charAt(Math.floor(Math.random() * characters.length));
            }
            return result;
        }

        // Genera una nuova chiave e aggiorna l'interfaccia
        function generateKey() {
            currentKey = 'KEY_' + generateRandomString(16);
            creationTime = Date.now();
            updateUI();
        }

        // Aggiorna il timer e l'interfaccia
        function updateUI() {
            if (!currentKey || !creationTime) return;

            document.getElementById('currentKey').textContent = currentKey;
            const date = new Date(creationTime);
            document.getElementById('createdTime').textContent = 
                Creata il: ${date.toLocaleString('it-IT')};
        }

        // Fornisce i dati della chiave in formato JSON
        function getKeyData() {
            const expirationTime = creationTime + 24 * 60 * 60 * 1000; // Scadenza in 24 ore
            return JSON.stringify({
                key: currentKey,
                expiration: expirationTime,
                valid: Date.now() < expirationTime
            });
        }

        // Rende disponibile la chiave tramite URL
        window.addEventListener('load', () => {
            const urlParams = new URLSearchParams(window.location.search);
            if (urlParams.has('getKey')) {
                document.body.textContent = getKeyData();
            }
        });

        // Genera una chiave al caricamento della pagina
        document.getElementById('newKeyButton').addEventListener('click', generateKey);
        generateKey();
    </script>
</body>
</html>
