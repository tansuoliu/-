<酥酥-情人节礼物>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>情人节礼物 - 刘宇航 ❤️ 李爽</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            background: url('https://i.imgur.com/6QZQZQZ.png') no-repeat center center fixed;
            background-size: cover;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.8);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            max-width: 400px;
            width: 100%;
            position: relative;
            z-index: 2;
        }
        h1 {
            color: #ff6f61;
            font-size: 2.5em;
            margin-bottom: 20px;
        }
        input {
            width: 80%;
            padding: 10px;
            margin: 10px 0;
            border: 2px solid #ff6f61;
            border-radius: 5px;
            font-size: 1em;
        }
        button {
            background: #ff6f61;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 1em;
            border-radius: 5px;
            cursor: pointer;
            transition: background 0.3s ease;
        }
        button:hover {
            background: #ff3b2f;
        }
        .message {
            margin-top: 20px;
            font-size: 1.2em;
            color: #333;
            opacity: 0;
            animation: fadeIn 2s forwards;
        }
        @keyframes fadeIn {
            to {
                opacity: 1;
            }
        }
        .heart {
            position: absolute;
            top: -10%;
            font-size: 2em;
            color: #ff6f61;
            animation: fall 5s linear infinite;
        }
        @keyframes fall {
            to {
                transform: translateY(110vh);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>💖 情人节快乐！ 💖</h1>
        <p>请输入你们的名字：</p>
        <input type="text" id="loverName" placeholder="爱人的名字">
        <input type="text" id="yourName" placeholder="你的名字">
        <button onclick="checkNames()">生成祝福</button>
        <div id="message" class="message"></div>
    </div>

    <!-- 动态爱心 -->
    <div id="hearts"></div>

    <script>
        function checkNames() {
            const loverName = document.getElementById('loverName').value;
            const yourName = document.getElementById('yourName').value;
            const messageDiv = document.getElementById('message');

            if (loverName !== '李爽' || yourName !== '刘宇航') {
                alert('请输入正确的名字哦！');
                return;
            }

            const messages = [
                `亲爱的李爽，`,
                `从2023年3月9号相识相知相爱至今，`,
                `每一天与你在一起都是幸福的时光。`,
                `你是我生命中最美好的存在，`,
                `无论未来如何，我都会一直爱你、珍惜你。`,
                `爱你的，刘宇航 💕`
            ];

            messageDiv.innerHTML = messages.join('<br>');
        }

        // 动态生成爱心
        function createHearts() {
            const heartsContainer = document.getElementById('hearts');
            for (let i = 0; i < 50; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart';
                heart.innerHTML = '❤️';
                heart.style.left = `${Math.random() * 100}vw`;
                heart.style.animationDuration = `${Math.random() * 3 + 2}s`;
                heartsContainer.appendChild(heart);
            }
        }

        // 初始化爱心
        createHearts();
    </script>
</body>
</html>
