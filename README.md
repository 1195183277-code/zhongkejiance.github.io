# <!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>中科检测 · 专业分析测试中心</title>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* ---------- 全局重置 ---------- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'PingFang SC', Roboto, sans-serif;
        }

        /* ---------- 科技蓝主题 ---------- */
        :root {
            --primary-blue: #0077be;      /* 主科技蓝 */
            --primary-dark: #005a8c;      /* 深蓝 */
            --primary-light: #4da6e0;     /* 亮蓝 */
            --accent-cyan: #00b4d8;       /* 青蓝点缀 */
            --light-bg: #f0f7fd;
            --text-dark: #1a2a3a;
            --text-gray: #4a5b6b;
            --shadow: 0 10px 30px rgba(0, 60, 120, 0.12);
            --radius: 12px;
        }

        body {
            color: var(--text-dark);
            background: #ffffff;
            line-height: 1.6;
            scroll-behavior: smooth;
        }

        /* ---------- 顶部公告 ---------- */
        .top-bar {
            background: var(--primary-dark);
            color: #fff;
            font-size: 0.85rem;
            padding: 8px 0;
            text-align: center;
            letter-spacing: 1px;
        }
        .top-bar i {
            margin-right: 8px;
            color: var(--accent-cyan);
        }

        /* ---------- 导航栏 ---------- */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 6%;
            height: 80px;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 20px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid transparent;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary-blue);
        }
        .logo span {
            color: var(--accent-cyan);
            font-weight: 300;
        }
        .logo small {
            font-size: 0.8rem;
            font-weight: 400;
            color: var(--text-gray);
            margin-left: 10px;
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2.2rem;
            font-weight: 500;
        }
        .nav-links a {
            text-decoration: none;
            color: var(--text-dark);
            transition: 0.3s;
            position: relative;
        }
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            background: var(--accent-cyan);
            bottom: -5px;
            left: 0;
            transition: 0.3s;
        }
        .nav-links a:hover {
            color: var(--primary-blue);
        }
        .nav-links a:hover::after {
            width: 100%;
        }
        .nav-links .active {
            color: var(--primary-blue);
            font-weight: 600;
        }
        .nav-links .active::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
            gap: 5px;
        }
        .hamburger span {
            width: 28px;
            height: 3px;
            background: var(--primary-blue);
            border-radius: 10px;
        }

        /* ---------- 通用容器 ---------- */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 5%;
        }

        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.4rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: var(--primary-dark);
        }
        .section-subtitle {
            text-align: center;
            color: var(--text-gray);
            font-size: 1.1rem;
            margin-bottom: 50px;
            letter-spacing: 1px;
        }
        .section-title i {
            color: var(--accent-cyan);
            margin-right: 12px;
        }

        /* ---------- Hero ---------- */
        .hero {
            background: linear-gradient(135deg, #e3f0fa 0%, #ffffff 100%);
            padding: 40px 0 60px 0;
            border-bottom: 1px solid rgba(0, 119, 190, 0.15);
        }
        .hero-grid {
            display: flex;
            align-items: center;
            gap: 40px;
        }
        .hero-text {
            flex: 1.2;
        }
        .hero-text h1 {
            font-size: 3.2rem;
            font-weight: 700;
            line-height: 1.2;
            color: var(--primary-dark);
        }
        .hero-text h1 .highlight {
            color: var(--primary-blue);
            background: linear-gradient(145deg, #0077be, #00b4d8);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .hero-text p {
            font-size: 1.2rem;
            color: var(--text-gray);
            margin: 25px 0 35px 0;
            max-width: 550px;
        }
        .hero-badges {
            display: flex;
            gap: 30px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        .hero-badges span {
            background: white;
            padding: 8px 22px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.9rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.02);
            border: 1px solid #d9e6f0;
        }
        .btn-group {
            display: flex;
            gap: 18px;
            flex-wrap: wrap;
        }
        .btn {
            padding: 14px 38px;
            border-radius: 50px;
            font-weight: 600;
            border: none;
            cursor: pointer;
            transition: 0.3s;
            text-decoration: none;
            display: inline-block;
            font-size: 1rem;
        }
        .btn-primary {
            background: var(--primary-blue);
            color: white;
            box-shadow: 0 8px 25px rgba(0, 119, 190, 0.35);
        }
        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 12px 30px rgba(0, 119, 190, 0.45);
        }
        .btn-outline {
            background: transparent;
            color: var(--primary-blue);
            border: 2px solid var(--primary-blue);
        }
        .btn-outline:hover {
            background: var(--primary-blue);
            color: white;
        }

        .hero-image {
            flex: 1;
            background: #cde0ef;
            border-radius: 30px;
            height: 320px;
            display: flex;
            align-items: center;
            justify-content: center;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="%230077be" opacity="0.12"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-7 3c1.93 0 3.5 1.57 3.5 3.5S13.93 13 12 13s-3.5-1.57-3.5-3.5S10.07 6 12 6zm7 13H5v-.23c0-.62.28-1.2.76-1.58C7.47 15.82 9.64 15 12 15s4.53.82 6.24 2.19c.48.38.76.97.76 1.58V19z"/></svg>');
            background-repeat: no-repeat;
            background-position: center;
            background-size: 120px;
            border: 2px dashed rgba(0,119,190,0.25);
            color: var(--primary-blue);
            font-weight: 500;
            position: relative;
        }
        .hero-image .label {
            background: white;
            padding: 8px 25px;
            border-radius: 40px;
            box-shadow: var(--shadow);
        }

        /* ---------- 数据条 ---------- */
        .stats {
            background: var(--primary-dark);
            color: white;
            padding: 40px 0;
        }
        .stats-grid {
            display: flex;
            justify-content: space-around;
            text-align: center;
            flex-wrap: wrap;
            gap: 20px;
        }
        .stats-grid div h2 {
            font-size: 2.8rem;
            font-weight: 700;
            color: var(--accent-cyan);
        }
        .stats-grid div p {
            opacity: 0.8;
            letter-spacing: 2px;
            font-size: 0.95rem;
        }

        /* ---------- 服务卡片 ---------- */
        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 30px;
        }
        .service-card {
            background: white;
            padding: 35px 25px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            text-align: center;
            border-bottom: 4px solid transparent;
            transition: 0.3s;
            border: 1px solid #ecf3fa;
        }
        .service-card:hover {
            transform: translateY(-10px);
            border-bottom-color: var(--accent-cyan);
            box-shadow: 0 20px 40px rgba(0,0,0,0.06);
        }
        .service-card i {
            font-size: 3rem;
            color: var(--primary-blue);
            margin-bottom: 20px;
            background: #e6f0fa;
            padding: 20px;
            border-radius: 50%;
            width: 80px;
            height: 80px;
            line-height: 40px;
        }
        .service-card h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }
        .service-card p {
            color: var(--text-gray);
            font-size: 0.95rem;
        }

        /* ---------- 资质 ---------- */
        .cert-grid {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 40px;
            background: var(--light-bg);
            padding: 50px 30px;
            border-radius: var(--radius);
        }
        .cert-item {
            display: flex;
            align-items: center;
            gap: 12px;
            background: white;
            padding: 15px 30px;
            border-radius: 60px;
            box-shadow: var(--shadow);
            font-weight: 600;
        }
        .cert-item i {
            color: var(--accent-cyan);
            font-size: 1.5rem;
        }

        /* ---------- 流程 ---------- */
        .process-steps {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            counter-reset: step;
        }
        .step {
            text-align: center;
            padding: 20px;
            position: relative;
        }
        .step::before {
            counter-increment: step;
            content: counter(step);
            background: var(--primary-blue);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 700;
            margin: 0 auto 15px;
        }
        .step h4 {
            font-size: 1.2rem;
        }
        .step p {
            color: var(--text-gray);
            font-size: 0.9rem;
        }

        /* ---------- 新增：在线委托 & 进度查询 ---------- */
        .two-col {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
        }
        .form-card, .query-card {
            background: white;
            padding: 40px 30px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border: 1px solid #e9f0f7;
        }
        .form-card h3, .query-card h3 {
            font-size: 1.8rem;
            color: var(--primary-dark);
            margin-bottom: 20px;
        }
        .form-card h3 i, .query-card h3 i {
            color: var(--accent-cyan);
            margin-right: 10px;
        }

        .form-group {
            margin-bottom: 20px;
        }
        .form-group label {
            display: block;
            font-weight: 600;
            margin-bottom: 5px;
            color: var(--text-dark);
        }
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #d0dce8;
            border-radius: 8px;
            font-size: 1rem;
            transition: 0.3s;
            background: #fafcfd;
        }
        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            border-color: var(--primary-blue);
            outline: none;
            box-shadow: 0 0 0 3px rgba(0,119,190,0.15);
        }
        .form-group textarea {
            resize: vertical;
            min-height: 80px;
        }

        .query-input-group {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            margin-bottom: 25px;
        }
        .query-input-group input {
            flex: 1;
            padding: 12px 15px;
            border: 1px solid #d0dce8;
            border-radius: 8px;
            font-size: 1rem;
            min-width: 200px;
        }
        .query-input-group input:focus {
            border-color: var(--primary-blue);
            outline: none;
            box-shadow: 0 0 0 3px rgba(0,119,190,0.15);
        }

        .btn-query, .btn-submit {
            padding: 12px 32px;
            background: var(--primary-blue);
            color: white;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
            font-size: 1rem;
        }
        .btn-query:hover, .btn-submit:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
        }

        .query-result {
            background: var(--light-bg);
            padding: 20px;
            border-radius: var(--radius);
            border-left: 5px solid var(--primary-blue);
            margin-top: 15px;
            display: none;
        }
        .query-result.show {
            display: block;
        }
        .query-result .status-badge {
            display: inline-block;
            padding: 6px 20px;
            border-radius: 40px;
            font-weight: 600;
            background: var(--accent-cyan);
            color: white;
        }

        /* ---------- 页脚 ---------- */
        footer {
            background: #0b1e2e;
            color: rgba(255,255,255,0.7);
            padding: 50px 0 20px;
        }
        .footer-grid {
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }
        .footer-grid h4 {
            color: white;
            margin-bottom: 20px;
        }
        .footer-grid i {
            margin-right: 10px;
            color: var(--accent-cyan);
        }
        .footer-bottom {
            border-top: 1px solid rgba(255,255,255,0.1);
            padding-top: 20px;
            text-align: center;
            font-size: 0.9rem;
        }

        /* ---------- 响应式 ---------- */
        @media (max-width: 900px) {
            .hero-grid {
                flex-direction: column;
                text-align: center;
            }
            .hero-text p {
                margin-left: auto;
                margin-right: auto;
            }
            .btn-group {
                justify-content: center;
            }
            .hero-badges {
                justify-content: center;
            }
            .nav-links {
                display: none;
                flex-direction: column;
                background: white;
                position: absolute;
                top: 80px;
                left: 0;
                width: 100%;
                padding: 30px;
                box-shadow: var(--shadow);
                gap: 15px;
                text-align: center;
            }
            .nav-links.open {
                display: flex;
            }
            .hamburger {
                display: flex;
            }
            .stats-grid div h2 {
                font-size: 2rem;
            }
            .two-col {
                grid-template-columns: 1fr;
            }
            .footer-grid {
                grid-template-columns: 1fr;
                text-align: center;
            }
            .section-title {
                font-size: 1.8rem;
            }
            .hero-text h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

<!-- 顶部公告 -->
<div class="top-bar">
    <i class="fas fa-phone-alt"></i> 全国服务热线：400-888-9999 ｜ 7x24小时 ｜ 已通过 CNAS & CMA 双认证
</div>

<!-- 导航栏 -->
<nav class="navbar">
    <div class="logo">
        ZK<span>Lab</span> <small>· 中科检测</small>
    </div>
    <ul class="nav-links" id="navLinks">
        <li><a href="#home" class="active">首页</a></li>
        <li><a href="#services">检测服务</a></li>
        <li><a href="#cert">资质荣誉</a></li>
        <li><a href="#order">在线委托</a></li>
        <li><a href="#track">进度查询</a></li>
        <li><a href="#footer">联系我们</a></li>
    </ul>
    <div class="hamburger" id="hamburger" onclick="toggleMenu()">
        <span></span><span></span><span></span>
    </div>
</nav>

<!-- 首屏 Hero -->
<section class="hero" id="home">
    <div class="container hero-grid">
        <div class="hero-text">
            <h1>精准检测 · 科技赋能<br><span class="highlight">守护品质生命线</span></h1>
            <p>专业提供材料分析、生物医药、环境监测等一站式检测服务，拥有国家级实验室资质，报告全球互认。</p>
            <div class="btn-group">
                <a href="#order" class="btn btn-primary"><i class="fas fa-flask"></i> 在线委托</a>
                <a href="#track" class="btn btn-outline">进度查询</a>
            </div>
            <div class="hero-badges">
                <span><i class="fas fa-check-circle" style="color:#28a745;"></i> 200+ 检测项目</span>
                <span><i class="fas fa-building" style="color:#0077be;"></i> 1500㎡ 实验室</span>
            </div>
        </div>
        <div class="hero-image">
            <span class="label"><i class="fas fa-microscope"></i> 实验室实景</span>
        </div>
    </div>
</section>

<!-- 信任数据条 -->
<section class="stats">
    <div class="container stats-grid">
        <div><h2>18</h2><p>年技术沉淀</p></div>
        <div><h2>5000+</h2><p>服务客户</p></div>
        <div><h2>98.7%</h2><p>客户满意度</p></div>
        <div><h2>50+</h2><p>权威资质认证</p></div>
    </div>
</section>

<!-- 核心服务 -->
<section id="services">
    <div class="container">
        <h2 class="section-title"><i class="fas fa-cogs"></i> 核心检测服务</h2>
        <p class="section-subtitle">覆盖多领域，提供定制化分析解决方案</p>
        <div class="service-grid">
            <div class="service-card">
                <i class="fas fa-atom"></i>
                <h3>材料科学</h3>
                <p>金属/高分子/复合材料成分分析、失效分析、力学性能测试。</p>
            </div>
            <div class="service-card">
                <i class="fas fa-dna"></i>
                <h3>生物医药</h3>
                <p>药物杂质分析、细胞活性检测、医疗器械生物相容性评价。</p>
            </div>
            <div class="service-card">
                <i class="fas fa-water"></i>
                <h3>环境监测</h3>
                <p>水质/土壤/大气检测、噪声监测、职业卫生现场评估。</p>
            </div>
            <div class="service-card">
                <i class="fas fa-bolt"></i>
                <h3>电子电气</h3>
                <p>可靠性测试、EMC电磁兼容、RoHS/REACH有害物质筛查。</p>
            </div>
        </div>
    </div>
</section>

<!-- 资质荣誉 -->
<section id="cert" style="background: var(--light-bg);">
    <div class="container">
        <h2 class="section-title"><i class="fas fa-shield-alt"></i> 权威资质 · 全球互认</h2>
        <p class="section-subtitle">以国际标准构建信任基石</p>
        <div class="cert-grid">
            <div class="cert-item"><i class="fas fa-certificate"></i> CNAS 国家认可</div>
            <div class="cert-item"><i class="fas fa-certificate"></i> CMA 资质认定</div>
            <div class="cert-item"><i class="fas fa-globe-americas"></i> ISO 17025</div>
            <div class="cert-item"><i class="fas fa-award"></i> 高新技术企业</div>
            <div class="cert-item"><i class="fas fa-lock"></i> 数据保密协议</div>
        </div>
        <div style="text-align:center; margin-top: 30px; background: white; padding: 20px; border-radius: var(--radius); border-left: 5px solid var(--accent-cyan);">
            <i class="fas fa-file-signature" style="color:var(--primary-blue); font-size: 1.5rem;"></i>
            <span style="font-weight:500; margin-left:10px;">承诺：检测结果仅对委托方公开，严格保护知识产权与商业机密。</span>
        </div>
    </div>
</section>

<!-- 检测流程 -->
<section>
    <div class="container">
        <h2 class="section-title"><i class="fas fa-route"></i> 透明化检测流程</h2>
        <p class="section-subtitle">简单四步，高效交付</p>
        <div class="process-steps">
            <div class="step"><h4>1. 在线咨询</h4><p>明确需求，提供定制方案与报价</p></div>
            <div class="step"><h4>2. 寄送样品</h4><p>免费上门取件或快递送达</p></div>
            <div class="step"><h4>3. 精准测试</h4><p>全程录像，数据可追溯</p></div>
            <div class="step"><h4>4. 出具报告</h4><p>电子版+纸质版，支持真伪查询</p></div>
        </div>
    </div>
</section>

<!-- ===== 新增：在线委托 & 进度查询 ===== -->
<section id="order-track" style="background: #f8fbfe;">
    <div class="container">
        <h2 class="section-title"><i class="fas fa-user-check"></i> 客户服务</h2>
        <p class="section-subtitle">在线委托检测 · 实时查询进度</p>
        <div class="two-col">
            <!-- 在线委托表单 -->
            <div class="form-card" id="order">
                <h3><i class="fas fa-pen-alt"></i> 在线委托</h3>
                <form id="orderForm" onsubmit="submitOrder(event)">
                    <div class="form-group">
                        <label for="name">联系人 <span style="color:red;">*</span></label>
                        <input type="text" id="name" placeholder="请输入姓名" required>
                    </div>
                    <div class="form-group">
                        <label for="phone">手机号码 <span style="color:red;">*</span></label>
                        <input type="tel" id="phone" placeholder="请输入手机号" required>
                    </div>
                    <div class="form-group">
                        <label for="sample">样品类型</label>
                        <select id="sample">
                            <option value="材料">材料类</option>
                            <option value="生物医药">生物医药</option>
                            <option value="环境">环境类</option>
                            <option value="电子电气">电子电气</option>
                            <option value="其他">其他</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="remark">备注（检测需求）</label>
                        <textarea id="remark" placeholder="请简要描述您的检测需求..."></textarea>
                    </div>
                    <button type="submit" class="btn-submit"><i class="fas fa-paper-plane"></i> 提交委托</button>
                </form>
                <div id="formFeedback" style="margin-top:15px; font-weight:500; color: var(--primary-blue);"></div>
            </div>

            <!-- 进度查询 -->
            <div class="query-card" id="track">
                <h3><i class="fas fa-search"></i> 进度查询</h3>
                <p style="color: var(--text-gray); margin-bottom: 15px;">输入您的委托单号，查询检测状态</p>
                <div class="query-input-group">
                    <input type="text" id="orderNumber" placeholder="例如：ZK2026-001" value="ZK2026-001">
                    <button class="btn-query" onclick="trackOrder()"><i class="fas fa-arrow-right"></i> 查询</button>
                </div>
                <!-- 查询结果显示区 -->
                <div class="query-result" id="queryResult">
                    <p><strong>委托单号：</strong><span id="displayOrderNo">ZK2026-001</span></p>
                    <p><strong>检测项目：</strong>材料成分分析</p>
                    <p><strong>当前状态：</strong><span class="status-badge" id="statusBadge">检测中</span></p>
                    <p><strong>预计完成：</strong>2026-06-28</p>
                    <p style="margin-top:10px; font-size:0.9rem; color:var(--text-gray);">* 模拟数据，仅供参考</p>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- 页脚 -->
<footer id="footer">
    <div class="container footer-grid">
        <div>
            <h3 style="color:white; font-size:1.8rem;">ZK<span style="color:var(--accent-cyan);">Lab</span></h3>
            <p style="margin-top:15px;">致力于为全球客户提供公正、科学、高效的检测技术服务。</p>
            <p style="margin-top:10px;"><i class="fas fa-map-pin"></i> 中国·上海浦东新区 张江高科技园区</p>
        </div>
        <div>
            <h4>快速链接</h4>
            <p><a href="#services" style="color:rgba(255,255,255,0.7); text-decoration:none;">检测服务</a></p>
            <p><a href="#cert" style="color:rgba(255,255,255,0.7); text-decoration:none;">资质证书</a></p>
            <p><a href="#order" style="color:rgba(255,255,255,0.7); text-decoration:none;">在线委托</a></p>
        </div>
        <div>
            <h4>联系方式</h4>
            <p><i class="fas fa-phone"></i> 400-888-9999</p>
            <p><i class="fas fa-envelope"></i> service@zklab.com</p>
            <p><i class="fas fa-clock"></i> 周一至周日 8:00-20:00</p>
        </div>
    </div>
    <div class="container footer-bottom">
        <p>© 2026 中科检测技术有限公司 ｜ <a href="#" style="color:rgba(255,255,255,0.5);">隐私政策</a> ｜ <a href="#" style="color:rgba(255,255,255,0.5);">网站地图</a></p>
    </div>
</footer>

<!-- JS 交互 -->
<script>
    // 手机菜单切换
    function toggleMenu() {
        document.getElementById('navLinks').classList.toggle('open');
    }
    // 点击导航链接自动收起
    document.querySelectorAll('.nav-links a').forEach(link => {
        link.addEventListener('click', () => {
            document.getElementById('navLinks').classList.remove('open');
        });
    });

    // 表单提交
    function submitOrder(e) {
        e.preventDefault();
        const name = document.getElementById('name').value.trim();
        const phone = document.getElementById('phone').value.trim();
        if (!name || !phone) {
            document.getElementById('formFeedback').innerHTML = '<span style="color:#d9534f;">请填写完整信息（姓名和手机号）</span>';
            return;
        }
        // 模拟提交成功
        document.getElementById('formFeedback').innerHTML = '<span style="color:#28a745;"><i class="fas fa-check-circle"></i> 委托提交成功！我们将在1小时内与您联系。</span>';
        // 清空表单（可选）
        // document.getElementById('orderForm').reset();
    }

    // 进度查询模拟
    function trackOrder() {
        const input = document.getElementById('orderNumber');
        const orderNo = input.value.trim();
        if (!orderNo) {
            alert('请输入委托单号');
            return;
        }
        const resultDiv = document.getElementById('queryResult');
        const displayNo = document.getElementById('displayOrderNo');
        const badge = document.getElementById('statusBadge');

        displayNo.textContent = orderNo;

        // 模拟不同的状态（根据单号后缀奇偶）
        const lastChar = orderNo.slice(-1);
        if (lastChar >= '0' && lastChar <= '9') {
            const num = parseInt(lastChar);
            if (num % 2 === 0) {
                badge.textContent = '已完成';
                badge.style.background = '#28a745';
            } else {
                badge.textContent = '检测中';
                badge.style.background = '#ffc107';
                badge.style.color = '#333';
            }
        } else {
            badge.textContent = '已接收';
            badge.style.background = '#0077be';
        }

        resultDiv.classList.add('show');
    }

    // 页面加载后自动显示一个示例查询结果（可选）
    window.onload = function() {
        // 默认显示一次查询结果
        trackOrder();
    };
</script>

</body>
</html>