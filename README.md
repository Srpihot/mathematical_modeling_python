# 数学建模导论：基于python语言（2022秋）

#### 介绍
本实验是《数学建模导论：基于Python语言》的配套实验内容，马马将在这次实验中带大家一步步从小白到竞赛实战，让数学建模不再是一项可怕的竞赛。

![输入图片说明](%E5%B0%81%E9%9D%A2.png)

## Python环境的安装
在开始实验之前，大家可以先去anaconda官网安装python大礼包：www.anaconda.com

当然如果想安装原生Python也可以直接上python官网：www.python.org

但是Python如果是原生状态下的话里面啥都没有，所以如果碰到了库不存在的话，将命令行打开，键入pip install xxxx 能够解决大多数问题。
不过我想应该没有什么同学愿意为了节约一点表面上的空间去安装原生Python吧，不会吧不会吧？一如你去集贸的呷哺呷哺吃火锅你难道只会点一个锅底不点菜的吗？
anaconda实际上就是提供锅底的同时还会提供你毛肚、鸭血、鸭肠等。所以，为什么不去安装一个anaconda呢？

如果觉得编程环境不好用的话可以加装一个VSCode或者Pycharm，但是华科的学生装正版Pycharm可能还有一点点问题因为学校邮箱出了点事。

## 实验一：Python的基础语法

本次实验的基本目的是熟悉Python的基础语法。首先我们可以打开命令行（windows用户可以在cortana中键入cmd，会弹出命令提示符），然后键入python回车就可以切换到python命令行模式了。这一模式下我们可以试试它的hello world和C的hello world有多大差距：

![输入图片说明](image.png)

可以看到Python的hello world仅需要一行。但是在更多情况下，我们和C一样会在文本文件中写程序然后运行。

这一次实验我们的目的就是熟悉基本的控制流和集合等内容。

### 1. 熟悉Python的输入输出操作，并实现对一个输入序列的冒泡排序
现在对计算机1915班的前五名同学模电成绩想排个序，要求：

- 输入成绩个数为5，用input()函数实现
- 将输入的五个数保存成列表，并进行冒泡排序
- 不允许使用list自带的sort()方法，必须自己设置冒泡排序
- 将五个数排序后的结果排成一行输出到控制台

### 2. 分支语句判断
现在马马考完了模电，老师想在控制台里面根据我的成绩评价我的学习水平，要求：

- 控制台输入马马的模电分数
- 如果分数高于95，输出“马马+是卷王”；如果在80-95之间，输出“马马+牛牛”；如果在60-80之间，输出“马马+摆烂了”；如果低于60，输出“马马+老师，你不会又得重修了吧”
- 异常处理：如果分数是一个小于零的数或者输入的根本就不是数字如何handle？

### 3. 循环语句
老师手里有一份光之国模电考试的成绩单，保存成了txt文件，每一行分别是班里同学的名字和分数。现在需要：

- 利用open和read函数循环读取每一行，将结果保存到字典中
- 首先输出杰克、雷欧和贝利亚的模电成绩，如果检索不到人名需要报警“找不到这位同学”
- 然后循环遍历这个字典，对于每个同学的模电成绩按照第二关中的操作输出这位同学的状态

### 4. 函数编写
试着将第三关的语句改写为一个函数，函数参数为成绩单文件的路径与文件名。


## 实验二：Python规划求解

本次实验的目的是为了熟悉基本的规划问题求解策略。求解规划问题需要用到numpy和scipy库，这两个库我建议先去熟悉一些基本操作会比较好。

这里我附上numpy和scipy的官方文档：

numpy官方文档：https://numpy.org/

scipy官方文档：https://scipy.org/

主要的方法就在scipy.optimize库当中，包括minimize、linear_sum_assignment等方法。

### 1. 线性规划问题求解
求这样一个线性规划的最优解：

