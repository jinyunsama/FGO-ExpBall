# 丸子制造机

FGO-ExpBall是专门用来搓丸子的程序  
所谓的搓丸子是把若干张低星礼装喂成一个,以保留其中的经验,并在喂给高星强化对象时节约QP的操作

## 特性

- 全自动免配置跨平台开箱即用的搓丸子  
- 自动对游戏内贩卖/强化时的的筛选与排序进行设定,保证账户资产安全  
- 稀有召唤(哈贝喵等所有你认为值得上锁的对象)自动上锁  
- 独立项目,专门用来搓丸子
- 所需依赖是FGO-py的子集,如果你已有FGO-py,可直接附加而无需配置任何环境  

## 运行

`FGO-ExpBall/fgoExpBall.py`是主程序,使用方法同FGO-py的cli  
主要就两个命令:

- connect \<serial\>  连接设备  
- main                搓丸子

如果已有安装好的portable FGO-py(可在[FGO-py的release](https://github.com/hgjazhgj/FGO-py/releases/tag/v2022.06.12)或[FGO-py官网](https://fgo-py.hgjazhgj.top/)获取),可按本项目的release操作,或是直接在portable FGO-py的根目录下clone本项目

由于搓丸子需要由程序本身而非玩家对游戏中的设置进行调整以保证账户资产安全从而并不符合FGO-py「小而美」的一贯设计风格,所以做成了一个独立项目

## 自动上锁

将你认为重要的召唤物自动上锁,默认配置为哈贝喵,同时unused中有小安和Saber lily备用  
本功能原理同FGO-py的助战筛选,你可以设置其他重要召唤物,具体见FGO-py readme,但是有以下区别:  

- 没有透明度通道,黑色就会被认为黑色  
- 不能热更改图片,需要在程序运行前调整好  

此外,如果一次抽出了至少两个重要召唤物,无论是相同还是不同,程序都会立刻停止运行,可以慢慢品一品然后截图晒卡什么的  

## 更新日志

### 2022/08/10 v0.0.2

Fix:将所有的FGO-py替换为FGO-ExpBall  

### 2022/08/10 v0.0.1

init  
好消息:FGO-py终于有搓丸子了  
坏消息:搓丸子不属于FGO-py  
本项目复用了FGO-py中许多已经成熟的代码,同时依照需要自动更改游戏内设置的需求引入了一个简陋的按钮系统~~没错我跟alas学的~~  
事实证明这个框架完美胜任了当前的工作,使得本项目在保证代码质量的同时从新建文件夹到全部完工只用了8小时(上午8点-下午4点),并且几乎一遍完工,测试才花了半小时不到,只不过代码看起来有些又臭又长,并且全是大写字母...这也是为什么不直接写在FGO-py里面的原因  
本次是一个成功的尝试,后续的想法是进一步将FGO-py的模块通用化出来,但还是先看看有没有bug吧  
另外,本人尚未通关2.6,所以本人暂时无法进行大量测试  
