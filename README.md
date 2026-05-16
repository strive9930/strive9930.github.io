<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的博客</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <!-- 导航栏 -->
    <nav class="navbar">
        <div class="container">
            <div class="nav-brand">
                <a href="#">MyBlog</a>
            </div>
            <ul class="nav-menu">
                <li><a href="#home" class="nav-link active">首页</a></li>
                <li><a href="#about" class="nav-link">关于</a></li>
                <li><a href="#articles" class="nav-link">文章</a></li>
                <li><a href="#contact" class="nav-link">联系</a></li>
            </ul>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero 区域 -->
    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">欢迎来到我的博客</h1>
                <p class="hero-subtitle">分享技术、生活与思考</p>
                <a href="#articles" class="btn btn-primary">浏览文章</a>
            </div>
        </div>
    </section>

    <!-- 个人简介 -->
    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">关于我</h2>
            <div class="about-content">
                <div class="about-image">
                    <img src="https://via.placeholder.com/300" alt="个人照片">
                </div>
                <div class="about-text">
                    <h3>你好，我是博主</h3>
                    <p>一名热爱技术的开发者，专注于 Web 开发、云计算和人工智能领域。在这里，我会分享我的学习心得、技术实践和生活感悟。</p>
                    <div class="social-links">
                        <a href="#" target="_blank"><i class="fab fa-github"></i></a>
                        <a href="#" target="_blank"><i class="fab fa-twitter"></i></a>
                        <a href="#" target="_blank"><i class="fab fa-linkedin"></i></a>
                        <a href="#" target="_blank"><i class="fas fa-envelope"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 文章列表 -->
    <section id="articles" class="articles">
        <div class="container">
            <h2 class="section-title">最新文章</h2>
            <div class="articles-grid" id="articlesGrid">
                <!-- 文章卡片将通过 JavaScript 动态生成 -->
            </div>
        </div>
    </section>

    <!-- 联系方式 -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">联系我</h2>
            <div class="contact-content">
                <form class="contact-form" id="contactForm">
                    <div class="form-group">
                        <input type="text" placeholder="您的姓名" required>
                    </div>
                    <div class="form-group">
                        <input type="email" placeholder="您的邮箱" required>
                    </div>
                    <div class="form-group">
                        <textarea placeholder="留言内容" rows="5" required></textarea>
                    </div>
                    <button type="submit" class="btn btn-primary">发送消息</button>
                </form>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2026 MyBlog. All rights reserved.</p>
        </div>
    </footer>

    <script src="script.js"></script>
</body>
</html>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --primary-color: #6366f1;
    --secondary-color: #8b5cf6;
    --text-dark: #1f2937;
    --text-light: #6b7280;
    --bg-light: #f9fafb;
    --white: #ffffff;
    --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    line-height: 1.6;
    color: var(--text-dark);
    background-color: var(--bg-light);
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* 导航栏 */
.navbar {
    background: var(--white);
    box-shadow: var(--shadow);
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
    transition: all 0.3s ease;
}

.navbar .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 20px;
}

.nav-brand a {
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--primary-color);
    text-decoration: none;
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: 2rem;
}

.nav-link {
    text-decoration: none;
    color: var(--text-dark);
    font-weight: 500;
    transition: color 0.3s ease;
    position: relative;
}

.nav-link:hover,
.nav-link.active {
    color: var(--primary-color);
}

.nav-link::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--primary-color);
    transition: width 0.3s ease;
}

.nav-link:hover::after,
.nav-link.active::after {
    width: 100%;
}

.hamburger {
    display: none;
    flex-direction: column;
    cursor: pointer;
    gap: 4px;
}

.hamburger span {
    width: 25px;
    height: 3px;
    background: var(--text-dark);
    transition: all 0.3s ease;
}

/* Hero 区域 */
.hero {
    margin-top: 70px;
    padding: 100px 0;
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: var(--white);
    text-align: center;
}

.hero-title {
    font-size: 3rem;
    margin-bottom: 1rem;
    animation: fadeInUp 1s ease;
}

.hero-subtitle {
    font-size: 1.5rem;
    margin-bottom: 2rem;
    opacity: 0.9;
    animation: fadeInUp 1s ease 0.2s backwards;
}

.btn {
    display: inline-block;
    padding: 12px 30px;
    border-radius: 50px;
    text-decoration: none;
    font-weight: 600;
    transition: all 0.3s ease;
    border: none;
    cursor: pointer;
}

.btn-primary {
    background: var(--white);
    color: var(--primary-color);
    animation: fadeInUp 1s ease 0.4s backwards;
}

.btn-primary:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-lg);
}

/* Section 通用样式 */
.section-title {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
    color: var(--text-dark);
    position: relative;
}

.section-title::after {
    content: '';
    display: block;
    width: 60px;
    height: 4px;
    background: var(--primary-color);
    margin: 10px auto 0;
    border-radius: 2px;
}

/* 关于我 */
.about {
    padding: 80px 0;
    background: var(--white);
}

.about-content {
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 3rem;
    align-items: center;
}

