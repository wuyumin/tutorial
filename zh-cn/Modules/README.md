# Go模块简明教程(Go语言依赖包管理工具)

> Go模块是Go语言的依赖包管理工具。

## Go模块的使用
> 1、Go1.11及以后版本才能使用。  
2、Go1.11需要设置环境变量 GO111MODULE 为 on（新特性开关，按照Go语言惯例，mod首次在go1.11版本中使用，go1.12及以后版本这个设置应该不会用了）。

mod是模块英文modules的简写。

列举一些常用的命令行：

- `go help mod`查看帮助。
- `go mod init <项目模块名称>`初始化模块，会在项目根目录下生成 `go.mod` 文件。参数`<项目模块名称>`是非必写的，但如果你的项目还没有代码编写，这个参数能快速初始化模块。如果之前使用其它依赖管理工具(比如dep，glide等)，mod会自动接管原来依赖关系。
- `go mod tidy`根据go.mod文件来处理依赖关系。
- `go mod vendor`将依赖包复制到项目下的 vendor 目录。建议一些使用了被墙包的话可以这么处理，方便用户快速使用命令`go build -mod=vendor`编译。
- `go list -m all`显示依赖关系。
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

## 参考资料
- 语义化版本(中文) <https://semver.org/lang/zh-CN/>
- Go模块官方文档(英文) <https://golang.google.cn/cmd/go/#hdr-Module_maintenance>

## 欢迎修正
`此篇文章最新的更改都会在GitHub上进行。`  
GitHub上的原文链接  
<https://github.com/wuyumin/tutorial/blob/master/zh-cn/Modules/README.md>  
欢迎在GitHub上star本项目或通过Issues提供修正建议。  
