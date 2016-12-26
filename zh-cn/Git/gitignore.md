# .gitignore 文件

> Git 忽略文件

### 官方说明链接
<https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E8%AE%B0%E5%BD%95%E6%AF%8F%E6%AC%A1%E6%9B%B4%E6%96%B0%E5%88%B0%E4%BB%93%E5%BA%93#%e5%bf%bd%e7%95%a5%e6%96%87%e4%bb%b6>

### 示例
- `# 说明一下` 注释说明
- `/.idea/` 忽略根目录下的某个文件夹(注意最前面有斜杠 / )
- `test/` 忽略目录 test 下的全部内容，注意，不管是根目录下的 /test/ 目录，还是某个子目录 /child/test/ 目录，都会被忽略
- `*.swp` 忽略所有 *.swp 文件
- `Thumbs.db` `/test/do.c` 忽略某个具体文件
- `!.gitignore` `!/fw/sf/` 避免忽略规则来忽略某个具体文件或某个文件夹

### 参考
- <https://github.com/github/gitignore>