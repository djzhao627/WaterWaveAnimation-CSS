# WaterWaveAnimation-CSS

> 网页展示水波纹

## 效果

![预览](https://raw.githubusercontent.com/djzhao627/WaterWaveAnimation-CSS/master/preview/waving.gif)

## 思路

在页面底部展示多张水波的图片，然后让每张水波以不同的方向和速度进行移动，并给不同的水波设置不同的透明度。

## 代码

**HTML**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="style.css">
    <title>WaterWaveAnimation</title>
</head>
<body>
    <section>
        <div class="wave wave1"></div>
        <div class="wave wave2"></div>
        <div class="wave wave3"></div>
        <div class="wave wave4"></div>
    </section>
</body>
</html>
```

**CSS**

```css
* {
    margin: 0;
    padding: 0;
}

section {
    position: relative;
    width: 100%;
    height: 100vh;
    background: #3586ff;
    overflow: hidden;
}

section .wave {
    width: 100%;
    height: 100px;
    position: absolute;
    bottom: 0;
    left: 0;
    background: url(wave.png);
    background-size: 1000px 100px;
}

section .wave.wave1 {
    animation: animate1 20s linear infinite;
    z-index: 1000;
    opacity: 1;
    animation-delay: 0s;
    bottom: 0;
}

section .wave.wave2 {
    animation: animate2 15s linear infinite;
    z-index: 999;
    opacity: 0.5;
    animation-delay: -5s;
    bottom: 10px;
}

section .wave.wave3 {
    animation: animate1 10s linear infinite;
    z-index: 998;
    opacity: 0.2;
    animation-delay: -7s;
    bottom: 15px;
}

section .wave.wave4 {
    animation: animate2 2s linear infinite;
    z-index: 997;
    opacity: 0.71;
    animation-delay: -5s;
    bottom: 20px;
}
    
@keyframes animate1 {
    0% {
        background-position-x: 0;
    }
    100% {
        background-position-x: 1000px;
    }
}

@keyframes animate2 {
    0% {
        background-position-x: 0;
    }
    100% {
        background-position-x: -1000px;
    }
}
```