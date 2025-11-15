<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>التوجيه والإعلام - البوابة الإخبارية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Arial', sans-serif;
        }

        :root {
            --primary: #1a3e6f;
            --secondary: #2c5aa0;
            --accent: #ff6b35;
            --success: #2ecc71;
            --warning: #f39c12;
            --danger: #e74c3c;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --gray: #7f8c8d;
        }

        body {
            background: #f8f9fa;
            color: #333;
            line-height: 1.7;
            min-height: 100vh;
        }

        /* الهيدر الرئيسي */
        .main-header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 20px 0;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo-section {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo {
            width: 60px;
            height: 60px;
            background: var(--accent);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
        }

        .site-title h1 {
            font-size: 1.8rem;
            margin-bottom: 5px;
        }

        .site-title p {
            opacity: 0.9;
            font-size: 0.9rem;
        }

        .date-section {
            text-align: center;
        }

        .current-date {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }

        .hijri-date {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        /* شريط الأخبار العاجلة */
        .breaking-news {
            background: var(--danger);
            color: white;
            padding: 12px 0;
            overflow: hidden;
        }

        .news-ticker {
            display: flex;
            align-items: center;
            gap: 20px;
            animation: ticker 30s linear infinite;
        }

        .breaking-label {
            background: rgba(0,0,0,0.2);
            padding: 5px 15px;
            border-radius: 20px;
            font-weight: bold;
            white-space: nowrap;
        }

        @keyframes ticker {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        /* التنقل */
        .main-nav {
            background: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 0;
        }

        .nav-item {
            position: relative;
        }

        .nav-link {
            display: block;
            padding: 18px 25px;
            color: var(--dark);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            border-bottom: 3px solid transparent;
        }

        .nav-link:hover,
        .nav-link.active {
            color: var(--primary);
            border-bottom-color: var(--accent);
            background: #f8f9fa;
        }

        /* المحتوى الرئيسي */
        .main-content {
            max-width: 1200px;
            margin: 30px auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 30px;
        }

        /* المقال الرئيسي */
        .featured-article {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            margin-bottom: 30px;
        }

        .article-image {
            width: 100%;
            height: 400px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            position: relative;
            overflow: hidden;
        }

        .article-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--accent);
            color: white;
            padding: 8px 15px;
            border-radius: 20px;
            font-weight: bold;
            font-size: 0.9rem;
        }

        .article-content {
            padding: 30px;
        }

        .article-meta {
            display: flex;
            gap: 20px;
            margin-bottom: 15px;
            color: var(--gray);
            font-size: 0.9rem;
        }

        .article-title {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--dark);
            line-height: 1.3;
        }

        .article-excerpt {
            font-size: 1.1rem;
            color: #555;
            margin-bottom: 25px;
            line-height: 1.8;
        }

        .read-more {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: var(--primary);
            color: white;
            padding: 12px 25px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .read-more:hover {
            background: var(--secondary);
            transform: translateY(-2px);
        }

        /* شبكة الأخبار */
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }

        .news-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
        }

        .news-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
        }

        .news-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, var(--secondary), var(--primary));
        }

        .news-content {
            padding: 20px;
        }

        .news-category {
            display: inline-block;
            background: var(--light);
            color: var(--primary);
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .news-title {
            font-size: 1.2rem;
            margin-bottom: 10px;
            color: var(--dark);
            line-height: 1.4;
        }

        .news-meta {
            display: flex;
            justify-content: space-between;
            color: var(--gray);
            font-size: 0.85rem;
            margin-top: 15px;
        }

        /* الشريط الجانبي */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .sidebar-widget {
            background: white;
            border-radius: 12px;
            padding: 25px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
        }

        .widget-title {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--primary);
            padding-bottom: 10px;
            border-bottom: 2px solid var(--light);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .important-links {
            list-style: none;
        }

        .important-links li {
            margin-bottom: 12px;
            padding-bottom: 12px;
            border-bottom: 1px solid #eee;
        }

        .important-links a {
            color: #555;
            text-decoration: none;
            transition: color 0.3s ease;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .important-links a:hover {
            color: var(--primary);
        }

        .social-stats {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .stat-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 12px;
            background: #f8f9fa;
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .stat-item:hover {
            background: var(--light);
            transform: translateX(5px);
        }

        .stat-icon {
            width: 40px;
            height: 40px;
            background: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
        }

        /* الفوتر */
        .main-footer {
            background: var(--dark);
            color: white;
            padding: 50px 0 20px;
            margin-top: 50px;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 30px;
        }

        .footer-section h3 {
            color: var(--accent);
            margin-bottom: 20px;
            font-size: 1.3rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #bbb;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: white;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 12px;
            color: #bbb;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-link {
            width: 40px;
            height: 40px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background: var(--accent);
            transform: translateY(-3px);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #bbb;
            font-size: 0.9rem;
        }

        /* التجاوب */
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .nav-menu {
                flex-direction: column;
            }
            
            .header-content {
                flex-direction: column;
                gap: 15px;
                text-align: center;
            }
            
            .news-grid {
                grid-template-columns: 1fr;
            }
            
            .article-image {
                height: 250px;
            }
            
            .article-title {
                font-size: 1.5rem;
            }
        }

        /* تأثيرات إضافية */
        .live-badge {
            display: inline-flex;
            align-items: center;
            gap: 5px;
            background: var(--danger);
            color: white;
            padding: 4px 10px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: bold;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        .video-container {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            border-radius: 12px;
            background: #000;
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
</head>
<body>
    <!-- الهيدر الرئيسي -->
    <header class="main-header">
        <div class="header-content">
            <div class="logo-section">
                <div class="logo">
                    <i class="fas fa-bullhorn"></i>
                </div>
                <div class="site-title">
                    <h1>التوجيه والإعلام</h1>
                    <p>البوابة الإخبارية الرسمية</p>
                </div>
            </div>
            <div class="date-section">
                <div class="current-date" id="currentDate"></div>
                <div class="hijri-date" id="hijriDate"></div>
            </div>
        </div>
    </header>

    <!-- شريط الأخبار العاجلة -->
    <div class="breaking-news">
        <div class="news-ticker">
            <div class="breaking-label">
                <i class="fas fa-bolt"></i> عاجل
            </div>
            <div class="ticker-content">
                📢 انعقاد المؤتمر السنوي لإدارة التوجيه والإعلام يوم الخميس المقبل - 📢 إطلاق المنصة الإلكترونية الجديدة للخدمات الإعلامية
            </div>
        </div>
    </div>

    <!-- شريط التنقل -->
    <nav class="main-nav">
        <div class="nav-container">
            <ul class="nav-menu">
                <li class="nav-item"><a href="#" class="nav-link active">الرئيسية</a></li>
                <li class="nav-item"><a href="#" class="nav-link">أخبار عاجلة</a></li>
                <li class="nav-item"><a href="#" class="nav-link">تقارير خاصة</a></li>
                <li class="nav-item"><a href="#" class="nav-link">فيديو</a></li>
                <li class="nav-item"><a href="#" class="nav-link">مقالات</a></li>
                <li class="nav-item"><a href="#" class="nav-link">اتصل بنا</a></li>
            </ul>
        </div>
    </nav>

    <!-- المحتوى الرئيسي -->
    <main class="main-content">
        <!-- القسم الرئيسي -->
        <div class="content-main">
            <!-- المقال الرئيسي -->
            <article class="featured-article">
                <div class="article-image">
                    <div class="article-badge">
                        <span class="live-badge">
                            <i class="fas fa-circle"></i> مباشر
                        </span>
                    </div>
                </div>
                <div class="article-content">
                    <div class="article-meta">
                        <span><i class="far fa-calendar"></i> 15 ديسمبر 2024</span>
                        <span><i class="far fa-eye"></i> 2,845 مشاهدة</span>
                        <span><i class="far fa-comments"></i> 43 تعليق</span>
                    </div>
                    <h2 class="article-title">
                        إطلاق الاستراتيجية الوطنية للتوجيه والإعلام 2025-2030
                    </h2>
                    <p class="article-excerpt">
                        أطلقت وزارة التوجيه والإعلام الاستراتيجية الوطنية الجديدة للفترة 2025-2030، والتي تهدف إلى تعزيز الشفافية الإعلامية ودعم التوجيه المهني للشباب. تشمل الاستراتيجية محاور رئيسية تتعلق بالتحول الرقمي وتمكين الشباب وتعزيز القيم الوطنية.
                    </p>
                    <a href="#" class="read-more">
                        اقرأ المزيد
                        <i class="fas fa-arrow-left"></i>
                    </a>
                </div>
            </article>

            <!-- شبكة الأخبار -->
            <div class="news-grid">
                <!-- خبر 1 -->
                <article class="news-card">
                    <div class="news-image"></div>
                    <div class="news-content">
                        <span class="news-category">توجيه مهني</span>
                        <h3 class="news-title">افتتاح مركز التوجيه الجامعي الجديد بالرباط</h3>
                        <p>تم اليوم افتتاح مركز التوجيه الجامعي المتطور الذي يخدم آلاف الطلاب سنوياً...</p>
                        <div class="news-meta">
                            <span><i class="far fa-clock"></i> منذ 3 ساعات</span>
                            <span><i class="far fa-newspaper"></i> جريدة الوطن</span>
                        </div>
                    </div>
                </article>

                <!-- خبر 2 -->
                <article class="news-card">
                    <div class="news-image"></div>
                    <div class="news-content">
                        <span class="news-category">إعلام رقمي</span>
                        <h3 class="news-title">ورشة عمل حول مكافحة الأخبار الكاذبة</h3>
                        <p>تنظم الوزارة ورشة عمل متخصصة للصحفيين حول آليات كشف ومكافحة المعلومات المضللة...</p>
                        <div class="news-meta">
                            <span><i class="far fa-clock"></i> منذ 5 ساعات</span>
                            <span><i class="far fa-newspaper"></i> وكالة الأنباء</span>
                        </div>
                    </div>
                </article>

                <!-- خبر 3 -->
                <article class="news-card">
                    <div class="news-image"></div>
                    <div class="news-content">
                        <span class="news-category">تعليم</span>
                        <h3 class="news-title">برنامج تدريبي لموجهي الطلاب في الجامعات</h3>
                        <p>انطلاق البرنامج التدريبي المتقدم لموجهي الطلاب بمختلف الجامعات الوطنية...</p>
                        <div class="news-meta">
                            <span><i class="far fa-clock"></i> منذ 7 ساعات</span>
                            <span><i class="far fa-newspaper"></i> التعليم اليوم</span>
                        </div>
                    </div>
                </article>
            </div>
        </div>

        <!-- الشريط الجانبي -->
        <aside class="sidebar">
            <!-- روابط مهمة -->
            <div class="sidebar-widget">
                <h3 class="widget-title">
                    <i class="fas fa-link"></i>
                    روابط مهمة
                </h3>
                <ul class="important-links">
                    <li><a href="#"><i class="fas fa-arrow-left"></i> البوابة الإلكترونية للوزارة</a></li>
                    <li><a href="#"><i class="fas fa-arrow-left"></i> خدمات التوجيه الإلكتروني</a></li>
                    <li><a href="#"><i class="fas fa-arrow-left"></i> المركز الإعلامي الرقمي</a></li>
                    <li><a href="#"><i class="fas fa-arrow-left"></i> دليل الخدمات الإلكترونية</a></li>
                    <li><a href="#"><i class="fas fa-arrow-left"></i> مكتبة الوسائط المتعددة</a></li>
                </ul>
            </div>

            <!-- إحصائيات -->
            <div class="sidebar-widget">
                <h3 class="widget-title">
                    <i class="fas fa-chart-bar"></i>
                    إحصائيات
                </h3>
                <div class="social-stats">
                    <div class="stat-item">
                        <div class="stat-icon">
                            <i class="fas fa-users"></i>
          
