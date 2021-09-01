# 了解 SVG

## 概念

> 可缩放矢量图形（Scalable Vector Graphics，SVG），是一种用于描述二维的**矢量图形**，基于 XML 的标记语言。作为一个基于文本的开放网络标准，SVG 能够**优雅而简洁**地渲染不同大小的图形，**并和 CSS，DOM，JavaScript 和 SMIL 等其他网络标准无缝衔接**。本质上，SVG 相对于图像，就好比 HTML 相对于文本。

## 优点

-   矢量图形：它的图像能够被无限放大而不失真或降低质量，并且可以方便地修改内容。
-   优雅而简洁：有些用 html 语言描述相对复杂的结构，svg 相对简单且没有牺牲可读性
-   无缝衔接前端开发三剑客。1. 嵌入 html 2. css 样式控制 3. js 逻辑控制

## 常用元素和样式

### 元素

-   circle
-   rect
-   ellipse
-   polygon
-   polyline
-   line
-   path
-   text
-   defs
-   use
-   animateTransform
-   animate

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Document</title>
        <style>
            .loader-container {
                position: absolute;
                top: 0;
                bottom: 0;
                left: 0;
                right: 0;
                padding: 5%;
            }

            .loader {
                position: relative;
                margin: 0px auto;
                width: 100px; /* SET SIZE OF SPINNER HERE */
            }

            .loader:before {
                content: '';
                display: block;
                padding-top: 100%;
            }

            .circular {
                -webkit-animation: rotate 2s linear infinite;
                animation: rotate 2s linear infinite;
                height: 100%;
                -webkit-transform-origin: center center;
                transform-origin: center center;
                width: 100%;
                position: absolute;
                top: 0;
                bottom: 0;
                left: 0;
                right: 0;
                margin: auto;
            }

            .path {
                stroke-dasharray: 1, 200;
                stroke-dashoffset: 0;
                -webkit-animation: dash 1.5s ease-in-out infinite, color 6s ease-in-out infinite;
                animation: dash 1.5s ease-in-out infinite, color 6s ease-in-out infinite;
                stroke-linecap: round;
            }

            @-webkit-keyframes rotate {
                100% {
                    -webkit-transform: rotate(360deg);
                    transform: rotate(360deg);
                }
            }

            @keyframes rotate {
                100% {
                    -webkit-transform: rotate(360deg);
                    transform: rotate(360deg);
                }
            }

            @-webkit-keyframes dash {
                0% {
                    stroke-dasharray: 1, 200;
                    stroke-dashoffset: 0;
                }
                50% {
                    stroke-dasharray: 89, 200;
                    stroke-dashoffset: -35px;
                }
                100% {
                    stroke-dasharray: 89, 200;
                    stroke-dashoffset: -124px;
                }
            }

            @keyframes dash {
                0% {
                    stroke-dasharray: 1, 200;
                    stroke-dashoffset: 0;
                }
                50% {
                    stroke-dasharray: 89, 200;
                    stroke-dashoffset: -35px;
                }
                100% {
                    stroke-dasharray: 89, 200;
                    stroke-dashoffset: -124px;
                }
            }

            @-webkit-keyframes color {
                100%,
                0% {
                    stroke: #d62d20;
                }
                40% {
                    stroke: #0057e7;
                }
                66% {
                    stroke: #008744;
                }
                80%,
                90% {
                    stroke: #ffa700;
                }
            }

            @keyframes color {
                100%,
                0% {
                    stroke: #d62d20;
                }
                40% {
                    stroke: #0057e7;
                }
                66% {
                    stroke: #008744;
                }
                80%,
                90% {
                    stroke: #ffa700;
                }
            }
        </style>
    </head>
    <body>
        <div class="loader-container">
            <div class="loader">
                <svg class="circular" viewBox="25 25 50 50">
                    <circle class="path" cx="50" cy="50" r="20" fill="none" stroke-width="2" stroke-miterlimit="10"></circle>
                </svg>
            </div>
        </div>
    </body>
</html>
```
