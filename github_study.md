# 1 配置SSH服务
## 1.1 获取ssh密匙  
- ssh-keygen -t rsa -C "690939050@qq.com"  

## 1.2 在github添加密匙  
- id_rsa.pub

## 1.3 测试是否已经成功连上了GitHub  
- ssh -T  git@github.com

## 1.4 设置全局变量  
- git config --global user.name "hai"
- git config --global user.email "690939050@qq.com"
---
# 2 设置忽略文件
- vi ~/.gitignore  
---
# 3 常用命令：
## 3.1 基本命令
- git status
- git add  file
- git commit -m "..."
- git push

---
- git config --global core.safecrlf false  //取消windows下换行警告
- git log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
---
## 3.1 设置命令别名：
- git config --global alias.ci  commit
- git config --global alias.hi log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
---

## 3.2 添加远程创库的链接：
- git remot add origin https://github.com/dhai1011/xxx