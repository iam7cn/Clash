# 搭建 proxypool 节点池

## 安装宝塔
为了方便，还是安装宝塔或者 aapanel（宝塔国际版），个人认为 aapanel 比宝塔好用不止一点，很多设置更加人性化，不过语言是英文的

宝塔：https://www.bt.cn/

安装：https://www.bt.cn/bbs/thread-19376-1-1.html

aapanel：https://www.aapanel.com/index.html

安装：https://www.aapanel.com/install.html

### ubuntu

```
wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && sudo bash install.sh
```



### Centos/Debian/Fedora

```
yum install -y wget && wget -O install.sh http://www.aapanel.com/script/install_6.0_en.sh && bash install.sh
```



### 安装 GO 环境
Golang 官网下载地址：https://golang.org/dl/

选择对应架构的最新版本，一般默认都是 linux-amd64 即可

https://golang.org/dl/go1.16.4.linux-amd64.tar.gz （截止至 2021.05.11 最新版本是 1.16.4）

在～下创建 go 文件夹，并进入 go 文件夹（为了方便找到 go 环境，创建一个新文件夹)

```
mkdir ~/go && cd ~/go
```

下载的 go 压缩包（这里是 1.16.4 版本的，根据最新版本自行更改版本号）

```
wget https://dl.google.com/go/go1.16.4.linux-amd64.tar.gz
```

执行 tar 解压到 /usr/loacl 目录下（官方推荐），得到 go 文件夹等

```
tar -C /usr/local -zxvf  go1.16.4.linux-amd64.tar.gz
```

添加 /usr/loacl/go/bin 目录到 PATH 变量中。添加到 /etc/profile 或 $HOME/.profile 都可以

习惯用 vim，没有的话可以用命令安装一个

```
sudo apt-get install vim
```

或 宝塔直接找到 /etc 下的 profile 文件打开，并在最后一行添加

> export GOROOT=/usr/local/go
> export PATH=$PATH:$GOROOT/bin

保存退出后 source 一下

```
source /etc/profile
```

检查一下是否已经正确安装环境

```
go version
```

应该返回 go version go1.16.4 linux/amd64

安装 go-bindata

如果你想要编辑网页内容的话就需要 go-bindata

如果想要默认跳过这一步即可

项目地址：https://github.com/go-bindata/go-bindata

```
go get -u github.com/go-bindata/go-bindata/...
```

安装以后会发现他安装在了 GOPATH 下

可以使用

```
go env
```

查看 go 相关环境目录

默认 GOPATH 应该是在 GOPATH="/root/go"

访问该目录下的 /bin 文件夹内，会发现有个 go-bindata

复制黏贴到 GOROOT="/usr/local/go" 目录下 /usr/local/go/bin 内

```
go-bindata -version
```

应该可以正常返回 go-bindata 的版本号了 

> go-bindata 3.1.2 (Go runtime go1.16.4). Copyright (c) 2010-2013, Jim Teeuwen.

至此安装完成全部环境了

下载运行程序
用 go 命令获取最新版本的程序  

```
go get -u -v github.com/Sansui233/proxypool 
```

默认下载的程序会在 /root/go/pkg/mod/github.com/!sansui233/proxypool@v0.7.1 下，建议将其换个位置

我是放在了 /www/wwwroot/proxypool/ 下

```
mkdir /www/wwwroot/proxypool                                                                 # 新建目录
mv /root/go/pkg/mod/github.com/\!sansui233/proxypool@v0.7.1/* /www/wwwroot/proxypool/        # 移动文件到指定文件中
```

上面如果无法get程序时可以用以下

```
wget https://github.com/Sansui233/proxypool/archive/refs/tags/v0.7.1.tar.gz    # 下载最新版本
mkdir /www/wwwroot/proxypool                                                   # 新建目录
tar -C /www/wwwroot/proxypool -zxvf v0.7.1.tar.gz                              # 解压程序到新建目录
mv /www/wwwroot/proxypool/proxypool-0.7.1/* /www/wwwroot/proxypool/            
```

修改 /config/config.yaml 中的网址，为你要用的网址。端口建议保持默认。抓取频率和速度等自己设定。[配置文件说明](https://github.com/Sansui233/proxypool/wiki/配置文件说明)

我是开了个 screen 运行 main.go，screen 使用方法参考[这里](https://blog.csdn.net/weixin_34001430/article/details/85538681?utm_medium=distribute.pc_relevant_t0.none-task-blog-2~default~BlogCommendFromMachineLearnPai2~default-1.control&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2~default~BlogCommendFromMachineLearnPai2~default-1.control)

screen 窗口中运行（程序根目录下）

```
go run main.go -c ./config/config.yaml
```

解析域名
将你的域名解析到该 VPS 的 IP，然后宝塔内添加网址，添加 SSL 证书并开启强制 https

网址设置中找到反代，填入 127.0.0.1:12580 和 $host 并保存

访问网站应该就可以看到内容了

## 修改网站内容

确保自己已经正确安装并且能显示 go-bindata 的版本号

自行修改 /www/wwwroot/proxypool/assets/html/ 下的 html 文件，请务必保留原作者版权信息！！！不要逼着大佬删库

修改后将 /www/wwwroot/proxypool/docs/ 下的 genbindata.sh 移动到程序根目录下，也就是 /www/wwwroot/proxypool/下，千万不要在docs目录下运行

然后运行 

```
./docs/genbindata.sh 
```

等待一会即可在 /internal/bindata/html/ 下生成新的 html.go 文件

然后重启 main.go 程序，刷新页面，即可生效


如果要生成程序

```
Make 
```

他会自动在www/wwwroot/proxypool/bin 下生成程序

