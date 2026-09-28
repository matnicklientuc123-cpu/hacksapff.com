# hacksapff.com
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Của Tôi - Personal Portfolio</title>
    <!-- FontAwesome Icon -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* ================= CSS VARIABLES & RESET ================= */
        :root {
            --bg-color: #f4f7f6;
            --card-bg: #ffffff;
            --text-color: #333333;
            --text-secondary: #666666;
            --primary-color: #4f46e5;
            --primary-hover: #4338ca;
            --border-color: #e5e7eb;
            --shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);
        }

        [data-theme="dark"] {
            --bg-color: #0f172a;
            --card-bg: #1e293b;
            --text-color: #f8fafc;
            --text-secondary: #94a3b8;
            --primary-color: #6366f1;
            --primary-hover: #818cf8;
            --border-color: #334155;
            --shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.5);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            transition: background-color 0.3s, color 0.3s;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* ================= CONTAINER ================= */
        .container {
            max-width: 800px;
            width: 100%;
            background-color: var(--card-bg);
            border-radius: 20px;
            box-shadow: var(--shadow);
            overflow: hidden;
            position: relative;
            border: 1px solid var(--border-color);
        }

        /* Dark Mode Button */
        .theme-toggle {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(5px);
            border: none;
            color: #fff;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2rem;
            z-index: 10;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* ================= HEADER ================= */
        .header {
            background: linear-gradient(135deg, #4f46e5, #9333ea);
            height: 180px;
            position: relative;
        }

        .profile-img-container {
            position: absolute;
            bottom: -50px;
            left: 50%;
            transform: translateX(-50%);
        }

        .profile-img {
            width: 130px;
            height: 130px;
            border-radius: 50%;
            border: 4px solid var(--card-bg);
            object-fit: cover;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
        }

        /* ================= CONTENT ================= */
        .content {
            padding: 60px 30px 40px;
            text-align: center;
        }

        .name {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .title {
            color: var(--primary-color);
            font-weight: 600;
            margin-bottom: 15px;
            font-size: 1rem;
        }

        .bio {
            color: var(--text-secondary);
            font-size: 0.95rem;
            max-width: 600px;
            margin: 0 auto 25px;
        }

        /* Social Icons */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
        }

        .social-btn {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background-color: var(--bg-color);
            color: var(--text-color);
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            font-size: 1.2rem;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }

        .social-btn:hover {
            background-color: var(--primary-color);
            color: #ffffff;
            transform: translateY(-3px);
        }

        /* ================= SECTIONS ================= */
        .section-title {
            text-align: left;
            font-size: 1.2rem;
            margin-bottom: 15px;
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 5px;
            color: var(--text-color);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        /* Skills */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 30px;
        }

        .skill-tag {
            background-color: var(--bg-color);
            color: var(--text-color);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            border: 1px solid var(--border-color);
        }

        /* Timeline / Experience */
        .timeline {
            text-align: left;
            margin-bottom: 30px;
        }

        .timeline-item {
            padding-left: 20px;
            border-left: 2px solid var(--primary-color);
            margin-bottom: 20px;
            position: relative;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -6px;
            top: 5px;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background-color: var(--primary-color);
        }

        .timeline-date {
            font-size: 0.8rem;
            color: var(--text-secondary);
        }

        .timeline-role {
            font-weight: 600;
            font-size: 1rem;
        }

        .timeline-desc {
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        /* Contact Button */
        .btn-contact {
            display: inline-block;
            width: 100%;
            padding: 12px;
            background-color: var(--primary-color);
            color: white;
            text-decoration: none;
            font-weight: 600;
            border-radius: 10px;
            transition: background 0.3s;
        }

        .btn-contact:hover {
            background-color: var(--primary-hover);
        }

        /* Responsive design */
        @media (max-width: 600px) {
            .content {
                padding: 60px 20px 30px;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Theme Toggle Button -->
        <button class="theme-toggle" id="themeToggle" title="Đổi giao diện">
            <i class="fa-solid fa-moon"></i>
        </button>

        <!-- Header Profile -->
        <div class="header">
            <div class="profile-img-container">
                <!-- Bạn có thể thay link ảnh đại diện dưới đây -->
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=400&auto=format&fit=crop&q=80" alt="Avatar" class="profile-img">
            </div>
        </div>

        <!-- Main Content -->
        <div class="content">
            <!-- Tên & Chức danh -->
            <h1 class="name">Nguyễn Văn A</h1>
            <p class="title">Lập Trình Viên Web / Full-Stack Developer</p>
            <p class="bio">
                Xin chào! Tôi là một lập trình viên yêu thích tạo ra các trải nghiệm web mượt mà, tối ưu và đẹp mắt. Luôn tìm tòi và học hỏi các công nghệ mới.
            </p>

            <!-- Mạng Xã Hội -->
            <div class="social-links">
                <a href="#" class="social-btn" title="Facebook"><i class="fa-brands fa-facebook-f"></i></a>
                <a href="#" class="social-btn" title="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="#" class="social-btn" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="#" class="social-btn" title="Instagram"><i class="fa-brands fa-instagram"></i></a>
            </div>

            <!-- Kỹ Năng -->
            <h3 class="section-title"><i class="fa-solid fa-code"></i> Kỹ Năng</h3>
            <div class="skills-container">
                <span class="skill-tag">HTML5 / CSS3</span>
                <span class="skill-tag">JavaScript</span>
                <span class="skill-tag">React.js</span>
                <span class="skill-tag">Node.js</span>
                <span class="skill-tag">Git / GitHub</span>
                <span class="skill-tag">UI/UX Design</span>
            </div>

            <!-- Kinh Nghiệm / Học Vấn -->
            <h3 class="section-title"><i class="fa-solid fa-briefcase"></i> Kinh Nghiệm Làm Việc</h3>
            <div class="timeline">
                <div class="timeline-item">
                    <span class="timeline-date">2022 - Hiện tại</span>
                    <div class="timeline-role">Senior Frontend Developer - Công ty ABC</div>
                    <div class="timeline-desc">Phát triển và tối ưu giao diện ứng dụng web cho hàng triệu người dùng.</div>
                </div>
                <div class="timeline-item">
                    <span class="timeline-date">2020 - 2022</span>
                    <div class="timeline-role">Web Developer - Công ty XYZ</div>
                    <div class="timeline-desc">Xây dựng các trang web Landing Page, hệ thống e-commerce bằng ReactJS.</div>
                </div>
            </div>

            <!-- Nút Liên Hệ -->
            <a href="mailto:emailcuaban@gmail.com" class="btn-contact">
                <i class="fa-regular fa-envelope"></i> Liên Hệ Với Tôi
            </a>
        </div>
    </div>

    <!-- JavaScript (Sáng/Tối) -->
    <script>
        const themeToggleBtn = document.getElementById('themeToggle');
        const themeIcon = themeToggleBtn.querySelector('i');

        // Kiểm tra chế độ đã lưu
        const currentTheme = localStorage.getItem('theme');
        if (currentTheme) {
            document.documentElement.setAttribute('data-theme', currentTheme);
            if (currentTheme === 'dark') {
                themeIcon.classList.replace('fa-moon', 'fa-sun');
            }
        }

        // Chuyển đổi Dark/Light mode
        themeToggleBtn.addEventListener('click', () => {
            let theme = document.documentElement.getAttribute('data-theme');
            if (theme === 'dark') {
                document.documentElement.setAttribute('data-theme', 'light');
                localStorage.setItem('theme', 'light');
                themeIcon.classList.replace('fa-sun', 'fa-moon');
            } else {
                document.documentElement.setAttribute('data-theme', 'dark');
                localStorage.setItem('theme', 'dark');
                themeIcon.classList.replace('fa-moon', 'fa-sun');
            }
        });
    </script>
</body>
</html>
