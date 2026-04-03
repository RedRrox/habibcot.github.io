<img src="hk.png" alt="Description">
<img src="hk.png" alt="Description" style="max-width: 100%; height: auto; display: block; margin: 0 auto;">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Habibcot Website</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
            padding: 20px;
        }
        img {
            max-width: 100%; /* মোবাইলে স্ক্রিনের বাইরে যাবে না */
            height: auto;
            border-radius: 15px; /* কোণাগুলো একটু গোল হবে */
            box-shadow: 0 4px 8px rgba(0,0,0,0.1); /* হালকা শ্যাডো */
        }
        h1 {
            color: #333;
        }
    </style>
</head>
<body>

    <h1>habibcot.github.io</h1>
    
    <img src="hk.png" alt="My Image">

    <br><br>

    <audio controls>
        <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
        আপনার ব্রাউজারটি অডিও সাপোর্ট করে না।
    </audio>

</body>
</html>
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Habibcot Animation Website</title>
    <style>
        body {
            margin: 0;
            padding: 20px;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            color: white;
            /* ব্যাকগ্রাউন্ড অ্যানিমেশন */
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradient 10s ease infinite;
            overflow-x: hidden;
        }

        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        h1 {
            font-size: 2.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        img {
            max-width: 90%;
            height: auto;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
            animation: float 4s ease-in-out infinite;
            border: 5px solid rgba(255, 255, 255, 0.2);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px); }
        }

        audio {
            margin-top: 30px;
            filter: drop-shadow(0 5px 15px rgba(0,0,0,0.2));
        }
    </style>
</head>
<body>

    <h1>habibcot.github.io</h1>
    
    <img src="hk.png" alt="My Image">

    <audio controls>
        <source src="meow-ghop-ghop-ghop.mp3" type="audio/mpeg">
        আপনার ব্রাউজারটি অডিও সাপোর্ট করে না।
    </audio>

</body>
</html>
