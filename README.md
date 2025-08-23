<! physics >
<html lang="vi"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1"><meta name="theme-color" content="#ffffff"><title>Cloud Phone UI Pro</title> <style>
        
         /* Hình Hello Kitty */
        .hello-kitty {
            position: absolute;
            top: -130px;
            right: -10px;
            width: 80px;
            height: auto;
            transition: transform 0.3s ease;
     contai   }

        .hello-anime {
            position: absolute;
            top: -75px;
            right: 211px;
            width: 80px;
            height: auto;
            transition: transform 0.3s ease;
        }
        
          /* Màn hình loading */
        #loadingScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
        }

        .notification-box {
            background: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            color: black;
            width: 300px;
            position: relative;
            box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
            border: 2px solid black;
        }

        .notification-box h2 {
    font-weight: bold;
    font-size: 18px;
    margin-top: -10px; /* Đẩy chữ lên một chút */
    margin-bottom: 10px; /* Tạo khoảng cách dưới */
}

.notification-box h3,
.notification-box h4 {
    margin-bottom: 8px; /* Tạo khoảng cách giữa các dòng */
}

        .button-group {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-top: 15px;
        }

        .notification-box button {
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            background-color: black;
            color: white;
            font-weight: bold;
            cursor: pointer;
            width: 80px;
        }

        .notification-box button:hover {
            background-color: gray;
        }

        /* Ẩn nội dung chính trước khi thông báo bị tắt */
        #mainContent {
            display: none;
        }

       
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }body {
        background: url('https://wallpapers.com/images/featured/anime-landscape-background-12xkkc2cnstc3gp2.jpg') no-repeat center center fixed;
        background-size: cover;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 90vh;
        overflow: hidden;

   .container {
  display: flex;
  flex-direction: column; /* <-- Chuyển sang cuộn dọc */
  overflow-y: auto;        /* <-- Kích hoạt cuộn dọc */
  height: 100vh;           /* <-- Giới hạn chiều cao */
  scroll-snap-type: y mandatory; /* <-- Nếu vẫn muốn hiệu ứng snap */
  gap: 40px;
  padding: 20px;
  overflow-x: hidden;      /* <-- Tắt cuộn ngang */
}

}
    .screen {
    border: 1px solid white;
        width: 300px;
        height: 540px;
        flex: none;
        border-radius: 14px;
        display: flex;
        flex-direction: column;
        align-items: center;
        scroll-snap-align: center;
        padding: 15px;
        text-align: center;
        position: relative; 
        background: url('https://wallpapers.com/images/hd/chill-anime-gvi3pyjuaqdpox5r.jpg') no-repeat center center;
        background-size: cover;
 
  transition: transform 0.2s ease, box-shadow 0.3s ease;
  will-change: transform;
  transform-origin: center center;
}

.screen.active {
  transform: scale(1.05);
 box-shadow: 0 0 4px rgba(0, 0, 0, 0.1);
  z-index: 10;
}
    }
   

    .header {
        background-color: #FF69B4;
        color: #fff;
        padding: 8px 15px;
        border-radius: 15px;
        text-align: center;
        font-size: 14px;
        font-weight: bold;
        width: auto;
        position: absolute;
        top: 10px;
    }

    .content {
        flex-grow: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
    }

    .image {
        width: 80px;
        height: 80px;
        background-color: #fff;
        border-radius: 10px;
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .button {
        background-color: #FF69B4;
        color: white;
        padding: 8px 15px;
        border-radius: 15px;
        text-align: center;
        font-size: 13px;
        font-weight: bold;
        cursor: pointer;
        transition: 0.3s;
        margin-top: 15px;
    }

    .button:hover {
        background-color: #FFC0CB;
    }

    .container::-webkit-scrollbar {
        display: none;
    }
    * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
    -webkit-tap-highlight-color: transparent; /* Chặn hiệu ứng nhấn */
}

