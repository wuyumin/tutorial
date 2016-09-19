# Composer简明教程

> Composer是PHP的一个依赖管理工具。  
> 使用和安装Composer，请确保已正确安装PHP(5.3.2+)，并设置了PHP的环境变量。  

## Composer的安装
### Windows系统
1. 想好安装目录。  
比如安装到`D:\Program Files\Composer`下  
2. 下载composer.phar文件到安装目录。  
下载最新版：<https://getcomposer.org/composer.phar>  
各个版本下载页：<https://getcomposer.org/download>  
3. 安装目录下创建名称为 composer.bat 的文件并在文件里填写如下一行内容：  
`@php "%~dp0composer.phar" %*`  
4. 设置环境变量  
电脑桌面上右击"计算机" -> 菜单"属性" -> "高级系统设置" -> 底下的"环境变量" -> "系统变量"里找到Path项，编辑，变量值在最后增加Composer安装目录，如`;D:\Program Files\Composer`(这个根据你的安装目录来写)，多个路径记得使用英文分号`;`隔开。  
5. 测试一下(使用DOS命令窗口)  
`composer -V`  

### Linux系统/Mac OSX系统
终端命令行下操作。  
1. 进入到临时下载文件夹(随意，比如自己的家目录)  
`# cd ~`  
2. 下载composer.phar文件  
`# wget https://getcomposer.org/composer.phar`  
3. 移动并重命名composer.phar文件到二进制目录  
`# mv composer.phar /usr/local/bin/composer`  
相当于设置环境变量了  
4. 设置执行权限，一定要有执行权限才行  
`# chmod 700 /usr/local/bin/composer`  
5. 测试一下  
`# composer -V`  

## Composer的使用
- `composer self-update`：更新composer版本。(当然，你也可以采取下载composer.phar文件进行覆盖更新方式)。
- `composer install`：根据项目目录下的composer.json文件来安装依赖代码库。
- 未完待续……

## Composer的资源
- Composer官网(英文) <https://getcomposer.org>
- PHP安装包列表(英文) <https://packagist.org>
- Composer中文网(中文) <http://www.phpcomposer.com>
- Packagist/Composer中国全量镜像(中文) <http://pkg.phpcomposer.com>

## 欢迎修正
GitHub上的原文链接  
<https://github.com/wuyumin/tutorial/blob/master/zh-cn/Composer>  
欢迎在GitHub上star本项目或通过Issues提供修正建议。  

### 未完待续……