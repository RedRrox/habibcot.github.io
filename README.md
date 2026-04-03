<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    
    <link rel="icon" type="image/jpeg" href="rrp.jpg?v=1.1">

    <style>
        :root {
            --bg-gradient: linear-gradient(-45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            --text-color: #222;
            --box-bg: rgba(255, 255, 255, 0.2);
            --title-color: white;
        }

        /* ডার্ক মোড কালার */
        [data-theme="dark"] {
            --bg-gradient: linear-gradient(-45deg, #2c3e50, #000000, #434343);
            --text-color: #ddd;
            --box-bg: rgba(0, 0, 0, 0.4);
            --title-color: #ff758c;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            transition: background 0.5s, color 0.5s;
        }

        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
            font-family: Arial, sans-serif;
            color: var(--title-color);
            background: var(--bg-gradient);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* ডার্ক মোড সুইচ */
        .theme-switch {
            position: absolute;
            top: 20px;
            right: 20px;
            cursor: pointer;
            background: var(--box-bg);
            padding: 10px;
            border-radius: 50%;
            border: 1px solid rgba(255,255,255,0.3);
            font-size: 1.2rem;
        }

        .description-container {
            max-width: 500px;
            background: var(--box-bg);
            backdrop-filter: blur(10px);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            text-align: center;
            margin: 40px 0 20px 0;
        }

        .description-container p {
            font-size: 15px;
            line-height: 1.6;
            color: var(--text-color);
            font-weight: 500;
        }

        h1 {
            font-size: 2.2rem;
            margin-bottom: 20px;
            text-transform: uppercase;
        }

        .photo-frame {
            width: 280px;
            margin-bottom: 30px;
        }

        img {
            width: 100%;
            height: auto;
            border-radius: 15px;
            border: 5px solid white;
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            animation: floating 3s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-12px); }
        }

        .play-music-btn {
            background: white;
            color: #ff758c;
            border: none;
            padding: 15px 40px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        /* ভিজিটর কাউন্টার স্টাইল */
        .visitor-counter {
            margin-top: auto;
            padding: 20px;
            font-size: 0.9rem;
            color: var(--text-color);
            text-align: center;
        }
    </style>
</head>
<body>

    <div class="theme-switch" onclick="toggleTheme()" id="themeIcon">🌙</div>

    <div class="description-container">
        <p>
            ধন্যবাদ আমাদের ওয়েবসাইটে আসার জন্য! <br>
            আমাদের ওয়েবসাইটটি কারো অপমান বা ছোট করার জন্য তৈরি করা হয়নি। এটি সম্পূর্ণভাবে মজা এবং বিনোদনের উদ্দেশ্যে তৈরি। তাই কেউ এই ওয়েবসাইটকে খারাপভাবে বা নেতিবাচকভাবে দেখবেন না। আমাদের উদ্দেশ্য শুধু হাসি, আনন্দ এবং ভালো সময় উপভোগ করা। ধন্যবাদ!
        </p>
    </div>

    <h1>Friends</h1>

    <div class="photo-frame">
        <img src="hk.png" alt="Profile Image">
    </div>

    <audio id="bgMusic" loop>
        <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
    </audio>

    <button class="play-music-btn" onclick="playPause()">
        <span id="btnIcon">▶</span> <span id="btnText">Play Music</span>
    </button>

    <div class="visitor-counter">
        <p>Total Visitors</p>
        <img src="https://profile-counter.glitch.me/redrrox/count.svg" alt="Visitor Count">
    </div>

    <script>
        // ডার্ক মোড ফাংশন
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

        // মিউজিক ফাংশন
        function playPause() {
            const audio = document.getElementById("bgMusic");
            const txt = document.getElementById("btnText");
            const icon = document.getElementById("btnIcon");
            
            if (audio.paused) {
                audio.play();
                txt.innerText = "Pause Music";
                icon.innerText = "⏸";
            } else {
                audio.pause();
                txt.innerText = "Play Music";
                icon.innerText = "▶";
            }
        }
    </script>

</body>
</html>
