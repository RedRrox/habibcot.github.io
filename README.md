<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends Collection</title>
    
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
            font-family: 'Segoe UI', Tahoma, sans-serif;
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
            font-size: 2.2rem;
            margin-bottom: 40px;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: white;
            text-shadow: 2px 2px 8px rgba(0,0,0,0.1);
        }

        /* এক লাইনে সব রাখার কন্টেইনার */
        .content-stack {
            width: 320px;
            max-width: 95%;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 45px; /* প্রতিটি মেমোরির মাঝে গ্যাপ */
        }

        .memory-item {
            width: 100%;
            text-align: center;
        }

        img {
            width: 100%;
            border-radius: 15px;
            border: 5px solid white;
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
            margin-bottom: 12px;
            background: rgba(255,255,255,0.1);
            min-height: 200px;
        }

        .play-btn {
            background: white;
            color: #ff758c;
            border: none;
            padding: 14px;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            width: 100%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .play-btn:active { transform: scale(0.98); }
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

    <div class="content-stack">
        
        <div class="memory-item">
            <img src="hk.png" alt="Memory 1">
            <audio id="audio1" loop><source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio1', this)">▶ Play Music 1</button>
        </div>

        <div class="memory-item">
            <img src="nayem.png" alt="Memory 2">
            <audio id="audio2" loop><source src="music2.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio2', this)">▶ Play Music 2</button>
        </div>

        <div class="memory-item">
            <img src="pic3.png" alt="Memory 3">
            <audio id="audio3" loop><source src="tuibesijanos.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio3', this)">▶ Play Music 3</button>
        </div>

        <div class="memory-item">
            <img src="dipjolpost.png" onerror="this.src='https://raw.githubusercontent.com/RedRrox/friend/main/dipjolpost.png'" alt="Memory 4">
            <audio id="audio4" loop><source src="asol.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio4', this)">▶ Play Music 4</button>
        </div>

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
            
            // সব অডিও বন্ধ করার লজিক
            document.querySelectorAll('audio').forEach(m => {
                if(m.id !== id) {
                    m.pause();
                    let b = m.nextElementSibling;
                    let num = m.id.replace('audio', '');
                    b.innerText = "▶ Play Music " + num;
                }
            });

            if (audio.paused) {
                audio.play();
                btn.innerText = "⏸ Pause Music";
            } else {
                audio.pause();
                btn.innerText = "▶ Play Music " + id.replace('audio', '');
            }
        }
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends Collection</title>
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
            font-family: 'Segoe UI', Tahoma, sans-serif;
            color: var(--text);
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
        }

        @keyframes gradient { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }

        .theme-btn { position: fixed; top: 20px; right: 20px; cursor: pointer; background: var(--glass); padding: 12px; border-radius: 50%; font-size: 1.5rem; border: 1px solid rgba(255,255,255,0.3); z-index: 1000; }

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
        }

        h1 { font-size: 2.2rem; margin-bottom: 40px; text-transform: uppercase; color: white; text-shadow: 2px 2px 8px rgba(0,0,0,0.1); }

        .content-stack {
            width: 320px;
            max-width: 95%;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 45px;
        }

        .memory-item { width: 100%; text-align: center; }

        img {
            width: 100%;
            min-height: 250px; /* ছবি না এলেও জায়গা ধরে রাখবে */
            border-radius: 15px;
            border: 5px solid white;
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
            margin-bottom: 12px;
            background: #eee;
            object-fit: cover;
            display: block;
        }

        .play-btn {
            background: white;
            color: #ff758c;
            border: none;
            padding: 14px;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            width: 100%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
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

    <div class="content-stack">
        
        <div class="memory-item">
            <img src="hk.png" loading="lazy">
            <audio id="audio1" loop><source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio1', this)">▶ Play Music 1</button>
        </div>

        <div class="memory-item">
            <img src="nayem.png" loading="lazy">
            <audio id="audio2" loop><source src="music2.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio2', this)">▶ Play Music 2</button>
        </div>

        <div class="memory-item">
            <img src="pic3.png" loading="lazy">
            <audio id="audio3" loop><source src="tuibesijanos.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio3', this)">▶ Play Music 3</button>
        </div>

        <div class="memory-item">
            <img src="dipjolpost.png" loading="lazy">
            <audio id="audio4" loop><source src="asol.mp3" type="audio/mpeg"></audio>
            <button class="play-btn" onclick="playMusic('audio4', this)">▶ Play Music 4</button>
        </div>

    </div>

    <script>
        function toggleTheme() {
            const body = document.body;
            const icon = document.getElementById("themeIcon");
            if (body.getAttribute("data-theme") === "dark") {
                body.removeAttribute("data-theme"); icon.innerText = "🌙";
            } else {
                body.setAttribute("data-theme", "dark"); icon.innerText = "☀️";
            }
        }

        function playMusic(id, btn) {
            const audio = document.getElementById(id);
            document.querySelectorAll('audio').forEach(m => {
                if(m.id !== id) {
                    m.pause();
                    let b = m.nextElementSibling;
                    let num = m.id.replace('audio', '');
                    b.innerText = "▶ Play Music " + num;
                }
            });
            if (audio.paused) {
                audio.play();
                btn.innerText = "⏸ Pause Music";
            } else {
                audio.pause();
                btn.innerText = "▶ Play Music " + id.replace('audio', '');
            }
        }
    </script>
</body>
</html>
