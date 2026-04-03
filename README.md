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
