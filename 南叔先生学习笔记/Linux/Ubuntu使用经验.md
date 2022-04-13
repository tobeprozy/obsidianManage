### 一、Ubuntu18.04 安装只能拼音
在设置中，language和regin添加Chinese之后，输入源里面可能没有Intelligent Pinyin

此时需要在terminal下载，安装IBus拼音

```sudo apt-get install ibus-pinyin```

然后，再次打开setting->region&language
![[Pasted image 20220410150420.png]]
![[Pasted image 20220410150436.png]]

如果还没有，重启之后就有了。


## 二、调整分区大小
安装gparted、打开gparted
```
sudo apt install gparted
gparted
```
![[Pasted image 20220410150836.png]]

## 三、使用 apt 安装 Visual Studio Code
1. 以 sudo 用户身份运行下面的命令，更新软件包索引，并且安装依赖软件：
```
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
```
2. 使用 wget 命令插入 Microsoft GPG key ：
```wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -```

3. 启用 Visual Studio Code 源仓库，输入：
```sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"```

4. 安装 Visual Studio Code 软件包：
```sudo apt install code```


## 四、编译c++
### 1.安装g++/gcc
想要安装开发工具软件包，以 拥有 sudo 权限用户身份或者 root 身份运行下面的命令：
```
sudo apt update
sudo apt install build-essential
```
这个命令将会安装一系列软件包，包括gcc,g++,和make。

你可能还想安装关于如何使用 GNU/Linux开发的手册。

通过运行下面的命令，打印 GCC 版本，来验证 GCC 编译器是否被成功地安装。

```gcc --version```

![[Pasted image 20220410200151.png]]
### 2.使用以下命令进行编译。

```
gcc hello.cpp -lstdc++ -o hello
//或
g++ hello.cpp -o hello
```

### 3.运行可执行文件，在当前目录下输入以下命令查看结果。

```./hello```

## 五、Network中的wired消失
1.输入下面的命令
![[Pasted image 20220412215043.png]]
2.回来了
![[Pasted image 20220412215145.png]]


## 六、ubuntu20.04使用clash
### 方法一
1.打开github
![[Pasted image 20220412221556.png]]
2.下载
![[Pasted image 20220412221637.png]]

3. 解压
![[Pasted image 20220412221753.png]]
5. 打开
![[Pasted image 20220412221833.png]]
6.出现界面
![[Pasted image 20220412221853.png]]
7.寻找订阅
www.v2rayse.com
![[Pasted image 20220412221947.png]]

![[Pasted image 20220412222014.png]]

8.在可以使用外网的地方获取密码
9.获取订阅链接
![[Pasted image 20220412222306.png]]

![[Pasted image 20220412222411.png]]
10.下载订阅
![[Pasted image 20220412222449.png]]

11.选择代理
![[Pasted image 20220412222609.png]]
12.打开代理

![[Pasted image 20220412223333.png]]

12.设置代理
![[Pasted image 20220412222817.png]]
13.上网
![[Pasted image 20220412223241.png]]


### 方法二
1.在主机上打开Clash
![[Pasted image 20220412223457.png]]

2.在虚拟机上设置VPN
![[Pasted image 20220412223950.png]]

3.上网

![[Pasted image 20220412224017.png]]

## 七、通过Xshell连接虚拟机上的linux

1.在虚拟机查看ip地址
![[Pasted image 20220413104307.png]]

2.新建Shell会话
![[Pasted image 20220413104357.png]]

此时发现连接不上，原因是虚拟机没有安装ssh服务

3.进入虚拟机，输入一下命令，安装ssh
```sudo apt-get install openssh-server```
使用命令
```csharp
sudo /etc/init.d/ssh start
```
若出现以下信息，说明安装和启动ssh服务成功：
![[Pasted image 20220413104732.png]]
4.双击会话，弹出用户名对话框，注意用户名是@前面那个
![[Pasted image 20220413104952.png]]
5.输入密码，密码就是登录密码
![[Pasted image 20220413105046.png]]
6.连接成功
![[Pasted image 20220413105145.png]]
## 八、通过Xshell给虚拟机上的linux传输文件
![[Pasted image 20220413105424.png]]
![[Pasted image 20220413105556.png]]

![[Pasted image 20220413112721.png]]

![[Pasted image 20220413112733.png]]

