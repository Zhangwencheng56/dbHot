##### 版本控制也就是要用git管理文件夹，步骤如下：

进入要管理的文件夹 ----> 初始化（提名） ----> 管理 ----> 生成版本

##### 进入要管理的目录

##### git init：初始化

初始化后就能让git真正管理起当前文件夹，会在当前文件夹中生成一个.git文件夹，git在管理这个文件夹中所有的配置和版本信息都会存储在里面

##### git status：查看状态

检测当前文件夹下的文件的状态

三种状态：

- 红色：新增的文件/修改了源文件  --> git add 文件名
- 绿色：git已经管理起来 --> git commit -m '描述信息'
- 生成版本

##### git add：管理文件

表示要管理哪个文件

git add index.html表示管理index.html文件

被git管理起来的文件是绿色的，没有被管理的文件是红色的

git add . 表示管理所有的文件

##### git commit -m 'v1'：生成版本

表示生成v1版本

之后再用git status会发现没有文件了，说明当前文件夹中的所有文件都被git管理起来了，并且生成了一个版本

注意：

- 当对git所管理的文件做修改时，用git status命令可以检测到该文件的状态（modified），这时原来被git管理的文件被修改了之后变成红色了

- 文件显示是红色时，是未被git管理，绿色是被管理；要生成版本必须先被git管理生成绿色文件，再用git commit -m '' 来生成版本

##### git log：查看版本

查看所有的版本，执行这个命令后，会将修改文件后的版本和修改之前的版本显示出来

##### git reset --hard 版本号

回滚到以前版本

##### git reflog

恢复所有版本，然后用git reset --hard ‘版本号’ 回到指定版本

##### 另外几个命令

```
git checkout -- 文件名        ---->  恢复到修改之前的状态
git reset HEAD 文件名         ---->  由管理状态恢复到未被管理状态
```

![image-20221111202134974](C:\Users\ZWC\AppData\Roaming\Typora\typora-user-images\image-20221111202134974.png)

注意：生成的新的版本中不会保留原本没有变化的文件，而是保留修改过的和新增的文件，重复的文件通过一个指针指向上一个版本，当需要读取当前版本的时候，会根据指针获取上一个版本的文件

分支：当项目在开发新功能时，开发到一半，已有功能出现bug，按以往的做法，得舍弃掉当前开发的功能，回到初始状态进行修复，这非常浪费时间，所以有了分支的概念，回到新功能开发之前的版本进行bug修复，完成修复后，再回到开发的新功能上继续开发

**面试题：**你们公司如果线上代码出问题了，是怎么解决的？

**回答：**项目开发时用git进行版本控制，开发人员从主干拉去代码到本地，形成一个分支，在自己的分支上修改代码，当代码写的没问题后，将主分支上（**master**）的代码拉到本地，与分支进行测试后没问题，再将分支的代码与主分支的代码进行合并
在公司继续开发一点功能，有点事耽误了，忘记上传到GitHub了，在公司继续开发，做到100%

在家里开发一些其他功能

