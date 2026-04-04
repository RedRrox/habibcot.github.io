<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    
    <link rel="icon" type="image/jpeg" href="rrp.jpg">

    <style>
        :root {
            --bg: linear-gradient(-45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            --text: #222;
            --glass: rgba(255, 255, 255, 0.3);
        }

        [data-theme="dark"] {
            --bg: linear-gradient(-45deg, #1a1a2e, #16213e, #0f3460);
            --text: #eee;
            --glass: rgba(0, 0, 0, 0.5);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; transition: 0.4s; }

        body {
            min-height: 100vh;
            background: var(--bg);
            background-size: 400% 400%;
            animation: gradient 15s infinite;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--text);
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .theme-btn {
            position: fixed;
            top: 20px;
            right: 20px;
            cursor: pointer;
            background: var(--glass);
            padding: 12px;
            border-radius: 50%;
            font-size: 1.5rem;
            border: 1px solid rgba(255,255,255,0.3);
            z-index: 1000;
        }

        .description-box {
            max-width: 550px;
            width: 95%;
            background: var(--glass);
            backdrop-filter: blur(15px);
            padding: 25px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.4);
            text-align: center;
            margin-top: 60px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .description-box p {
            font-size: 16px;
            line-height: 1.7;
            font-weight: 500;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            text-transform: uppercase;
            letter-spacing: 3px;
            color: white;
            text-shadow: 2px 2px 10px rgba(0,0,0,0.2);
        }

        .card {
            width: 320px;
            max-width: 90%;
            margin-bottom: 50px;
            text-align: center;
        }

        img {
            width: 100%;
            border-radius: 20px;
            border: 6px solid white;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            margin-bottom: 20px;
        }

        .play-btn {
            background: white;
            color: #ff758c;
            border: none;
            padding: 15px 40px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            width: 100%;
            box-shadow: 0 8px 20px rgba(0,0,0,0.1);
        }

        .play-btn:active { transform: scale(0.95); }
    </style>
</head>
<body>

    <div class="theme-btn" onclick="toggleTheme()" id="themeIcon">🌙</div>

    <div class="description-box">
        <p>
            ধন্যবাদ আমাদের ওয়েবসাইটে আসার জন্য! <br>
            আমাদের ওয়েবসাইটটি কারো অপমান বা ছোট করার জন্য তৈরি করা হয়নি। এটি সম্পূর্ণভাবে মজা এবং বিনোদনের উদ্দেশ্যে তৈরি। তাই কেউ এই ওয়েবসাইটকে খারাপভাবে বা নেতিবাচকভাবে দেখবেন না। আমাদের উদ্দেশ্য শুধু হাসি, আনন্দ এবং ভালো সময় উপভোগ করা। ধন্যবাদ!
        </p>
    </div>

    <h1>Friends</h1>

    <div class="card">
        <img src="hk.png" alt="Memory 1">
        <audio id="audio1" loop><source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg"></audio>
        <button class="play-btn" onclick="playMusic('audio1', this)">▶ Play Music 1</button>
    </div>

    <div class="card">
        <img src="nk.jpg?v=1.1" alt="Memory 2">
        <audio id="audio2" loop><source src="cid.mp3?v=1.1" type="audio/mpeg"></audio>
        <button class="play-btn" onclick="playMusic('audio2', this)">▶ Play Music 2</button>
    </div>

    <script>
        function toggleTheme() {
            const body = document.body;
            const icon = document.getElementById("themeIcon");
            if (body.getAttribute("data-theme") === "dark") {
                body.removeAttribute("data-theme");
                icon.innerText = "🌙";
            } else {
                body.setAttribute("data-theme", "dark");
                icon.innerText = "☀️";
            }
        }

        function playMusic(id, btn) {
            const audio = document.getElementById(id);
            
            // একটি চালালে অন্যটি বন্ধ হবে
            document.querySelectorAll('audio').forEach(m => {
                if(m.id !== id) {
                    m.pause();
                    m.nextElementSibling.innerText = m.id === "audio1" ? "▶ Play Music 1" : "▶ Play Music 2";
                }
            });

            if (audio.paused) {
                audio.play();
                btn.innerText = "⏸ Pause Music";
            } else {
                audio.pause();
                btn.innerText = "▶ Play Music";
            }
        }
    </script>

</body>
</html>
