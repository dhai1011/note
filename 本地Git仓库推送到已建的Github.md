# 1 进入项目目录
cd /xx/
 
# 2 初始化本地git仓库
git init
 
# 3 在你的项目中设置你在GitHub新建的公开仓库，并命名为 origin
git remote add origin git@github.com:dhai1011/xxx
 
# 4 拉取Github仓库上master主分支上的文件
git pull origin master
 
##########代码提交并推送#################
 
# 5 把所有的代码加入缓存区 除.gitignore排除外
git add *
 
# 6 提交代码，并附上消息："init"
git commit -m "init"
 
# 7 推送代码到远程仓库 origin 的master主分支上
git push origin master
 
# 完成
