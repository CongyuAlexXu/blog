开始学习Numpy
==================
1.学习环境：Windows 10, Anaconda，Jupyter Notebook
-----------------------
强烈建议使用Anaconda进行python和数据科学的学习。
因为`Anaconda`集成了许多必备的包，类似于集成开发环境
而`Jupyter Notebook`就可以视为十分方便专业的文本工具

下载[Anaconda](https://www.anaconda.com/download/), 这里建议先使用一个版本，不过我自己本机上安装了python2.7还有python3.6。 所以需要解决python2还有python3同时使用的问题

2.同时使用python2.7还有python3.6
-------------------------
    windows 搜索栏输入anaconda prompt
    基于3.6:
    在prompt中输入： conda create -- name test_py3 python = 3.6
    激活时输入: conda activate test_py3
    关闭时输入：conda deactivate
    
    基于2.7:
    在prompt中输入： conda create -- name test_py3 python = 2.7
    激活时输入: conda activate test_py2
    关闭时输入：conda deactivate
 
3.配置过程中的问题
-------------------------
    我第一次配置的时候安装好了numpy，但是在jupyter notebook里无法使用，会有报错： Importerror: no module named 'numpy'
    这个原因应该是我电脑里安装过太多次python，虽然我在安装了2.7环境里安装了numpy, 但是jupyter notebook不知道调用的是电脑里的另一个2.7.
    （我没有装Anaconda的时候在python官网下栽过一次2.7）.这个问题的解决办法是：
    （1） 打开Anaconda Navigator
    （2） 左侧菜单栏进入Environment
    （3） 找到对应的所有2.7版本，更新numpy包
    
参考的文章：
  [1](https://blog.csdn.net/qq_27997427/article/details/78546126)
  [2](https://blog.csdn.net/VincentLuo91/article/details/70826859)
  [3]()
