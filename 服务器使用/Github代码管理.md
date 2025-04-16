



#### 项目上传

**命令行操作**

```bash
#本地初始化
git init 
#建立远程连接
git remote git remote add origin git@github.com:WangChengJun4713/EEG.git
#文件添加到缓冲区
git add <file>
#commit到工作树
git commit -m "first commit"
#可选分支，默认master
git branch -M main
#不选分支就是main -> master
git push -u origin main
```

*如果没有配置username和email 需要以下操作*

```bash
git config user.name "wcj"
git config user.email "charles4713@163.com"
```

**等价于vscode处理步骤**

1、初始化

![image-20250416173045215](D:\Typora\Data\Image\image-20250416173045215.png)

2、等价于git add 好处是部分上传时只需要逐个点击

![image-20250416173133813](D:\Typora\Data\Image\image-20250416173133813.png)

3、等价于git commit -m "first commit"

![image-20250416173737368](D:\Typora\Data\Image\image-20250416173737368.png)

4、选分支，这里默认新建项目

![image-20250416174022212](D:\Typora\Data\Image\image-20250416174022212.png)

如果要选择已有项目的话

![image-20250416174338468](D:\Typora\Data\Image\image-20250416174338468.png)

填充URL即可

![image-20250416174357443](D:\Typora\Data\Image\image-20250416174357443.png)

5、等价于push

![image-20250416173810996](D:\Typora\Data\Image\image-20250416173810996.png)

