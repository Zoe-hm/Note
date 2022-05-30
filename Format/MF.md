# 本地连接远程
```git
git --version 
git config --global init.defaultBranch main 
git init 
git add .
git commit -m " "
git remote add origin git@git...
> git remote add 名 git@git...
git pull --rebase origin main
> git pull origin main --allow-unrelated-histories
> git pull origin main
git push origin main
```

# issues
1. REBASE 1/1
> git add .
> git commit --no-verify -m "提交描述"
> git status
> git rebase --continue
> git status
2. 