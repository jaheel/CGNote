# 2.1 视频显示设备

CRT（Cathode Ray Tube）：阴极射线管



## 2.1.1 刷新式CRT

refresh rate：刷新频率

refresh CRT：刷新式CRT

## 2.1.2 光栅扫描显示器

raster-scan display

refresh buffer：刷新缓存

frame buffer：帧缓存

color buffer：颜色缓存

缓存深度(depth)、位平面(bit plane)：每像素的位数

位图(bitmap)：每像素一位的帧缓存

像素图(pixmap)：每像素多位的帧缓存

## 2.1.3 随机扫描显示器

random scan display

图形的组成线条由随机扫描系统按任意指定的顺序绘制并刷新

## 2.1.4 彩色CRT监视器

电子束穿透法(beam-penetration)

荫罩法(shadow-mask)

## 2.1.5 平板显示器

flat-panel display

* **发射设备**

  1. 等离子体显示板(plasma panel)

     > 也称 气体放电显示器(gas-discharge display)
     >
     > 包含氖气的混合气体充入两块玻璃板之间的区域而构成，一块玻璃板上放置一系列垂直导电带，而另一块玻璃板上构造一组水平导电带。
     >
     > 施加点火电压，导致两导电带交叉点处的气体进入电子和离子的辉光放电等离子区

  2. 薄膜光电显示器(thin-film electroluminescent display)

     > 与等离子体显示板类似结构
     >
     > 不同之处：在玻璃板之间的区域充以荧光物

  3. 发光二极管(light-emitting diode, LED)

     > 二极管以矩阵排列形成显示器的像素位置
     >
     > 图形的定义存储在刷新缓存中
     >
     > 流程：
     >
     > 1. 信息从刷新缓存读出
     > 2. 转换成电压电平
     > 3. 应用于二极管，在显示器上产生发光图案

* **非发射设备**

  液晶显示器(liquid-crystal display, LCD)

  > 通过能阻塞或传递光的液晶材料，传递来自周围的或内部光源偏振光
  >
  > * 液晶：具有晶状结构的分子化合物，可像液体那样流动

## 2.1.6 立体感和虚拟现实系统

左眼左视图、右眼右视图，两个视图合成为单个图像，并感觉到场景带有深度。

产生立体感途径：使用光栅系统在不同的刷新周期交替显示两种视图