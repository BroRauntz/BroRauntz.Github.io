<!DOCTYPE html>
<html lang="et">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentinipäev</title>
    <style>
        body {
            background-color: black;
            text-align: center;
            font-family: Arial, sans-serif;
            color: white;
            margin: 0;
            overflow: hidden;
        }
        .screen {
            width: 100vw;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: absolute;
            top: 0;
            left: 0;
            background-color: black;
        }
        h1 {
            font-size: 3rem;
            color: red;
            text-shadow: 0 0 10px white;
        }
        .heart {
            font-size: 5rem;
            animation: heartbeat 0.5s infinite alternate, neonGlow 1.5s infinite alternate;
        }
        @keyframes heartbeat {
            from {
                transform: scale(1);
            }
            to {
                transform: scale(1.5);
            }
        }
        @keyframes neonGlow {
            from {
                text-shadow: 0 0 10px red;
            }
            to {
                text-shadow: 0 0 20px white;
            }
        }
        .btn {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 1.5rem;
            background-color: red;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            box-shadow: 0 0 10px red;
            transition: transform 0.2s;
        }
        .btn:hover {
            transform: scale(1.1);
        }
        #noBtn {
            position: absolute;
            font-size: 1.2rem;
            background-color: gray;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 10px;
            cursor: pointer;
        }
        #yesBtn {
            font-size: 1.5rem;
        }
        #secondScreen {
            display: none;
        }
    </style>
</head>
<body>
    <div id="firstScreen" class="screen">
        <h1>Tsau Nunnu, Kelli :3</h1>
        <p class="heart">💖</p>
        <h2>Kas sina oleksid minu valentiin?</h2>
        <img src="tsau.gif" alt="Armas pilt" width="300"> <!-- Lae see fail GitHubi -->
        <br>
        <button class="btn" id="yesBtn" onclick="showSecondScreen()">JAH</button>
        <button id="noBtn" onclick="moveNo()">EI</button>
    </div>
    
    <div id="secondScreen" class="screen">
        <h2>AWWWW AITÄH KALLA 🥰 Ma muud sinust ei ootanudki!</h2>
        <img src="aww.gif" alt="Armastus" width="300"> <!-- Lae see fail GitHubi -->
    </div>
    
    <audio id="bgMusic" loop>
        <source src="macky-gee-erotic.mp3" type="audio/mp3"> <!-- Lae see fail GitHubi -->
        Your browser does not support the audio element.
    </audio>
    
    <script>
        function showSecondScreen() {
            document.getElementById("firstScreen").style.display = "none";
            document.getElementById("secondScreen").style.display = "flex";
            document.getElementById("bgMusic").play();
        }
        function moveNo() {
            let noBtn = document.getElementById("noBtn");
            let x = Math.random() * (window.innerWidth - 100);
            let y = Math.random() * (window.innerHeight - 100);
            noBtn.style.position = "absolute";
            noBtn.style.left = x + "px";
            noBtn.style.top = y + "px";
            noBtn.style.fontSize = (parseFloat(window.getComputedStyle(noBtn).fontSize) - 2) + "px";
            if (parseFloat(noBtn.style.fontSize) < 10) {
                noBtn.style.display = "none";
            }
        }
    </script>
</body>
</html>