.about-image img {
    width: 100%;
    border-radius: 20px;
    box-shadow: var(--shadow-lg);
}

.about-text h3 {
    font-size: 2rem;
    margin-bottom: 1rem;
    color: var(--primary-color);
}

.about-text p {
    color: var(--text-light);
    margin-bottom: 1.5rem;
    line-height: 1.8;
}

.social-links {
    display: flex;
    gap: 1rem;
}

.social-links a {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: var(--bg-light);
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--primary-color);
    text-decoration: none;
    transition: all 0.3s ease;
}

.social-links a:hover {
    background: var(--primary-color);
    color: var(--white);
    transform: translateY(-3px);
}

/* 文章列表 */
.articles {
    padding: 80px 0;
}

.articles-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.article-card {
    background: var(--white);
    border-radius: 15px;
    overflow: hidden;
    box-shadow: var(--shadow);
    transition: all 0.3s ease;
    cursor: pointer;
}

.article-card:hover {
    transform: translateY(-10px);
    box-shadow: var(--shadow-lg);
}

.article-image {
    width: 100%;
    height: 200px;
    object-fit: cover;
}

.article-content {
    padding: 1.5rem;
}

.article-category {
    display: inline-block;
    padding: 5px 15px;
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: var(--white);
    border-radius: 20px;
    font-size: 0.85rem;
    margin-bottom: 1rem;
}

.article-title {
    font-size: 1.3rem;
    margin-bottom: 0.5rem;
    color: var(--text-dark);
}

.article-excerpt {
    color: var(--text-light);
    margin-bottom: 1rem;
    line-height: 1.6;
}

.article-meta {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: var(--text-light);
    font-size: 0.9rem;
}

.article-date {
    display: flex;
    align-items: center;
    gap: 5px;
}

.read-more {
    color: var(--primary-color);
    text-decoration: none;
    font-weight: 600;
    transition: color 0.3s ease;
}

.read-more:hover {
    color: var(--secondary-color);
}

/* 联系方式 */
.contact {
    padding: 80px 0;
    background: var(--white);
}

.contact-form {
    max-width: 600px;
    margin: 0 auto;
}

.form-group {
    margin-bottom: 1.5rem;
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 12px 20px;
    border: 2px solid #e5e7eb;
    border-radius: 10px;
    font-size: 1rem;
    transition: all 0.3s ease;
    font-family: inherit;
}

.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.1);
}

.contact-form .btn-primary {
    width: 100%;
    background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
    color: var(--white);
}

.contact-form .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: var(--shadow-lg);
}

/* 页脚 */
.footer {
    background: var(--text-dark);
    color: var(--white);
    text-align: center;
    padding: 2rem 0;
}

/* 动画 */
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* 响应式设计 */
@media (max-width: 768px) {
    .hamburger {
        display: flex;
    }

    .nav-menu {
        position: fixed;
        left: -100%;
        top: 70px;
        flex-direction: column;
        background: var(--white);
        width: 100%;
        text-align: center;
        transition: 0.3s;
        box-shadow: var(--shadow);
        padding: 2rem 0;
    }

    .nav-menu.active {
        left: 0;
    }

    .hero-title {
        font-size: 2rem;
    }

    .hero-subtitle {
        font-size: 1.2rem;
    }

    .about-content {
        grid-template-columns: 1fr;
        text-align: center;
    }

    .social-links {
        justify-content: center;
    }

    .section-title {
        font-size: 2rem;
    }
}
// 示例文章数据
const articles = [
    {
        id: 1,
        title: "现代 Web 开发最佳实践",
        excerpt: "探索现代 Web 开发中的最佳实践，包括性能优化、代码组织和用户体验设计。",
        category: "前端开发",
        date: "2026-05-10",
        image: "https://via.placeholder.com/400x200/6366f1/ffffff?text=Web+Dev",
        readTime: "5 分钟"
    },
    {
        id: 2,
        title: "深入理解 JavaScript 异步编程",
        excerpt: "从回调函数到 Promise，再到 async/await，全面解析 JavaScript 异步编程模式。",
        category: "JavaScript",
        date: "2026-05-05",
        image: "https://via.placeholder.com/400x200/8b5cf6/ffffff?text=JavaScript",
        readTime: "8 分钟"
    },
    {
        id: 3,
        title: "CSS Grid 布局完全指南",
        excerpt: "掌握 CSS Grid 布局系统，创建复杂而灵活的网页布局变得轻而易举。",
        category: "CSS",
        date: "2026-04-28",
        image: "https://via.placeholder.com/400x200/ec4899/ffffff?text=CSS+Grid",
        readTime: "6 分钟"
    },
    {
        id: 4,
        title: "React Hooks 实战技巧",
        excerpt: "分享在实际项目中使用 React Hooks 的最佳实践和常见陷阱。",
        category: "React",
        date: "2026-04-20",
        image: "https://via.placeholder.com/400x200/14b8a6/ffffff?text=React",
        readTime: "10 分钟"
    },
    {
        id: 5,
        title: "Node.js 性能优化策略",
        excerpt: "提升 Node.js 应用性能的关键技术和优化方法。",
        category: "后端开发",
        date: "2026-04-15",
        image: "https://via.placeholder.com/400x200/f59e0b/ffffff?text=Node.js",
        readTime: "7 分钟"
    },
    {
        id: 6,
        title: "Git 工作流最佳实践",
        excerpt: "团队协作中的 Git 工作流设计，提高开发效率和代码质量。",
        category: "工具",
        date: "2026-04-08",
        image: "https://via.placeholder.com/400x200/ef4444/ffffff?text=Git",
        readTime: "5 分钟"
    }
];

