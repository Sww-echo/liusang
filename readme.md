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

### 文件夹作为工作区

1. git init 初始化版本库
2. git add . 将所有改动（新增，修改，删除）提交到暂存区
3. git commit -m '这里是提交注释' 将暂存区提交到本地仓库
4.

### 辅助命令

1. git status 查看当前目录的操作状态
2. git reflog 查看简易版日志

### 版本回退

1. git reset --hard HEAD^ 退回到上一个版本
2. git reset --hard 1818181 退回到置顶版本

### 将本地仓库提交到远程仓库

1. git remote add origin https://github.com/Sww-echo/liusang.git 本地仓库和远程仓库关联
2. git remote -v 查看本地仓库关联
3. git push -u origin master
   get push 把本地仓库推送到远程仓库
   -u origin master 设置默认提交主分支 master 到 origin（设置一次，下次直接 Git push 就行）
4. git push origin 分支名 提交到其他分支
123456789
