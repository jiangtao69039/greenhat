##                       仿写绿叶学习网

* [绿叶学习网](http://www.lvyestudy.com/) <http://www.lvyestudy.com/>

#### 要求:

* 0基础

* 仿写时每一步详细记录在本项目"笔记"文件夹中,格式用markdown
* html文件放在src中



#### 如何使用git协作

* 先fork一份本项目
* fork完毕后项目会出现在你github账户的repository中
* 将你账户中fork的本项目clone到你本地
* 进入项目目录,执行git remote add upstream https://github.com/jiangtao69039/greenhat.git 
* 上一步是为了将你本地的项目和原作者的项目关联,使用git remove -v 可以看到你本地项目有origin和upstream两个远程地址,origin表示你github账户地址,upstream表示原作者项目的github地址



#### 做好上面的工作后,你就可以开始修改你本地的项目了

* 务必在你本地项目中先执行 git checkout -b yourBranchName 来切换到一个新分支,不要在master分支直接做开发/修改
* 在你新切出的分支上添加代码



#### 完成了修改,如何提交给原项目作者?

* 先在你本地执行 git checkout master  切换到master分支
* 再执行git pull upstream master   这一步将原作者项目master分支最新内容拉取到你本地的master分支上(由于你的修改在你自己的新分支上,所以这里不会出现冲突)
* 执行 git checkout yourBranchName 切到你自己的开发分支上(记得你分支上的修改commit)
* 执行 git rebase -i upstream/master  这一步是将原作者项目的新内容合并到你的开发分支上,可能会出现冲突
* 如果有冲突就解决掉,再git add 添加后使用git rebase --continue继续完成之前由冲突引起的中断
* 执行git push -f origin yourBranchName 来将你的分支提交到你的远程仓库
* 最后,在你github的项目页面里点击pull Request ,原作者就能收到你的合并请求了