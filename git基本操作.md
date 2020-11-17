## git 学习

### 常用命令

1. cd d: 进入文件夹
2. cd .. 返回上一层目录
3. mkdir 创建目录
4. pwd 显示当前工作目录的全路径
5. touch xx 新建 xx 文件
6. vi xx 编辑 xx 文件，按 i 切换到编辑模式，按 esc 切换到命令模式，输入冒号:wq 回车，保存并返回
7. rm 删除文件
8. ls 查看当前目录所有文件
9. clear 清屏

### 全局配置

1. 配置用户名：git config --global user.name "你的 git 名称"
2. 配置用户邮箱：git config --global user.email "你的 git 验证邮箱"
3. 一台电脑配置一次就可以了
4. 查看你的配置信息：git config --list

### 文件夹作为工作区

1. git init 初始化版本库
2. git add . 将所有改动（新增，修改，删除）提交到暂存区
3. git commit -m '这里是提交注释' 将暂存区提交到本地仓库

### 辅助命令

1. git status 查看当前目录的操作状态
2. git reflog 查看简易版日志
3. git log 查看日志

### 版本回退

1. git reset --hard HEAD^ 退回到上一个版本
2. git reset --hard 1818181 退回到置顶版本

### 将本地仓库提交到远程仓库

1. git remote add origin https://github.com/Sww-echo/liusang.git 本地仓库和远程仓库关联
2. git remote -v 查看本地仓库与远程仓库关联状态
3. git push -u origin master（第一次推送）
   get push 把本地仓库推送到远程仓库
   -u origin master 设置默认提交主分支 master 到 origin（设置一次，下次直接 Git push 就行）
4. git push origin 分支名 提交到其他分支
5. git push -u -f origin master 强制推送到远程，不推荐！！

### 下载项目到本地

1. git clone 适用于本地没项目，直接从远程克隆到本地（整个版本库克隆下来）
2. git pull 本地没有，直接从远程更新到本地
3. 一定要先把工作区的修改提交到本地仓库再更新远程到本地
4. 如果本地有该项目，应该直接更新到本地：git pull

### 分支操作

1. git branch 查看本地所有分支（git branch -r 查看远程分支）
2. git branch test 创建 test 分支（test 为分支名）
3. git checkout test 切换到 test 分支
4. 未提交到本地仓库切换不了分支，切换分支后，工作区的代码会自动切换到对应分支的代码
5. git merge test 把 test 分支合并到当前分支
6. git branch -d test 删除 test 分支
7. git pull origin test 更新代码到本地，会自动合并到当前分支
8. git fetch origin test 更新代码到本地，不会合并到当前分支
9. git merge FETCH_HEAD 把 FETCH_HEAD 合并到当前分支

### git 忽略列表

1. 新建.gitignore 文件，列出不需要提交到版本库的文件及目录（必须将.gitignore 文件忽略）

#### 项目版本管理

- 第一次下载项目版本（从远程 github 仓库分支到本地仓库分支）

> git clone github 上新创建的项目 https 标识（路径）

- 第一次发布项目版本（从本地仓库分支到远程 github 仓库分支）

> 1. git add .
> 2. git commit -m"提交日志说明"
> 3. git push -u origin master

- 后续提交版本（从本地仓库分支到远程 github 仓库分支）

> git push origin master （与第一次发布的操作相比只是少了一个-u）

- 后续更新 版本 （从远程 github 仓库分支到本地仓库分支）

> git pull

【注：】后续每一次提交新版本之前，要遵循先更新，后上传的原则，目的是为了避免出现版本冲突的问题，即：

> git pull
>
> git push origin master
>
> 以上操作是没有冲突的情况下的操作，如果 git pull 更新后,很有可能出现版本冲突，处理好冲突后，再作如下处理：
>
> 1. git add .
> 2. git commit -m"处理了冲突"
> 3. git push origin master
