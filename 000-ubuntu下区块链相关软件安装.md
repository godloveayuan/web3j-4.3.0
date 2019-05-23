## 一、安装git
```
sudo apt-get install git
```
查看版本： `git --version`

---
## 二、安装 go
```
sudo apt-get install golang-go
```
查看版本：`go version`

---
## 三、安装geth
```
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo apt-get update
sudo apt-get install ethereum
```
查看版本： `geth version`

---
## 四、安装nodejs，npm (暂不需要)
更新软件源：
```
sudo apt-get update
sudo apt-get install -y python-software-properties  
sudo apt-get install -y software-properties-common
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
```
安装nodejs
```
sudo apt-get install nodejs
sudo apt install nodejs-legacy
sudo apt install npm
```
更新npm的包镜像源，方便快速下载
```
sudo npm config set registry https://registry.npm.taobao.org
sudo npm config list
```

---
## 五、安装solc  (暂不需要)
更新软件源：
```
sudo add-apt-repository -y ppa:ethereum/ethereum
sudo add-apt-repository -y ppa:ethereum/ethereum-dev
sudo apt-get update
```
安装：
```
sudo apt-get install solc
```
检测是否安装成功: `solc --help` <br/>
查看版本：`solc --version`  <br/>
说明：这种方法一般安装的是最新版本，0.5.x ,对于想使用 0.4.x 的需要找其他方式安装 <br/>

---
## 六、安装 solc 0.4.26 版本
+ 1、去github 下载tar.gz 源码，找到0.4.26 <br/>
[官网](https://github.com/ethereum/solidity/releases) <br/>
[我的gitHub](https://github.com/godloveayuan/Solc-0.4)

+ 2、拷贝、 解压 tar.gz 文件
```
tar -xvf solidity_0.4.26.tar.gz
```
注意：这是个源码文件，需要自己编译安装.
+ 3、编译，安装
```
// 安装 cmake
sudo apt install cmake

// 进入解压的tar文件夹下
cd solidity_0.4.26/sripts

// 执行脚本，安装依赖的模块，过程会很久
sudo ./install_deps.sh

// 执行脚本，编译安装solc
sudo ./build.sh

// 出现以下日志，说明安装完成
// [100%] Built target soltest
// Installing solc and soltest

// 检查安装是否成功
solc --version
```

---
### 七、安装 web3j
#### 1. 下载安装包
[官网](https://github.com/web3j/web3j/releases) <br/>
[我的gitHub](https://github.com/godloveayuan/web3j-4.3.0)

#### 2. 解压
```
tar -xvf web3j-4.3.0-tar -C /home/godloveayuan/programfiles/
```
#### 3. 配置环境变量
+ 打开 ~/.bashrc 文件
+ 备注：也可以在 /etc/profile 文件下添加
+ 在文件结尾添加以下内容
```
# Set web3j Path
export WEB3J_HOME=/home/godloveayuan/programfiles/web3j-4.3.0
export PATH=${WEB3J_HOME}/bin:$PATH
```
+ 使环境变量立即生效
```
source .bashrc
```

#### 4. 检查安装成功
```
// 查看版本
web3j --version
```
---