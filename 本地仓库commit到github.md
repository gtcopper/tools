#本地仓库commit到github远程仓库
----
1. 在**Git Bah**中输入以下命令
	* **$ git config --global user.name "github账号"**
	* **$ git config --global user.email "github邮箱"**
2. 设置**SSH Key**(若配置好跳转到第3步)
    * **生成ssh key**
      + 检查是否已生成ssh key  : **$ cd ~/.ssh**  若返回的**ls**有2个文件(**id\_rsa**和**id\_rsa.pub**)，则秘钥已经生成,反之则没有生成，需要自己生成.
      + **生成秘钥** :  **$ ssh-keygen -t rsa -C "github邮箱"**
        默认回车3次生成.
		生成后到**C:\Users\Administrator(电脑用户名)\\.ssh**
		用**记事本打开id_rsa.pub**，得到ssh key**公钥**。
	* **为github账号配置ssh key**
		+ 切换到github，展开个人头像的小三角，点击settings，然后打开SSH keys菜单， 点击Add SSH key新增密钥，填上标题（最好跟本地仓库保持一致）。
		+ 接着将id_rsa.pub文件中key粘贴到此，最后Add key生成密钥.
3. 上传本地项目到github
	* 创建一个本地项目xxx
	* 进入本地仓库文件夹
		+ **$ cd d:xxx**
	* 初始化仓库
		+ **$ git init(仓库隐藏文件夹会有.git文件)**
	* 将文件添加到仓库中
		+ **$ git add .**
	*文件提交
	    + **$ git commit -m "提交注释"**
4. 关联github仓库
    * 复制github仓库(xxx)地址  如https://github.com/gtcopper/xxx.git
    * 将本地仓库添加到远程仓库github上
    	+ **$ git remote add origin https://github.com/gtcopper/xxx.git**
    	+ 倘若需要变更远程仓库地址，有以下方法(进入根目录):
    	  + 方法一通过命令直接修改远程地址 : ``git remote 查看所有远程仓库， git remote xxx 查看指定远程仓库地址 ``
			``git remote set-url origin http:github.com/gtcopper/xxx.git ``
		  + 方法二 : 通过命令先删除再添加远程仓库 
		  +  ``git remote rm origin``
     ``git remote add origin http:github.com/gtcopper/xxx.git``
		       
		     
    * 上传本地代码(仓库)到github
    	+ **$ git push -u origin master**
5. 上传成功    
**注意：git是不能管理空的文件夹的，文件夹里必须有文件才能上传。**

参考来源:[本地仓库commit到github远程仓库](https://www.jianshu.com/p/c70ca3a02087)