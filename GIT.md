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

1. git status 查看当前项目状态  
	- 红色：表示本地改动了，需要添加到暂存区来。
	- 绿色：表示已添加到暂存区。（执行了git add .后就变成了绿色）  
2. git log 查看提交记录  
	- git log --author="作者名称" 查看作者名称的提交记录，作者名称是包含匹配  
	- git log --author="作者名称1|作者名称2" 查看作者名称1或者作者名称2的提交记录  
3. git rm [file] 删除某个文件  

4. git mv [file] [newfile]






## GIT创建新项目

1. git 初始化  
git init

2. git 添加  
git add .

3. git 提交到仓库  
git commit -m 'new project'

4. git 关联远程仓库  
git remote add origin 仓库地址

5. git 推送到远程仓库  
git push -u origin master  
*输入用户名和密码，密码是在github设置中心生成的personal access tokens*


