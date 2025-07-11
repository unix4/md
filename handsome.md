左侧边栏导航
```
{"name":"豆瓣","class":"glyphicon glyphicon-eye-open","link":"https://type.700050.xyz/index.php/douban.html","target":"_self"},
{"name":"归档","class":"archive","link":"https://type.700050.xyz/index.php/artical.html","target":"_self"},
{"name":"说说","class":"lock","link":"https://type.700050.xyz/index.php/cross.html","target":"_self"}
```

PJAX回调函数
```
// 彩色标签云
let tags = document.querySelectorAll("#tag_cloud-2 a");
let infos = document.querySelectorAll(".badge");
let colorArr = ["#1B4B7A", "#4A8149", "#A13F3D", "#8C419E", "#994C26", "#806543"];
tags.forEach(tag => {
    tagsColor = colorArr[Math.floor(Math.random() * colorArr.length)];
    tag.style.backgroundColor = tagsColor;
});
infos.forEach(info => {
    infosColor = colorArr[Math.floor(Math.random() * colorArr.length)];
    info.style.backgroundColor = infosColor;
});
function addNumber(a) {
    var length = document.getElementById("comment").value.length;
    if(length> 0){
        document.getElementById("comment").focus()
        document.getElementById("comment").value += '\n' + a + new Date
    }else{
        document.getElementById("comment").focus()
        document.getElementById("comment").value += a + new Date
    }
}
```
自定义 CSS
```

/*呼吸特效*/
.img-full {
    width: 160px;
    height: 200px; /* 添加固定高度 */
    object-fit: cover; /* 确保图片填充容器且不变形 */
    animation: light 4s ease-in-out infinite;
}

@keyframes light {
    0% {
        box-shadow: 0 0 4px rgba(255, 0, 0, 0.8);
    }
    25% {
        box-shadow: 0 0 16px rgba(0, 255, 0, 0.8);
    }
    50% {
        box-shadow: 0 0 4px rgba(0, 0, 255, 0.8);
    }
    75% {
        box-shadow: 0 0 16px rgba(0, 255, 0, 0.8);
    }
    100% {
        box-shadow: 0 0 4px rgba(255, 0, 0, 0.8);
    }
}
/*文章悬停漂浮*/
.blog-post .panel-small:not(article),
.blog-post .panel:not(article), .panel-picture {
    transition: all 0.3s;
}

.blog-post .panel-small:not(article):hover,
.blog-post .panel:not(article):hover, .panel-picture:hover {
    transform: translateY(-10px);
    box-shadow: 0 8px 10px rgba(73, 90, 47, 0.47);
}
/*首页文章版式圆角化*/
.panel{
    border: none;
    border-radius: 15px;
}

.panel-small{
    border: none;
    border-radius: 15px;
}

.item-thumb{
    border-radius: 15px;  
}




```
自定义 JavaScript
```


/* 左侧图标颜色and彩色标签云 */
let tags = document.querySelectorAll("#tag_cloud-2 a");
let infos = document.querySelectorAll(".badge");
let colorArr = ["#1B4B7A", "#4A8149", "#A13F3D", "#8C419E", "#994C26", "#806543"];
tags.forEach(tag => {
    tagsColor = colorArr[Math.floor(Math.random() * colorArr.length)];
    tag.style.backgroundColor = tagsColor;
});
infos.forEach(info => {
    infosColor = colorArr[Math.floor(Math.random() * colorArr.length)];
    info.style.backgroundColor = infosColor;
});
function addNumber(a) {
    var length = document.getElementById("comment").value.length;
    if(length> 0){
        document.getElementById("comment").focus()
        document.getElementById("comment").value += '\n' + a + new Date
    }else{
        document.getElementById("comment").focus()
        document.getElementById("comment").value += a + new Date
    }
}
let leftHeader = document.querySelectorAll("span.nav-icon>svg,span.nav-icon>i");
let leftHeaderColorArr = ["#FF69B4", "#58c7ea", "#E066FF", "#FF69B4", "#FFA54F", "#90EE90"];
leftHeader.forEach(tag => {
    tagsColor = leftHeaderColorArr[Math.floor(Math.random() * colorArr.length)];
    tag.style.color = tagsColor;
});
<!--转载提醒-->
document.body.oncopy=function(){layer.msg('复制成功,若要转载请务必保留原文链接！');};



```
自定义输出head 头部的HTML代码

