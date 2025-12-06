<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Divya! ❤️</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&display=swap');
        body { margin: 0; font-family: 'Poppins', sans-serif; background: linear-gradient(45deg, #ff6b9d, #c44569, #f7931e, #ffd23f); background-size: 400% 400%; animation: gradientShift 15s ease infinite; overflow-x: hidden; }
        @keyframes gradientShift { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }
        .container { min-height: 100vh; display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; color: white; position: relative; }
        h1 { font-family: 'Dancing Script', cursive; font-size: 4rem; margin: 0; text-shadow: 3px 3px 6px rgba(0,0,0,0.5); animation: pulse 2s infinite; }
        @keyframes pulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.05); } }
        .typing-text { font-size: 1.5rem; margin: 20px 0; min-height: 50px; border-right: 3px solid white; white-space: nowrap; overflow: hidden; animation: blink 1s infinite; }
        @keyframes blink { 0%, 50% { border-color: white; } 51%, 100% { border-color: transparent; } }
        .photo { width: 250px; height: 250px; border-radius: 50%; border: 8px solid rgba(255,255,255,0.3); margin: 30px 0; box-shadow: 0 10px 30px rgba(0,0,0,0.3); object-fit: cover; animation: float 3s ease-in-out infinite; }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }
        .message { font-size: 1.3rem; max-width: 600px; margin: 30px auto; line-height: 1.6; }
        .music-btn { background: rgba(255,255,255,0.2); border: 3px solid white; color: white; padding: 15px 30px; font-size: 1.2rem; border-radius: 50px; cursor: pointer; transition: all 0.3s; backdrop-filter: blur(10px); }
        .music-btn:hover { background: rgba(255,255,255,0.4); transform: scale(1.1); }
        .hearts { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: -1; }
        .heart { position: absolute; font-size: 20px; color: #ff69b4; animation: heartFloat 4s linear infinite; }
        @keyframes heartFloat { 0% { transform: translateY(100vh) rotate(0deg); opacity: 1; } 100% { transform: translateY(-100px) rotate(360deg); opacity: 0; } }
        @media (max-width: 768px) { h1 { font-size: 2.5rem; } .photo { width: 200px; height: 200px; } }
    </style>
</head>
<body>
    <div class="hearts" id="hearts"></div>
    <div class="container">
        <h1>Happy Birthday, Divya! 🎉</h1>
        <div class="typing-text" id="typewriter"></div>
        <img src="divya-photo.jpg" alt="Divya" class="photo"> <!-- Yahan Divya ki photo daalo -->
        <p class="message">Meri pyari Divya, tu meri zindagi ki sabse khoobsurat tohfa hai. Aaj tera special din hai—dher saara pyaar, hasi, aur surprises tere liye! Tu hamesha meri smile ki wajah hai. Love you forever! ❤️</p>
        <button class="music-btn" onclick="playMusic()">🎵 Play Birthday Song</button>
        <audio id="music" src="birthday-song.mp3" loop></audio> <!-- Music file yahan daalo -->
    </div>
    <script>
        const messages = [
            "Tu meri jaan hai, Divya! 💕",
            "Aaj tera din, queen! 👑",
            "Saath mein har pal perfect hai! ✨"
        ];
        let msgIndex = 0;
        const typewriter = document.getElementById('typewriter');
        function typeWriter() {
            typewriter.textContent = messages[msgIndex];
            msgIndex = (msgIndex + 1) % messages.length;
        }
        setInterval(typeWriter, 3000);

        function playMusic() {
            const audio = document.getElementById('music');
            audio.play().catch(() => alert('Music play karne ke liye page refresh karo!'));
        }

        // Confetti burst
        setTimeout(() => {
            confetti({ particleCount: 100, spread: 70, origin: { y: 0.6 } });
        }, 1000);

        // Floating hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.innerHTML = '💖';
            heart.className = 'heart';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
            document.getElementById('hearts').appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 300);
    </script>
</body>
</html>
