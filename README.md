# CG_Lab

> **系统使用说明书**

[toc]

### 1 开发环境

| 依赖   | 版本     |
| ------ | -------- |
| python | >=3.7.4  |
| conda  | ==4.11.0 |
| numpy  | >=1.18.1 |
| pillow | ==7.0.0  |
| pyqt5  | ==5.15.4 |

### 2 程序运行

```python
# 运行CLI
python cg_cli.py [-i<绘制指令序列文件>] [-o<图像保存目录>]
# 运行GUI
python cg_gui.py
```

### 3 窗口布局

初始主窗体宽/高为1000/800，可在`cg_gui.py`中修改变量`MAINWINDOW_W`和`MAINWINDOW_H`来修改；

```python
# 主窗体的宽与高
MAINWINDOW_W = 1000
MAINWINDOW_H = 800
```

<img src=".\imgs\image-20230216005955910.png" alt="image-20230216005955910" style="zoom:67%;" />

### 4 文件菜单

<img src=".\imgs\image-20230216002623699.png" alt="image-20230216002623699" style="zoom:80%;" />

#### 4.1 保存图片

<img src=".\imgs\image-20230216002756003.png" alt="image-20230216002756003" style="zoom:67%;" />

#### 4.2 设置画笔

##### 设置画笔颜色

<img src=".\imgs\image-20230216003015847.png" alt="image-20230216003015847" style="zoom:50%;" />

##### 设置画笔粗细

大小范围[1, 10]，默认为2

<img src=".\imgs\image-20230216003231642.png" alt="image-20230216003231642" style="zoom:50%;" />

#### 4.3 重置画布

按照对话框提示输入，即可

<img src=".\imgs\image-20230216003928309.png" alt="image-20230216003928309" style="zoom:67%;" />

假设水平设为400，垂直为300，效果如下：

<img src=".\imgs\image-20230216004030037.png" alt="image-20230216004030037" style="zoom:50%;" />

#### 4.4 退出

直接退出

### 5 编辑菜单

<img src=".\imgs\image-20230216004134481.png" alt="image-20230216004134481" style="zoom:67%;" />

#### 5.1 选择

<img src=".\imgs\image-20230216004512628.png" alt="image-20230216004512628" style="zoom:100%;" />

<img src=".\imgs\image-20230216004544257.png" alt="image-20230216004544257" style="zoom:80%;" />

#### 5.2 复制

如果直接点击复制，则会提示：

<img src=".\imgs\image-20230216004643825.png" alt="image-20230216004643825" style="zoom:100%;" />

如果点击了图元，则会提示：

<img src=".\imgs\image-20230216004615434.png" alt="image-20230216004615434" style="zoom:100%;" />

#### 5.3 粘贴

<img src=".\imgs\image-20230216004715605.png" alt="image-20230216004715605" style="zoom:100%;" />

点击后效果如下：

<img src=".\imgs\image-20230216004738660.png" alt="image-20230216004738660" style="zoom:50%;" />

#### 5.4 平移

先选择图元，然后按住鼠标左键平移，松开结束。

<img src=".\imgs\image-20230216004846103.png" alt="image-20230216004846103" style="zoom:100%;" />

#### 5.5 旋转

<img src=".\imgs\image-20230216004907940.png" alt="image-20230216004907940" style="zoom:100%;" />

#### 5.6 缩放

<img src=".\imgs\image-20230216004931867.png" alt="image-20230216004931867" style="zoom:100%;" />

#### 5.7 裁剪

<img src=".\imgs\image-20230216005008170.png" alt="image-20230216005008170" style="zoom:100%;" />

蓝色框为裁剪框，

<img src=".\imgs\image-20230216005035413.png" alt="image-20230216005035413" style="zoom:100%;" />

### 6 绘制菜单

<img src=".\imgs\image-20230216005305677.png" alt="image-20230216005305677" style="zoom:80%;" />

按照界面左下角提示绘制即可。

#### 6.1 曲线

**曲线最多可按6个点或者按右键结束，控制点数可在`cg_gui.py`中修改个数。**

```python
# cg_gui.py#21
MAX_NUM_CONTROL_POINTS = 6                  # 最大控制点个数
```

##### 6.1.1 Bezier算法绘制

![image-20230216005610478](D:\Program Files\Typora\img\image-20230216005610478.png)

1.先画出一条直线

![image-20230216005654897](.\imgs\image-20230216005654897.png)

2.再按住鼠标左键移动，绘制出控制点多边形，松开鼠标左键，控制点生成

<img src=".\imgs\image-20230216005717339.png" alt="image-20230216005746790" style="zoom:100%;" />

3.再绘制一个控制点

<img src=".\imgs\image-20230216005734782.png" alt="image-20230216005746790" style="zoom:80%;" />

4.按右键结束绘制，控制多边形也随之消失

<img src=".\imgs\image-20230216005746790.png" alt="image-20230216005746790" style="zoom:80%;" />



##### 6.1.2 B-spline算法绘制

<img src=".\imgs\image-20230216005820165.png" alt="image-20230216005820165" style="zoom:100%;" />

### 7 视图

#### 7.1 显示网格

**不显示网格：**

<img src=".\imgs\image-20230216005906573.png" alt="image-20230216005906573" style="zoom:67%;" />

### 8 帮助

#### 8.1 系统文档

> **点击“系统文档”将会跳转至[网页版系统](https://github.com/stu-yue/cg-lab/blob/main/cg_lab/%E7%B3%BB%E7%BB%9F%E8%AF%B4%E6%98%8E%E4%B9%A6.pdf)文档说明。**
