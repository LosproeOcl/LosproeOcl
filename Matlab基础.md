









# **Matlab基础**

















| @author ' YQY' |
| -------------: |







[TOC]

------



### **软件基础**



1. fix()向0取整；[左闭右开区间);round()四舍五入；floor()向负无穷取整；ceil()向正无穷取整；bhb
2.  rem()==mod()取余；
3. N阶幻方矩阵magic(n)，行列对角线和相同,N>=3的标量有效；
4.  与或非：&、|、~;
5. ones(m,n),zeros(m,n)||m=n;
6. rand()均匀分布在0~1之间的 伪随机矩阵;
7. randn()标准正态分布的伪随机数矩阵（期望（均值）：0；方差：1）；
8. find(条件)； find a factor which can bridge with the “tiao jian” in the Matrix ; e.g. : find(A>4)找到A矩阵中大于4的元素的位置（每列往下排序）;
9.  对角阵diag([,,,,]);diag(A)即提取A(m*n)矩阵的对角线上的元素,形成一个min(m,n)个元素的**列向量**；
10. diag（V，k）提取V矩阵的第k条对角线元素，形成**列向量**；
11. triu(A)上三角（tri-up），triu(A,k)提取A矩阵的第k条对角线以上的三角形成**新矩阵**（**是提取元素，不是化简**）；
12. 矩阵的转置（单引号’）：b是a的转置矩阵，b=a’；
13. rot90(A，k)对矩阵A逆时针旋转90°的k倍；
14. flipud()上下翻转（up、down）fliplr()左右翻转；
15. inv(A),inverse , A的逆矩;Ax=bàx=(/*(A^-1)*b*/)||x=inv(A)*b||x=A\b（即b/A）；
16. pinv(A),A的伪逆 ABA=A，则B是A的伪逆；
17. det（A）求矩阵值；
18. rank（）求秩；trace()求迹；
19. E=eig()特征值列向量;[V,D]=eig()V特征向量，D =tr（A）对角矩阵;[V,D,W]=eig();
20. log是语言中自然对数、log10，其他换底；
20. length求列宽，ndims求维度，size求行列宽，numel求元素数；
20. 非关键字无需定义为变量，第一次使用时同时完成定义，定义类型同步使用方式；

 

 

### **程序设计基础**



1. 关键字：nargin输入参数数目 nargout输出参数数目；Inf正无穷，NaN不定值、realmax、realmin最大最小正实数；eps计算时容许误差；

2. 局部变量不用特殊说明、全局变量global,习惯上全局变量用大写字母表示；

3.  isvarname验证用户指定变量是否有效

4.  数组生成方式：a、直接输入法；b、冒号生产法；

5.  线性等分数组生成法：vec=linspace(a,b,n)a初b末n等分点数（n省略默认100）；

6.  对数等分生成法：vec=logspace(a,b,n)创建10a到10b间的数组，n是数组点的个数（n默认为50）；

7.  行列（RC）双编号与C语言相通，但单编号是按列排的一维数组；

8.  数组元素访问：冒号方式（手段）、单下标访问和双下标访问（路径）；

9.  M文件：命令文件;script脚本文件;function函数文件（相当于头文件.h）；

10. M文件的一般格式：①声明行、H1行②在线帮助文本区③日志区④主体；

11. 程序运行快捷键：F9、命令行窗口输入不带后缀的文件名；

12. 函数文件：①开头声明行：function[outarglist]=函数名（inarglist）；②注释说明语句；③函数体；

13. 函数代码示例

    ```Matlab
    function F=multisiginal(n)
    A=1;w=2;phi=pi/2;
    signal=createsing(A,w,phi)
    F=signal.^n
    %subfunction
    function signal=createsing(A,w,phi)
    x=0:p/100:pi*2;
    signal=A*sin(w*x+phi);
    ```

14. 选择结构示例

    ```matlab
    %选择结构示例
    clc
    num1=rand(1)
    if num1>0.5
        num2=num1
    else
    	num1
    end
    num3=num1-0.5
    
    %双分支
    function vec =compare(a1,a2)
    %比较两数大小
    if a1<a2
        vec=[a1,a2];
    else
        vec=[a2,a1];
    end
    
    
    %多分支if~elseif~else~end
    function y=tripfee(x)
    %<20 0;20,50 0.2perkg;
    
    if x<=20&&x>0
        y=0;
    elseif x<0
        y='EOF';
    elseif x>20&&x<=50
        y=0.2*(x-20);
    else
        y=0.2*30+0.3*(x-50);
    end
    
    %like this
    if condition
    	body
    elseif condition
    	body
    else
    	body
    end
    ```

15. switch语句，基本同C语言；

    ```matlab
    function y=score(x)
    
    n=fix(x/10);
    %除以10，向0取整
    switch(n)
        case 1
    
        case 2
            ....
    
    end
            
    ```
    
    
    
16. for：array数组中取一列，遍取array中列，则跳出循环

    ```matlab
    for 循环变量=array
    	循环体
    end
    
    %e.g
    sum=0;
    for n=0:100;
    	sum=sum+n;
    end
    
    
    function result=fact(~)
    %n的阶乘
    
    result=1;
    for k=1:n
        result=result*k;
    end
    result
    
    %嵌套特殊矩阵
    for i=1:3
        for j=5:-1:1
            a(i,j)=i^2+j^2;
        end
    end
    a(i,j)%显示（i，j）元素
    a%显示a矩阵
    
    function y=yRx(x)
    %x为一维向量(数组)
    n=length(x);
    for k=1:n
        if x(k)<-1;
            y(k)=x(k);
        elseif x(k)<1
            y(k)=x(k)^3;
        else
            y(k)=exp(1-x(k));
        end
    end
    y(k)%y的第k个元素
    y%y数组（向量）
    
    
    
    %Hilbert矩阵
    x=randn(10);
    for i=1:ndims(x)
        for j=1:length(x)
            x(i,j)=1/(i+j-1);
        end
    end
    x
    ```
    
