# 主页

这是 zerolook 的个人网站源代码，托管在 GitHub Pages 上。

## Features
- **Home Page**: 介绍 zerolook 的个人信息及工作。
- **Portfolio**: 展示 zerolook 的作品和项目。
- **Contact**: 提供联系 zerolook 的方式。

## How to Use
你可以通过以下网址访问该网站：  
[https://zerolook.github.io/gsweb.github.io/](https://zerolook.github.io/gsweb.github.io/)

要查看主页文件 `Home.html`，请点击以下链接：  
[点击这里查看 Home 页面](https://zerolook.github.io/gsweb.github.io/Home.html)

## Home.html 内容
下面是 `Home.html` 文件的一部分内容：

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>九部分网页设计</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }

        section {
            margin: 0;
            padding: 0;
        }

        section img {
            width: 100%;
            height: auto;
            display: block;
        }

        /* 菜单栏样式 */
        #menu {
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #fff; /* 根据需要设置背景颜色 */
            padding: 10px 0;
        }

        #menu img {
            height: 80px; /* 设置图片的高度 */
            width: auto;  /* 等比缩放宽度 */
            cursor: pointer; /* 鼠标移动到图片上时显示手形指针 */
        }

        /* 项目介绍样式 */
        #projects {
            position: relative;
            width: 100%;
            height: 100vh; /* 高度设置为视口高度 */
            background: no-repeat center center;
            background-size: cover;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        #projects-bg {
            width: 100%;
            height: auto;
            display: block;
        }

        .overlay-images {
            position: absolute;
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            height: 100%;
            padding: 0 20%; /* 图片的间距为底图宽度的四分之一的160% */
            box-sizing: border-box;
            top: 50%;
            transform: translateY(-50%);
        }

        .overlay-images a {
            display: block;
            margin: 0 20%; /* 保持图片之间的间隔 */
            height: auto;
            width: auto;
            transition: opacity 0.3s ease;
        }

        .overlay-images img {
            height: auto;
            max-height: 160%; /* 图片高度最大为底图高度的160% */
            width: auto; /* 宽度自动等比缩放 */
            transition: opacity 0.3s ease;
        }

        /* 经典案例1 */
        #case-studies1 {
            background-color: #fff;
            width: 100%;
            height: auto;
            padding: 10px; /* 区域内边距 */
        }

        #case-studies1 img {
            width: 100%;
            height: auto;
        }

        /* 经典案例2 */
        #case-studies2 {
            background-color: #fff;
            width: 100%;
            height: auto;
            padding: 10px; /* 区域内边距 */
        }

        #case-studies2 img {
            width: 100%;
            height: auto;
        }

        /* 地图1、地图2和公司介绍区域样式 */
        #map1, #map2, #company-intro {
            background-color: #fff;
            width: 100%;
            height: auto;
        }
    </style>
    <script>
        // 菜单栏的图片切换脚本
        var originalImages = {
            "img2": "file:///F:/桌面/网页试做/图片/菜单栏/2.gif",
            "img4": "file:///F:/桌面/网页试做/图片/菜单栏/4.gif",
            "img6": "file:///F:/桌面/网页试做/图片/菜单栏/6.gif",
            "img8": "file:///F:/桌面/网页试做/图片/菜单栏/8.gif",
            "img10": "file:///F:/桌面/网页试做/图片/菜单栏/10.gif"
        };

        var hoverImages = {
            "img2": "file:///F:/桌面/网页试做/图片/菜单栏/images/2.gif",
            "img4": "file:///F:/桌面/网页试做/图片/菜单栏/images/4.gif",
            "img6": "file:///F:/桌面/网页试做/图片/菜单栏/images/6.gif",
            "img8": "file:///F:/桌面/网页试做/图片/菜单栏/images/8.gif",
            "img10": "file:///F:/桌面/网页试做/图片/菜单栏/images/10.gif"
        };

        function resetImages() {
            for (var imgId in originalImages) {
                document.getElementById(imgId).src = originalImages[imgId];
            }
        }

        function handleMouseOver(imgId) {
            resetImages();
            document.getElementById(imgId).src = hoverImages[imgId];
        }

        function handleMouseOut(imgId) {
            document.getElementById(imgId).src = originalImages[imgId];
        }

        function handleClick(url) {
            setTimeout(function() {
                window.location.href = url;
            }, 500);
        }

        // 项目介绍图片切换脚本
        document.addEventListener('DOMContentLoaded', function() {
            document.querySelectorAll('.overlay-images img').forEach(img => {
                const originalSrc = img.getAttribute('data-src');
                const hoverSrc = img.getAttribute('data-hover-src');
                
                img.addEventListener('mouseover', function() {
                    this.src = hoverSrc;
                });

                img.addEventListener('mouseout', function() {
                    this.src = originalSrc;
                });
            });
        });
    </script>
