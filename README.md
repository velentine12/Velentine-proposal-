<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Special Message For You</title>
    <style>
        body {
            background-color: #fff0f3;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
            text-align: center;
        }

        .container {
            background: white;
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(255, 75, 110, 0.2);
            z-index: 10;
        }

        h1 {
            color: #ff4b6e;
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        p {
            color: #555;
            font-size: 1.2rem;
            line-height: 1.6;
        }

        .buttons {
            margin-top: 2rem;
        }

        button {
            padding: 15px 30px;
            font-size: 1.1rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.2s;
            margin: 0 10px;
        }

        #yesBtn {
            background-color: #ff4b6e;
            color: white;
        }

        #yesBtn:hover {
            background-color: #e03a5c;
            transform: scale(1.1);
        }

        #noBtn {
            background-color: #f0f0f0;
            color: #888;
        }

        /* Floating hearts animation */
        .heart {
            position: absolute;
            color: #ff4b6e;
            font-size: 20px;
            user-select: none;
            animation: float 5s linear infinite;
            opacity: 0.6;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); }
            100% { transform: translateY(-10vh) rotate(360deg); }
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>Hey [Bumblebee]! ❤️</h1>
        <p>I put this together because I wanted to tell you <br> 
        how much you mean to me. Every day is better with you.</p>
        
        <h2>Will you be my Valentine?</h2>

        <div class="buttons">
            <button id="yesBtn" onclick="celebrate()">YES!</button>
            <button id="noBtn" onmouseover="moveButton()">No</button>
        </div>
    </div>

    <script>
        // Create falling hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 2 + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 300);

        // Make the "No" button run away
        function moveButton() {
            const btn = document.getElementById('noBtn');
            const x = Math.random() * (window.innerWidth - btn.offsetWidth);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight);
            btn.style.position = 'absolute';
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        // Celebrate the "Yes"
        function celebrate() {
            document.querySelector('.container').innerHTML = `
                <h1>Yay! See you on the 14th! 🎉</h1>
                <p>You just made me the happiest person ever.</p>
                <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHY5eWJ6N3Z6ZzJ3ZzJ3ZzJ3ZzJ3ZzJ3ZzJ3ZzJ3ZzJ3ZzJ3JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1n/KzM1lAfJjCW3dq3Zvx/giphy.gif" width="250">
            `;
        }
    </script>
</body>
</html>
