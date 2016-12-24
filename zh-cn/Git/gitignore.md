# .gitignore 文件

> Git 忽略文件

### 示例
- `# 说明一下` 注释说明
- `/.idea/` 忽略根目录下的某个文件夹(注意最前面有斜杠 / )
- `test/` 忽略目录 test 下的全部内容，注意，不管是根目录下的 /test/ 目录，还是某个子目录 /child/test/ 目录，都会被忽略
- `*.swp` 忽略所有 *.swp 文件
- `Thumbs.db` `/test/do.c` 忽略某个具体文件
- `!.gitignore` `!/fw/sf/` 避免忽略规则来忽略某个具体文件或某个文件夹

### 参考资料
- <https://github.com/github/gitignore>