// 渲染文章列表
function renderArticles() {
    const articlesGrid = document.getElementById('articlesGrid');
    
    articles.forEach(article => {
        const articleCard = createArticleCard(article);
        articlesGrid.appendChild(articleCard);
    });
}

// 创建文章卡片
function createArticleCard(article) {
    const card = document.createElement('article');
    card.className = 'article-card';
    
    card.innerHTML = `
        <img src="${article.image}" alt="${article.title}" class="article-image">
        <div class="article-content">
            <span class="article-category">${article.category}</span>
            <h3 class="article-title">${article.title}</h3>
            <p class="article-excerpt">${article.excerpt}</p>
            <div class="article-meta">
                <span class="article-date">
                    <i class="far fa-calendar"></i>
                    ${formatDate(article.date)}
                </span>
                <span>
                    <i class="far fa-clock"></i>
                    ${article.readTime}
                </span>
            </div>
            <a href="#" class="read-more">阅读更多 →</a>
        </div>
    `;
    
    return card;
}

// 格式化日期
function formatDate(dateString) {
    const date = new Date(dateString);
    const year = date.getFullYear();
    const month = String(date.getMonth() + 1).padStart(2, '0');
    const day = String(date.getDate()).padStart(2, '0');
    return `${year}-${month}-${day}`;
}

// 导航栏滚动效果
function handleNavbarScroll() {
    const navbar = document.querySelector('.navbar');
    
    window.addEventListener('scroll', () => {
        if (window.scrollY > 50) {
            navbar.style.boxShadow = '0 4px 6px -1px rgba(0, 0, 0, 0.1)';
        } else {
            navbar.style.boxShadow = '0 2px 4px rgba(0, 0, 0, 0.1)';
        }
    });
}

// 移动端菜单切换
function initMobileMenu() {
    const hamburger = document.querySelector('.hamburger');
    const navMenu = document.querySelector('.nav-menu');
    
    hamburger.addEventListener('click', () => {
        navMenu.classList.toggle('active');
        hamburger.classList.toggle('active');
    });
    
    // 点击导航链接后关闭菜单
    document.querySelectorAll('.nav-link').forEach(link => {
        link.addEventListener('click', () => {
            navMenu.classList.remove('active');
            hamburger.classList.remove('active');
        });
    });
}

// 平滑滚动
function initSmoothScroll() {
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
            e.preventDefault();
            const target = document.querySelector(this.getAttribute('href'));
            
            if (target) {
                const offsetTop = target.offsetTop - 70;
                window.scrollTo({
                    top: offsetTop,
                    behavior: 'smooth'
                });
            }
        });
    });
}

// 激活导航链接
function activateNavLink() {
    const sections = document.querySelectorAll('section');
    const navLinks = document.querySelectorAll('.nav-link');
    
    window.addEventListener('scroll', () => {
        let current = '';
        
        sections.forEach(section => {
            const sectionTop = section.offsetTop;
            const sectionHeight = section.clientHeight;
            if (window.scrollY >= sectionTop - 200) {
                current = section.getAttribute('id');
            }
        });
        
        navLinks.forEach(link => {
            link.classList.remove('active');
            if (link.getAttribute('href').includes(current)) {
                link.classList.add('active');
            }
        });
    });
}

// 联系表单处理
function initContactForm() {
    const contactForm = document.getElementById('contactForm');
    
    contactForm.addEventListener('submit', (e) => {
        e.preventDefault();
        
        // 这里可以添加表单提交逻辑
        alert('感谢您的留言！我会尽快回复您。');
        contactForm.reset();
    });
}

// 滚动动画
function initScrollAnimation() {
    const observerOptions = {
        threshold: 0.1,
        rootMargin: '0px 0px -100px 0px'
    };
    
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.style.opacity = '1';
                entry.target.style.transform = 'translateY(0)';
            }
        });
    }, observerOptions);
    
    // 观察所有文章卡片
    setTimeout(() => {
        document.querySelectorAll('.article-card').forEach((card, index) => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = `all 0.6s ease ${index * 0.1}s`;
            observer.observe(card);
        });
    }, 100);
}

// 页面加载完成后初始化
document.addEventListener('DOMContentLoaded', () => {
    renderArticles();
    handleNavbarScroll();
    initMobileMenu();
    initSmoothScroll();
    activateNavLink();
    initContactForm();
    initScrollAnimation();
});
