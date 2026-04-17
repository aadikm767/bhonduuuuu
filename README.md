# bhonduuuuu
<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Bhondu! ❤️</title>
    <style>
        :root {
            --pink: #ff85a2;
            --dark-pink: #ff4d6d;
            --soft-white: #fff0f3;
        }

        body, html {
            margin: 0; padding: 0; height: 100%; width: 100%;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--soft-white);
            overflow: hidden;
            display: flex; justify-content: center; align-items: center;
        }

        .page {
            position: absolute; width: 100%; height: 100%;
            display: flex; flex-direction: column;
            justify-content: center; align-items: center;
            transition: all 0.8s ease-in-out;
            text-align: center; padding: 20px; box-sizing: border-box;
        }

        .hidden { opacity: 0; pointer-events: none; display: none !important; }

        /* Page 1 Styles */
        .profile-img {
            width: 200px; height: 200px; border-radius: 50%;
            border: 6px solid white; box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            object-fit: cover; animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        input {
            padding: 12px; border-radius: 25px; border: 2px solid var(--pink);
            margin-top: 20px; width: 220px; text-align: center; outline: none; font-size: 16px;
        }

        .btn {
            background: var(--pink); color: white; border: none;
            padding: 12px 25px; border-radius: 25px; cursor: pointer;
            font-weight: bold; margin-top: 15px; transition: 0.3s;
        }
        .btn:hover { background: var(--dark-pink); transform: scale(1.05); }

        /* Page 2 Styles */
        .big-gift { font-size: 120px; cursor: pointer; animation: shake 1s infinite; display: inline-block; }
        @keyframes shake {
            0% { transform: rotate(0); }
            20% { transform: rotate(-10deg); }
            40% { transform: rotate(10deg); }
            60% { transform: rotate(-10deg); }
            80% { transform: rotate(10deg); }
            100% { transform: rotate(0); }
        }

        /* Page 3 Styles */
        .grid { display: flex; gap: 15px; justify-content: center; flex-wrap: wrap; }
        .small-box {
            font-size: 50px; background: white; padding: 20px;
            border-radius: 15px; cursor: pointer; box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: 0.3s;
        }
        .small-box:hover { transform: scale(1.1); background: #fff5f7; }

        /* Modals */
        .modal {
            position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%);
            background: white; padding: 25px; border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3); z-index: 100;
            width: 85%; max-width: 380px; text-align: center;
        }

        #cake-img { width: 140px; cursor: pointer; transition: 0.5s; }
        .sweet-pic { width: 100%; border-radius: 15px; margin-bottom: 15px; }
        .letter-text { text-align: left; line-height: 1.6; color: #444; font-size: 15px; }

        .hearts-container { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 1; }
    </style>
</head>
<body>

    <audio id="music" loop>
        <source src="https://docs.google.com/uc?export=download&id=1v7OxNPdOqlXrTus4x-xNmzFKwd2UIGOS" type="audio/mpeg">
    </audio>

    <div class="hearts-container" id="hearts"></div>

    <div id="p1" class="page">
        <img src="https://docs.google.com/uc?export=download&id=1QO6l3p3zUNc1sZblGxMvhXaOSW1cT7fQ" class="profile-img">
        <h2 style="color: var(--dark-pink); margin-top: 20px;">Hey My Panda! ❤️</h2>
        <input type="password" id="pass" placeholder="Enter secret code...">
        <button class="btn" onclick="login()">Unlock My Heart 🔓</button>
    </div>

    <div id="p2" class="page hidden">
        <h1 style="color: var(--dark-pink);">A Surprise for You...</h1>
        <div class="big-gift" onclick="openBigGift()">🎁</div>
        <p style="color: #666; font-style: italic;">Tap the box to see what's inside!</p>
    </div>

    <div id="p3" class="page hidden">
        <h2 style="color: var(--dark-pink); margin-bottom: 30px;">Choose your gifts, Bhondu! ✨</h2>
        <div class="grid">
            <div class="small-box" onclick="showGift(1)">📦</div>
            <div class="small-box" onclick="showGift(2)">📦</div>
            <div class="small-box" onclick="showGift(3)">📦</div>
        </div>
        <p style="margin-top: 20px; color: #888;">Ek-ek karke kholo! 😉</p>
    </div>

    <div id="m1" class="modal hidden">
        <h3>Gift #1: Blow the Candle! 🕯️</h3>
        <img src="https://cdn-icons-png.flaticon.com/512/3132/3132715.png" id="cake-img" onclick="blow()">
        <div id="cake-msg"></div>
        <button class="btn" onclick="closeM(1)">Close</button>
    </div>

    <div id="m2" class="modal hidden">
        <h3>Gift #2: My Sweetest View ✨</h3>
        <img src="https://docs.google.com/uc?export=download&id=1rdVd6sgKWsodlG2BhqGrRQnK875DrOVe" class="sweet-pic">
        <p>You look so cute here! 🌸</p>
        <button class="btn" onclick="closeM(2)">Close</button>
    </div>

    <div id="m3" class="modal hidden">
        <h3>Gift #3: From My Heart 💌</h3>
        <div class="letter-text">
            Happy Birthday pyaari Bhonduuuu! 🎂❤️<br><br>
            Tumhe pata hai na ki tum mere liye kitni special hai? Tum thodi si buddhu ho thodi si ziddi bhi 😝😝 lekin jaisi bhi ho... Bestest ever ho!<br><br>
            I promise ki main hamesha tumahre saath khada raunga tumhari saari baate sunne ke liye aur tumhe har mushkil mein sambhalne ke liye Tayyar hu. Tum hamesha aise hi hasti rehna kyunki tumhari smile dekh kar mera din ban jata hai.<br><br>
            Stay the same, my favorite Bhonduuuu! ✨🥹🎈
        </div>
        <button class="btn" onclick="closeM(3)">Close</button>
    </div>

    <script>
        const music = document.getElementById('music');

        function login() {
            if(document.getElementById('pass').value.toLowerCase() === 'panda') {
                document.getElementById('p1').classList.add('hidden');
                document.getElementById('p2').classList.remove('hidden');
                music.play().catch(e => console.log("Music play blocked"));
                spawnHearts();
            } else {
                alert("Wrong code, Bhondu! Hint: Panda 😉");
            }
        }

        function openBigGift() {
            document.getElementById('p2').classList.add('hidden');
            document.getElementById('p3').classList.remove('hidden');
        }

        function showGift(n) { document.getElementById('m' + n).classList.remove('hidden'); }
        function closeM(n) { document.getElementById('m' + n).classList.add('hidden'); }

        function blow() {
            document.getElementById('cake-img').style.opacity = "0.4";
            document.getElementById('cake-img').style.transform = "scale(0.8)";
            document.getElementById('cake-msg').innerHTML = "<h2 style='color:var(--dark-pink)'>Happy birthday bhonduuuu! 🎉</h2>";
        }

        function spawnHearts() {
            const container = document.getElementById('hearts');
            setInterval(() => {
                const h = document.createElement('div');
                h.innerHTML = "❤️";
                h.style.position = "absolute";
                h.style.left = Math.random() * 100 + "vw";
                h.style.bottom = "-20px";
                h.style.fontSize = Math.random() * 20 + 10 + "px";
                h.style.color = "#ff4d6d";
                h.style.opacity = Math.random();
                h.style.transition = "all 4s linear";
                container.appendChild(h);
                setTimeout(() => {
                    h.style.transform = "translateY(-110vh) rotate(360deg)";
                    h.style.opacity = "0";
                }, 100);
                setTimeout(() => h.remove(), 4000);
            }, 400);
        }
    </script>
</body>
</html>
