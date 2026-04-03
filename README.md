<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends</title>
    
    <link rel="icon" type="image/jpeg" href="rrp.jpg">

    <style>
        :root {
            --bg-gradient: linear-gradient(-45deg, #0f2027, #203a43, #2c5364);
            --text-color: #ffffff;
            --box-bg: rgba(255, 255, 255, 0.1);
        }

        [data-theme="dark"] {
            --bg-gradient: linear-gradient(-45deg, #000000, #434343);
            --text-color: #ff758c;
            --box-bg: rgba(0, 0, 0, 0.6);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; transition: 0.5s; }

        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background: var(--bg-gradient);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
            font-family: sans-serif;
            color: var(--text-color);
            padding: 20px;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .theme-switch {
            position: fixed;
            top: 20px;
            right: 20px;
            cursor: pointer;
            background: var(--box-bg);
            padding: 10px;
            border-radius: 50%;
            border: 1px solid rgba(255,255,255,0.2);
            font-size: 1.5rem;
        }

        .description-container {
            max-width: 500px;
            background: var(--box-bg);
            backdrop-filter: blur(10px);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            margin-bottom: 20px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        h1 { margin-bottom: 20px; letter-spacing: 2px; }

        .photo-frame { width: 300px; max-width: 90%; }

        img.profile-img {
            width: 100%;
            height: auto;
            border-radius: 15px;
            border: 5px solid white;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .play-music-btn {
            margin-top: 25px;
            background: white;
            color: #ff758c;
            border: none;
            padding: 15px 35px;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 10px;
        }
    </style>
</head>
<body>

    <div class="theme-switch" onclick="toggleTheme()" id="themeIcon">🌙</div>

    <div class="description-container">
        <p>ধন্যবাদ আমাদের ওয়েবসাইটে আসার জন্য! এটি বিনোদনের উদ্দেশ্যে তৈরি।</p>
    </div>

    <h1>Friends</h1>

    <div class="photo-frame">
        <img src="nk.jpg" alt="Profile Image" class="profile-img">
    </div>

    <audio id="bgMusic" loop>
        <source src="cid.mp3" type="audio/mpeg">
    </audio>

    <button class="play-music-btn" onclick="playPause()">
        <span id="btnIcon">▶</span> <span id="btnText">Play Music</span>
    </button>

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
