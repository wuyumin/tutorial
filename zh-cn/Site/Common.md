# 网站开发时常用的特殊文件

## 站点根目录下的特殊文件

###  favicon.ico图标文件
　　favicon.ico图标是网站的缩略标志，可以显示在浏览器标签、地址栏左边和收藏夹，是展示网站个性的缩略logo标志，也可以说是网站的头像，如果要让网站看起来更专业、更美、更有个性，favicon.ico图标是必不可少的。

　　尺寸一般是16x16为好。

　　一般放在站点根目录下，并且该文件是可以通过互联网访问的，相关软件会自动调用。如果要强制使用，请在网页HTML代码的<head></head>之间插入代码`<link rel="shortcut icon" href="ico图标文件路径或网址">`

参考资料：
- <http://www.ico.la>

###  robots.txt搜索引擎文件
　　robots.txt是存放在站点根目录下的一个纯文本文件。虽然它的设置很简单，但是作用却很强大。它可以指定搜索引擎蜘蛛只抓取指定的内容，或者是禁止搜索引擎蜘蛛抓取网站的部分或全部内容。
- User-agent：用于描述搜索引擎蜘蛛的名字。如果该项的值设为`*`，则该协议对任何搜索引擎蜘蛛均有效。
- `#`用来注释
- 每个路径之前都要包含`/`
- Disallow：限制目录
- Sitemap：搜索引擎检索 sitemap 链接
- Crawl-delay：搜索引擎检索间隔(单位秒)
- 文件保存时尽量使用 utf-8 编码

举例
```
User-agent:*
Disallow:/admin/
Sitemap:http://www.domain.com/sitemap.xml
```

禁止任何搜索引擎抓取网站，设置方法如下
```
User-agent:*
Disallow:/
```

参考资料：
- <http://www.robotstxt.org/robotstxt.html>
- <http://tool.chinaz.com/robots>

###  sitemap.xml网站地图文件
　　网站地图也就是sitemap，是一个网站链接的容器。很多网站的连接层次比较深，蜘蛛很难抓取到，网站地图可以方便搜索引擎蜘蛛抓取网站页面，通过抓取网站页面，清晰了解网站的架构，网站地图一般存放在根目录下并命名为sitemap，为搜索引擎蜘蛛指路，增加网站重要内容页面的收录。网站地图就是根据网站的结构、框架、内容，生成的导航网页文件。

举例
```xml
<?xml version="1.0" encoding="utf-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
<url>
<loc>http://www.domain.com/</loc>
<priority>0.9</priority>
<lastmod>2017-04-07</lastmod>
<changefreq>always</changefreq>
</url>
<url>
<loc>http://www.domain.com/sitemap.html</loc>
<priority>0.5</priority>
<lastmod>2017-04-07</lastmod>
<changefreq>always</changefreq>
</url>
</urlset>
```

(未完待续……)