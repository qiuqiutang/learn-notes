## GIT版本查看和配置用户名、邮箱

1. 查看版本  
git --version

2. 用户名  
git config --global user.name "用户名"

3. 邮箱  
git config --global user.email "邮箱地址"  github 注册的邮箱

4. 查看配置的用户名和邮箱  
git config --global --list



## GIT常用指令

1. git status                                 (查看当前项目状态)  
	- 红色：表示本地改动了，需要添加到暂存区来。
	- 绿色：表示已添加到暂存区。执行了git add .后就变成了绿色

2. git log                                    (查看提交记录)  
	- git log --author="作者名称"              (查看作者名称的提交记录，作者名称是包含匹配)  
	- git log --author="作者名称1|作者名称2"    (查看作者名称1或者作者名称2的提交记录)  
	- git log --pretty=oneline [file]         (查看文件变化,输出提交的id)
	- git log --oneline                       (查看简易的日志)
	- git log --oneline --graph               (查看版本路线)

3. git rm [file]                              (删除某个文件)  

4. git mv [file] [newfile]                    (重命名)
	- git mv [file] [文件夹名称]               (移动文件到文件夹中)  
	- git mv [file] [文件夹名称]/[newfile]     (移动到文件夹中并重命名) 

5. git show [id]                             (查看具体某提交id的详情)          

6. git diff                                  (比较文件在暂存区和工作区的差异)  

7. git checkout -- [file]                    (拉取暂存区文件，并将其替换成工作区文件)  
	- git checkout [id] -- [file]            (拉取暂存区里某个版本中的某个文件) 
	- git checkout [分支名称]                （切换到某个分支）
	- git checkout -b [分支名称]             （创建分支，并且直接切换到创建的分支）

8. git reset HEAD [file]                     (对于已添加到暂存区的文件进行撤销追踪)  
	- git reset --hard HEAD^^^               (^的数量表示回退的版本提交的次数)  
	- git reset --hard [id]                  (回退到指定版本，id是通过git log 输出的版本id)

9. git tag                                   (查看标签)
	- git tag [标签名称]                     （给最近的提交创建一个标签）
	- git tag [标签名称] [id]                 (给某个提交创建一个标签)
    - git tag -d [标签名称]                  （删除某个标签）
    - git push origin v1.0                   (把标签推送到远程仓库)
    - git push --delete origin [标签名称]    （删除远程仓库的标签）

10. git branch                               (查看分支)
	- git branch [分支名称]                  （创建分支）
	- git branch -d [分支名称]               （删除分支，注：不能删除当前分支）
	- git branch -D [分支名称]               （强制删除分支，注：不能删除当前分支）
	- git branch -av                         (查看所有的分支信息)
	- git push origin HEAD -u               （将新建的分支推送到远程仓库）
	- git push origin --delete [分支名]       (删除远程仓库的分支)

11. git push
	- git push origin [分支名称]  
	- git push origin [标签名称]              （创建远程仓库的标签）
	- git push origin --delete [标签名称]     （删除远程仓库的标签）
	- git push origin HEAD -u                （创建远程仓库的分支）
	- git push origin --delete [分支名称]     （删除远程仓库的分支）

12. git merge [分支名称]                       (合并分支)  
	** 出现冲突后的解决方法： **
	- 忽略其它分支  
	git merge --abort                         (忽略其它分支的内容，保留当前分支)
	- 手动修改冲突内容  
	> git add .  
	> git commit 进入可编辑的界面  
	> 输入 i 进入编辑状态，输入修改的备注  
	> 输入 esc 退出编辑状态  
	> 输入 :wq 保存并退出   
	> git add .  
	> git commit -m "提交备注"  
	> git push   

13. git fetch 与 git push
    - git fetch                              (拉取远程仓库的分支, 本地仓库的代码并没有更改)          
	- git pull                               (拉取远程仓库的代码，并与本地分支进行合并)  
		git pull = git fetch + git merge

## GIT创建新项目

1. git 初始化  
git init

2. git 添加到暂存区  
git add .

3. git 提交到仓库  
git commit -m 'new project'

4. git 关联远程仓库  
git remote add origin 仓库地址

5. git 推送到远程仓库  
git push -u origin master  
*输入用户名和密码，密码是在github设置中心生成的personal access tokens*



## GIT修改提交

1. git 添加到暂存区   
git add .

2. git 提交到仓库  
git commit -m '操作事项'

3. git 推送到远程仓库  
git push origin master



## GIT将当前修改的内容提交到新的分支上

1. 在当前的分支上的修改暂存起来  
git stash

2. 暂存后，在本地新建分支（new_branch为新分支的名字） 
git checkout -b new_branch 

3. 将暂存的修改放到新建分支中 
git stash pop

4. 使用命令进行常规的add、commit 步骤 
git add .
git commit -m '操作事项'

5. 将提交的内容push到远程服务器（在远程也同步新建分支new_branch） 
git push origin new_branch:new_branch


## GIT 拓展

- Octotree - GitHub code tree  树结构方式查看github项目

- Enhanced GitHub  查看单个文件的大小

- GitZip for github  下载选中的文件夹或者文件








