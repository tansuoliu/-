<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>永恒之约 | 刘宇航 ❤️ 李爽</title>
    <style>
        :root {
            --primary: #ff3366;
            --secondary: #ff758c;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Microsoft YaHei', sans-serif;
            min-height: 100vh;
            background: linear-gradient(135deg, #0f0c29, #302b63);
            overflow: hidden;
            position: relative;
        }

        .container {
            position: relative;
            z-index: 2;
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.1);
            max-width: 800px;
            margin: 5% auto;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .title {
            text-align: center;
            color: white;
            margin-bottom: 40px;
            position: relative;
        }

        .title h1 {
            font-size: 3.5em;
            text-shadow: 0 0 20px var(--primary);
            animation: glow 2s ease-in-out infinite;
        }

        .timeline {
            position: relative;
            padding: 40px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            width: 4px;
            height: 100%;
            background: linear-gradient(to bottom, var(--primary), var(--secondary));
        }

        .timeline-item {
            position: relative;
            width: 50%;
            padding: 20px;
            opacity: 0;
            transform: translateY(50px);
            transition: all 1s ease;
        }

        .timeline-item.left {
            left: 0;
            text-align: right;
        }

        .timeline-item.right {
            left: 50%;
        }

        .timeline-content {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 10px;
            position: relative;
            backdrop-filter: blur(5px);
        }

        .heart-container {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 1;
        }

        .heart {
            position: absolute;
            width: 50px;
            height: 50px;
            background: var(--primary);
            transform: rotate(45deg);
            animation: pulse 2s infinite;
        }

        .heart::before,
        .heart::after {
            content: '';
            position: absolute;
            width: 50px;
            height: 50px;
            background: var(--primary);
            border-radius: 50%;
        }

        .heart::before {
            top: -25px;
            left: 0;
        }

        .heart::after {
            left: -25px;
            top: 0;
        }

        @keyframes pulse {
            0% { transform: rotate(45deg) scale(1); }
            50% { transform: rotate(45deg) scale(1.2); }
            100% { transform: rotate(45deg) scale(1); }
        }

        @keyframes glow {
            0%, 100% { text-shadow: 0 0 20px var(--primary); }
            50% { text-shadow: 0 0 40px var(--secondary); }
        }

        .particles {
            position: fixed;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
    </style>
</head>
<body>
    <canvas class="particles" id="canvas"></canvas>

    <div class="heart-container">
        <div class="heart"></div>
    </div>

    <div class="container">
        <div class="title">
            <h1>刘宇航 ❤️ 李爽</h1>
            <p style="color: rgba(255,255,255,0.8); margin-top: 20px;">2023.03.09 - 永恒</p>
        </div>

        <div class="timeline">
            <div class="timeline-item left" style="transition-delay: 0.2s;">
                <div class="timeline-content">
                    <h3 style="color: var(--primary);">初见</h3>
                    <p style="color: rgba(255,255,255,0.8); margin-top: 10px;">2023年3月9日<br>命运安排我们在时光长河中相遇</p>
                </div>
            </div>

            <div class="timeline-item right" style="transition-delay: 0.4s;">
                <div class="timeline-content">
                    <h3 style="color: var(--primary);">相知</h3>
                    <p style="color: rgba(255,255,255,0.8); margin-top: 10px;">365个日夜的温暖<br>每个瞬间都在编织我们的故事</p>
                </div>
            </div>

            <div class="timeline-item left" style="transition-delay: 0.6s;">
                <div class="timeline-content">
                    <h3 style="color: var(--primary);">相爱</h3>
                    <p style="color: rgba(255,255,255,0.8); margin-top: 10px;">星辰见证的誓言<br>心跳的节奏谱成永恒乐章</p>
                </div>
            </div>

            <div class="timeline-item right" style="transition-delay: 0.8s;">
                <div class="timeline-content">
                    <h3 style="color: var(--primary);">未来</h3>
                    <p style="color: rgba(255,255,255,0.8); margin-top: 10px;">以爱为舟<br>共渡每一个朝阳与星夜</p>
                </div>
            </div>
        </div>
    </div>

    <script>
        // 粒子背景
        const canvas = document.getElementById('canvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2;
                this.speedX = Math.random() * 3 - 1.5;
                this.speedY = Math.random() * 3 - 1.5;
            }

            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                if (this.x > canvas.width) this.x = 0;
                if (this.x < 0) this.x = canvas.width;
                if (this.y > canvas.height) this.y = 0;
                if (this.y < 0) this.y = canvas.height;
            }

            draw() {
                ctx.fillStyle = `rgba(255,51,102,${this.size/2})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        const particles = Array(200).fill().map(() => new Particle());

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(particle => {
                particle.update();
                particle.draw();
            });
            requestAnimationFrame(animate);
        }
        animate();

        // 时间轴动画
        const timelineItems = document.querySelectorAll('.timeline-item');
        window.addEventListener('scroll', () => {
            timelineItems.forEach(item => {
                const itemTop = item.getBoundingClientRect().top;
                if (itemTop < window.innerHeight * 0.8) {
                    item.style.opacity = 1;
                    item.style.transform = 'translateY(0)';
                }
            });
        });

        // 动态爱心
        document.addEventListener('click', (e) => {
            const heart = document.createElement('div');
            heart.style.cssText = `
                position: absolute;
                left: ${e.clientX - 10}px;
                top: ${e.clientY - 10}px;
                width: 20px;
                height: 20px;
                background: ${Math.random() > 0.5 ? '#ff3366' : '#ff758c'};
                transform: rotate(45deg);
                animation: burst 0.8s linear forwards;
            `;

            heart.innerHTML = '<div></div>';
            document.body.appendChild(heart);
            
            setTimeout(() => heart.remove(), 800);
        });
    </script>
</body>
</html>
