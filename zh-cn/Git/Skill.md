# 技巧

### git 仓库误上传了 /.idea 这类编辑器产生的文件，后来在 .gitignore 中做了忽略但线上的如何删除？

1. 在项目目录下执行：`git rm -r --cached  .idea/`
2. 将 .idea/ 添加到 ignore 文件
3. 其它原理类似
