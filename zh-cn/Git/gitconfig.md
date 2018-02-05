# Git 配置

一般是操作用户目录下的`.gitconfig`文件(也可以使用命令行操作，命令行最终也是修改各个级别的配置文件的)。

`.gitconfig`配置文件例子：

```ini
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
