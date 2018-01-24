# 修改历史邮箱地址

参考：

- 《[Git 工具 - 重写历史](https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E9%87%8D%E5%86%99%E5%8E%86%E5%8F%B2)》 的“全局修改邮箱地址”部分
- GitHub 的 《[Changing author info](https://help.github.com/articles/changing-author-info/)》
  * 涉及的 Sell 脚本：<https://gist.github.com/octocat/0831f3fbd83ac4d46451>(可能需要梯子)

```bash
#!/bin/sh

git filter-branch --env-filter '

OLD_EMAIL="旧的邮箱地址"
CORRECT_NAME="新的姓名"
CORRECT_EMAIL="新的邮箱地址"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags

```
