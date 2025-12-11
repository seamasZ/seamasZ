<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile - 开发者名称</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #6366f1;
            --secondary-color: #8b5cf6;
            --accent-color: #ec4899;
            --bg-color: #0f172a;
            --card-bg: #1e293b;
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --border-color: #334155;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, var(--bg-color) 0%, #1e1b4b 100%);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            padding: 80px 0 60px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .header-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 50% 50%, var(--primary-color) 0%, transparent 70%);
            opacity: 0.1;
            animation: pulse 8s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.1; }
            50% { transform: scale(1.1); opacity: 0.15; }
        }

        .avatar {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 4px solid var(--primary-color);
            margin: 0 auto 30px;
            display: block;
            box-shadow: 0 0 40px rgba(99, 102, 241, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            z-index: 2;
        }

        .avatar:hover {
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 0 60px rgba(99, 102, 241, 0.5);
        }

        h1 {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 10px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            z-index: 2;
            animation: slideInDown 1s ease-out;
        }

        @keyframes slideInDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .title {
            font-size: 1.25rem;
            color: var(--text-secondary);
            margin-bottom: 30px;
            position: relative;
            z-index: 2;
            animation: slideInUp 1s ease-out 0.2s both;
        }

        @keyframes slideInUp {
            from {
                transform: translateY(50px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            position: relative;
            z-index: 2;
            animation: fadeIn 1s ease-out 0.4s both;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .social-links a {
            color: var(--text-secondary);
            font-size: 1.5rem;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .social-links a:hover {
            color: var(--primary-color);
            transform: translateY(-5px);
            background: rgba(99, 102, 241, 0.1);
            border-color: var(--primary-color);
            box-shadow: 0 10px 20px rgba(99, 102, 241, 0.2);
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 60px 0;
        }

        .stat-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 20px;
            border: 1px solid var(--border-color);
            text-align: center;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .stat-card:hover::before {
            transform: scaleX(1);
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border-color: var(--primary-color);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary-color);
            display: block;
        }

        .stat-label {
            font-size: 1rem;
            color: var(--text-secondary);
            margin-top: 10px;
        }

        /* Repositories */
        .repositories {
            margin: 80px 0;
        }

        .section-title {
            font-size: 2rem;
            font-weight: 600;
            margin-bottom: 40px;
            text-align: center;
            position: relative;
            padding-bottom: 20px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 2px;
        }

        .repo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .repo-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 20px;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .repo-card::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, var(--primary-color), transparent);
            opacity: 0.1;
            transition: transform 0.3s ease;
        }

        .repo-card:hover::before {
            transform: scale(2);
        }

        .repo-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            border-color: var(--primary-color);
        }

        .repo-name {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--primary-color);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .repo-name i {
            font-size: 1.2rem;
        }

        .repo-description {
            color: var(--text-secondary);
            margin-bottom: 20px;
            font-size: 0.95rem;
        }

        .repo-meta {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            align-items: center;
        }

        .repo-meta span {
            display: flex;
            align-items: center;
            gap: 5px;
            color: var(--text-secondary);
            font-size: 0.85rem;
        }

        .language-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: var(--accent-color);
        }

        /* Contributions Graph */
        .contributions {
            margin: 80px 0;
            text-align: center;
        }

        .contribution-graph {
            background: var(--card-bg);
            padding: 40px;
            border-radius: 20px;
            border: 1px solid var(--border-color);
            display: inline-block;
            margin: 0 auto;
        }

        .graph-grid {
            display: grid;
            grid-template-columns: repeat(52, 15px);
            gap: 5px;
            grid-template-rows: repeat(7, 15px);
        }

        .graph-cell {
            width: 15px;
            height: 15px;
            border-radius: 3px;
            background: var(--border-color);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .graph-cell:hover {
            transform: scale(1.5);
        }

        .graph-cell.level-1 { background: rgba(59, 130, 246, 0.3); }
        .graph-cell.level-2 { background: rgba(59, 130, 246, 0.5); }
        .graph-cell.level-3 { background: rgba(59, 130, 246, 0.7); }
        .graph-cell.level-4 { background: rgba(59, 130, 246, 0.9); }

        /* Skills */
        .skills {
            margin: 80px 0;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
        }

        .skill-item {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 15px;
            border: 1px solid var(--border-color);
            text-align: center;
            transition: all 0.3s ease;
        }

        .skill-item:hover {
            transform: translateY(-5px);
            border-color: var(--primary-color);
            box-shadow: 0 10px 20px rgba(99, 102, 241, 0.2);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        .skill-name {
            font-weight: 500;
            color: var(--text-primary);
        }

        /* Footer */
        footer {
            padding: 60px 0 30px;
            text-align: center;
            color: var(--text-secondary);
            border-top: 1px solid var(--border-color);
            margin-top: 100px;
        }

        .footer-content {
            max-width: 600px;
            margin: 0 auto;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
        }

        .footer-links a {
            color: var(--text-secondary);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--primary-color);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }

            .avatar {
                width: 150px;
                height: 150px;
            }

            .stats {
                grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
                gap: 15px;
            }

            .repo-grid {
                grid-template-columns: 1fr;
            }

            .graph-grid {
                grid-template-columns: repeat(52, 10px);
                gap: 3px;
                grid-template-rows: repeat(7, 10px);
            }

            .graph-cell {
                width: 10px;
                height: 10px;
            }

            .contribution-graph {
                padding: 20px;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 2rem;
            }

            .title {
                font-size: 1.1rem;
            }

            .social-links {
                gap: 15px;
            }

            .social-links a {
                width: 45px;
                height: 45px;
                font-size: 1.25rem;
            }

            .stat-card {
                padding: 20px;
            }

            .stat-number {
                font-size: 2rem;
            }
        }

        /* Scroll Animation */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.6s ease, transform 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <header>
            <div class="header-bg"></div>
            <img src="https://avatars.githubusercontent.com/u/your-user-id" alt="Avatar" class="avatar">
            <h1>开发者名称</h1>
            <p class="title">全栈开发者 | 开源贡献者 | 技术爱好者</p>
            <div class="social-links">
                <a href="https://github.com/your-username" target="_blank" title="GitHub"><i class="fab fa-github"></i></a>
                <a href="https://twitter.com/your-username" target="_blank" title="Twitter"><i class="fab fa-twitter"></i></a>
                <a href="https://linkedin.com/in/your-username" target="_blank" title="LinkedIn"><i class="fab fa-linkedin"></i></a>
                <a href="https://dev.to/your-username" target="_blank" title="Dev.to"><i class="fab fa-dev"></i></a>
                <a href="https://blog.your-website.com" target="_blank" title="Blog"><i class="fas fa-blog"></i></a>
            </div>
        </header>

        <!-- Stats -->
        <section class="stats">
            <div class="stat-card fade-in">
                <span class="stat-number">100+</span>
                <span class="stat-label">仓库</span>
            </div>
            <div class="stat-card fade-in">
                <span class="stat-number">500+</span>
                <span class="stat-label">贡献</span>
            </div>
            <div class="stat-card fade-in">
                <span class="stat-number">10k+</span>
                <span class="stat-label">星标</span>
            </div>
            <div class="stat-card fade-in">
                <span class="stat-number">100+</span>
                <span class="stat-label">关注者</span>
            </div>
        </section>

        <!-- Contributions Graph -->
        <section class="contributions fade-in">
            <h2 class="section-title">贡献图表</h2>
            <div class="contribution-graph">
                <div class="graph-grid">
                    <!-- 生成贡献图表单元格 -->
                    <script>
                        for (let i = 0; i < 364; i++) {
                            const level = Math.floor(Math.random() * 5);
                            const cell = document.createElement('div');
                            cell.className = `graph-cell level-${level}`;
                            cell.title = `${Math.floor(Math.random() * 10)} contributions`;
                            document.querySelector('.graph-grid').appendChild(cell);
                        }
                    </script>
                </div>
            </div>
        </section>

        <!-- Repositories -->
        <section class="repositories fade-in">
            <h2 class="section-title">精选仓库</h2>
            <div class="repo-grid">
                <div class="repo-card">
                    <h3 class="repo-name"><i class="fab fa-react"></i> awesome-project</h3>
                    <p class="repo-description">一个基于React的现代化Web应用，提供了丰富的功能和优雅的用户界面。</p>
                    <div class="repo-meta">
                        <span><div class="language-dot" style="background: #61DAFB;"></div> React</span>
                        <span><i class="fas fa-star"></i> 120</span>
                        <span><i class="fas fa-code-branch"></i> 25</span>
                        <span><i class="far fa-calendar"></i> 2天前更新</span>
                    </div>
                </div>
                <div class="repo-card">
                    <h3 class="repo-name"><i class="fab fa-node-js"></i> node-api</h3>
                    <p class="repo-description">高性能的Node.js API框架，支持RESTful和GraphQL接口。</p>
                    <div class="repo-meta">
                        <span><div class="language-dot" style="background: #339933;"></div> JavaScript</span>
                        <span><i class="fas fa-star"></i> 85</span>
                        <span><i class="fas fa-code-branch"></i> 18</span>
                        <span><i class="far fa-calendar"></i> 5天前更新</span>
                    </div>
                </div>
                <div class="repo-card">
                    <h3 class="repo-name"><i class="fab fa-python"></i> data-science-tools</h3>
                    <p class="repo-description">数据科学和机器学习工具集合，包含各种实用的算法和模型。</p>
                    <div class="repo-meta">
                        <span><div class="language-dot" style="background: #3776AB;"></div> Python</span>
                        <span><i class="fas fa-star"></i> 200</span>
                        <span><i class="fas fa-code-branch"></i> 40</span>
                        <span><i class="far fa-calendar"></i> 1周前更新</span>
                    </div>
                </div>
                <div class="repo-card">
                    <h3 class="repo-name"><i class="fab fa-vuejs"></i> vue-components</h3>
                    <p class="repo-description">Vue.js组件库，提供了丰富的UI组件和工具函数。</p>
                    <div class="repo-meta">
                        <span><div class="language-dot" style="background: #4FC08D;"></div> Vue</span>
                        <span><i class="fas fa-star"></i> 150</span>
                        <span><i class="fas fa-code-branch"></i> 32</span>
                        <span><i class="far fa-calendar"></i> 3天前更新</span>
                    </div>
                </div>
                <div class="repo-card">
                    <h3 class="repo-name"><i class="fas fa-database"></i> database-utils</h3>
                    <p class="repo-description">数据库工具包，支持多种数据库的连接和操作。</p>
                    <div class="repo-meta">
                        <span><div class="language-dot" style="background: #007ACC;"></div> TypeScript</span>
                        <span><i class="fas fa-star"></i> 95</span>
                        <span><i class="fas fa-code-branch"></i> 15</span>
                        <span><i class="far fa-calendar"></i> 1周前更新</span>
                    </div>
                </div>
                <div class="repo-card">
                    <h3 class="repo-name"><i class="fab fa-android"></i> android-app</h3>
                    <p class="repo-description">Android移动应用开发项目，使用Kotlin语言编写。</p>
                    <div class="repo-meta">
                        <span><div class="language-dot" style="background: #7F52FF;"></div> Kotlin</span>
                        <span><i class="fas fa-star"></i> 110</span>
                        <span><i class="fas fa-code-branch"></i> 22</span>
                        <span><i class="far fa-calendar"></i> 2周前更新</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills -->
        <section class="skills fade-in">
            <h2 class="section-title">技术栈</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <div class="skill-icon"><i class="fab fa-html5"></i></div>
                    <div class="skill-name">HTML5</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><i class="fab fa-css3-alt"></i></div>
                    <div class="skill-name">CSS3</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><i class="fab fa-js"></i></div>
                    <div class="skill-name">JavaScript</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><i class="fab fa-react"></i></div>
                    <div class="skill-name">React</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><i class="fab fa-node-js"></i></div>
                    <div class="skill-name">Node.js</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><i class="fab fa-python"></i></div>
                    <div class="skill-name">Python</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><i class="fab fa-docker"></i></div>
                    <div class="skill-name">Docker</div>
                </div>
                <div class="skill-item">
                    <div class="skill-icon"><i class="fas fa-database"></i></div>
                    <div class="skill-name">Database</div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="fade-in">
            <div class="footer-content">
                <p>感谢访问我的GitHub主页！</p>
                <div class="footer-links">
                    <a href="https://github.com/your-username">GitHub</a>
                    <a href="https://twitter.com/your-username">Twitter</a>
                    <a href="https://linkedin.com/in/your-username">LinkedIn</a>
                    <a href="mailto:your-email@example.com">Email</a>
                </div>
                <p style="margin-top: 30px; font-size: 0.9rem;">&copy; 2024 开发者名称. All rights reserved.</p>
            </div>
        </footer>
    </div>

    <script>
        // 滚动动画
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // GitHub API 集成（可选）
        // 取消注释以下代码以获取真实的GitHub数据
        /*
        const username = 'your-username';
        
        // 获取用户信息
        fetch(`https://api.github.com/users/${username}`)
            .then(response => response.json())
            .then(data => {
                document.querySelector('.avatar').src = data.avatar_url;
                document.querySelector('h1').textContent = data.name || data.login;
                document.querySelector('.title').textContent = data.bio || '';
            })
            .catch(error => console.error('Error fetching user data:', error));
        
        // 获取仓库信息
        fetch(`https://api.github.com/users/${username}/repos?sort=updated&per_page=6`)
            .then(response => response.json())
            .then(repos => {
                const repoGrid = document.querySelector('.repo-grid');
                repoGrid.innerHTML = '';
                
                repos.forEach(repo => {
                    const repoCard = document.createElement('div');
                    repoCard.className = 'repo-card';
                    repoCard.innerHTML = `
                        <h3 class="repo-name"><i class="fab fa-${repo.language ? getLanguageIcon(repo.language) : 'code'}"></i> ${repo.name}</h3>
                        <p class="repo-description">${repo.description || 'No description'}</p>
                        <div class="repo-meta">
                            <span><div class="language-dot" style="background: ${getLanguageColor(repo.language)}"></div> ${repo.language || 'Unknown'}</span>
                            <span><i class="fas fa-star"></i> ${repo.stargazers_count}</span>
                            <span><i class="fas fa-code-branch"></i> ${repo.forks_count}</span>
                            <span><i class="far fa-calendar"></i> ${formatDate(repo.updated_at)}</span>
                        </div>
                    `;
                    repoGrid.appendChild(repoCard);
                });
            })
            .catch(error => console.error('Error fetching repos:', error));
        
        function getLanguageIcon(language) {
            const icons = {
                'JavaScript': 'js',
                'TypeScript': 'js',
                'Python': 'python',
                'Java': 'java',
                'C++': 'cplusplus',
                'C#': 'csharp',
                'PHP': 'php',
                'Ruby': 'ruby',
                'Go': 'golang',
                'Rust': 'rust',
                'Swift': 'swift',
                'Kotlin': 'kotlin',
                'HTML': 'html5',
                'CSS': 'css3-alt',
                'React': 'react',
                'Vue': 'vuejs',
                'Angular': 'angular',
                'Node.js': 'node-js',
                'Docker': 'docker'
            };
            return icons[language] || 'code';
        }
        
        function getLanguageColor(language) {
            const colors = {
                'JavaScript': '#F7DF1E',
                'TypeScript': '#3178C6',
                'Python': '#3776AB',
                'Java': '#007396',
                'C++': '#00599C',
                'C#': '#239120',
                'PHP': '#777BB4',
                'Ruby': '#CC342D',
                'Go': '#00ADD8',
                'Rust': '#DEA584',
                'Swift': '#FA7343',
                'Kotlin': '#7F52FF',
                'HTML': '#E34F26',
                'CSS': '#1572B6',
                'React': '#61DAFB',
                'Vue': '#4FC08D',
                'Angular': '#DD0031'
            };
            return colors[language] || '#94A3B8';
        }
        
        function formatDate(dateString) {
            const date = new Date(dateString);
            const now = new Date();
            const diffTime = Math.abs(now - date);
            const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));
            
            if (diffDays === 0) return '今天更新';
            if (diffDays === 1) return '昨天更新';
            if (diffDays < 7) return `${diffDays}天前更新`;
            if (diffDays < 30) return `${Math.floor(diffDays / 7)}周前更新`;
            if (diffDays < 365) return `${Math.floor(diffDays / 30)}个月前更新`;
            return `${Math.floor(diffDays / 365)}年前更新`;
        }
        */
    </script>
</body>
</html>
