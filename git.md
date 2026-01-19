### 绑定用户信息
依次执行：
1. git config --global user.name "用户名"
2. git config --global user.mail "邮箱"
(此处用户名与邮箱可乱填)

### 创建本地仓库
1. 直接clone：git clone [项目地址]
2. 新建：git init

### 仓库管理
1. 把文件放入暂存区：git add [文件名] / git add .（当前目录所有文件和文件夹，不包括子目录和被删除的文件）/ git add * （当前目录下的所有内容）
2. 把文件放入仓库：git commit -m “备注内容” 
3. 查看提交节点：git log,加参数--stat查看每次提交修改了哪些文件
4. 查看对应提交修改了哪些内容：git diff [commit id]
5. 回退到指定节点：git reset --hard [commit id]/git checkout [commit id]

### 分支
1. 查看分支：git branch
2. 创建分支：git checkout -b develop (创建并切换)
3. 切换分支：git checkout master
4. 合并分支：git merge develop (把develop合并到master)
5. 修改当前分支名称：git branch -m 新分支名称
6. 修改其他分支名称：git branch -m 旧分支名称 新分支名称

### 与github等互动

#### 绑定
1. git clone [项目地址] 自动绑定
2. git remote add <远程仓库名称> <远程仓库地址> （名称常用origin）

#### 登录并校验权限
1. HTTPS地址+账号密码 （简单，但安全性较差）/ 用户名+PAT令牌 （github使用）
2. SSH链接+密钥：
   1. git remote add origin [SSH链接]
   2. ssh-keygen -t rsa -C [邮箱]
   3. 在本地找到公钥
   4. 将公钥绑定到github账号

#### 推送和拉取
1. git push <远程仓库名> <本地分支名>:<远程分支名>
2. git push origin master:把代码上传到origin仓库的master分支
3. git push:把代码上传到**默认仓库**中和**本地分支**对应的分支里
4. git pull:把**默认远程仓库**中，**对应远程分支**的最新代码拉取下来
5. git pull origin master:把origin仓库的master分支的最新代码拉取下来

### 简单工作流举例
1. git checkout develop
2. git checkout -b \<feature>
3. 完成开发
4. add,commit提交代码
5. git checkout develop
6. git pull origin develop
7. git merge \<freature>
8. git push origin develop
  

