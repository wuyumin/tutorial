# Git 配置

一般是操作用户目录下的`.gitconfig`文件(也可以使用命令行操作，命令行最终也是修改各个级别的配置文件的)。

`.gitconfig`配置文件例子：

```ini
[http]
    ;proxy = http://127.0.0.1:1080
[https]
    ;proxy = http://127.0.0.1:1080
[gui]
    ;GUI图形化工具编码
    encoding = utf-8
[core]
    ;关闭git忽略大小写
    ignorecase = false
[user]
    ;电子邮箱
    email = xxx@example.com
    ;姓名可以使用中文或英文
    ;name = 张三
    name = San Zhang
    ;GPG签署密匙ID(16位)
    signingkey = xxxxxxxxxxxx
[commit]
    ;是否启用GPG签署
    ;gpgsign = true
```

http 协议换为 git 协议：

```ini
[url "git://"]
    insteadOf = http://
[url "git://"]
    insteadOf = https://
```

SSH形式使用代理需要`vi ~/.ssh/config`  
windows系统
```
Host github.com
    #http代理(需要connect: git安装后一般是D:\Program Files\Git\mingw64\bin\connect.exe)
    #ProxyCommand connect -H 127.0.0.1:1080 %h %p
```
mac系统
```
Host github.com
    #http代理(需要socat)
    #ProxyCommand socat - PROXY:127.0.0.1:%h:%p,proxyport=1087
    #socks5代理(需要nc)
    #ProxyCommand nc -X 5 -x 127.0.0.1:1086 %h %p
```
