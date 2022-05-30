**前提是，已经安装好Vscode和Git**
1. 新建文件，拉入Vscode图标(就是用Vscode打开)，写入项目。
2. 点击左侧源代码管理，直接显示文件，或者刷新后显示。点击对勾提交，根据左下角同样标志的名称，写入相同名字与文本框中(因为最新的Github分支名称变为main，可以再Vscode重命名master分支为main)，可以看到数字消失。
3. *第一次先看4.*第一次想要上传，需要点击三个点，选择推送(push)，这是右下角出现弹窗，让添加远程(也就是Github库)，点击添加，这是中间出现弹窗，点击允许(Allow)，就会让你连接Github。再点击三个点，选择推送到，从出现的文本框下面点从Github添加远程，然后输入你想要连接到的Github库名(没有就到Github新建一个repo)。
4. 第一次上传，这样可能不可行。首先现在的Github是main分支，而Vscode是master分支，需要再Vscode终端更改。下面是整个上传流程代码。
```Git
git branch -m main 或者[git branch -m master main]#改分支master为main
git branch -v #看看有没有改成main
//git remote add origin git@github.com:你的Github名/库名.git #添加远程
git remote add 库名 git@github.com:你的Github名/库名.git #添加远程
git pull origin main 或者[git pull origin main -f]#把本地仓库连接到远程库
git pull --rebase origin main #Github远程有ReadMe文件，而本地没有，生成一个。
git push orgin main #推送上传Github
```
5. 查看Github库中有没有上传的内容。之后就可以点击三个点中的推送到，直接点击推送库上传。
```
git branch -D master #删除master分支
git branch -a #查看所有分支
git branch -r #查看远程分支
```
很奇怪：
git branch -vv #发现有库名的main，有origin的main
所以决定删除远程的origin main：点三个点，选择远程中的删除远程存储库，点击文本框中想要删除的origin main。
之后想要上传，就写：
git pull Github的库名 main
在查看远程库：git branch -r就只有一个main了。