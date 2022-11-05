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

![Win10安装git-右键](E:\Git\testgit\fig\Win10安装git-右键.png)

### 基本操作指令

![git操作指令关系](E:\Git\testgit\fig\git操作指令关系.png)

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
$ git remote add [shortname] [url]  # 关联远程版本库
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
$ git pull github main				# 下载 GitHub 远程仓库 main 分支代码
$ git pull gitee master				# 下载 Gitee 远程仓库 master 分支代码
```



---

**`$ git push`**

上传远程代码并合并

```git 
$ git push -u [shortname] [local_branch]:[remote_branch] 	# 下载远程仓库代码 本地与远程分支相同，可省略远程分支名
$ git push -u github main				# 下载 GitHub 远程仓库 main 分支代码
$ git push -u gitee master				# 下载 Gitee 远程仓库 master 分支代码
```



---



### 创建本地仓库

1. 创建一新文件夹，并打开
2. 空白位置处右键，点击 [Git Bash Here]，会启动 git 终端

![启动git](E:\Git\testgit\fig\启动git.png)

3. 使用**`$ git config --global user.name "[name]"`**  和 **`$ git config --global user.email "[email address]"`** 指令设置全局用户名和用户邮箱地址

   ![设置用户名](E:\Git\testgit\fig\设置用户名.png)![设置邮箱地址](E:\Git\testgit\fig\设置邮箱地址.png)

4. 输入： `git init` 指令，初始化仓库，建立一个新的本地空仓库。

![初始化仓库](E:\Git\testgit\fig\初始化仓库.png)

**修改 git 终端字体大小**

启动 git 终端，右键选择 `options` ，选择 `Text` 点击`Select`，

![git终端修改字体大小](E:\Git\testgit\fig\git终端修改字体大小.png)

## git 实现本地仓库与 GitHub 和 Gitee 关联

#### 远程仓库操作

首先分别找到 GitHub 和 Gitee 配置公钥的地方，把用户主目录下的 **.ssh\id_rsa.pub** 文件中的内容粘贴进去。

然后在 GitHub 和 Gitee 上分别建立相同名称的仓库，如 **learngit** ，此处不赘述远端新建仓库过程。

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

这时在本地进行相应的修改操作，只要分别执行下面这两条语句（不分先后顺序），就可以将本地commit信息同时push到两个远程仓库的主分支（master）中。

```git
$ git push github main
$ git push gitee master
```

![推送GitHub](E:\Git\testgit\fig\推送GitHub.png)

![推送Gitee](E:\Git\testgit\fig\推送Gitee.png)



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