17. while：几乎同C lang；

    ```matlab
    while condition
    	  body
    end
    
    %e.g
    k=1;
    result=1;
    while k<=n 
    result=result*k;
    k=k+1;
    end
    result
    ```

18. 程序流程控制：

    ```matlab
    input('prompt') %提示信息，获取输入；
    disp('s') 		%s是（事先定义使用过的）字符串；
    fprintf('%s',v) %按照“%s”的格式打印v的内容；按照C语言printf理解；
    return			%终止函数，返回上级(权限还给键盘（命令行）或者调用它				 	 的程序）
    continue break  %同C lang；
    
    
    %e.g
    %求解方程ax?十bx十c=0的根. 
    a=input (' a=');
    b=input (' b=');
    c=input (' c=');
    d=6^2-4*a*c;
    if d>0 
        disp ('There are two answers!');
    x1=(-b+sqrt (d)) / (2*a) ;
    x2=(-b-sqrt (d)) / (2*a) ; 
    root=[x1, x2]
    elseif d==0
    disp ('There is only one answer!');
    x=-b/(2*a);
    root=x
    else
    disp (' There is no answer!');
    end
    
    
    %例如：输出九九乘法表到命令窗口 
    for r=1:9 
        for c=1:r
            p=r*c;
            fprintf (' %d*%d-%d', c, r, p)
        end
        fprintf (' \n' )
    end
    
    
    %例如：删除一维数组中不能开平方根的元素
    a=[4 1 16 25 0 -1 9];
    b=[];
    for k=1:7 
        if a(k)<0 
            continue
        end
    b=[b sqrt(a(k))];
    end
    ```

    

    

    

### 数据可视化及数据存取

二维绘图：plot()\fplot()\ezplot()及其图形标注

1.  `plot(Y)` 绘制 `Y` 对一组隐式 x 坐标的图。

   - 如果 `Y` 是向量，则 x 坐标范围从 1 到 `length(Y)`。
   - 如果 `Y` 是矩阵，则对于 `Y` 中的每个列，图中包含一个对应的行。x 坐标的范围是从 1 到 `Y` 的行数。

   如果 `Y` 包含复数，MATLAB® 绘制 `Y` 的虚部对 `Y` 的实部的图。如果同时指定了 `X` 和 `Y`，虚部将被忽略。

