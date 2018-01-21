# Composer简明教程

> Composer是PHP的一个依赖管理工具。  
使用和安装Composer，请确保已正确安装PHP(版本5.3.2+)，并且设置了PHP的环境变量(就是使用命令 `php -v`可以显示出php版本号的那种)。  

## Composer的安装
### Windows系统
1. 安装目录。  
比如安装在`D:\Program Files\Composer`下 ， 这个目录会用来设置Composer的环境变量。 
2. 下载composer.phar文件到安装目录。
  - 下载最新版：<https://getcomposer.org/composer.phar>
  - 各个版本下载列表页：<https://getcomposer.org/download>
3. 安装目录下创建名称为 composer.bat 的执行文件并在文件里填写下面一行内容即可：  
`@php "%~dp0composer.phar" %*`  
4. 设置Composer环境变量  
电脑桌面上右击"计算机" -> 菜单"属性" -> "高级系统设置" -> 底下的"环境变量" -> "系统变量"里找到Path项，编辑，变量值在最后添加Composer安装目录路径字符，如`;D:\Program Files\Composer`(这个根据你的安装目录来写)，多个路径间记得使用英文分号`;`隔开。  
5. 测试一下(使用DOS命令窗口)  
`composer -V`  

### Linux系统/Mac OSX系统
终端命令行下操作。  
1. 进入到临时下载文件夹(随意，比如自己的家目录)  
`# cd ~`  
2. 下载composer.phar文件  
`# wget https://getcomposer.org/composer.phar`  
3. 移动并重命名composer.phar文件到二进制目录  
`# mv composer.phar /usr/local/bin/composer`  相当于设置Composer环境变量了  
4. 设置执行权限，一定要有执行权限才行  
`# chmod 755 /usr/local/bin/composer`  
5. 测试一下  
`# composer -V`  

## Composer的使用
列举一些常用的命令行。
- `composer --help`：composer 帮助信息。
- `composer self-update`：更新composer版本。(当然，你也可以采取下载composer.phar文件进行覆盖更新)。
- `composer install`：根据当前目录下的composer.json文件来安装依赖代码库。
- `composer require`：安装依赖包并写入 composer.json 文件。
- `composer update`：更新依赖代码包。
- `composer create-project`：创建项目。
- `composer init`：交互方式在当前目录下创建composer.json文件。
- `composer remove`：移除依赖包及其依赖(在依赖没有被其它包使用的情况下)。
- `composer dump-autoload`：打印自动加载索引。

## PHP 代码使用示例

> 本例只是测试 composer 的 PHP 代码使用，其实 JSON 操作可直接用`json_encode`函数编码和`json_decode`函数解码。

安装依赖包`composer require gointegro/json:0.9.16`

```php
<?php
require __DIR__ . '/vendor/autoload.php'; // 自动加载文件

use GoIntegro\Json\JsonCoder; // 命名空间

// 逻辑代码
$json = new JsonCoder();
$arr = [
    'name' => '姓名',
    'sex'  => '男',
    'age'  => 18
];
echo $json->encode($arr);
```

## Composer的资源
- Composer官网(英文) <https://getcomposer.org>
- PHP安装包列表(英文) <https://packagist.org>
- Composer中文网(中文) <http://www.phpcomposer.com>
- Packagist/Composer中国全量镜像(中文) <http://pkg.phpcomposer.com>

## 欢迎修正
GitHub上的原文链接  
<https://github.com/wuyumin/tutorial/blob/master/zh-cn/Composer/README.md>  
欢迎在GitHub上star本项目或通过Issues提供修正建议。  
