# Git 使用 GPG 进行签名

> 首先自己要有 GPG Key。如何生成 GPG Key 请自己查阅相关资料一下，这里不做介绍。

```
Windows系统注意：
说明一下：目录的Administrator是本地电脑用户名，使用其他用户名请自行替换。
GPG软件安装配置文件默认目录 C:\Users\Administrator\AppData\Roaming\gnupg
Git Bash调用是这个目录 C:\Users\Administrator\.gnupg 需要将钥匙再导入这里才能在Git Bash运行正常
pubring.gpg 公钥库
secring.gpg 私钥库
trustdb.gpg 信任库
```

## 配置
`git config --global user.signingkey [GPG Key-ID]`配置 GPG Key-ID  
`git config --global commit.gpgsign true`如果设置这个，相关操作就直接使用 GPG 签名了  
配置也可以通过gitconfig文件进行设置。  

## 添加 GPG 公钥到 GitHub 帐号
将 GPG `公钥`添加到 GitHub 帐号的设置里，记得是`公钥`哦。  

## git 提交使用 GPG 签名
`git commit -S -m "提交说明"`记得这里的 -S 是大写字母 S。  
参考：<https://help.github.com/articles/signing-commits-using-gpg>  

## git 标签使用 GPG 签名
`git tag -s v1.0.0 -m "标签说明" [CommitID]`  
参考：<https://help.github.com/articles/signing-tags-using-gpg>  

## 列出 GPG 签名
`git log --show-signature`  
默认情况下git log不会列出 GPG 签名，要使用 --show-signature 选项。  
