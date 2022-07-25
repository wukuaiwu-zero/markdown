### Git--分布式版本控制系统

将目录下的所有文件上传至Git生成一个版本库  
该目录下所有文件修改新增删除都可以被Git跟  
踪并可以在任何时候还原其以前版本

#### 创建仓库

    This is code 🌐

    touch README.md  // 创建仓库说明文档

    git init // 初始化仓库

所有的版本控制系统只能跟踪文本文件改动，包括但不限于txt html css等程序代  
码文件，可以通过Git来访问这些文件的每次改动，但是图片 视频 word等二级制文  
件也可以由Git控制但无法通过Git访问这些文件的变化

#### 创建第一个版本

    This is code 🌐

    git add . // 当前目录下的所有文件上传至缓存区

    git add README.md // 指定文件上传至缓存区

    git commit -m'上传至仓库的说明' // 将缓存区的文件上传至本地仓库

    git status // 查看缓存区文件状态是否有修改后未提交文件

    git diff // 查看缓存区文件修改前后的内容

    git diff README.md // 查看缓存区指定文件修改前后的内容

#### Git版本管理

根据Git提交记录来决定回退的版本或回退后并选择前进的版本

    This is code 🌐
    
    git log // 时间由近至远的仓库版本日志 版本提交时间 提交人 提交备注

    git log --pretty=oneline // 仓库版本日志更直观

    git reset --hard HEAD^ // 回退上个版本

    git reset --hard HEAD^^ // 回退上上个版本

    git reset --hard HEAD~5 // 回退前五个版本

    git reflog // 查看所有版本号

    git reset --hard 版本号 // 通过版本号来回退或者恢复版本

#### Git工作区和缓存区

git所在的目录为工作区，对文件的修改添加等操作都属于工作区  
git不属于工作区而是版本库 版本库中有自动创建的第一个默认分支master的缓存区
使用Git将文件提交至版本库：  
  通过git add 将文件提交至缓存区
  使用git commit 将缓存区的文件提交到当前分支

#### Git撤销修改和删除文件

    This is code 🌐

    git checkout --file // 撤销指定文件的修改和删除

当使用git checkout的时候有两种情况：  
  未上传至缓存区时 使用git checkout会回退至和版本库中文件状态一样  
  当文件已上传至缓存区并再次修改 此时使用git checkout则会回到文件刚提交至缓存区状态
  
### Github--远程仓库

Git仓库和Github仓库之间的传输通过SSH加密

#### 创建SSH Key

检查用户目录下是否有.ssh目录且目录下是否包含id_rsa和id_rsa.pub  
如果没有则执行

    This is code 🌐

    ssh-keygen -t rsa –C “youremail@example.com”

#### 在Github中添加SSH

登录Github 找到Setting中的SSH Keys填写SSH标题名称并粘贴id_rsa.pub内容  
点击Add Key可以看到添加的key

#### 远程仓库的建立

点击右上角的New repository选项进入Create a new repository页面
自上至下为:

1. 拥有者仓库名称
2. 仓库描述  
3. 共享或私有  
4. 初始化仓库方式(如果导入现有的储存库则跳过此步骤)

   1. 添加README文件(在此可以编写您的项目描述)

5. 添加.gitignore(选择不被追踪的文件类型)
6. 选择许可证类型(决定其他人是否可以和你一起处理代码)
7. create repository  

#### 本地仓库和远程仓库的连接

在本地项目目录下添加Git后，再将本地的新建分支或主分支推送到远程仓库

    This is code 🌐

    git remote add origin 'yourRepository' // 将你的仓库从Github添加至本地仓库

    git branch -M main // 创建main分支并切换到该分支

    git push -u origin main // 推送main分支至远程仓库

### 创建与合并分支

    This is code 🌐

    git checkout -b dev // 创建并切换分支

    git branch dev // 创建dev分支

    git checkout dev // 切换dev分支

    git branch // 查看分支

    git merge dev // 合并dev分支

    git branch -d dev // 删除dev分支

1. Git中每一次的提交都会将其处理成一条时间线，不同分支具有不同的时间线  
2. HEAD指向当前分支，当前分支提交后形成一个Git版本  
3. 使用查看分支命令可以看到当前所在的分支名称前会有星号标记  
4. 不同分支在未合并前改动并不相互影响，且合并分支是将指定分支合并到当前分支上
5. 如果同一个文件在两个分支上修改了不同的内容则会出现标识，当前分支会标记HEAD
6. 通过添加 --no--ff 的方式来禁用快速模式，快速模式下合并分支后会丢失被合并分支信息

### 分支处理

Git一般使用Fast forward模式，该模式下删除分支会丢失分支信息  
一般master分支为稳定发布版本的分支，而开发工作往往在新建分支中处理  
如果主分支中出现Bug，则可以通过新建一个临时分支来进行修复，修复完成之后合并分支并删除  
如果Bug分支和开发分支共同进行时，可以先将工作分支隐藏，然后重新创建修复Bug的分支  
修复Bug之前先确定Bug出现在哪个分支，然后从该分支创建修复Bug的分支，修复后合并  
恢复隐藏分支后有两种情况，恢复分支不删除隐藏列表中的记录和恢复分支并删除隐藏列表中的记录

    This is code 🌐

    git stash // 隐藏当前分支

    git stash list // 查看隐藏分支

    git stash apply // 恢复隐藏的分支且不删除隐藏分支记录

    git stash drop // 删除隐藏分支记录

    git stash pop // 恢复隐藏分支且删除分支记录

### 多人协作

远程仓库克隆项目时，实际是将本地的master分支和远程库的master分支对应起来且默认远程库名称为origin  
推送分支就是把当前分支提交至远程库中，推送时须指定本地分支，这样Git就会将本地推送的分支和远程库指定的分支同步  
修复Bug分支不需要推送，可先进行合并分支至主分支中，然后推送主分支  
需要多人协作处理项目时，先将项目克隆至本地并创建和远程仓库开发分支一样的分支来进行工作
当不同的人修改同分支下的同一文件时会产生冲突，应先抓取分支的修改内容，再提交

    This is code 🌐

    git remote // 查看远程仓库信息

    git remote -v // 查看远程仓库详细信息

    git push origin dev // 推送本地分支至远程仓库指定分支

    git checkout -b dev origin/dev // 拉去远程仓库dev分支并在本地仓库创建dev分支

### Git工作原理


                                    pull
         ----------------------------------------------------------------
        |                                                                |
        |           add            commit                  push          | 
        |         --------      ------------            -----------      |
        V        |        |    |            |          |           |     |
    workspace(工作区)--->index(缓存区)--->repository(本地仓库)--->remote(远程仓库)
                |                            |      |                |
                 ----------------------------        ----------------
                          checkout                      fetch/clone