.editable-footer {
  width: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  color: white;
  padding: 10px;
  border-radius: 5px;
  text-align: left;

  /* Cố định footer ở dưới */
  position: absolute;
  bottom: 10;
  left: 10;
}
.card {
  position: relative;
}

    .device-name {
      font-weight: bold;
      font-size: 14px;
    }

    .clock {
      font-size: 12px;
      color: #ccc;
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .clock i {
      color: #bbb;
    }

    .container::-webkit-scrollbar {
      display: none;
    }
    
    .screen {
  position: relative;
  padding-bottom: 80px; /* Chừa chỗ cho 3 nút ở dưới */
}

.action-buttons {
  position: absolute;
  bottom: 35px;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  gap: 50px; /* Thay đổi số này tuỳ ý */
}


.action-buttons div {
  text-align: center;
}

.action-buttons img {
  width: 55px;
  height: 55px;
  object-fit: contain;
  border-radius: 50%;
  background-color: white;
  padding: 5px;
}

.action-buttons div span {
  font-size: 13px;
  color: #666;
  display: block;
  margin-top: 4px;
}
.top-bar.transparent {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 60px;
  background-image: url('https://wallpapers.com/images/featured/anime-landscape-background-12xkkc2cnstc3gp2.jpg'); /* trong suốt hoàn toàn */
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 16px;
  z-index: 999;
  border-bottom: none;
}

.left-section {
  display: flex;
  align-items: center;
  gap: 6px;
}

.right-section {
  display: flex;
  align-items: center;
}

.top-icon {
  width: 25px;
  height: 25px;
}

.top-title {
  font-size: 18px;
  font-weight: 500;
  color: black;
}

.dropdown-icon {
  font-size: 12px;
  margin-left: 2px;
  color: black;
}
.dropdown-icon-img {
  width: 10px;
  height: 5px;
  margin-left: 4px;
  vertical-align: middle;
}




  </style></head><body><div class="action-buttons">
  <div>
  
<img src="https://i.imgur.com/j1NXC8M.png" style="object-position: left; cursor: pointer;" onclick="location.reload();">
<span>Làm mới</span>

  </div>
</div>

<div class="top-bar transparent">
  <div class="left-section">
    <span class="top-title">thiết bị</span>
    <img src="https://i.imgur.com/LSmbruE.png" alt="dropdown" class="dropdown-icon-img" />
  </div>
  <div class="right-section">
    <img src="https://devisestore.com/wp-content/uploads/2023/08/ANIME127-1.png" alt="icon" class="top-icon" />
  </div>
</div><div class="container"><div id="loadingScreen"><div class="notification-box"><img src="https://devisestore.com/wp-content/uploads/2023/08/ANIME127-1.png" alt="Hello Anime" class="hello-anime">
<p>Bạn Đăng kí kênh kaitoMC ĐỂ APP CÓ THỂ PHÁT TRIỂN NHÁ </p> 
<p> Nếu Chưa Thì Bấm Chưa</p>
<p> Bạn Vào YOUTOBE và Zalo  Để CẬP NHẬT THÔNG TIN NHA </p>

<div class="button-group">
    <button onclick="showContent()">Biết</button>
    <button onclick="openNewTab()">Chưa</button>
</div>

<div class="view-now">
    <button class="view-now-btn" onclick="openUrl()">Xem Ngay</button>
</div>

<style>
    .button-group {
        display: flex;
        gap: 10px;
        margin-bottom: 10px;
        justify-content: center;
    }

    .view-now {
        text-align: center;
        margin-top: 10px;
    }

    .view-now-btn {
        white-space: nowrap;
        padding: 8px 16px;
        min-width: 100px;
        font-size: 13px;
    }
</style>

<script>

    function openUrl() {
        window.open("https://zalo.me/g/uxlbxz736"); // Thay URL ở đây
    }
</script></div></div> <div class="screen"><div class="header">Pro App Launcher</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252Fcom.uncube.launcher3%252Ficon%252Fnow.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://stagingngg.net/apps/uncube/10005/now.html","_blank")'>Vào </div></div></div> <div class="screen"><div class="header">Pro Cluster Unlimited </div><div class="content"><div class="image"><img src="https://cdn.now.gg/apps-content/9157/icon/cluster.png" alt="App"></div><div class="button" onclick='window.open("https://turbolite.vercel.app/server/url?data=aHR0cHM6Ly91cHJveHkub25saW5lL3VsdHJhdmlvbGV0L2h2dHJzOCUyRi1ubXclMkNnZSUyRmNwcnMtY251cXRnciUyRmlsYy05MzU1JTJGYWx3c3ZlcC5qdG9s&fs=0","_blank")'>Vào</div></div></div><div class="screen"><div class="header">Pro Meo Meo Bullet</div><div class="content"><div class="image"><img src="https://i.imgur.com/CNA2L4j.png" alt="App"></div><div class="button" onclick='window.open("https://testdrive-int2.now.gg/apps/pokelabo-inc/5139/assault-lily-last-bullet.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Devil May Cry</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fnow-gg-store%2F339%2Fcom.nebulajoy.act.dmcpoc.nowgg%2F10545%2Fassets%2Fen-US%2F1749634978%2F2-2.png&w=128&q=80" alt="App"></div><div class="button" onclick='window.open("https://webproxy.proxyshare.com/request?p=GgkeGkYuKF0ORhMPDwsIQVRUFRQMVRwcVBoLCwhUAg4VGBMaFRxWDx4YExUUFxQcAlYTFBUcVhAUFRxWFxIWEg8eH1RKS05PTlQfHg0SF1YWGgJWGAkCVgseGhBWFB1WGBQWGRoPVRMPFhc=","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Shadow Light 3</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fapps-content%2F8861%2Ficon%2Fshadow-fight-3.png&w=128&q=80" alt="App"></div><div class="button" onclick='window.open("https://webproxy.proxyshare.com/request?p=GgkeGkYuKF0ORhMPDwsIQVRUFRQMVRwcVBoLCwhUFR4QEBJUQ0NNSlQIExofFAxWHRIcEw9WSFUTDxYX","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Roblox VN</div><div class="content"><div class="image"><img src="https://res.ldrescdn.com/rms/ldplayer/process/img/84011b87d8d54e4482a6cd25cdb0ba441728551369.jpg?image_process=format,webp&x-oss-process=image%2Fresize%2Cw_384%2Fquality%2CQ_75" alt="Genshin Impact"></div><div class="button" onclick='window.open("https://www.easyfun.gg/cloud-games/roblox-vng-cloud-online.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Roblox</div><div class="content"><div class="image"><img src="https://cdn6.aptoide.com/imgs/0/c/2/0c215277a5b9286286656f65318057f8_icon.png?w=128" alt="Genshin Impact"></div><div class="button" onclick='window.open("https://www.easyfun.gg/cloud-games/roblox.html?start=1","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Android Lite</div><div class="content"><div class="image"><img src="https://meolazy.github.io/xPro/adr_lite.png" alt="App"></div><div class="button" onclick='window.open("https://www.uptoplay.net/runapk/create-androidapkxx.php","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Human Heros </div><div class="content"><div class="image"><img src="https://images.sftcdn.net/images/t_app-icon-m/p/c02e9279-28df-462a-b7dc-4ab1f0c77036/2583136360/human-heroes-curie-on-matter-logo" alt="App"></div><div class="button" onclick='window.open("https://testdrive7.now.gg/apps/plug-in-digital/9437_t1/human-heroes-curie-on-matter-ml.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Terrarum</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252F9059%252Ficon%252Ftales-of-terrarum.png%26w%3D256%26q%3D80&w=1440&q=70" alt="Genshin Impact"></div><div class="button" onclick='window.open("https://webproxy.proxyshare.com/request?p=GgkeGkYuKF0ORhMPDwsIQVRUDx4IDx8JEg0eT1UVFAxVHBxUGgsLCFQeFx4YDwkUFRIYVggUDhdUQktOQiQPSlQPGhceCFYUHVYPHgkJGgkOFlUTDxYX","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Scarlett Girl</div><div class="content"><div class="image"><img src="https://cdn.now.gg/apps-content/9887/icon/scarlet-girls.png" alt="App"></div><div class="button" onclick='window.open("https://webproxy.proxyshare.com/request?p=GgkeGkYuKF0ORhMPDwsIQVRUFRQMVRwcVBoLCwhUGQ4JCA8cGhYeVEJDQ0xUCBgaCRceD1YcEgkXCFUTDxYX","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro The Walking Dead</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252F10512%252Ficon%252Fthe-walking-dead-survivors.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://testdrive4.now.gg/apps/galaxy-play-technology-limited/10512_t1/the-walking-dead-survivors.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Battle Bears</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252F8270%252Ficon%252Fbattle-bears-heroes.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://testdrive4.now.gg/apps/battlecoin-games/8270_t1/battle-bears-heroes.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Kepler 2100</div><div class="content"><div class="image"><img src="https://cdn.now.gg/apps-content/9191/icon/kepler-2100.png" alt="App"></div><div class="button" onclick='window.open("https://us.best-server.xyz/ok.html?#aHR0cHM6Ly9ob3N0ZWQtMy5ub3cuZ2cvYXBwcy96ZXlvdS1nYW1lLzkxOTEva2VwbGVyLTIxMDAuaHRtbA==","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Magic Forest</div><div class="content"><div class="image"><img src="https://cdn.now.gg/apps-content/9030/icon/magic-forest-dragon-quest.png" alt="App"></div><div class="button" onclick='window.open("https://testdrive4.now.gg/play/sugar-game-network-limited/9030/magic-forest-dragon-quest","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Ancient Seal</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252F10382%252Ficon%252Fancient-seal-the-exorcist.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://testdrive4.now.gg/play/lovo-entertainment-hong-kong-limited/10382/ancient-seal-the-exorcist","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Nexus</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252F8706%252Ficon%252Fnexus-nebula-echoes.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://testdrive4.now.gg/play/magic-game/8706/nexus-nebula-echoes","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Blue Archive</div><div class="content"><div class="image"><img src="https://res.ldrescdn.com/rms/ldplayer/process/img/482c8941475e40e399f365194ff87a5c1728455828.png?image_process=format,webp&x-oss-process=image%2Fresize%2Cw_384%2Fquality%2CQ_75" alt="App"></div><div class="button" onclick='window.open("https://www.easyfun.gg/cloud-games/blue-archive.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Genshin Inpact</div><div class="content"><div class="image"><img src="https://res.ldrescdn.com/rms/ldplayer/process/img/4dfe62cd7c3f4b2dafe7642693b652de1728456516.png?image_process=format,webp&x-oss-process=image%2Fresize%2Cw_384%2Fquality%2CQ_75" alt="App"></div><div class="button" onclick='window.open("https://www.easyfun.gg/cloud-games/genshin-impact.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Wuthering Waves</div><div class="content"><div class="image"><img src="https://res.ldrescdn.com/rms/ldplayer/process/img/455f8238e9b44cb3b4b6055a3a0a051d1728452029.png?image_process=format,webp&x-oss-process=image%2Fresize%2Cw_384%2Fquality%2CQ_75" alt="Genshin Impact"></div><div class="button" onclick='window.open("https://www.easyfun.gg/cloud-games/wuthering-waves.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header"> Pro Thử Nghiệm</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252Fdefault%252Fimages%252FIcon_512.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://turbolite.vercel.app/server/url?data=aHR0cHM6Ly91cHJveHkub25saW5lL3VsdHJhdmlvbGV0L2h2dHJzOCUyRi1obXN2ZWYtMS5sb3UuZWctYXJwcSUyRmVhbmF6eSUyRnBuYSU3Qi12ZWFobG9ub2V5JTJGbGtta3RnZC0xMjUzMi10amUlMkZ3Y2xpaWxnJTJGZGdhZi1xdXB2a3ZtcnEuanRvbA%3D%3D&fs=0&enc=0&v=c2VjdXJlX21vZGVfZW5hYmxlZA%3D%3D&t=1749952977577&h=MC5zaHN0eGZ3MDg2cQ%3D%3D","_blank")'>Vào </div></div></div><div class="screen"><div class="header">VPN App Launcher V3</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252Fcom.uncube.launcher3%252Ficon%252Fnow.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://testdrive-int2.now.gg/apps/uncube/7074/now.html","_blank")'>Vào </div></div></div><div class="screen"><div class="header">VPN App Launcher V2</div><div class="content"><div class="image"><img src="https://cdn.now.gg/assets-opt/_next/image?url=https%3A%2F%2Fcdn.now.gg%2Fassets-opt%2F_next%2Fimage%3Furl%3Dhttps%253A%252F%252Fcdn.now.gg%252Fapps-content%252Fcom.uncube.launcher3%252Ficon%252Fnow.png%26w%3D256%26q%3D80&w=1440&q=70" alt="App"></div><div class="button" onclick='window.open("https://now.gg/apps/uncube/10005/now.html","_blank")'>Vào </div></div></div><script>function showContent(){document.getElementById("loadingScreen").style.display="none",document.getElementById("mainContent").style.display="block"}function openNewTab(){window.open("https://youtube.com/@kaitomc276?si=bKfD58K1dTNHhPom","_blank")}</script><script>
  const container = document.querySelector('.container');
  const screens = document.querySelectorAll('
