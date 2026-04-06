<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Friends Collection</title>
    <link rel="icon" type="image/jpeg" href="rrp.jpg">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: linear-gradient(-45deg, #1e3c72, #2a5298, #ff512f, #dd2476);
            --text: #fff;
            --glass: rgba(255, 255, 255, 0.15);
        }
        [data-theme="dark"] {
            --bg: linear-gradient(-45deg, #0f0c29, #302b63, #24243e);
            --glass: rgba(0, 0, 0, 0.6);
        }
        * { margin: 0; padding: 0; box-sizing: border-box; transition: 0.4s; font-family: 'Poppins', sans-serif; }
        body {
            min-height: 100vh;
            background: var(--bg);
            background-size: 400% 400%;
            animation: gradientBG 12s ease infinite;
            color: var(--text);
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
        }
        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        canvas { position: fixed; top: 0; left: 0; z-index: -1; }
        .theme-btn { position: fixed; top: 20px; right: 20px; cursor: pointer; background: var(--glass); padding: 12px; border-radius: 50%; font-size: 1.5rem; border: 1px solid rgba(255,255,255,0.3); z-index: 1000; }
        .description-box {
            max-width: 550px;
            width: 95%;
            background: var(--glass);
            backdrop-filter: blur(15px);
            padding: 25px;
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            text-align: center;
            margin-top: 60px;
            margin-bottom: 30px;
        }
        h1 { 
            font-size: 2.5rem; 
            margin-bottom: 40px; 
            text-transform: uppercase; 
            text-shadow: 0 0 10px cyan, 0 0 20px cyan;
        }
        .content-stack {
            width: 320px;
            max-width: 95%;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 50px;
        }
        .fade-in {
            opacity: 0;
            transform: translateY(40px);
            transition: 1s all ease-out;
            width: 100%;
        }
        .fade-in.show {
            opacity: 1;
            transform: translateY(0);
        }
        img, video {
            width: 100%;
            border-radius: 20px;
            border: 4px solid white;
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
            margin-bottom: 15px;
        }
        .play-btn {
            background: white;
            color: #ff512f;
            border: none;
            padding: 15px;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            width: 100%;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            text-transform: uppercase;
        }
        .play-btn:hover {
            background: #222;
            color: white;
            transform: scale(1.05) rotate(2deg);
        }
    </style>
</head>
<body>

    <canvas id="particles"></canvas>
    <div class="theme-btn" onclick="toggleTheme()" id="themeIcon">🌙</div>

    <div class="description-box">
        <p>
            ধন্যবাদ আমাদের ওয়েবসাইটে আসার জন্য! <br>
            আমাদের ওয়েবসাইটটি কারো অপমান বা ছোট করার জন্য তৈরি করা হয়নি। এটি সম্পূর্ণভাবে মজা এবং বিনোদনের উদ্দেশ্যে তৈরি। তাই কেউ এই ওয়েবসাইটকে খারাপভাবে বা নেতিবাচকভাবে দেখবেন না। আমাদের উদ্দেশ্য শুধু হাসি, আনন্দ এবং ভালো সময় উপভোগ করা। ধন্যবাদ!
        </p>
    </div>

    <h1>Friends</h1>

    <div class="content-stack">
        <div class="memory-item fade-in">
            <img src="hk.png">
            <audio id="audio1" loop><source src="meow-ghop-ghop-ghop.mp3"></audio>
            <button class="play-btn" onclick="playMusic('audio1', this)">▶ Play Music 1</button>
        </div>
        <div class="memory-item fade-in">
            <img src="nayem.png">
            <audio id="audio2" loop><source src="music2.mp3"></audio>
            <button class="play-btn" onclick="playMusic('audio2', this)">▶ Play Music 2</button>
        </div>
        <div class="memory-item fade-in">
            <img src="pic3.png">
            <audio id="audio3" loop><source src="tuibesijanos.mp3"></audio>
            <button class="play-btn" onclick="playMusic('audio3', this)">▶ Play Music 3</button>
        </div>
        <div class="memory-item fade-in">
            <img src="pic4.jpg">
            <audio id="audio4" loop><source src="asol.mp3"></audio>
            <button class="play-btn" onclick="playMusic('audio4', this)">▶ Play Music 4</button>
        </div>
        <div class="memory-item fade-in">
            <video controls><source src="irfan.mp4"></video>
        </div>
    </div>

    <script>
        window.addEventListener("scroll", function(){
            document.querySelectorAll(".fade-in").forEach(function(el){
                if(el.getBoundingClientRect().top < window.innerHeight / 1.2){
                    el.classList.add("show");
                }
            });
        });
        window.dispatchEvent(new Event('scroll'));

        const canvas = document.getElementById("particles");
        const ctx = canvas.getContext("2d");
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        let particlesArray = [];
        class Particle{
            constructor(){
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 1;
                this.speedX = Math.random() * 1 - 0.5;
                this.speedY = Math.random() * 1 - 0.5;
            }
            update(){
                this.x += this.speedX;
                this.y += this.speedY;
                if(this.x > canvas.width) this.x = 0;
                if(this.x < 0) this.x = canvas.width;
                if(this.y > canvas.height) this.y = 0;
                if(this.y < 0) this.y = canvas.height;
            }
            draw(){
                ctx.fillStyle = "rgba(255, 255, 255, 0.7)";
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI*2);
                ctx.fill();
            }
        }
        function init(){ for(let i=0;i<80;i++){ particlesArray.push(new Particle()); } }
        function animate(){
            ctx.clearRect(0,0,canvas.width,canvas.height);
            for(let i=0;i<particlesArray.length;i++){
                particlesArray[i].update();
                particlesArray[i].draw();
            }
            requestAnimationFrame(animate);
        }
        init(); animate();

        function toggleTheme() {
            const body = document.body;
            if (body.getAttribute("data-theme") === "dark") {
                body.removeAttribute("data-theme"); document.getElementById("themeIcon").innerText = "🌙";
            } else {
                body.setAttribute("data-theme", "dark"); document.getElementById("themeIcon").innerText = "☀️";
            }
        }

        function playMusic(id, btn) {
            const audio = document.getElementById(id);
            document.querySelectorAll('video').forEach(v => v.pause());
            document.querySelectorAll('audio').forEach(m => {
                if(m.id !== id) {
                    m.pause();
                    m.nextElementSibling.innerText = "▶ Play Music " + m.id.replace('audio', '');
                }
            });
            if (audio.paused) {
                audio.play(); btn.innerText = "⏸ Pause Music";
            } else {
                audio.pause(); btn.innerText = "▶ Play Music " + id.replace('audio', '');
            }
        }
    </script>
</body>
</html>
