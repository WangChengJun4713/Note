#### 1 项目上传

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

![image-20250416173045215](..\Imgs\image-20250416173045215.png)

2、等价于git add 好处是部分上传时只需要逐个点击

![image-20250416173133813](..\Imgs\image-20250416173133813.png)

3、等价于git commit -m "first commit"

![image-20250416173737368](..\Imgs\image-20250416173737368.png)

4、选分支，这里默认新建项目

![image-20250416174022212](..\Imgs\image-20250416174022212.png)

如果要选择已有项目的话

![image-20250416174338468](..\Imgs\image-20250416174338468.png)

填充URL即可

![image-20250416174357443](..\Imgs\image-20250416174357443.png)

5、等价于git push

![image-20250416173810996](..\\Imgs\image-20250416173810996.png)

---



#### 2 从远程仓库拉取项目

**命令行操作**

首次拉取

```bash
# 直接从远程仓库克隆下来
git clone git@github.com:WangChengJun4713/EEG.git
```

更新内容

```bash
git pull git@github.com:WangChengJun4713/EEG.git main
```

**vscode操作**

![image-20250416175752572](..\\Imgs\image-20250416175752572.png)

### 3 配置密钥

在github的setting中新建SSH key

把本机的公钥上传 

![image-20250416175535274](..\\Imgs\image-20250416175535274.png)

### 4 大文件上传和下载

git限制文件传输大小为100MB，所以在处理大文件时需要利用到LFS

Ubuntu

```bash
sudo apt-get install git-lfs
```

Windows

 [Git LFS 官方下载页面](https://git-lfs.github.com/)

安装后验证

```bash
git lfs version
```

LFS初始化

```bash
git lfs install
```

若你只想对当前仓库启用 Git LFS，可添加 `--local` 选项

```bash
git lfs install --local
```

跟踪文件

```bash
git lfs track "large_file.iso"
```

可以使用通配符

```bash
git lfs track "*.mp4" "*.zip"
```

执行上述命令后，Git 会在仓库中创建一个 `.gitattributes` 文件，其中记录了被跟踪的文件规则。你需要将这个文件添加到版本控制中：

```bash
git add .gitattributes
```

### 上传文件到远程仓库

当你完成文件跟踪设置后，就可以像使用普通 Git 一样将文件添加、提交并推送到远程仓库。

```bash
# 添加文件到暂存区
git add your_large_file.mp4

# 提交更改
git commit -m "Add large file using Git LFS"

# 推送到远程仓库
git push origin master
```

在推送过程中，Git LFS 会自动将大文件上传到其对应的存储服务器，并在 Git 仓库中只保存文件的指针信息。



当你克隆一个使用 Git LFS 管理的仓库，或者从远程仓库拉取更新时，需要确保下载的是文件的实际内容而不是指针。

拉取更新

```bash
git lfs pull
```

查看当前由 Git LFS 跟踪的文件：

```bash
git lfs track
```
