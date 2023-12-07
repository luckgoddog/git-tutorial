#Git 使用教程

- fix-B
- 创建一个仓库>切换到仓库目录下>初始化仓库：`mkdir git-turtorial` `cd git-turtorial` `git init`
- 查看仓库的状态   `git status`
- 向暂存区中添加文件  README.md `git add README.md` 
- 保存仓库的历史记录 `git commit`     记述一行提交信息 `git commit -m "First commit"`
- 查看提交日志 `git log`  只显示第一行简述信息  `git log --pretty=short` 可以指定文件 `git log README.md`
- 显示文件的变动 `git log -p`  可以指定文件 `git log -p README.md`
- 查看更改前后的差别 `git diff`
- 查看工作树和最新提交的差别  `git diff HEAD`

