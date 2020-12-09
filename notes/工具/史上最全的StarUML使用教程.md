# 史上最全的StarUML使用教程

### 文章目录



StarUML是一款很全面，很好用的UML画图工具。相比PlantUML那种使用代码画图方式，StarUML的拖拽式更简单易用。

StarUML支持类图、时序图、用例图等十几种图形模式。

## 一. 版本

目前官网[http://staruml.io](http://staruml.io/)上的最新版本是3.X系列，可进入官网进行下载。下载后理论上是要付费使用的，但是不付费也不太影响使用。

注意，非官方途径可用会发现有5.0版本的starUML，那是比较老的开源版本，建议使用官网上最新版的。

## 二. 界面说明

![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/2020032110070662.png)
说明：默认打开starUML后，会默认进入类图模式，各模块区域功能如下：

**1.菜单栏：** 最上方是菜单栏，新建工程啥的，具体不详细介绍；

**2.已经建类图列表**：左上方列表显示已经创建的图，比如类图，时序图等；

**3.工具箱**：左下方工具箱，显示当前类型的图可以使用的工具，主要是各种连线或者图形，是最常用的区域；

**4.绘图区域**：中间白色格子区域，就是绘图区域；

**5.工程区**：右上方区域是工程区，显示工程，model和各种已经绘出的图形；

**6.属性编辑区域**：当画出来一个图形或者一根线时，这个区域会显示这个图形的各种属性，可以修改；

## 三. 画图种类介绍

下面介绍各种图的创建和画法。

### 1. 类图（Class Diagram）

打开starUML工具时，默认进入的就是类图模式，右上角工程区如下显示：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321103608411.png)
默认创建了一个名字为【Untitled】的工程，工程下面有个模块，名字叫【Model】，模块下有个类图，名字叫【Main】。这3个名字是默认的，都可以修改为你自己想要的名字。

比如修改工程名，只需要鼠标选中工程名字，然后右下方属性编辑区域会如下显示：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/2020032110395822.png)
输入你想要的名字即可。模块和类图名字，用同样的方法也可以修改。

**创建类图**

假如我想重新将建一个类图，如何操作？如下步骤：

工程区-》选择Model-》右键-》选择【Add Diagram】，然后如下图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321104622651.png)
可以发现，StarUML支持的图类型有十几种，选择【Class Diagram】，表示类图，这时会默认创建一个名字为“ClassDiagram1”的类图（名字自随便修改），显示在左上角的图列表区，
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321104814259.png)
**画类图**

接下来我们，就可以画类图了，现在左下角工具箱显示了在类图模式下，可以使用的工具列表：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321105241525.png)

下面是随便画的类图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321105429941.png)

### 2. 用例图（Use Case Diagram）

有了上面类图的介绍，创建一个用例图流程，就很简单了：
工程区-》选择Model-》右键-》选择【Add Diagram】-》选择【Use Case Diagram】，然后你就会发现，左下角工具箱变成了用例图的模式：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321105703479.png)
下面是随便画的用例图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321105747730.png)

### 3. 时序图（Sequence Diagram）

工程区-》选择Model-》右键-》选择【Add Diagram】-》选择【Sequence Diagram】，然后你就会发现，左下角工具箱变成了时序图的模式：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321110057629.png)

下面是随便画的时序图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321105939294.png)

### 4. 组件图（Component Diagram）

下面是随便画的组件图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321110259115.png)

### 5. 部署图（Deployment Diagram）

下面是随便画的部署图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321110440498.png)

### 6. 协作图（Comunication Diagram）

下面是随便画的协作图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321110551117.png)

### 7. 对象图（Object Diagram）

下面是随便画的对象图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321110706702.png)

### 8. 活动图（Activity Diagram）

下面是随便画的活动图：
![在这里插入图片描述](http://test-fangsong-imgsubmit.oss-cn-beijing.aliyuncs.com/img/20200321110829666.png)