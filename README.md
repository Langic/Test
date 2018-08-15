# GitHub上的使用
1.登录[GitHub](https://github.com/) 注册账号

2.下载[Git工具](https://git-scm.com/downloads)--通过命令行进行上传提交等一系列操作
下载安装成功后点击git-bash.exe或者在对应文件夹右键再选择git-bash就有git命令框弹出

3.绑定用户（用户和邮箱为你github注册的账号和邮箱）
执行
* git config --global user.name "Langic"
* git config --global user.email "gaoyue_516547237@qq.com"
绑定用户

4.设置`SSH key`
首先检查是否已生成密钥cd C:/Users(每台电脑不同)/.ssh，如果返回的ls有3个文件,则密钥已经生成。
如果没有密钥，则通过执行 * ssh-keygen -t rsa -C "gaoyue_516547237@qq.com"生成密钥
生成过程中一路按3次回车键就好了。（默认路径，默认没有密码登录）
生成成功后，去对应目录C:/Users/.ssh里,用记事本打开id_rsa.pub，得到ssh key公钥。

5.为GitHub账号配置ssh key
切换到GitHub，展开个人头像的小三角，点击settings，然后打开SSH keys菜单， 点击Add SSH key新增密钥，填上标题
接着将id_rsa.pub文件中key粘贴到此，最后Add SSH key生成密钥

6.上传本地项目到GitHub
在本地创建一个文件夹作为本地仓库
在该文件夹中创建要用的文件等
在git-bash中进行该文件夹路径，执行 * git init 初始化仓库(会出现一个隐藏文件夹.git)
执行* git add . 将所有文件添加到仓库，添加单个文件用 * git add filename(注意该文件的路径)
执行 * git commit -m "log des" 去提交文件(双引号内是提交注释)

7.关联GitHub仓库
在GitHub上，点击右上角+号选择New repository新建一个存储库
然后复制仓库地址执行 * git remote add origin https://github.com/Langic/Test.git 让本地仓库和github存储库进行关联
执行 * git push -u origin master进行上传代码
注意如果新建存储库时选择了或者自己创建了README.md，先执行 * git pull -u origin master那该文件拉回本地仓库，不然上传代码不会成功。