![image](https://user-images.githubusercontent.com/61874427/172415401-32d55e34-d877-4a70-8656-830339c75566.png)


### 2. 非线性规划问题求解
求这样一个非线性规划的最优解，要求使用scipy.optimize.minimize求解：

![image](https://user-images.githubusercontent.com/61874427/172414855-dc1b4e38-c59d-497f-b811-0606beb10136.png)


### 3. 指派问题求解
现在光之国的五位奥特曼与阿布索留特族的五个小金人开始了1v1的车轮战，如果你现在安排奥特兄弟与他们1v1的战斗，每一项代表一个奥解决一个小金人所需要的时间。只有在最短的时间内打败所有小金人才能救出尤莉安公主。请问对于给定的小金人ABCDE，应该按照怎样的战斗策略使得五场战斗的时间总和最短？

| 奥特曼 | A    | B    | C    | D    | E    |
| ------ | ---- | ---- | ---- | ---- | ---- |
| 佐菲   | 22   | 16   | 20   | 35   | 18   |
| 初代   | 20   | 12   | 35   | 40   | 26   |
| 赛文   | 11   | 19   | 15   | 17   | 21   |
| 杰克   | 25   | 30   | 21   | 37   | 40   |
| 艾斯   | 22   | 26   | 35   | 30   | 19   |

### 4. 综合建模
原题的链接附上：https://blog.csdn.net/OK_XIAOCHEN/article/details/124523838?utm_term=matlab%E4%B8%AD%E7%9A%84%E6%8C%87%E6%B4%BE%E9%97%AE%E9%A2%98&utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~sobaiduweb~default-0-124523838-null-null&spm=3001.4430

现在光之国开通了从M78星云（A）到L77星云（B）和U40（C）星云的宇宙航线，这些航线每天班次起飞与到达时间如下表。 设飞船在机场停留的损失费用大致与停留时间的平方成正比. 又每架飞船从降落到下班起飞至少需 2 小时准备时间， 试决定一个使停留费用损失为最小的分配飞行方案。

![image](https://user-images.githubusercontent.com/61874427/172405114-de0bd77a-416d-4836-913b-635d27573470.png)

到M78星云损失费用：

![img](https://img-blog.csdnimg.cn/7c421911268f43b1a17a5126430bd535.png)

到L77星云损失费用：

![image](https://img-blog.csdnimg.cn/7c421911268f43b1a17a5126430bd535.png)

到U40星云损失费用：

![image](https://img-blog.csdnimg.cn/68617b292cf34e79a0da7db521ccc6ca.png)

对于问题四，写出你的分析思路，建立的模型表达式，程序和求解结果。最终形成一个不超过两页A4纸的文档。没啥格式要求，你认为你将你的思路表达清楚就够了。

## 实验三：Python微分方程建模

本次实验的目的是对视频中讲到的微分方程模型进行进一步探究和补充。题目并不太多。

### 1. 计算微分方程
计算这样一个微分方程的符号解和数值解：y''-4y'+3y=x*exp(x)

### 2. 计算微分方程组
计算这样一个微分方程组的数值解：

![image](https://user-images.githubusercontent.com/61874427/173194058-6395aa4a-b501-4238-bd8c-a26d2aa83d71.png)

三个方程定义了三维空间中的各个坐标点上度速度矢量，其中ρ、σ、β为常数，不同的参数可以算出不同的轨迹：x(t)、y(t)、z(t)。当参数为某些值时，轨迹出现混沌现象。即最小的初值差别也会显著地影响运动轨迹。

### 3. 对SEIR模型的进一步探讨
为了巩固经济增长基础、保障国内国际双循环，中国政府已决定在全国进行 
全人群的新冠病毒疫苗接种，以建立最大规模的国民群体新冠免疫屏障。但目前多地爆发二次疫情，在二次疫情中流行了一种名为“奥密克戎”的病毒。这种病毒是普通COVID-19效果的9-11倍，能在14秒之内使人感染，传播速度极快。对于某一个城市而言，请考虑这样一些问题：

1. 目前疫苗对“奥密克戎”病毒并无免疫作用，现在考虑在没有对“奥密克戎”有效疫苗的情况下病毒的传播情况。
2. 若现在已经研制出针对“奥密克戎”的疫苗，并且接种以后就可以不被感染，讨论在这一情况下某个城市内“奥密克戎”的传播情况。
3. 事实上，疫苗并不能保证接种后不被感染，而是降低其感染后危重症的概率和死亡率，那么讨论在这一情况下病毒传播的效果。
4. 以任意一个城市为例，考虑采取怎样的步骤、需要多大成本、多长时间可完成群体免疫屏障的建立。

### 4. 捕食者模型的分析
在白垩纪时期潜伏在地底的怪兽双尾怪和古墩是一对捕食者和被捕食者关系。白垩纪的某一天，美菲拉斯星人的飞船队从太空带来了2000只双尾怪和3000只古墩来地球。假设双尾怪和古墩每年生育率为0.004和0.006，古墩会以双尾怪为食，试着分析
1. 设置不同的参数绘制古墩和双尾怪在1000年内的变化情况
2. 试着画出古墩和双尾怪变化的相轨图
3. 1972年的一天在东京K地区，潜伏在地底的一只古墩和双尾怪复活了并打败了杰克奥特曼。地球防卫军准备开发一枚浓缩核弹将东京K地区炸毁。这枚核弹的爆炸威力是100万吨TNT当量，假设采用U235作为核弹原料，请查找资料并分析在引爆核弹以后半径多少以外是安全的？并给出半径与放射强度之间的数学建模与仿真。

![image](https://user-images.githubusercontent.com/61874427/173193648-72174f07-39d0-4d52-b068-013b7131ef5e.png)



## 实验四：鸢尾花的数据预处理与可视化

## 实验五：产品的多维度评价

## 实验六：比特币价格预测

## 实验七：最短路径问题

## 实验八：量化投资选股问题

## 实验九：鸢尾花的分类与聚类

## 实验十： 波士顿房价预测

## 实验十一：34城市的TSP问题

## 实验十二：关联关系挖掘