2. `plot(X,Y)` 创建 `Y` 中数据对 `X` 中对应值的二维线图。

   - 要绘制由线段连接的一组坐标，请将 `X` 和 `Y` 指定为相同长度的向量。

   - 要在同一组坐标区上绘制多组坐标，请将 `X` 或 `Y` 中的至少一个指定为矩阵。

   - `plot(X,Y,LineSpec)` 使用指定的线型、标记和颜色创建绘图。

   - `LineSpec` — 线型、标记和颜色 字符串 | 字符向量

     线型、标记和颜色，指定为包含符号的字符串或字符向量。符号可以按任意顺序显示。您不需要同时指定所有三个特征（线型、标记和颜色）。例如，如果忽略线型，只指定标记，则绘图只显示标记，不显示线条。

     **示例：** `"--or"` 是带有圆形标记的红色虚线

     | 线型   | 描述   | 表示的线条                                                   |
     | :----- | :----- | :----------------------------------------------------------- |
     | `"-"`  | 实线   | ![Sample of solid line](https://www.mathworks.com/help/releases/R2022b/matlab/ref/linestyle_solid.png) |
     | `"--"` | 虚线   | ![Sample of dashed line](https://www.mathworks.com/help/releases/R2022b/matlab/ref/linestyle_dashed.png) |
     | `":"`  | 点线   | ![Sample of dotted line](https://www.mathworks.com/help/releases/R2022b/matlab/ref/linestyle_dotted.png) |
     | `"-."` | 点划线 | ![Sample of dash-dotted line, with alternating dashes and dots](https://www.mathworks.com/help/releases/R2022b/matlab/ref/linestyle_dashdotted.png) |

     | 标记          | 描述     |                          生成的标记                          |
     | :------------ | :------- | :----------------------------------------------------------: |
     | `"o"`         | 圆圈     | ![Sample of circle marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_o.png) |
     | `"+"`         | 加号     | ![Sample of plus sign marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_plus.png) |
     | `"*"`         | 星号     | ![Sample of asterisk marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_asterisk.png) |
     | `"."`         | 点       | ![Sample of point marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_point.png) |
     | `"x"`         | 叉号     | ![Sample of cross marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_x.png) |
     | `"_"`         | 水平线条 | ![Sample of horizontal line marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_hline.png) |
     | `"|"`         | 垂直线条 | ![Sample of vertical line marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_vline.png) |
     | `"square"`    | 方形     | ![Sample of square marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_s.png) |
     | `"diamond"`   | 菱形     | ![Sample of diamond line marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_d.png) |
     | `"^"`         | 上三角   | ![Sample of upward-pointing triangle marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_uptriangle.png) |
     | `"v"`         | 下三角   | ![Sample of downward-pointing triangle marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_downtriangle.png) |
     | `">"`         | 右三角   | ![Sample of right-pointing triangle marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_righttriangle.png) |
     | `"<"`         | 左三角   | ![Sample of left-pointing triangle marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_lefttriangle.png) |
     | `"pentagram"` | 五角形   | ![Sample of pentagram marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_p.png) |
     | `"hexagram"`  | 六角形   | ![Sample of hexagram marker](https://www.mathworks.com/help/releases/R2022b/matlab/ref/marker_h.png) |

     | 颜色名称    | 短名称 | RGB 三元组 | 外观                                                         |
     | :---------- | :----- | :--------- | :----------------------------------------------------------- |
     | `"red"`     | `"r"`  | `[1 0 0]`  | ![Sample of the color red](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_red.png) |
     | `"green"`   | `"g"`  | `[0 1 0]`  | ![Sample of the color green](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_green.png) |
     | `"blue"`    | `"b"`  | `[0 0 1]`  | ![Sample of the color blue](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_blue.png) |
     | `"cyan"`    | `"c"`  | `[0 1 1]`  | ![Sample of the color cyan](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_cyan.png) |
     | `"magenta"` | `"m"`  | `[1 0 1]`  | ![Sample of the color magenta](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_magenta.png) |
     | `"yellow"`  | `"y"`  | `[1 1 0]`  | ![Sample of the color yellow](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_yellow.png) |
     | `"black"`   | `"k"`  | `[0 0 0]`  | ![Sample of the color black](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_black.png) |
     | `"white"`   | `"w"`  | `[1 1 1]`  | ![Sample of the color white](https://www.mathworks.com/help/releases/R2022b/matlab/ref/hg_white.png) |

3. plot(X1,Y1,...,Xn,Yn) 在同一组坐标轴上绘制多对 x 和 y 坐标。此语法可替代将坐标指定为矩阵的形式。

   ```matlab
   plot(matlab,y,'--*b','linewidth',1.8)
   text(3.4,0.5,'y=sin(matlab)','Fontname','华文中宋','FontSize',20)
   title('y=sin(matlab)的图形','Fontsize',20,'Fontname','宋体')
   xlabel('X轴','Fontsize',20,'Fontname','宋体')
   ylabel('y轴','Fontsize',20,'Fontname','宋体')
   ```

   <img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\plot1.png" style="zoom:75%;" />

4. fplot(@(x)  f(x),[xmin,xmax],'属性名'，属性值（依情况加）);

   text\label\title属性设置格式；

   ```matlab
   fplot(@(matlab) sin(matlab),[-10,30],'--*b','linewidth',1.8)
   text(3.6,0,'y=sinx','Fontname','华文中宋','FontSize',20)
   title('y=sin(matlab)的图形','Fontsize',20,'Fontname','宋体')
   xlabel('X轴','Fontsize',20,'Fontname','宋体')
   ylabel('y轴','Fontsize',20,'Fontname','宋体')
   ```

   <img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\fplot2.png" style="zoom:48%;" />

   

5. sinx：泰勒级数

   ```matlab
   clc
   x=0:0.03:(2*pi);
   y=sin(x);
   plot(x,y,'*k','LineWidth',0.8)
   text(3.3,2.3,'y=sinx','FontSize',12,'FontName','微软雅黑')
   xlabel('x轴','FontName','幼圆','FontSize',20)
   ylabel('y轴','FontSize',20)
   title('y=sinx的图形','FontSize',20)
   hold on   %保持图形
   y3=x-(x.^3)/6+(x.^5)/120-(x.^7)/5040;
   plot(x,y3,'ob','LineWidth',1.6)
   text(2.1,-13,'y=x-x^3/6+x^5/120-x^7/5040','FontSize',12,'FontName','微软雅黑')
   legend('sinx','7次泰勒多项式','Location','SouthWest')
   ```

   <img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\taylorsinx.png" style="zoom:75%;" />

   ```matlab
   clc
   x=0:0.05:(2*pi);
   y=cos(x);
   plot(x,y,'--ok','LineWidth',0.0008)
   text(3.3,3,'y=cosx','FontSize',20,'FontName','黑体')
   %3.3,0wa hanshu no biaoda place
   xlabel('x轴','FontName','黑体','FontSize',25)
   ylabel('y轴','FontName','黑体','FontSize',25)
   title('y=cosx的图形和他的6次泰勒展开图','FontSize',25)
   
   hold on
   taler=1-1/2*x.^2+1/24*x.^4-1/720*x.^6
   plot(x,taler,'--*k','LineWidth',0.0008)
   text(1,-10,'6次泰勒展开图','FontSize',20,'FontName','黑体')
   legend('cos(x)','1-1/2*x^2+1/24*x^4-1/720*x^6','Location','SouthWest')
   
   ```

   <img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\taylor.png" style="zoom:75%;" />

6. ezplot();

   ```matlab
    %函数绘图
           f = 'sin(2*x)';
           ezplot(f, [0, 2*pi]);  % 绘制f并规定横坐标范围，也有[xmin, xmax, ymin, ymax]
           x = '2*cos(t)';
           y = '4*sin(t)';
           ezplot(x, y);  % 绘制x(t),y(t)在[0, 2*pi]图像, 也可以在最后用[tmin, tmax]规定t的范围
   ```

   

三维绘图

1. plot3();三维曲线；

2. mesh();自动着色网格曲面；

   1.meshc()在mesh()的基础上，在xoy底面上增添等高线；

   2.meshz()在mesh()的基础上再绘出边界面；

3. surf();自动着色连续曲面；

   1.surfc();在xoy底面上增添等高线；

   2.surfz();再绘出边界面；

4. [x,y,z]=peaks(number)有波峰和波谷的函数；

   ```matlab
   %三维曲线曲面绘制
       %三维曲线
           x = 0:0.1:2*pi;
           y = sin(x); z = cos(x);
           plot3(x, y, z, 'b-*');
       %三维曲面
           %三维网格
           x = -5:0.1:5;  % 规定了x轴采样点，也规定了x轴范围
           y = -4:0.1:4;  % 规定了y轴采样点，也规定了y轴范围
           [X, Y] = meshgrid(x, y);  % 得到了xoy面网格点
           Z = X.^2+Y.^2;
           mesh(X, Y, Z)  % XY是meshgrid得到的网格点，Z是网格顶点，c是用色矩阵可省略
           %三维表面图
               x = -5:0.1:5;  
               y = -4:0.1:4;
               [X, Y] = meshgrid(x, y);
               Z = X.^2+Y.^2;  % 以上部分同上
               surf(X, Y, Z)  % 与上一个类似
   ```

   ```matlab
   %e.g
   [x,y]=meshgrid(-8:0.5:8);
   z=sin(sqrt(x.^2+y.^2))./sqrt(x.^2+y.^2+eps);
   subplot(2,2,1);
   mesh(x,y,z);
   title('mesh(x,y,z)')
   subplot(2,2,2);
   meshc(x,y,z);
   title('meshc(x,y,z)')
   subplot(2,2,3);
   meshz(x,y,z)
   title('meshz(x,y,z)')
   subplot(2,2,4);
   surf(x,y,z);
   title('surf(x,y,z)')
   ```

   <img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\meshattempt.png" style="zoom:75%;" />

   [^mesh]: 上述代码图

   ```matlab
   [x,y]=meshgrid(0:0.25:4*pi);
   z=sin(x+sin(y))-x/10;
   mesh(x,y,z);
   axis([0 4*pi 0 4*pi -2.5 1]);
   ```

   <img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\meshgridattempt.png" style="zoom:75%;" />

   [^meshgrid]: 上述代码图

   

图形标注

```matlab
axis([-1*pi, 3*pi, -1.5, 1.5]);  % 规定横纵坐标范围
title('a title');  % 图像标题
xlabel('this is x');  % x轴标记，同理还有ylabel，zlabel
legend('hahaha', 'location', 'best'); %str的顺序与绘图顺序一致; 'best'指图例位置最佳化，还有其他位置
hold on;  % 在原有窗口y1曲线上增加绘制下一个图形
subplot(2, 2, 1);  % 分割成2x2区域，在第一块区域绘制下一个图形
hold off;
subplot(2, 2, 2);  % 分割方法相同，区域改变
gtext('string1','string2','.....');%text的坐标在图形绘制完成后用鼠标交互选定；
zoom on/off; %缩放
grid on/minor/off; %增减网格线
box on/off %坐标刻度对面的刻度
subplot(m,n,p) %分割绘制
            subplot(2, 2, 1);  % 分割成2x2区域，在第一块区域绘制下一个图形
            plot(x, y1);  % y1被绘制在4块区域的第一块
            subplot(2, 2, 2);  % 分割方法相同，区域改变
            plot(x, y2);  % y2在第二块区域

```

```matlab
x=-pi:0.01*pi:pi;
y=sin(2*x);
y2=cos(x);
plot(x,y,x,y2,'bd');
xlabel('x轴(-\pi<x<\pi)');
ylabel('y轴');
title('sin2x的图形')
legend('sin','cos','Best')
gtext('sin(2x)')
gtext('cos(x)')
```

[^]: gtext（）的使用示例

```matlab
%subplotattemption
x=-2:0.02:2;
subplot(2,3,[1 4])
plot(x,cos(x));
subplot(2,3,[2 3])
plot(x,sin(x));
subplot(2,3,5)
plot(x,exp(x));
subplot(2,3,6)
plot(x,log(x)+3);
```

[^]: subplot()使用示例

<img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\subplotattemption.png" style="zoom:75%;" />

二维统计图

```matlab
%柱状图
        bar(x, y, width, '参数');  % x横坐标向量，m个元素; y为向量时，每个x画一竖条共m条，矩阵mxn时，每个x画n条;
                                   % width宽度默认0.8，超过1各条会重叠;
                                   % 参数有grouped分组式，stacked堆栈式; 默认grouped
                                   % bar垂直柱状图,barh水平柱状图,bar3三维柱状图,barh3水平三维柱状图(三维多一个参数detached, 且为默认)
    %饼形图
        pie(x, explode, 'lable');  % x为向量显示每个元素占总和百分比, 为矩阵显示每个元素占所有总和百分比
                                   % explode向量与x同长度，为1表示该元素被分离突出显示，默认全0不分离
                                   % pie3绘制三维饼图
    %直方图
        hist(y, n);  % y为向量，把横坐标分为n段绘制
        hist(y, x);  % x为向量，用于指定每段中间值, 若取N = hist(y, x), N为每段元素个数
    %离散数据图
        stairs(x, y, 'b-o');  % 阶梯图，参数同plot
        stem(x, y, 'fill');  % 火柴杆图，参数fill是填充火柴杆，或定义线形
        candle(HI, LO, CL, OP);  % 蜡烛图:HI为最高价格向量,LO为最低价格向量,CL为收盘价格向量,OP为开盘价格向量
    %向量图
        compass(u, v, 'b-o');  % 罗盘图横坐标u纵坐标v
        compass(Z, 'b-o');  % 罗盘图复向量Z
        feather(u, v, 'b-o');  % 羽毛图横坐标u纵坐标v
        feather(Z, 'b-o');  % 羽毛图复向量Z
        quiver(x, y, u, v);  % 以(x, y)为起点(u, v)为终点向量场图
    %极坐标图
        % polar(theta, rho, 'b-o');  % 极角theta, 半径rho
        theta = -pi:0.01:pi;
        rho = sin(theta);
        polar(theta, rho, 'b')
    %对数坐标图
        semilogx(x1, y1, 'b-o');  % 把x轴对数刻度表示, semilogy是y轴对数刻度表示，loglog是两个坐标都用对数表示
     %双纵坐标
        plotyy(x1, y1, x2, y2, 'fun1', 'fun2');  % fun规定了两条条线的绘制方式，如plot,semilogx,semilogy,loglog,stem等
```

```matlab
x=0:pi/10:2*pi;
y=2*sin(x);
subplot(2,2,1);bar(x,y,'g');
title('bar(x,y,''g'')');axis([0,7,-2,2]);
subplot(2,2,2);stairs(x,y,'b');
title('stairs(x,y,''b'')');axis([0,7,-2,2]);
subplot(2,2,3);stem(x,y,'k');
title('stem(x,y,''k'')');axis([0,7,-2,2]);
subplot(2,2,4);fill(x,y,'y');
title('fill(x,y,''y'')');axis([0,7,-2,2]);
```

<img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\barstairs.png" style="zoom:75%;" />

```matlab
%极坐标
t=0:pi/50:2*pi;
r=sin(t).*cos(t);
polar(t,r,'-*');
```

<img src="C:\Users\19284\Desktop\Workspace\MatlabPlace\Course\pie.png" style="zoom:75%;" />

### **MATLAB数据统计处理**



1. **max ——** **各列最大值**

   **1.** **最大值和最小值**

   **MATLAB****提供的求数据序列的最大值和最小值的**

   **函数分别为****max**和**min**，两个函数的调用格式和**

   **操作过程类似。**

   **1**.求向量的最大值和最小值

   **求一个向量****X**的最大值的函数有两种调用格式，**

   **分别是：**

   (1)**y=max(X)**：返回向量**X**的最大值存入**y**，

   (2)**如果**X**中包含复数元素，则按模取最大值。**

   **(3) [y,I]=max(X)**：返回向量**X**的最大值存入**y**，最大值的序号存入**I**，如果**X**中包含复数元素，则按模取最大值。**,**求向量**X**的最小值的函数是**min(X)**，用法和**max(X)**完全相同。

   ```matlab
   x=[-43,72,9,16,23,47];
   y=max(x)             %求向量x中的最大值
   [y,l]=max(x)         %求向量x中的最大值及其该元素的位置
   ```

   **2.求矩阵的最大值和最小值**

   **求矩阵**A**的最大值的函数有**3**种调用格式，分别是：**

   (1) max(A)：返回一个行向量，向量的第i个元素是矩阵A的第i列上的最大值。

   (2) [Y,U]=max(A)：返回行向量Y和U，Y向量记录A的每列的最大值，U向量记录每列最大值的行号。

   (3) max(A,[],dim)：dim取1或2。dim取1时，该函数和max(A)完全相同；dim取2时，该函数返回一个列向量，其第i个元素是A矩阵的第i行上的最大值。求最小值的函数是min，其用法和max完全相同。

   **3．两个向量或矩阵对应元素的比较**
   **函数max和min还能对两个同型的向量或矩阵进行比较，调用格式为：**
   (1) U=max(A,B)：A,B是两个同型的向量或矩阵，结果U是与A,B同型的向量或矩阵，U的每个元素等于A,B对应元素的较大者。
   (2) U=max(A,n)：n是一个标量，结果U是与A同型的向量或矩阵，U的每个元素等于A对应元素和n中的较大者。min函数的用法和max完全相同。

   ------

   `M = max(A)` 返回数组的最大元素。

   - 如果 `A` 是向量，则 `max(A)` 返回 `A` 的最大值。
   - 如果 `A` 为矩阵，则 `max(A)` 是包含 `A` 的每一列的最大值的行向量。
   - 如果 `A` 是多维数组，则 `max(A)` 沿大小不等于 `1` 的 `A` 的第一个维度计算，并将这些元素视为向量。此维度的大小将变为 `1`，而所有其他维度的大小保持不变。如果 `A` 是第一个维度长度为零的空数组，则 `max(A)` 返回与 `A` 大小相同的空数组。

   

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/max.html#bupr490)

   `M = max(A,[],dim)` 返回维度 `dim` 上的最大元素。例如，如果 `A` 为矩阵，则 `max(A,[],2)` 是包含每一行的最大值的列向量。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/max.html#buql2dq)

   `M = max(A,[],nanflag)` 指定在计算中包括还是忽略 `NaN` 值。例如，`max(A,[],'includenan')` 包括 `A` 中的所有 `NaN` 值，而 `max(A,[],'omitnan')` 则会忽略这些值。

   `M = max(A,[],dim,nanflag)` 还指定使用 `nanflag` 选项时的运算维度。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/max.html#bupr8_p)

   `[M,I] = max(___)` 在上述语法基础上，还返回 `A` 中最大值在运算维度上的对应索引。

   

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/max.html#mw_aa367634-21ae-4688-98d9-365f8c5f1d05)

   `M = max(A,[],'all')` 查找 `A` 的所有元素的最大值。此语法适用于 MATLAB® R2018b 及更高版本。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/max.html#mw_aa367634-21ae-4688-98d9-365f8c5f1d05)

   `M = max(A,[],vecdim)` 计算向量 `vecdim` 所指定的维度上的最大值。例如，如果 `A` 是矩阵，则 `max(A,[],[1 2])` 计算 `A` 中所有元素的最大值，因为矩阵的每个元素都包含在由维度 1 和 2 定义的数组切片中。

   `M = max(A,[],'all',nanflag)` 计算在使用 `nanflag` 选项时 `A` 的所有元素的最大值。

   `M = max(A,[],vecdim,nanflag)` 指定在使用 `nanflag` 选项时要运算的多个维度。

   

   `[M,I] = max(A,[],'all',___)` 返回在指定 `'all'` 时 `A` 中最大值在 `A` 中的对应线性索引。

   

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/max.html#mw_f4dadb60-ee1a-4996-a37b-2fdd20904ffb)

   `[M,I] = max(A,[],___,'linear')` 返回 `A` 中最大值在 `A` 中的对应线性索引。

   

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/max.html#bupr915)

   `C = max(A,B)` 返回从 `A` 或 `B` 中提取的最大元素的数组。

   `C = max(A,B,nanflag)` 还指定如何处理 `NaN` 值。

   

   `___ = max(___,'ComparisonMethod',method)` 为上述任何语法指定如何比较元素，此项为可选项。例如，对于向量 `A = [-1 2 -9]`，语法 `max(A,[],'ComparisonMethod','abs')` 根据绝对值比较 `A` 的元素并返回 `-9`。

   ------

   

2. **mean ——** **各列平均值**

   **平均值和中值**
   **求数据序列平均值的函数是mean，求数据序列中值的函数是median。两个函数的调用格式为：**

   ​		mean(X)：返回向量X的算术平均值。
   ​		median(X)：返回向量X的中值。
   ​		mean(A)：返回一个行向量，其第i个元素是A的第i列的算术平均值。
   ​		median(A)：返回一个行向量，其第i个元素是A的第i列的中值。
   ​		mean(A,dim)：当dim为1时，该函数等同于mean(A)；当dim为2时，返回一个列向量，其第i个元素是A的第i行的算术平均值。
   ​		median(A,dim)：当dim为1时，该函数等同于median(A)；当dim为2时，返回一个列向量，其第i个元素是A的第i行的中值。

   

   **累加和与累乘积**
   **在MATLAB中，使用cumsum和cumprod函数能方便地求得向量和矩阵元素的累加和与累乘积向量，函数的调用格式为：**

   ​		cumsum(X)：返回向量X累加和向量。
   ​		cumprod(X)：返回向量X累乘积向量。
   ​		cumsum(A)：返回一个矩阵，其第i列是A的第i列的累加和向量。
   ​		cumprod(A)：返回一个矩阵，其第i列是A的第i列的累乘积向量。

   ​		cumsum(A,dim)：当dim为1时，该函数等同于cumsum(A)；当dim为2时，返回一个矩阵，其第i行是A的第i行的累加和向量。
   ​		cumprod(A,dim)：当dim为1时，该函数等同于cumprod(A)；当dim为2时，返回一个向量，其第i行是A的第i行的累乘积向量。

3. **sum ——** **各列求和**

   **求和与求积**
   **数据序列求和与求积的函数是sum和prod，其使**
   **用方法类似。设X是一个向量，A是一个矩阵，函**
   **数的调用格式为：**
   **sum(X)：返回向量X各元素的和。**
   **prod(X)：返回向量X各元素的乘积。**
   **sum(A)：返回一个行向量，其第i个元素是A的第i列的元素和。**

4. **std ——** **各列标准差**

   **语法**

   ```matlab
   S = std(A)
   S = std(A,w)
   S = std(A,w,"all")
   S = std(A,w,dim)
   S = std(A,w,vecdim)
   S = std(___,nanflag)
   [S,M] = std(___)
   ```

   **说明**

   `S = std(A)` 返回 `A` 沿大小不等于 1 的第一个数组维度的元素的标准差。默认情况下，标准差按 `N-1` 实现归一化，其中 `N` 是观测值数量。

   - 如果 `A` 是观测值的向量，则 `S` 是标量。
   - 如果 `A` 是一个列为随机变量且行为观测值的矩阵，则 `S` 是一个包含与每列对应的标准差的行向量。
   - 如果 `A` 是多维数组，则 `std(A)` 沿大小不等于 1 的第一个数组维度计算，并将这些元素视为向量。此维度中 `S` 的大小变为 `1`，而所有其他维度的大小与 `A` 相同。
   - 如果 `A` 是标量，则 `S` 为 `0`。
   - 如果 `A` 是一个 `0`×`0` 的空数组，则 `S` 为 `NaN`。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/std.html#bune5v7-8)

   `S = std(A,w)` 指定加权方案。当 `w = 0`（默认值）时，标准差按 `N-1` 实现归一化，其中 `N` 是观测值数量。当 `w = 1` 时，标准差按观测值数量进行归一化。`w` 也可以是包含非负元素的权重向量。在这种情况下，`w` 的长度必须等于 `std` 将作用于的维度的长度。

   当 `w` 为 0 或 1 时，`S = std(A,w,"all")` 计算 `A` 的所有元素的标准差。此语法适用于 MATLAB® R2018b 及更高版本。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/std.html#bune5v9-9)

   `S = std(A,w,dim)` 返回沿维度 `dim` 的标准差。要维持默认归一化并指定操作的维度，请在第二个参数中设置 `w = 0`。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/std.html#mw_06ef61f4-c950-4f98-9b72-e858d42c3e84)

   当 `w` 为 0 或 1 时，`S = std(A,w,vecdim)` 计算向量 `vecdim` 中指定维度的标准差。例如，如果 `A` 是矩阵，则 `std(A,0,[1 2])` 计算 `A` 中所有元素的标准差，因为矩阵的每个元素包含在由维度 1 和 2 定义的数组切片中。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/std.html#buqntrm)

   `S = std(___,nanflag)` 指定在上述任意语法的计算中包括还是忽略 `NaN` 值。例如，`std(A,"includenan")` 包括 `A` 中的所有 `NaN` 值，而 `std(A,"omitnan")` 则会忽略这些值。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/std.html#mw_5a3bc4f3-5982-4046-80af-1a1f88279d45)

   `[S,M] = std(___)` 还返回 `A` 中用于计算标准差的元素的均值。如果 `S` 是[加权标准差](https://www.mathworks.com/help/releases/R2022b/matlab/ref/std.html#mw_a330308a-5529-4116-9970-575fbfc6e40d)，则 `M` 是[加权均值](https://www.mathworks.com/help/releases/R2022b/matlab/ref/std.html#mw_fc3866f5-bc20-4c2c-b168-95c6de1a691f)。此语法适用于 MATLAB R2022a 及更高版本。

5. **var ——** **各列方差**

   **语法**

   ```
   V = var(A)
   V = var(A,w)
   V = var(A,w,"all")
   V = var(A,w,dim)
   V = var(A,w,vecdim)
   V = var(___,nanflag)
   [V,M] = var(___)
   ```

   **说明**

   `V = var(A)` 返回 `A` 中沿大小不等于 1 的第一个数组维度的元素的方差。默认情况下，方差按 `N-1` 实现归一化，其中 `N` 是观测值数量

   - 如果 `A` 是观测值的向量，则 `V` 是标量。
   - 如果 `A` 是一个列为随机变量且行为观测值的矩阵，则 `V` 是一个包含与每列对应的方差的行向量。
   - 如果 `A` 是多维数组，则 `var(A)` 沿大小不等于 1 的第一个数组维度计算，并将这些元素视为向量。此维度中 `V` 的大小变为 `1`，而所有其他维度的大小与 `A` 相同。
   - 如果 `A` 是标量，则 `V` 为 `0`。
   - 如果 `A` 是一个 `0`×`0` 的空数组，则 `V` 为 `NaN`。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/var.html#bum85_b)

   `V = var(A,w)` 指定加权方案。当 `w = 0`（默认值）时，方差按 `N-1` 实现归一化，其中 `N` 是观测值数量。如果 `w = 1`，则方差按观测值数量实现归一化。`w` 也可以是包含非负元素的权重向量。在这种情况下，`w` 的长度必须等于 `var` 将作用于的维度的长度。

   当 `w` 为 0 或 1 时，`V = var(A,w,"all")` 计算 `A` 的所有元素的方差。此语法适用于 MATLAB® R2018b 及更高版本。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/var.html#bum85ue)

   `V = var(A,w,dim)` 返回沿维度 `dim` 的方差。要维持默认归一化并指定操作的维度，请在第二个参数中设置 `w = 0`。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/var.html#mw_fc1ec600-0ff8-4763-9785-ba8e8d480f84)

   当 `w` 为 0 或 1 时，`V = var(A,w,vecdim)` 计算向量 `vecdim` 中指定维度的方差。例如，如果 `A` 是矩阵，则 `var(A,0,[1 2])` 计算 `A` 中所有元素的方差，因为矩阵的每个元素包含在由维度 1 和 2 定义的数组切片中。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/var.html#buqnlcy)

   `V = var(___,nanflag)` 指定在上述任意语法的计算中包括还是忽略 `NaN` 值。例如，`var(A,"includenan")` 包括 `A` 中的所有 `NaN` 值，而 `var(A,"omitnan")` 则会忽略这些值。

   [示例](https://www.mathworks.com/help/releases/R2022b/matlab/ref/var.html#mw_9c0feb0a-5ace-4287-97e9-ac9c1f8520aa)

   `[V,M] = var(___)` 还返回 `A` 中用于计算方差的元素的均值。如果 `V` 是[加权方差](https://www.mathworks.com/help/releases/R2022b/matlab/ref/var.html#mw_53545f32-0c1e-41a1-8fc7-97b34d926fb2)，则 `M` 是[加权均值](https://www.mathworks.com/help/releases/R2022b/matlab/ref/var.html#mw_59066162-9261-4dae-b5c3-e0b8319a4084)。此语法适用于 MATLAB R2022a 及更高版本。

6. **sort ——** **各列递增排序**

   语法
   B = sort(A)
   B = sort(A,dim)
   B = sort(___,direction)
   B = sort(___,Name,Value)
   [B,I] = sort(___)
   说明
   B = sort(A) 按升序对 A 的元素进行排序。

   如果 A 是向量，则 sort(A) 对向量元素进行排序。

   如果 A 是矩阵，则 sort(A) 会将 A 的列视为向量并对每列进行排序。

   如果 A 是多维数组，则 sort(A) 沿大小不等于 1 的第一个数组维度计算，并将这些元素视为向量。
   B = sort(A,dim) 返回 A 沿维度 dim 的排序元素。例如，如果 A 是一个矩阵，则 sort(A,2) 对每行中的元素进行排序。
   B = sort(___,direction) 使用上述任何语法返回按 direction 指定的顺序显示的 A 的有序元素。'ascend' 表示升序（默认值），'descend' 表示降序。


   B = sort(___,Name,Value) 指定用于排序的其他参数。例如，sort(A,'ComparisonMethod','abs') 按模对 A 的元素进行排序。


   [B,I] = sort(___) 还会为上述任意语法返回一个索引向量的集合。I 的大小与 A 的大小相同，它描述了 A 的元素沿已排序的维度在 B 中的排列情况。例如，如果 A 是一个向量，则 B = A(I)。

   

   按升序对向量排序
   创建一个行向量，并按升序对其元素排序。

   A = [9 0 -7 5 3 8 -10 4 2];
   B = sort(A)
   B = 1×9

      -10    -7     0     2     3     4     5     8     9

   



   按升序对矩阵行排序
   创建一个矩阵，并按升序对每一行排序。

   A = [3 6 5; 7 -2 4; 1 0 -9]
   A = 3×3

        3     6     5
        7    -2     4
        1     0    -9

   B = sort(A,2)
   B = 3×3

        3     5     6
       -2     4     7
       -9     0     1

   按降序对矩阵列排序
   创建一个矩阵，并按升序对每一列排序。

   A = [10 -12 4 8; 6 -9 8 0; 2 3 11 -2; 1 1 9 3]
   A = 4×4

       10   -12     4     8
        6    -9     8     0
        2     3    11    -2
        1     1     9     3

   B = sort(A,'descend')
   B = 4×4

       10     3    11     8
        6     1     9     3
        2    -9     8     0
        1   -12     4    -2

   对字符串数组排序
   从 R2017a 开始，您可以使用双引号创建字符串数组，并使用 sort 函数对它们进行排序。根据 Unicode® 字典顺序对字符串数组的每一列中的字符串进行排序。

   A = ["Santos","Burns"; ...
        "Jones","Morita"; ...
        "Petrov","Adams"];
   B = sort(A)
   B = 3x2 string
       "Jones"     "Adams" 
       "Petrov"    "Burns" 
       "Santos"    "Morita"

   对每一行中的字符串进行排序。

   B = sort(A,2)
   B = 3x2 string
       "Burns"    "Santos"
       "Jones"    "Morita"
       "Adams"    "Petrov"

   对 datetime 数组排序并进行索引
   打开实时脚本
   创建一个由 datetime 值构成的数组，然后按升序排序，也就是从最早到最近的日历日期排序。

   ds = {'2012-12-22';'2063-04-05';'1992-01-12'};
   A = datetime(ds,'Format','yyyy-MM-dd')
   A = 3x1 datetime
      2012-12-22
      2063-04-05
      1992-01-12

   [B,I] = sort(A)
   B = 3x1 datetime
      1992-01-12
      2012-12-22
      2063-04-05

   I = 3×1

        3
        1
        2

   B 列出排序后的日期以及包含 A 的相应索引的 I。

   使用索引数组 I 从原始数组直接访问排序后的元素。

   A(I)
   ans = 3x1 datetime
      1992-01-12
      2012-12-22
      2063-04-05

   按相同顺序对向量进行排序
   打开实时脚本
   创建两个在对应元素中包含相关数据的行向量。

   X = [3 6 4 2 1 5];
   Y = ["yellow" "purple" "green" "orange" "red" "blue"];
   首先对向量 X 进行排序，然后按照与 X 相同的顺序对向量 Y 进行排序。

   [Xsorted,I] = sort(X)
   Xsorted = 1×6

        1     2     3     4     5     6

   I = 1×6

        5     4     1     3     6     2

   Ysorted = Y(I)
   Ysorted = 1x6 string
       "red"    "orange"    "yellow"    "green"    "blue"    "purple"

   对三维数组排序
   打开实时脚本
   创建一个 2×2×2 数组，并沿第三维度按升序对元素进行排序。

   A(:,:,1) = [2 3; 1 6];
   A(:,:,2) = [-1 9; 0 12];
   A
   A = 
   A(:,:,1) =

        2     3
        1     6


   A(:,:,2) =

       -1     9
        0    12

   B = sort(A,3)
   B = 
   B(:,:,1) =

       -1     3
        0     6


   B(:,:,2) =

        2     9
        1    12

   使用 A(:)（A 的列表示形式）对 A 的所有元素进行排序。

   B = sort(A(:))
   B = 8×1

       -1
        0
        1
        2
        3
        6
        9
       12

   复数向量
   打开实时脚本
   按复数向量元素的实部对元素进行排序。默认情况下，sort 函数按复数值的幅值对其进行排序，再使用相位角对幅值相同的值继续排序。将 'ComparisonMethod' 的值指定为 'real'，以按复数值的实部对其排序。对于具有相等实部的元素，sort 将基于其虚部进行排序。

   A = [1+2i 3+1i 1i 0 -1i];
   B = sort(A,'ComparisonMethod','real')
   B = 1×5 complex

      0.0000 - 1.0000i   0.0000 + 0.0000i   0.0000 + 1.0000i   1.0000 + 2.0000i   3.0000 + 1.0000i

   输入参数
   全部折叠
   A — 输入数组
   向量 | 矩阵 | 多维数组
   输入数组，指定为向量、矩阵或多维数组。

   如果 A 是标量，则 sort(A) 返回 A。

   如果 A 是复数，默认情况下，sort 会按模对元素进行排序。如果有多个元素具有相等的模，则按区间 (−π, π] 上的相位角对这些元素进行排序。

   如果 A 是字符向量元胞数组或字符串数组，则 sort(A) 按照 UTF-16 字符编码方案的代码顺序对元素进行排序。排序区分大小写。有关对字符和字符串数组进行排序的详细信息，请参阅字符和字符串数组的排序顺序。

   如果 A 是字符串数组，则 sort 将对数组元素重新排序，但不会对字符串中的字符重新排序。

   如果 A 是分类数组，则排序顺序基于 categories(A) 返回的类别顺序。

   数据类型： double | single | int8 | int16 | int32 | int64 | uint8 | uint16 | uint32 | uint64 | logical | char | string | cell | categorical | datetime | duration
   复数支持： 是

   dim — 沿其运算的维度
   正整数标量
   沿其运算的维度，指定为正整数标量。如果未指定值，则默认值是大小不等于 1 的第一个数组维度。

   假定有矩阵 A。sort(A,1) 对 A 的列元素进行排序。

   

   sort(A,2) 对 A 的行元素进行排序。

   

   如果 dim 大于 ndims(A)，sort 将返回 A。当 A 是元胞数组时，不支持 dim，即，sort 仅沿其大小不等于 1 的第一个数组维度进行运算。

   数据类型： double | single | int8 | int16 | int32 | int64 | uint8 | uint16 | uint32 | uint64

   direction — 排序方向
   'ascend' （默认） | 'descend'
   排序方向，指定为 'ascend' 或 'descend'。当 A 是元胞数组时，不支持 direction，即，sort 仅按升序排序。

   名称-值参数
   将可选的参数对组指定为 Name1=Value1,...,NameN=ValueN，其中 Name 是参数名称，Value 是对应的值。名称-值参数必须出现在其他参数之后，但参数对组的顺序无关紧要。

   在 R2021a 之前，使用逗号分隔每个名称和值，并用引号将 Name 引起来。

   示例： sort(A,'MissingPlacement','last')

   MissingPlacement — 缺失值的位置
   'auto' （默认） | 'first' | 'last'
   缺失值（NaN、NaT、<undefined> 和 missing）的位置，指定为逗号分隔的对组，包含 'MissingPlacement' 和下列项之一：

   'auto' - 缺失的元素放在最后（对于升序排序）或放在最前面（对于降序排序）。

   'first' - 缺失的元素放在最前面。

   'last' - 缺失的元素放在最后。

   ComparisonMethod — 元素比较方法
   'auto' （默认） | 'real' | 'abs'
   元素比较方法，指定为逗号分隔的对组，包含 'ComparisonMethod' 和下列项之一：

   'auto' - 当 A 为实数时，按 real(A) 对 A 进行排序；当 A 为复数时，按 abs(A) 进行排序。

   'real' - 当 A 为实数或复数时，按 real(A) 对 A 进行排序。如果 A 包含具有相等实部的元素，则使用 imag(A) 进行排序。

   'abs' - 当 A 为实数或复数时，按 abs(A) 对 A 进行排序。如果 A 包含具有相等模的元素，则使用区间 (-π,π] 中的 angle(A) 进行排序。

   输出参数
   全部折叠
   B — 已排序数组
   向量 | 矩阵 | 多维数组
   已排序数组，以向量、矩阵或多维数组的形式返回。B 的大小和类型均与 A 相同。

   数据类型： double | single | int8 | int16 | int32 | int64 | uint8 | uint16 | uint32 | uint64 | logical | char | string | cell | categorical | datetime | duration

   I — 排序索引
   向量 | 矩阵 | 多维数组
   排序索引，以向量、矩阵或多维数组的形式返回。I 的大小与 A 相同。这些索引向量沿 sort 作用于的同一维度指定方向。例如，如果 A 是一个 2×3 矩阵，则 [B,I] = sort(A,2) 对 A 中的每行元素进行排序。输出 I 是 1×3 行索引向量的集合，用于描述 A 中每行元素的重新排列。

   sort 函数使用一种稳定的排序算法。因此，当输入包含重复值时，无论排序方向如何，排序索引都会保留输入的原始顺序。例如，如果 A = [1 2 1 2]，则 [Ba,Ia] = sort(A,'ascend') 返回排序索引 Ia = [1 3 2 4]，[Bd,Id] = sort(A,'descend') 返回排序索引 Id = [2 4 1 3]。

