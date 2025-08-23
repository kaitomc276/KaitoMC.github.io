<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Galactic Key Interface</title>
    <style>
        :root {
            --glow-color: #00e0ff;
            --main-bg-color: #0d1a2f;
            --container-bg-color: rgba(18, 30, 50, 0.8);
            --border-color: #0a2040;
            --text-color: #e0f0ff;
            --button-primary: #00d4ff;
            --button-secondary: #ff3366;
            --input-bg: rgba(255, 255, 255, 0.05);
            --input-border: 1px solid rgba(255, 255, 255, 0.2);
        }

        @keyframes star-fall {
            0% { transform: translateY(0) scale(1); opacity: 1; }
            100% { transform: translateY(1500px) scale(0.5); opacity: 0; }
        }

        @keyframes astronaut-fly {
            0% { transform: translate(-100vw, 50vh) rotate(-10deg) scale(0.7); }
            100% { transform: translate(150vw, -50vh) rotate(30deg) scale(0.8); }
        }

        @keyframes earth-spin {
            0% { transform: rotate(0deg) scale(1.2); }
            100% { transform: rotate(360deg) scale(1.2); }
        }

        @keyframes card-tilt {
            0% { transform: rotateX(10deg) rotateY(-5deg); }
            50% { transform: rotateX(0deg) rotateY(5deg); }
            100% { transform: rotateX(10deg) rotateY(-5deg); }
        }
        
        @keyframes glowing {
            0% { box-shadow: 0 0 5px var(--glow-color); }
            50% { box-shadow: 0 0 20px var(--glow-color), 0 0 30px var(--glow-color); }
            100% { box-shadow: 0 0 5px var(--glow-color); }
        }

        @keyframes button-pulse {
            0% { transform: scale(1); box-shadow: 0 0 10px rgba(0, 224, 255, 0.5); }
            50% { transform: scale(1.05); box-shadow: 0 0 20px rgba(0, 224, 255, 0.8); }
            100% { transform: scale(1); box-shadow: 0 0 10px rgba(0, 224, 255, 0.5); }
        }

        @keyframes text-wave {
            0%, 100% { transform: translateY(0); }
            20% { transform: translateY(-3px); }
            40% { transform: translateY(0); }
            60% { transform: translateY(-3px); }
            80% { transform: translateY(0); }
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            transition: all 0.3s ease-in-out;
        }

        body {
            background-color: var(--main-bg-color);
            color: var(--text-color);
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            position: relative;
        }

        .background-effect {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        .stars-container {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }
        
        .star {
            position: absolute;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            opacity: 0;
            animation: star-fall 20s linear infinite;
        }
        
        .star.medium { width: 3px; height: 3px; animation-duration: 25s; }
        .star.large { width: 5px; height: 5px; animation-duration: 30s; }
        
        .astronaut {
            position: absolute;
            width: 100px;
            height: 100px;
            background-image: url('https://files.catbox.moe/gpvkt6.png');
            background-size: contain;
            background-repeat: no-repeat;
            opacity: 0;
            animation: astronaut-fly 40s linear infinite;
            pointer-events: none;
        }

        .earth {
            position: absolute;
            bottom: -200px;
            right: -200px;
            width: 800px;
            height: 800px;
            background-image: url('https://files.catbox.moe/sa28yy.png');
            background-size: contain;
            background-repeat: no-repeat;
            z-index: -1;
            opacity: 0.6;
            animation: earth-spin 120s linear infinite;
        }

        .container {
            position: relative;
            z-index: 10;
            max-width: 500px;
            width: 90%;
            padding: 3rem;
            background: var(--container-bg-color);
            backdrop-filter: blur(10px);
            border: 2px solid var(--border-color);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            perspective: 1000px;
            transform-style: preserve-3d;
            transform: rotateX(10deg) rotateY(-5deg);
            animation: card-tilt 20s ease-in-out infinite;
        }

        @media (max-width: 600px) {
            body {
                overflow-y: auto;
                min-height: 100vh;
            }

            .background-effect {
                display: none; /* Ẩn hiệu ứng nền trên điện thoại để tránh lỗi vuốt và tăng hiệu suất */
            }

            .container {
                width: 95%;
                padding: 1.5rem;
                margin: 2rem 0; /* Thêm margin để không dính sát viền */
                transform: none !important; /* Vô hiệu hóa hiệu ứng nghiêng trên mobile */
                animation: none;
            }
        }

        .header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .header h1 {
            font-size: 2.5rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 0 0 10px var(--glow-color);
            animation: glowing 3s ease-in-out infinite;
        }

        .header p {
            font-size: 1rem;
            color: rgba(255, 255, 255, 0.7);
            margin-top: 0.5rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
            position: relative;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: var(--glow-color);
            text-shadow: 0 0 5px var(--glow-color);
        }

        .form-group input {
            width: 100%;
            padding: 0.8rem 1rem;
            font-size: 1rem;
            background: var(--input-bg);
            border: var(--input-border);
            border-radius: 5px;
            color: var(--text-color);
            outline: none;
            transition: all 0.3s;
        }

        .form-group input:focus {
            border-color: var(--glow-color);
            box-shadow: 0 0 10px var(--glow-color), inset 0 0 5px var(--glow-color);
        }

        .button-group {
            display: flex;
            justify-content: space-between;
            gap: 1rem;
            margin-top: 2rem;
        }

        .btn {
            flex: 1;
            padding: 1rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: bold;
            text-transform: uppercase;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            letter-spacing: 1px;
            transition: all 0.4s ease;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            transition: width 0.4s ease, height 0.4s ease;
            z-index: 0;
        }

        .btn:hover::before {
            width: 300%;
            height: 300%;
        }

        .btn-primary {
            background-color: var(--button-primary);
            color: var(--main-bg-color);
            box-shadow: 0 0 15px var(--button-primary);
            animation: button-pulse 2s infinite;
        }

        .btn-primary:hover {
            box-shadow: 0 0 25px var(--button-primary), 0 0 40px var(--button-primary);
            transform: translateY(-3px) scale(1.02);
        }
        
        .btn-secondary {
            background-color: var(--button-secondary);
            color: var(--text-color);
            box-shadow: 0 0 15px var(--button-secondary);
        }

        .btn-secondary:hover {
            background-color: #ff5588;
            box-shadow: 0 0 25px #ff5588;
            transform: translateY(-3px) scale(1.02);
        }

        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background: rgba(0, 224, 255, 0.9);
            color: var(--main-bg-color);
            padding: 1rem 1.5rem;
            border-radius: 5px;
            font-weight: bold;
            z-index: 100;
            opacity: 0;
            visibility: hidden;
            transform: translateY(-50px);
            transition: all 0.5s ease-in-out;
            box-shadow: 0 0 20px rgba(0, 224, 255, 0.8);
        }

        .notification.show {
            opacity: 1;
            visibility: visible;
            transform: translateY(0);
        }

        .footer {
            margin-top: 2rem;
            text-align: center;
            font-size: 0.8rem;
            color: rgba(255, 255, 255, 0.5);
            line-height: 1.5;
        }
        
        .char-wave {
            display: inline-block;
            animation: text-wave 1s infinite;
            animation-timing-function: cubic-bezier(0.68, -0.55, 0.27, 1.55);
        }

    </style>
