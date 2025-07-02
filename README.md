```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chúc Mừng Sinh Nhật Anime Style!</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap');
        
        :root {
            --primary: #ff6b6b;
            --secondary: #ffb8b8;
            --accent: #ff4757;
            --text: #2f3542;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f1f2f6;
            overflow-x: hidden;
            margin: 0;
            padding: 0;
            color: var(--text);
        }
        
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            background: linear-gradient(135deg, #fff1f1 0%, #ffdfd3 100%);
            z-index: 1;
        }
        
        .bday-text {
            font-size: 5rem;
            font-weight: 700;
            background: linear-gradient(to right, #ff6b6b, #ff0000);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            position: relative;
            z-index: 2;
            text-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        .anime-character {
            width: 300px;
            height: 300px;
            object-fit: contain;
            margin-bottom: 2rem;
            filter: drop-shadow(0 10px 15px rgba(0,0,0,0.1));
            animation: float 3s ease-in-out infinite;
        }
        
        .bday-message {
            font-size: 1.5rem;
            text-align: center;
            max-width: 600px;
            line-height: 1.6;
            margin: 1rem 0;
            padding: 1rem;
            background-color: rgba(255,255,255,0.8);
            border-radius: 15px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        .btn {
            background: linear-gradient(to right, #ff6b6b, #ff4757);
            color: white;
            border: none;
            padding: 0.75rem 1.5rem;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.25rem;
            cursor: pointer;
            margin-top: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255,107,107,0.4);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 25px rgba(255,107,107,0.6);
        }
        
        .btn:active {
            transform: translateY(0);
        }
        
        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 400%;
            height: 100%;
            background: linear-gradient(90deg, 
                              rgba(255,255,255,0.1), 
                              rgba(255,255,255,0.3), 
                              rgba(255,255,255,0.1), 
                              rgba(255,255,255,0.3));
            transform: translateX(-50%);
            transition: all 0.6s ease;
            z-index: -1;
        }
        
        .btn:hover::before {
            animation: shine 1.5s infinite;
        }
        
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #f00;
            border-radius: 50%;
            animation: confetti 5s linear infinite;
            z-index: 0;
        }
        
        .cake {
            margin-top: 2rem;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        
        @keyframes confetti {
            0% { 
                transform: translateY(0) rotate(0deg); 
                opacity: 1;
            }
            100% { 
                transform: translateY(100vh) rotate(720deg); 
                opacity: 0;
            }
        }
        
        @keyframes shine {
            0% { transform: translateX(-50%); }
            100% { transform: translateX(0%); }
        }
    </style>
</head>
<body>
    <div class="hero">
        <img src="https://placehold.co/400x400/ff6b6b/white" alt="Anime character kawaii with big eyes and birthday hat celebrating with confetti" class="anime-character" />
        <h1 class="bday-text">お誕生日おめでとう!</h1>
        <div class="bday-message">
            Nhân dịp sinh nhật, chúc bạn một năm mới tràn ngập niềm vui, hạnh phúc và may mắn! Hy vọng bạn sẽ có một ngày thật đặc biệt với nhiều điều bất ngờ! 
            <br><br>
            "Hãy tiếp tục tỏa sáng như một ngôi sao trên con đường của chính mình!" ✨
        </div>
        <button class="btn" id="birthdayBtn">Ấn Vào Đây Để Nhận Quà!</button>
        
        <!-- Confetti elements will be generated by JS -->
    </div>
    
    <div class="cake">
        <img src="https://placehold.co/400x200/ff6b6b/white" alt="Anime style birthday cake with strawberries and candles glowing in soft light" />
    </div>
    
    <script>
        const btn = document.getElementById('birthdayBtn');
        const colors = ['#ff6b6b', '#ff7f50', '#ffa502', '#eccc68', '#2ed573', '#1dd1a1', '#2e86de', '#5f27cd', '#a55eea', '#ff6b81'];
        
        btn.addEventListener('click', function() {
            // Create confetti
            for(let i = 0; i < 150; i++) {
                createConfetti();
            }
            
            // Change message
            const messages = [
                "Sinh nhật vui vẻ! 🎉",
                "Chúc bạn một ngày tuyệt vời! ✨",
                "Mãi xinh đẹp và hạnh phúc nhé! 💖",
                "Năm mới nhiều thành công! 🏆",
                "Hẹn một năm đáng nhớ phía trước! 🌟"
            ];
            
            document.querySelector('.bday-message').textContent = messages[Math.floor(Math.random() * messages.length)];
            
            // Change button text
            btn.textContent = "Yay! Cảm Ơn Bạn!";
            setTimeout(() => {
                btn.textContent = "Ấn Thêm Lần Nữa!";
            }, 2000);
        });
        
        function createConfetti() {
            const confetti = document.createElement('div');
            confetti.classList.add('confetti');
            
            // Random properties
            const size = Math.random() * 10 + 5;
            const color = colors[Math.floor(Math.random() * colors.length)];
            const posX = Math.random() * window.innerWidth;
            const duration = Math.random() * 3 + 2;
            const delay = Math.random() * 2;
            const shape = Math.random() > 0.5 ? '50%' : '0';
            
            // Apply styles
            confetti.style.width = `${size}px`;
            confetti.style.height = `${size}px`;
            confetti.style.backgroundColor = color;
            confetti.style.left = `${posX}px`;
            confetti.style.borderRadius = shape;
            confetti.style.animationDuration = `${duration}s`;
            confetti.style.animationDelay = `${delay}s`;
            
            document.querySelector('.hero').appendChild(confetti);
            
            // Remove after animation
            setTimeout(() => {
                confetti.remove();
            }, duration * 1000);
        }
    </script>
</body>
</html>