</head>
<body>

    <!-- 菜单栏 -->
    <section id="menu">
        <img id="img1" src="file:///F:/桌面/网页试做/图片/菜单栏/1.gif" alt="1">
        <img id="img2" src="file:///F:/桌面/网页试做/图片/菜单栏/2.gif" alt="2"
             onmouseover="handleMouseOver('img2')"
             onmouseout="handleMouseOut('img2')"
             onclick="handleClick('file:///F:/桌面/网页试做/Home.html')">
        <img id="img3" src="file:///F:/桌面/网页试做/图片/菜单栏/3.gif" alt="3">
        <img id="img4" src="file:///F:/桌面/网页试做/图片/菜单栏/4.gif" alt="4"
             onmouseover="handleMouseOver('img4')"
             onmouseout="handleMouseOut('img4')"
             onclick="handleClick('file:///F:/桌面/网页试做/Work.html')">
        <img id="img5" src="file:///F:/桌面/网页试做/图片/菜单栏/5.gif" alt="5">
        <img id="img6" src="file:///F:/桌面/网页试做/图片/菜单栏/6.gif" alt="6"
             onmouseover="handleMouseOver('img6')"
             onmouseout="handleMouseOut('img6')"
             onclick="handleClick('file:///F:/桌面/网页试做/Team.html')">
        <img id="img7" src="file:///F:/桌面/网页试做/图片/菜单栏/7.gif" alt="7">
        <img id="img8" src="file:///F:/桌面/网页试做/图片/菜单栏/8.gif" alt="8"
             onmouseover="handleMouseOver('img8')"
             onmouseout="handleMouseOut('img8')"
             onclick="handleClick('file:///F:/桌面/网页试做/About%20US.html')">
        <img id="img9" src="file:///F:/桌面/网页试做/图片/菜单栏/9.gif" alt="9">
        <img id="img10" src="file:///F:/桌面/网页试做/图片/菜单栏/10.gif" alt="10"
             onmouseover="handleMouseOver('img10')"
             onmouseout="handleMouseOut('img10')"
             onclick="handleClick('file:///F:/桌面/网页试做/Contact%20Us.html')">
        <img id="img11" src="file:///F:/桌面/网页试做/图片/菜单栏/11.gif" alt="11">
        <img id="img12" src="file:///F:/桌面/网页试做/图片/菜单栏/12.gif" alt="12">
    </section>

    <!-- 视频 -->
    <section id="video">
        <img src="file:///F:/桌面/网页试做/图片/视频展示.png" alt="视频展示">
    </section>

    <!-- 关于我们 -->
    <section id="about-us">
        <img src="file:///F:/桌面/网页试做/图片/关于我们.png" alt="关于我们">
    </section>

    <!-- 项目介绍 -->
    <section id="projects">
        <img id="projects-bg" src="file:///F:/桌面/网页试做/图片/项目介绍.png" alt="项目介绍">
        <div class="overlay-images">
            <a href="file:///F:/桌面/网页试做/brand-strategy.html">
                <img src="file:///F:/桌面/网页试做/图片/BRAND STRATEGY.png" alt="BRAND STRATEGY" data-src="file:///F:/桌面/网页试做/图片/BRAND STRATEGY.png" data-hover-src="file:///F:/桌面/网页试做/图片/BRAND STRATEGY 红.png">
            </a>
            <a href="file:///F:/桌面/网页试做/offline-services.html">
                <img src="file:///F:/桌面/网页试做/图片/OFFLINE SERVIES.png" alt="OFFLINE SERVIES" data-src="file:///F:/桌面/网页试做/图片/OFFLINE SERVIES.png" data-hover-src="file:///F:/桌面/网页试做/图片/OFFLINE SERVIES 红.png">
            </a>
            <a href="file:///F:/桌面/网页试做/online-services.html">
                <img src="file:///F:/桌面/网页试做/图片/ONLINE SERVICES.png" alt="ONLINE SERVICES" data-src="file:///F:/桌面/网页试做/图片/ONLINE SERVICES.png" data-hover-src="file:///F:/桌面/网页试做/图片/ONLINE SERVICES 红.png">
            </a>
        </div>
    </section>

    <!-- 经典案例1 -->
    <section id="case-studies1">
        <img src="file:///F:/桌面/网页试做/图片/经典案例1.png" alt="经典案例1">
    </section>

    <!-- 经典案例2 -->
    <section id="case-studies2">
        <img src="file:///F:/桌面/网页试做/图片/经典案例2.png" alt="经典案例2">
    </section>

    <!-- 地图1 -->
    <section id="map1">
        <img src="file:///F:/桌面/网页试做/图片/地图1.png" alt="地图1">
    </section>

    <!-- 地图2 -->
    <section id="map2">
        <img src="file:///F:/桌面/网页试做/图片/地图2.gif" alt="地图2">
    </section>

    <!-- 公司介绍 -->
    <section id="company-intro">
        <img src="file:///F:/桌面/网页试做/图片/公司介绍.png" alt="公司介绍">
    </section>

</body>
</html>
