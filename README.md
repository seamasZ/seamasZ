<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>图片展示主页</title>
    <style>
        /* 全局样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
            padding: 2rem;
            font-family: 'Arial', sans-serif;
        }

        /* 霓虹标题 */
        .neon-title {
            text-align: center;
            margin-bottom: 2rem;
            font-size: 2.5rem;
            color: #fff;
            text-shadow: 0 0 5px #ff6b9d, 0 0 20px #ff6b9d, 0 0 40px #ff6b9d;
            animation: flicker 2s infinite alternate;
        }
        @keyframes flicker {
            from { text-shadow: 0 0 5px #ff6b9d, 0 0 20px #ff6b9d; }
            to { text-shadow: 0 0 10px #ff6b9d, 0 0 30px #ff6b9d, 0 0 60px #ff6b9d; }
        }

        /* 轮播容器 */
        .carousel-container {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 0 30px rgba(255, 107, 157, 0.5);
        }
        .carousel {
            display: flex;
            transition: transform 0.8s cubic-bezier(0.4, 0, 0.2, 1); /* 平滑过渡动画 */
        }
        .carousel-item {
            flex-shrink: 0;
            width: 100%;
            height: 500px;
            position: relative;
        }
        .carousel-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        /* 悬停放大特效 */
        .carousel-item:hover .carousel-img {
            transform: scale(1.05); /* 放大5% */
        }
        /* 图片描述遮罩 */
        .img-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            padding: 1.5rem;
            background: linear-gradient(transparent, rgba(0,0,0,0.7));
            color: white;
            font-size: 1.2rem;
            opacity: 0;
            transition: opacity 0.5s ease;
        }
        .carousel-item:hover .img-caption {
            opacity: 1; /* 悬停显示描述 */
        }

        /* 轮播控制按钮 */
        .carousel-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            border: none;
            background: rgba(255,255,255,0.8);
            color: #ff6b9d;
            font-size: 1.5rem;
            cursor: pointer;
            z-index: 10;
            transition: all 0.3s ease;
        }
        .carousel-btn:hover {
            background: #ff6b9d;
            color: white;
            box-shadow: 0 0 15px #ff6b9d;
        }
        .prev-btn { left: 20px; }
        .next-btn { right: 20px; }

        /* 指示器圆点 */
        .indicators {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
            z-index: 10;
        }
        .indicator {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255,255,255,0.5);
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .indicator.active {
            background: #ff6b9d;
            width: 30px;
            border-radius: 6px;
            box-shadow: 0 0 10px #ff6b9d;
        }

        /* 响应式适配（手机/电脑通用） */
        @media (max-width: 768px) {
            .neon-title { font-size: 1.8rem; }
            .carousel-item { height: 300px; }
            .carousel-btn { width: 35px; height: 35px; font-size: 1rem; }
        }
    </style>
</head>
<body>
    <!-- 霓虹标题 -->
    <h1 class="neon-title">石原里美 图片展示</h1>

    <!-- 轮播容器 -->
    <div class="carousel-container">
        <div class="carousel" id="carousel">
            <!-- 图片1 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1027/1200/500" alt="石原里美-写真" class="carousel-img">
                <div class="img-caption">清新写真风格</div>
            </div>
            <!-- 图片2 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1025/1200/500" alt="石原里美-日常" class="carousel-img">
                <div class="img-caption">日常穿搭记录</div>
            </div>
            <!-- 图片3 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1011/1200/500" alt="石原里美-杂志" class="carousel-img">
                <div class="img-caption">杂志封面拍摄</div>
            </div>
            <!-- 图片4 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1005/1200/500" alt="石原里美-活动" class="carousel-img">
                <div class="img-caption">活动现场造型</div>
            </div>
            <!-- 图片5 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1003/1200/500" alt="石原里美-街拍" class="carousel-img">
                <div class="img-caption">街头随拍瞬间</div>
            </div>
            <!-- 图片6 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1015/1200/500" alt="石原里美-复古" class="carousel-img">
                <div class="img-caption">复古风写真</div>
            </div>
            <!-- 图片7 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1018/1200/500" alt="石原里美-职场" class="carousel-img">
                <div class="img-caption">职场剧造型</div>
            </div>
            <!-- 图片8 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1019/1200/500" alt="石原里美-休闲" class="carousel-img">
                <div class="img-caption">休闲度假风格</div>
            </div>
            <!-- 图片9 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1023/1200/500" alt="石原里美-正装" class="carousel-img">
                <div class="img-caption">正装出席活动</div>
            </div>
            <!-- 图片10 -->
            <div class="carousel-item">
                <img src="https://picsum.photos/id/1024/1200/500" alt="石原里美-清新" class="carousel-img">
                <div class="img-caption">夏日清新写真</div>
            </div>
        </div>

        <!-- 控制按钮 -->
        <button class="carousel-btn prev-btn" id="prevBtn">←</button>
        <button class="carousel-btn next-btn" id="nextBtn">→</button>

        <!-- 指示器 -->
        <div class="indicators" id="indicators">
            <div class="indicator active"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
            <div class="indicator"></div>
        </div>
    </div>

    <script>
        // 轮播逻辑
        const carousel = document.getElementById('carousel');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        const indicators = document.getElementById('indicators').children;
        const items = carousel.children;
        let currentIndex = 0;
        const itemCount = items.length;
        const autoplayInterval = 3000; // 自动轮播间隔（3秒）
        let autoplayTimer;

        // 更新轮播位置
        function updateCarousel() {
            carousel.style.transform = `translateX(-${currentIndex * 100}%)`;
            // 更新指示器
            Array.from(indicators).forEach((ind, idx) => {
                ind.classList.toggle('active', idx === currentIndex);
            });
        }

        // 下一张
        function nextSlide() {
            currentIndex = (currentIndex + 1) % itemCount;
            updateCarousel();
        }

        // 上一张
        function prevSlide() {
            currentIndex = (currentIndex - 1 + itemCount) % itemCount;
            updateCarousel();
        }

        // 指示器点击
        Array.from(indicators).forEach((ind, idx) => {
            ind.addEventListener('click', () => {
                currentIndex = idx;
                updateCarousel();
                restartAutoplay(); // 点击后重启自动轮播
            });
        });

        // 自动轮播
        function startAutoplay() {
            autoplayTimer = setInterval(nextSlide, autoplayInterval);
        }

        // 重启自动轮播
        function restartAutoplay() {
            clearInterval(autoplayTimer);
            startAutoplay();
        }

        // 按钮事件
        prevBtn.addEventListener('click', () => {
            prevSlide();
            restartAutoplay();
        });
        nextBtn.addEventListener('click', () => {
            nextSlide();
            restartAutoplay();
        });

        // 鼠标悬停暂停自动轮播
        carousel-container.addEventListener('mouseenter', () => {
            clearInterval(autoplayTimer);
        });
        carousel-container.addEventListener('mouseleave', startAutoplay);

        // 初始化
        startAutoplay();
    </script>
</body>
</html>
