# .gitattributes 文件

> Git 属性文件

### 导出项目归档（git archive）发挥作用
`export-ignore`当归档的时候，可以设置 Git 不导出某些文件和目录。
```markdown
tests/ export-ignore
.travis.yml export-ignore
```

### 参考资料
- <https://git-scm.com/book/zh/v2/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-Git-%E5%B1%9E%E6%80%A7>