# 利用 VSCode 建立 OpenGL 开发环境
想用VSCode写OpenGL，网上没什么部署的教程，搞了一天，参考了各种方法，各种失败，“困难总比办法多”，真的难顶，不过最后还是顶住了，在这里记录下，以免以后又要再踩一遍坑，也给有同样需求的人一个指导。


具体步骤按下面的网站（需要科学上网）操作：
https://medium.com/@mikechen26/%E5%88%A9%E7%94%A8-vscode-%E5%BB%BA%E7%AB%8B-opengl-%E9%96%8B%E7%99%BC%E7%92%B0%E5%A2%83-d79c20830533
不要着急跳转，不然你可能会给坑了，看完下面的文字

步骤主要是安装好这几个工具

LLVM
MinGW
Freeglut

然后把安装后的MinGW和Freeglut里所有的文件，复制到LLVM文件夹里，
然后再给vscode添加C++的扩展工具，和编译的配置文件（上传到本GitHub上了）。

但是！！！！
他的教程里MinGW和LLVM都是64位的，我跟着他的教程装了64位，运行会提示：skipping incompatible LLVM\lib\freeglut.lib，报错，无法编译，后来想到Freeglut好像是32位的，于是把MinGW和LLVM和vscode配置都改成了32位的，于是就编译出来了~~~~~

下面给出32位的下载

LLVM：http://releases.llvm.org/download.html

MinGW：https://osdn.net/projects/mingw/releases/

Freeglut：不要下载源文件的，要下载编译好的。参考：https://sudo.tw/article/setup-opengl-for-development-on-cpp

c_cpp_properties.json此处要改成自己的LLVM目录。

装好了，就试试本项目的helloworld.cpp，右键Run Code，

看看有没有显示这个水壶

