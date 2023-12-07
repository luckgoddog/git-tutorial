#Git 使用教程

- 首先设置用户名和邮箱一个文件夹中只允许设置一次 `git config --global user.name "John Doe"` `git config --global user.email johndoe@example.com`
- 创建一个仓库>切换到仓库目录下>初始化仓库：`mkdir git-turtorial` `cd git-turtorial` `git init`
- 查看仓库的状态   `git status`
- 向暂存区中添加文件  README.md `git add README.md` 
- 保存仓库的历史记录 `git commit`     记述一行提交信息 `git commit -m "First commit"`
- 查看提交日志 `git log`  只显示第一行简述信息  `git log --pretty=short` 可以指定文件 `git log README.md`
- 显示文件的变动 `git log -p`  可以指定文件 `git log -p README.md`
- 查看更改前后的差别 `git diff`
- 查看工作树和最新提交的差别  `git diff HEAD`  一般在执行 `git commit` 命令之前先执行 `git diff HEAD` 命令，查看本次提交与上次提交之间有什么差别，等确认完毕之后再进行提交
- 分支的操作  
  - `git branch` 显示分支一览表
  - `git checkout -b` 创建、切换分支  例如 创建名为 feature-A 的分支：`git checkout -b feature-A`
  - `git checkout master`切换到 master 分支    `git checkout -`  连字符 - 代替分支名 切换到上一个分支
  - 特性分支 `git merge`  合并分支  ` git merge --no-ff feature-A`为了在历史记录中明确记录下本次分支合并，我们需要创建合并提交。因此，在合并时加上 `--no-ff` 参数
  - `git log --graph` 以图表形式查看分支

- 更改提交的操作
  - `git reset`回溯历史版本 `git rest --hard 目标时间点的哈希值` 例如 : `git reset --hard fd0cbf0d4a25f747230694d95cac1be72d33441d`   由于 所有文件都回溯到了指定哈希值对应的时间点上，README.md 文件的 内容也恢复到了当时的状态
  - `git reflog`命令，查看当前仓库的操作日志，在日志中找出 回溯历史之前的哈希值，通过 `git reset --hard`命令恢复到回溯历 史前的状态

- 消除冲突  分支在合并过程中有时因为更改部分发生了冲突  用编辑器打开 README.md 文件  ======= 以上的部分是当前 HEAD 的内容，以下的部分是要合并的分支中的内容。我们在编辑器中将其改成想要的样子  解决冲突之后  重新执行 `git add` 与 `git commit`命令    `git commit --amend`修改提交信息  会直接启动编辑器 进行修改

- feature-C
