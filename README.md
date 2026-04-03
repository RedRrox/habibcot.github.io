<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends Official Site</title>
    <style>
        /* পুরো পেজের জন্য মেইন ডিজাইন */
        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            font-family: 'Segoe UI', Arial, sans-serif;
            color: white;
            /* কালারফুল ব্যাকগ্রাউন্ড অ্যানিমেশন */
            background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* আপনার নতুন নাম: Friends */
        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            text-shadow: 2px 4px 10px rgba(0,0,0,0.2);
            letter-spacing: 3px;
            text-transform: uppercase;
        }

        /* ইমেজ কন্টেইনার এবং ভাসমান অ্যানিমেশন */
        .image-box {
            width: 250px;
            max-width: 80%;
            margin-bottom: 30px;
        }

        img {
            width: 100%;
            height: auto;
            border-radius: 30px; /* সুন্দর রাউন্ডেড কোণা */
            border: 8px solid rgba(255, 255, 255, 0.4);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            animation: floating 4s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* অডিও প্লেয়ার ডিজাইন */
        audio {
            width: 300px;
            max-width: 90%;
            filter: drop-shadow(0 10px 15px rgba(0,0,0,0.2));
            border-radius: 50px;
        }

        /* নিচের ছোট টেক্সট */
        .footer-text {
            margin-top: 30px;
            font-size: 1.2rem;
            font-weight: 500;
            background: rgba(255, 255, 255, 0.2);
            padding: 10px 25px;
            border-radius: 30px;
            backdrop-filter: blur(5px);
        }
    </style>
</head>
<body>

    <h1>Friends</h1>

    <div class="image-box">
        <img src="hk.png" alt="Friends Profile">
    </div>

    <audio controls>
        <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
        আপনার ব্রাউজারটি অডিও সাপোর্ট করে না।
    </audio>

    <div class="footer-text">Welcome to the world of Friends!</div>

</body>
</html>
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Friends Official Site</title>
    <style>
        /* মোবাইল অপ্টিমাইজড রিসেট */
        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent; /* মোবাইলে ক্লিকের নীল দাগ সরাতে */
        }

        body {
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            font-family: 'Segoe UI', Roboto, sans-serif;
            color: white;
            background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            background-size: 400% 400%;
            animation: gradientBG 10s ease infinite;
            overflow: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        h1 {
            font-size: 2.2rem;
            margin-bottom: 15px;
            text-shadow: 1px 3px 8px rgba(0,0,0,0.2);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        /* ইমেজ সেকশন */
        .image-box {
            width: 220px;
            height: 220px;
            margin-bottom: 25px;
        }

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%;
            border: 4px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
            animation: floating 3s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-12px); }
        }

        /* ফ্যান্সি মিউজিক বাটন */
        .music-wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
        }

        #play-btn {
            background: rgba(255, 255, 255, 0.9);
            color: #ff758c;
            border: none;
            padding: 18px 45px;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
            display: flex;
            align-items: center;
            gap: 12px;
            transition: transform 0.2s active;
        }

        /* মোবাইলে চাপ দিলে হালকা ছোট হবে (ক্লিক ইফেক্ট) */
        #play-btn:active {
            transform: scale(0.95);
        }

        /* মিউজিক ওয়েভস */
        .waves-container {
            display: flex;
            align-items: flex-end;
            height: 25px;
            gap: 4px;
            visibility: hidden; /* শুরুতে জায়গা দখল করবে কিন্তু দেখাবে না */
        }

        .bar {
            width: 5px;
            height: 8px;
            background: white;
            border-radius: 10px;
        }

        .playing .bar {
            animation: wave 0.6s linear infinite;
        }

        @keyframes wave {
            0%, 100% { height: 8px; }
            50% { height: 25px; }
        }

        .bar:nth-child(2) { animation-delay: 0.1s; }
        .bar:nth-child(3) { animation-delay: 0.2s; }
        .bar:nth-child(4) { animation-delay: 0.3s; }

    </style>
</head>
<body>

    <h1>Friends</h1>

    <div class="image-box">
        <img src="hk.png" alt="Profile">
    </div>

    <div class="music-wrapper">
        <audio id="myAudio" loop>
            <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
        </audio>

        <button id="play-btn" onclick="toggleMusic()">
            <span id="icon">▶</span> <span id="text">Play Music</span>
        </button>

        <div class="waves-container" id="waveBox">
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
        </div>
    </div>

    <script>
        const audio = document.getElementById("myAudio");
        const btnText = document.getElementById("text");
        const btnIcon = document.getElementById("icon");
        const waveBox = document.getElementById("waveBox");

        function toggleMusic() {
            if (audio.paused) {
                audio.play().catch(e => {
                    alert("মোবাইলে অটো-প্লে বন্ধ থাকতে পারে। বাটনে আবার ক্লিক করুন!");
                });
                btnText.innerText = "Pause Music";
                btnIcon.innerText = "⏸";
                waveBox.style.visibility = "visible";
                waveBox.classList.add("playing");
            } else {
                audio.pause();
                btnText.innerText = "Play Music";
                btnIcon.innerText = "▶";
                waveBox.classList.remove("playing");
                waveBox.style.visibility = "hidden";
            }
        }
    </script>

</body>
</html>
