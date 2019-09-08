# 利用 VSCode 建立 OpenGL 开发环境
想用VSCode写OpenGL，网上可参考的教程不多，搞了一天，参考了各种方法，各种失败，“困难总比办法多”，真的难顶，不过最后还是顶住了，在这里记录下，以免以后又要再踩一遍坑，也给有同样需求的人一个指导。

使用 VSCode 编译并执行 C/C++ 语言
---
参考：https://junyou.tw/vscode-c/
不要着急跳转，不然你可能会给坑了，看完下面的文字

他的LLVM安装的是64位的，我跟着他的教程装了64位，运行opengl方程会提示：skipping incompatible LLVM\lib\freeglut.lib，报错，无法编译，后来想到Freeglut好像是32位的，于是把MinGW和LLVM和vscode配置都改成了x86的，于是就编译出成功了~~~~~

所以下面给出相关工具32位的下载：

LLVM：http://releases.llvm.org/download.html
![Image text](https://github.com/sunbrando/-VSCode-OpenGL-/blob/master/Image/QQ%E6%88%AA%E5%9B%BE20190908230246.png)

MinGW：https://osdn.net/projects/mingw/releases/ ，直接下mingw-get-setup.exe即可，这个默认是32位

Freeglut：不要下载源文件的，要下载编译好的。参考：https://sudo.tw/article/setup-opengl-for-development-on-cpp

移动文件
---
安装好上面三个工具后，把MinGW和Freeglut这两个文件夹里的文件都拖进LLVM文件夹里。
![Image text](https://github.com/sunbrando/-VSCode-OpenGL-/blob/master/Image/QQ截图20190908235856.png)
![Image text](https://github.com/sunbrando/-VSCode-OpenGL-/blob/master/Image/QQ%E6%88%AA%E5%9B%BE20190908235748.png)

vscode的C/C++编译环境配置
---
vscode的编译环境配置也要改成x86的，并且要加上opengl的编译参数。
相关文件已上传到本仓库.vscode文件夹里，可以全部替换掉。
注意要把c_cpp_properties.json里的LLVM目录改成自己的LLVM安装目录。
![Image text](https://github.com/sunbrando/-VSCode-OpenGL-/blob/master/Image/QQ%E6%88%AA%E5%9B%BE20190908230921.png)

好了，完成上面相关的步骤，就可以试试本项目的helloworld.cpp，看看是否配置成功，右键Run Code

祝好运。
![Image text](https://github.com/sunbrando/-VSCode-OpenGL-/blob/master/Image/QQ%E6%88%AA%E5%9B%BE20190908230641.png)

Reference:
---
https://medium.com/@mikechen26/%E5%88%A9%E7%94%A8-vscode-%E5%BB%BA%E7%AB%8B-opengl-%E9%96%8B%E7%99%BC%E7%92%B0%E5%A2%83-d79c20830533



