## TODO

https://payhip.com/b/Ag0yQ 背光aep

---

p粒子运动思路：

1. 对p粒子 world transform 帧
2. 绑定点光源，对点光源位置k帧
3. 使用motion path设置

---

magic colorista 和mojo调色

---

打光（含工程文件）： [简单的MAD合成分享【Anppi 2021】 - 哔哩哔哩 (bilibili.com)](https://www.bilibili.com/read/cv13382830?from=search&spm_id_from=333.337.0.0)

侧光、顶光、正面逆光、背影逆光、舞台投影光。

---

眼睛的绘制 

[自己画眼睛的方法分享 ✨✨👀 | Digital painting tutorials, Anime drawings tutorials, Eye drawing tutorials (pinterest.jp)](https://www.pinterest.jp/pin/580612576956568477/)

---

LOOK制作颗粒感画面：

1. diffusion => 画面漫射
2. lens vignette => 压暗角
3. Haze/flare => 画面雾气感
4. Chromatic Aberration => 色差，RGB/CMY分离
5. edge softness => 边缘柔化，这一步可以进一步突出画面中间区域。此时中间清晰，周围模糊。
6. colorista => 关键调色。高光、中间调、阴影；以及Hue、饱和度，亮度。这个效果可以多次添加，直到调出合适的画面色彩。
7. File Grain => 电影颗粒感。怀旧风格的关键。

---

depth scanner插件可以生成深度图

结合摄像机模糊map参数可以模拟景深

---

丁达尔效应。

- 分型杂色线条加旋转
- rg shine
- 或者rays 插件

---

漏光leaks的实现

---

BCC led效果可以制作图片网格屏幕效果。

---

一些杂乱的笔记
```
1. 人物内投影。可以通过定式，投影+set matte+cc composite+多层yy ramp+来实现。主要是表现人物线性侧光。
2. 人物眼睛高亮。在某些适当的分镜，可以利用人物图层副本+mask 抠出眼睛部分，fill填充颜色，然后设置图层模式为加亮系实现，例如screen模式。
3. 环境光。使用of作为侧光，并设置合理的光源位置。漫画系常见光的颜色是淡黄色，尽量避免也是白色。因为漫画人物本身就是白色了。或者新的调节层来制造局部亮光或者全局明暗控制。
4. 画面整体调色：使用多层looks来处理画面细节。在looks中，常见为压椭圆暗角（vignette），压边缘柔化（edge softness），物理漫射（diffusion），渐变（gradient light）打亮或者打暗，colorista或者4-way color或者高光暗部来调整高光，中间调，暗部，全局颜色。最后使用curve来定义画面风格。到了这步，画面细节已经比较饱满了。
5. 背景处理：利用色调/三色调/五色调/色调变体+模糊（快速，高斯，摄像机blur模糊）来伪造自然景深，模糊前景和背景，保持人物层清晰。也可以使用摄像机的景深功能来实现。
6. 空间纵深。图层z轴拉开，图层z轴数值可以参考三角透视理论来大致确定z轴的值。这样，摄像机运动拍摄时，空间感就很明显。
7.丰富画面元素。在适当的时机，背景加一些星轨螺旋，流星等，避免画面重量过轻，从而看起来没那么单薄。
8.加强文字动画。除了淡入淡出和字符间距缩放，可以大胆尝试动画范围器的其他属性动画。
9.加强文案排版。适当增加修饰性线条，在视觉上排版文案。例如倾斜线和下划线。同时，可以适当给想要突出的文字设置红色。小幅度合理随机化文字字符的字号大小。
```

