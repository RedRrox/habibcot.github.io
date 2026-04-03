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
            font-family: sans-serif;
            color: white;
            background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* ডিসক্রিপশন বক্স */
        .desc-box {
            max-width: 450px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            text-align: center;
            margin-top: 20px;
            margin-bottom: 20px;
        }

        .desc-box p {
            font-size: 15px;
            line-height: 1.5;
            color: #222;
            font-weight: 500;
        }

        h1 {
            font-size: 2rem;
            margin-bottom: 20px;
            text-transform: uppercase;
            text-shadow: 1px 1px 5px rgba(0,0,0,0.1);
        }

        /* ছবির জন্য ফিক্সড ডিজাইন */
        .image-box {
            width: 280px; /* আপনার ছবির সাইজ বড় করা হয়েছে */
            margin-bottom: 30px;
        }

        img {
            width: 100%;
            height: auto;
            border-radius: 15px; /* হালকা গোল কোণা, কিন্তু ছবি থাকবে চারকোণা */
            border: 5px solid white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            animation: floating 3s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        #play-btn {
            background: white;
            color: #ff758c;
            border: none;
            padding: 12px 35px;
            font-size: 1rem;
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

    <div class="desc-box">
        <p>
            ধন্যবাদ আমাদের ওয়েবসাইটে আসার জন্য! <br>
            আমাদের ওয়েবসাইটটি কারো অপমান বা ছোট করার জন্য তৈরি করা হয়নি। এটি সম্পূর্ণভাবে মজা এবং বিনোদনের উদ্দেশ্যে তৈরি। তাই কেউ এই ওয়েবসাইটকে খারাপভাবে বা নেতিবাচকভাবে দেখবেন না। আমাদের উদ্দেশ্য শুধু হাসি, আনন্দ এবং ভালো সময় উপভোগ করা। ধন্যবাদ!
        </p>
    </div>

    <h1>Friends</h1>

    <div class="image-box">
        <img src="hk.png" alt="Profile Photo">
    </div>

    <audio id="myAudio" loop>
        <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
    </audio>

    <button id="play-btn" onclick="toggleMusic()">
        <span id="icon">▶</span> <span id="text">Play Music</span>
    </button>

    <script>
        function toggleMusic() {
            const audio = document.getElementById("myAudio");
            const btnText = document.getElementById("text");
            const btnIcon = document.getElementById("icon");
            if (audio.paused) {
                audio.play();
                btnText.innerText = "Pause Music";
                btnIcon.innerText = "⏸";
            } else {
                audio.pause();
                btnText.innerText = "Play Music";
                btnIcon.innerText = "▶";
            }
        }
    </script>

</body>
</html>
