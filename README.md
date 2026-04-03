<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends Official Site</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
            font-family: Arial, sans-serif;
            color: white;
            /* ব্যাকগ্রাউন্ড কালার */
            background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* উপরের ডিসক্রিপশন বক্স */
        .description-container {
            max-width: 500px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            text-align: center;
            margin: 20px 0;
        }

        .description-container p {
            font-size: 15px;
            line-height: 1.6;
            color: #222;
            font-weight: 500;
        }

        h1 {
            font-size: 2.2rem;
            margin-bottom: 20px;
            text-transform: uppercase;
        }

        /* ছবির ডিজাইন (চারকোণা রাখার জন্য) */
        .photo-frame {
            width: 300px; /* আপনার পছন্দমতো বড় করা হয়েছে */
            margin-bottom: 30px;
        }

        img {
            width: 100%;
            height: auto;
            border-radius: 10px; /* খুব সামান্য গোল কোণা, যা চারকোণা ভাব নষ্ট করবে না */
            border: 6px solid white;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
            animation: floating 3s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-12px); }
        }

        /* মিউজিক বাটন */
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
    </style>
</head>
<body>

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

    <script>
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