</head>
<body>

    <div class="background-effect">
        <div class="stars-container"></div>
        <div class="astronaut"></div>
        <div class="earth"></div>
    </div>

    <div class="container" id="mainContainer">
        <div class="header">
            <h1><span class="char-wave" style="animation-delay: 0s;">V</span><span class="char-wave" style="animation-delay: 0.1s;">I</span><span class="char-wave" style="animation-delay: 0.2s;">Ệ</span><span class="char-wave" style="animation-delay: 0.3s;">T</span><span class="char-wave" style="animation-delay: 0.4s;">N</span><span class="char-wave" style="animation-delay: 0.5s;">A</span><span class="char-wave" style="animation-delay: 0.6s;">M</span><span class="char-wave" style="animation-delay: 0.7s;">V</span> <span class="char-wave" style="animation-delay: 0.8s;">Ô</span><span class="char-wave" style="animation-delay: 0.9s;">Đ</span><span class="char-wave" style="animation-delay: 1s;">I</span> <span class="char-wave" style="animation-delay: 1.1s;">C</span>  
            <p>Hệ thống yêu cầu key truy cập không gian vũ trụ</p>
        </div>
        
        <div class="form-group">
            <label for="keyInput">Nhập khóa truy cập</label>
            <input type="text" id="keyInput" placeholder="Dán key của bạn vào đây...">
        </div>
        
        <div class="button-group">
            <button class="btn btn-primary" id="getKeyBtn">Get Key</button>
            <button class="btn btn-secondary" id="confirmBtn">Xác Nhận</button>
        </div>

        <div class="footer">
            <p>Vui lòng lấy khóa truy cập từ liên kết bên dưới để xác thực.</p>
            <p id="linksSection">
                <span id="keyLink" style="display: none;"></span>
                <span id="mainLink" style="display: none;"></span>
            </p>
        </div>
    </div>
    
    <div class="notification" id="notification"></div>

    <script>
        // --- CẤU HÌNH LIÊN KẾT TẠI ĐÂY ---
        const GET_KEY_LINK = "https://link4sub.com/SOcC"; // Đổi đường link lấy key tại đây
        const MAIN_WEBSITE_LINK = "content://ru.zdevs.zarchiver.external/storage/emulated/0/Download/Zalo/m%C3%A1y.html"; // Đổi đường link trang web chính tại đây
        // --- KẾT THÚC CẤU HÌNH LIÊN KẾT ---

        // --- CẤU HÌNH KHÓA TRUY CẬP TẠI ĐÂY ---
        const ACCESS_KEY = "Key-768";
        // --- KẾT THÚC CẤU HÌNH KHÓA TRUY CẬP ---


        const getKeyBtn = document.getElementById('getKeyBtn');
        const confirmBtn = document.getElementById('confirmBtn');
        const keyInput = document.getElementById('keyInput');
        const notification = document.getElementById('notification');
        const mainContainer = document.getElementById('mainContainer');
        const starsContainer = document.querySelector('.stars-container');
        const astronaut = document.querySelector('.astronaut');

        // Hiệu ứng ngôi sao
        function createStar() {
            const star = document.createElement('div');
            star.className = 'star';
            const size = Math.random() * 3 + 1;
            star.style.width = `${size}px`;
            star.style.height = `${size}px`;
            star.style.left = `${Math.random() * 100}vw`;
            star.style.top = `${-20 - Math.random() * 50}px`;
            star.style.animationDelay = `${Math.random() * 15}s`;
            star.style.animationDuration = `${Math.random() * 20 + 10}s`;
            starsContainer.appendChild(star);

            star.addEventListener('animationend', () => {
                star.remove();
            });
        }

        // Tắt hiệu ứng nền trên mobile
        if (window.innerWidth > 600) {
            for (let i = 0; i < 150; i++) {
                createStar();
            }

            setInterval(() => {
                if (starsContainer.children.length < 150) {
                    createStar();
                }
            }, 200);

            // Hiệu ứng phi hành gia
            function startAstronautAnimation() {
                astronaut.style.animationPlayState = 'running';
                astronaut.style.opacity = '1';
            }

            setTimeout(() => {
                startAstronautAnimation();
            }, 500);
        }


        // Hiển thị thông báo
        function showNotification(message, isError = false) {
            notification.textContent = message;
            notification.classList.add('show');
            if (isError) {
                notification.style.background = 'rgba(255, 51, 102, 0.9)';
                notification.style.boxShadow = '0 0 20px rgba(255, 51, 102, 0.8)';
            } else {
                notification.style.background = 'rgba(0, 224, 255, 0.9)';
                notification.style.boxShadow = '0 0 20px rgba(0, 224, 255, 0.8)';
            }
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        // Sao chép key vào clipboard
        async function copyToClipboard(text) {
            try {
                await navigator.clipboard.writeText(text);
                return true;
            } catch (err) {
                console.error('Không thể sao chép văn bản:', err);
                return false;
            }
        }

        // Xử lý nút Get Key
        getKeyBtn.addEventListener('click', async () => {
            // Cập nhật thông báo với liên kết để người dùng biết
            showNotification(`Đang sao chép liên kết lấy key: ${GET_KEY_LINK}`);

            // Mô phỏng quá trình xử lý key
            await new Promise(resolve => setTimeout(resolve, 1500));

            const isCopied = await copyToClipboard(GET_KEY_LINK);
            if (isCopied) {
                showNotification('Đã sao chép liên kết lấy key vào bộ nhớ!');
            } else {
                showNotification('Không thể tự động sao chép. Vui lòng truy cập:', true);
                window.open(GET_KEY_LINK, '_blank');
            }
        });

        // Xử lý nút Xác Nhận
        confirmBtn.addEventListener('click', () => {
            const key = keyInput.value.trim();
            if (key === "") {
                showNotification('Vui lòng dán khóa truy cập vào ô.', true);
                keyInput.focus();
                return;
            }
            
            // Đây là phần kiểm tra key
            if (key === ACCESS_KEY) {
                showNotification('Xác thực thành công! Đang dịch chuyển đến trang web chính...');
                setTimeout(() => {
                    window.location.href = MAIN_WEBSITE_LINK;
                }, 2000);
            } else {
                showNotification('Khóa không hợp lệ. Vui lòng thử lại.', true);
            }
        });

        // Thêm hiệu ứng hover cho container
        if (window.innerWidth > 600) {
            mainContainer.addEventListener('mousemove', (e) => {
                const containerRect = mainContainer.getBoundingClientRect();
                const centerX = containerRect.left + containerRect.width / 2;
                const centerY = containerRect.top + containerRect.height / 2;
                const mouseX = e.clientX;
                const mouseY = e.clientY;
                
                const rotateY = (mouseX - centerX) / containerRect.width * 20;
                const rotateX = (centerY - mouseY) / containerRect.height * 20;

                mainContainer.style.transform = `rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
            });

            mainContainer.addEventListener('mouseleave', () => {
                mainContainer.style.transform = `rotateX(10deg) rotateY(-5deg)`;
            });
        }
    </script>
</body>
</html>
