# 安装MSYS2  
打开MSYS2的国内镜像：https://mirrors.tuna.tsinghua.edu.cn/msys2/distrib/x86_64/ 。下滑至最底处，点击“msys2-x86_64-xxx.exe”
![alt text](/images/image.png)
下载完成后，双击运行，一直点击“下一步”即可。等待安装完成后关闭。
# 安装Clang及相关依赖  

1、更新镜像，在开始菜单中选择“MSYS2 MSYS”，并执行：
```
sed -i "s#https\?://mirror.msys2.org/#https://mirrors.tuna.tsinghua.edu.cn/msys2/#g" /etc/pacman.d/mirrorlist*
pacman -Syu
```  
一路回车即可，最后命令行窗口大概率会退出，重新在开始菜单打开即可（如果没有退出，可以直接执行下面的命令）。  
等待安装完成，输入clang -v检验之前步骤是否正确  
![alt text](/images/image-1.png)  
# 配置环境变量
打开任务栏搜索框，搜索PATH，点击打开  
在打开窗口点击“环境变量”：  
在用户变量中选择PATH，点击编辑，新建一条：  
```
C:\msys64\ucrt64\bin
```
# 配置VSC  
重启后，从开始菜单打开VSCode，使用快捷键Ctrl+Shift+X打开插件栏  
安装如下插件：
* Chinese (Simplified) (简体中文) Language Pack for  
* Visual Studio Code  
* Clangd  
* Code Runner  

# 可能遇到的问题
+ vscode中相关c++标准库飘红  
![alt text](/images/image-5.png)
原因是，clangd配置的问题
![alt text](/images/image-6.png)  

解决方法:  
1、点击界面左上角的文件，选择首选项，点击设置，或快捷键(Ctrl + ,)  
2、在搜索设置框中输入 clangd path，如下图示
![alt text](/images/image-7.png)  
将path改为msys2安装的ucrt64目录