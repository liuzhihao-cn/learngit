# learngit
GitHub 与 Gitee 使用同一个本地仓

## 前言

无论是使用 GitHub 还是 Gitee，应是知晓些 git 操作命令的。以此仓库为例，学习使用 git、 GitHub 和 Gitee。

## git 基本操作指令

> Git 不仅仅是个版本控制系统，它也是个内容管理系统(CMS)，工作管理系统等。

参考：[git 简明指南 (菜鸟)](https://www.runoob.com/manual/git-guide/)

### 安装

在 [Git 官网](https://git-scm.com/) 下载并安装对应所使用电脑系统的 git 版本。

以 Windows10 系统为例，安装 git 后，任意空白位置点击右键，会显示有 git 相关内容。

![Win10安装git-右键](.\fig\Win10安装git-右键.png)
![Win10安装git-右键](https://github.com/liuzhihao-cn/learngit/blob/main/fig/%E5%90%AF%E5%8A%A8git.png)

### 基本操作指令

![git操作指令关系](.\fig\git操作指令关系.png)

#### 基本设置

**`$ git config --global user.name "[name]"`**

设置 git 全局用户名，用于提交改动

---

**`$ git config --global user.email "[email address]"`**

设置 git 全局用户邮箱，用于提交改动

---

**`$ git config --global color.ui auto`**

设置命令行颜色，不常使用

---

#### 创建新本地仓库

**`$ git init [project-name] ` **或 **`$ git init `**

初始化仓库，建立新的本地空仓库

---

**`$ git clone [url]`**

克隆一个本地仓库的克隆版本或者将远端服务器仓库克隆至本地

---

#### 提交与修改

**`$ git status`**

显示有改动的文件，新建或者修改的文件

---

**`$ git diff`**

比较暂存区和工作区文件的不同

---

**`$ git add [file]`**

添加文件到暂存区

---

**`$ git --staged`**

【TODO】

---

**`$ git reset [file]`**

回退版本

---

**`$ git commit -m "[descriptive message]"`**

提交暂存区文件至本地仓库

---

**`$ git rm [file]`**

从工作区中删除文件

---

**`$ git rm --cached [file]`**

从版本控制中删除文件，但是保留本地工作区文件

---

**`$ git mv [file-original] [file-renamed]`**

移动或重命名工作区文件

---

**`$ git log `**

查看历史提交记录

---

**`$ git blame<file>`**

以列表形式查看指定文件的历史修改记录

---

#### 分支操作指令



#### 远程操作指令

**`$ git remote `**

关联远程仓库

```git
$ git remote add [shortname] [url]  	# 关联远程版本库
$ git remote add github [url]		# 关联 GitHub 远程仓库
$ git remote add gitee [url]		# 关联 Gitee 远程仓库
```



---

**`$ git fetch`**

从远程获取代码库

---

**`$ git pull`**

下载远程代码并合并

```git
$ git pull [shortname] [local_branch]:[remote_branch]	# 下载远程仓库代码 本地与远程分支相同，可省略远程分支名

$ git pull
$ git pull github main					# 下载 GitHub 远程仓库 main 分支代码
$ git pull gitee master					# 下载 Gitee 远程仓库 master 分支代码
```



---

**`$ git push`**

上传远程代码并合并

```git 
$ git push -u [shortname] [local_branch]:[remote_branch] 	# 下载远程仓库代码 本地与远程分支相同，可省略远程分支名
$ git push -u github main					# 下载 GitHub 远程仓库 main 分支代码
$ git push -u gitee master					# 下载 Gitee 远程仓库 master 分支代码
```



---



### 创建本地仓库

1. 创建一新文件夹，并打开
2. 空白位置处右键，点击 [Git Bash Here]，会启动 git 终端

![启动git](.\fig\启动git.png)

3. 使用**`$ git config --global user.name "[name]"`**  和 **`$ git config --global user.email "[email address]"`** 指令设置全局用户名和用户邮箱地址

   ![设置用户名](.\fig\设置用户名.png)![设置邮箱地址](.\fig\设置邮箱地址.png)

4. 输入： `git init` 指令，初始化仓库，建立一个新的本地空仓库。

![初始化仓库](.\fig\初始化仓库.png)

**修改 git 终端字体大小**

启动 git 终端，右键选择 `options` ，选择 `Text` 点击`Select`，

![git终端修改字体大小](.\fig\git终端修改字体大小.png)

## git 实现本地仓库与 GitHub 和 Gitee 关联

#### 远程仓库操作

首先生成公钥：`ssh-keygen -t rsa -C "你的github邮箱"` ，生成的公钥存储与**C:\Users\用户名\.ssh** 目录下的 **id_rsa.pud** 文件中；

然后分别找到 GitHub 和 Gitee 配置公钥的地方，把用户主目录下的 **.ssh\id_rsa.pub** 文件中的内容粘贴进去。

之后在 GitHub 和 Gitee 上分别建立相同名称的仓库，如 **learngit** ，此处不赘述远端新建仓库过程。下面介绍本地仓库关联远程仓库操作。

#### 本地操作

选择以路径，新建文件夹，文件夹名称与所建立仓库名称一致；

双击打开仓库文件夹，右键选择 **Git Bash Here** ；

`$ git init ` 初始化仓库；

`$ git remote add github [githubRepoURL]` 连接到 GitHub 仓库；

`$ git remote add gitee [giteeRepoURL]` 连接到 Gitee 仓库；

`$ git remote -v` 查看仓库连接情况。

![关联至远程仓库](E:\Git\testgit\fig\关联至远程仓库.png)

```git
$ git init
$ git remote add github [githubRepoURL]
$ git remote add gitee [giteeRepoURL]
$ git remote -v
```

这时在本地进行相应的修改操作，并添加到本地仓库之后，只要分别执行下面这两条语句（不分先后顺序），就可以将本地commit信息push到两个远程仓库的主分支（master）中。

```git
$ git push github main
$ git push gitee master
```

![推送GitHub](.\fig\推送GitHub.png)

![推送Gitee](.\fig\推送Gitee.png)



## 多台设备

第一步操作同样是生成设备的公钥，和填写到 GitHub 和 Gitee 个人账号的SSH公钥中。

第二步关联或者克隆远程仓库只本地

	1. 本地仓库关联远程仓库

此时，因为是第二甚至更多设备关联此远程仓库，所以是在一个有文件的仓库中关联到本地，那么有以下几个操作步骤：

``` git
1.
git init 				# 初始化仓库

2.
git remote add github [github-URL]	# 本地仓库关联 github 远程仓库
git remote add gitee [gitee-URL]	# 本地仓库关联 gitee 远程仓库

3.
git remote -v				# 查看关联远程仓库信息

4.
# 下面两条指令二选一
git pull github main:mastr		# 拉取远程 github 仓库文件至本地
git pull gitee master:mastr		# 拉取远程 github 仓库文件至本地

5.
git branch --set-upstream-to=origin/master mastr # 本地master设置为远程master  此条指令可以不用，目前未用到

6.
git status 				# 查看有改动的文件和文件夹

7.
git add . 				# 工作区改动的文件和文件夹添加至暂存区

8.
git commit -m "添加的注释"		    # 暂存区文件提交至本地仓库

9.
git push github master:main		# 本地仓库推送至 github 远程仓库
git push gitee master:master 		# 本地仓库推送至 gitee 远程仓库
```



2. 克隆远程仓库至本地

在本地克隆远程仓库。

```git
1.
git clone [URL] 		# 克隆远程仓库地址

2.
git pull			# 修改之前先拉取远程仓库文件
git status			# 克隆之后，做修改后，查看修改文件和文件夹
git add .			# 添加修改文件和文件夹至暂存区
git commit -m ""		# 提交至本地仓库

3.
git push			# 将本地仓库推动到远程
```





## 错误记录

### 1. `fatal: refusing to merge unrelated histories`

在 `git pull` 或 `git push` 时可能会遇到，原因是两个分支没有取得关系。

**解决方法：** 在操作命令后面加 `--allow-unrelated-histories`

例如：

```git
git pull --allow-unrelated-histories
git push --allow-unrelated-histories
git merge master --allow-unrelated-histories
```

## 2. 强制推送

```git
git push -f
```

