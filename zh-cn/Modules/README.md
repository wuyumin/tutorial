# Go模块简明教程(Go语言依赖包管理工具)

> Go模块是Go语言的依赖包管理工具。

## Go模块的使用

> 1、Go1.11及以后版本才能使用。  
2、Go1.11需要设置环境变量 GO111MODULE 为 on（新特性开关，按照Go语言惯例，mod首次在go1.11版本中使用，go1.13及以后版本这个设置可以不用了）。  
3、可以设置模块代理：设置环境变量 GOPROXY 的值为代理网址，目前可用的模块公共代理网址有:  
<https://goproxy.io>  
<https://goproxy.cn>  
<https://mirrors.aliyun.com/goproxy/>  
<https://mirrors.cloud.tencent.com/go/>  
<https://goproxy.baidu.com/>  
<https://athens.azurefd.net>  
<https://gocenter.io>  
(注：Go语言官方已推出官方模块代理 <https://proxy.golang.org> 但目前国内处于被墙状态。)  
或者自建模块代理工具:  
<https://github.com/goproxyio/goproxy>  
<https://github.com/goproxy/goproxy>  
<https://github.com/gomods/athens>  

mod是模块英文modules的简写。

列举一些常用的命令行：

- `go help mod`查看帮助。
- `go mod init <项目模块名称>`初始化模块，会在项目根目录下生成 `go.mod` 文件。参数`<项目模块名称>`是非必写的，但如果你的项目还没有代码编写，这个参数能快速初始化模块。如果之前使用其它依赖管理工具(比如dep，glide等)，mod会自动接管原来依赖关系。
- `go mod tidy`根据go.mod文件来处理依赖关系。
- `go mod vendor`将依赖包复制到项目下的 vendor 目录。建议一些使用了被墙包的话可以这么处理，方便用户快速使用命令`go build -mod=vendor`编译。
- `go list -m all`显示依赖关系。`go list -m -json all`显示详细依赖关系。
- `go list -m -versions <path>`显示包有哪些已发布版本
- `go mod download <path@version>`下载依赖。参数`<path@version>`是非必写的，path是包的路径，version是包的版本。
- 其它命令可以通过`go help mod`来查看。

另外：  
go.mod文件是文本文件，是可以自己手动编辑的。  
Go模块版本控制的下载文件及信息会存储到GOPATH的pkg/mod文件夹里。  
使用了Go模块，源码不一定要在GOPATH中进行。  

## 使用示例

go.mod文件
```go
module github.com/wuyumin/easydoc

require (
	github.com/BurntSushi/toml v0.3.0
	github.com/mostafah/fsync v0.0.0-20151120150823-6c37e2827238
	github.com/russross/blackfriday v1.5.1
)
```

## Git建议

go.mod文件必须要提交到git仓库，但go.sum文件可以不用提交到git仓库(git忽略文件.gitignore中设置一下)。

## 问题解答

- 问：git操作时，我的go.mod文件没有修改，为什么git老是提示是修改状态呢？  
  
  答：这个问题一般出现在windows系统上，是换行符导致(类Unix系统一般使用LF换行符，windows系统使用CRLF换行符，而go.mod文件一般是使用LF换行符，windows系统上git默认会将LF换行符转换成CRLF换行符)。  
  解决方法：在项目根目录下添加或更新`.gitattributes`文件，写入这样语句：  
```
go.mod text eol=lf
```

- 问：启用Go模块以后，使用`go get xxx`时会报错提示"go: cannot find main module; see 'go help modules'"，这个是怎么回事？  
  
  答：因为没有找到`go.mod`文件，所以会报错。你只要在项目根目录下生成一个go.mod文件就可以了。

- 问：如何在Go模块里使用本地依赖包？  
  
  答：首先在项目的`go.mod`文件的require处添加依赖包，然后在replace处添加替换本地依赖包(路径要处理妥当)。比如：

```go
require (
	mytest v0.0.0
)
replace (
	mytest v0.0.0 => ../mytest
)
```

- 问：如何获取依赖的特定版本？  
  
  答：go get可以在末尾加@符号，用来指定版本。  

```bash
go get github.com/gorilla/mux           #匹配最新的一个tag
go get github.com/gorilla/mux@latest    #跟上面一样
go get github.com/gorilla/mux@master    #匹配master分支
go get github.com/gorilla/mux@v1.6.2    #匹配v1.6.2
go get github.com/gorilla/mux@c856192   #匹配commit的SHA-1码的版本
```

  针对于开发者的建议：仓库必须是带v前缀的、语义化的版本号来打标签tag，格式如`v1.2.0`  
  注：有些模块代理还不支持一些指定版本的处理。  

## 参考资料

- 语义化版本(中文) <https://semver.org/lang/zh-CN/>
- Go模块官方文档(英文) <https://github.com/golang/go/wiki/Modules>
- Go模块命令说明(英文) <https://golang.google.cn/cmd/go/#hdr-Module_maintenance>

## 附

- Go语言官方网站(中国) <https://golang.google.cn>
- Go语言官方网站 <https://golang.org>

## 欢迎修正

`此篇文章最新的更改都会在GitHub上进行。`  
GitHub上的原文链接  
<https://github.com/wuyumin/tutorial/blob/master/zh-cn/Modules/README.md>  
欢迎在GitHub上star本项目或通过Issues提供修正建议。  