```
<!--动态滚动进度条-->
<div class="scroll-line" style="z-index: 999;position: fixed;height: 3px;margin-top: 0px;background-color: #6B999B;width: 0%;"></div>
<script type="text/javascript">
    $(window).scroll(function() {
        var winTop = $(window).scrollTop(), //滚动条的位置
                docHeight = $(document).height(),   //文档高度
                winHeight = $(window).height(); //窗口高度
 
        var scrolled = (winTop / (docHeight - winHeight))*100;
 
        $('.scroll-line').css('width', (scrolled + '%'));
    });
</script>
<script>  
// 浏览器标题切换  
var OriginTitile = document.title;    // 保存之前页面标题  
var titleTime;  
document.addEventListener('visibilitychange', function(){  
    if (document.hidden){  
        document.title = '别肘~';  
        clearTimeout(titleTime);  
    }else{  
        document.title = 'Man!';  
        titleTime = setTimeout(function() {  
            document.title = OriginTitile;  
        }, 2000); // 2秒后恢复原标题  
    }  
});  
</script>
</script>
<!--转载提醒-->
<script src="//lib.baomitu.com/layer/3.1.1/layer.js"></script>

```
自定义输出body 尾部的HTML代码
```
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<!--网格动态背景开始-->
<script type="text/javascript">
    !function () {
        function get_attribute(node, attr, default_value) {
            return node.getAttribute(attr) || default_value;
        }

        function get_by_tagname(name) {
            return document.getElementsByTagName(name);
        }

        function get_config_option() {
            var scripts = get_by_tagname("script"),
                script_len = scripts.length,
                script = scripts[script_len - 1];
            return {
                l: script_len,
                z: get_attribute(script, "zIndex", -1),
                o: get_attribute(script, "opacity", 0.8),
                c: get_attribute(script, "color", "255,255,255"),
                n: get_attribute(script, "count", 350)
            };
        }

        function set_canvas_size() {
            canvas_width = the_canvas.width = window.innerWidth || document.documentElement.clientWidth || document.body.clientWidth,
                canvas_height = the_canvas.height = window.innerHeight || document.documentElement.clientHeight || document.body.clientHeight;
        }

        function draw_canvas() {
            context.clearRect(0, 0, canvas_width, canvas_height);
            var e, i, d, x_dist, y_dist, dist;
            random_points.forEach(function (r, idx) {
                r.x += r.xa,
                    r.y += r.ya,
                    r.xa *= r.x > canvas_width || r.x < 0 ? -1 : 1,
                    r.ya *= r.y > canvas_height || r.y < 0 ? -1 : 1,
                    context.fillRect(r.x - 0.5, r.y - 0.5, 1, 1);
                
                for (i = idx + 1; i < all_array.length; i++) {
                    e = all_array[i];
                    if (null !== e.x && null !== e.y) {
                        x_dist = r.x - e.x;
                        y_dist = r.y - e.y;
                        dist = x_dist * x_dist + y_dist * y_dist;

                        dist < e.max && (e === current_point && dist >= e.max / 2 && (r.x -= 0.03 * x_dist, r.y -= 0.03 * y_dist),
                            d = (e.max - dist) / e.max,
                            context.beginPath(),
                            context.lineWidth = d / 2,
                            context.strokeStyle = "#00FF00", // 改为亮绿色
                            context.moveTo(r.x, r.y),
                            context.lineTo(e.x, e.y),
                            context.stroke());
                    }
                }
            }), frame_func(draw_canvas);
        }

        var the_canvas = document.createElement("canvas"),
            config = get_config_option(),
            canvas_id = "c_n" + config.l,
            context = the_canvas.getContext("2d"), canvas_width, canvas_height,
            frame_func = window.requestAnimationFrame || window.webkitRequestAnimationFrame || window.mozRequestAnimationFrame || window.oRequestAnimationFrame || window.msRequestAnimationFrame || function (func) {
                window.setTimeout(func, 1000 / 40);
            }, random = Math.random,
            current_point = {
                x: null,
                y: null,
                max: 20000
            },
            all_array;
        the_canvas.id = canvas_id;
        the_canvas.style.cssText = "position:fixed;top:0;left:0;z-index:" + config.z + ";opacity:" + config.o;
        get_by_tagname("body")[0].appendChild(the_canvas);

        set_canvas_size();
        window.onresize = set_canvas_size;
        
        window.onmousemove = function (e) {
            e = e || window.event;
            current_point.x = e.clientX;
            current_point.y = e.clientY;
        }, window.onmouseout = function () {
            current_point.x = null;
            current_point.y = null;
        };

        for (var random_points = [], i = 0; config.n > i; i++) {
            var x = random() * canvas_width,
                y = random() * canvas_height,
                xa = 2 * random() - 1,
                ya = 2 * random() - 1;
            random_points.push({
                x: x,
                y: y,
                xa: xa,
                ya: ya,
                max: 6000
            });
        }
        all_array = random_points.concat([current_point]);
        
        setTimeout(function () {
            draw_canvas();
        }, 100);
    }();
</script>
</body>
</html>
```
