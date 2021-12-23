# Linux组队学习

## 1 vscode配置远程连接环境

在扩展市场搜索remote ssh扩展，然后左侧会出来一个图标<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216174429462.png" alt="image-20211216174429462" style="zoom:67%;" />，点击后出现下面界面

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216174730946.png" alt="image-20211216174730946" style="zoom: 50%;" />

左上角选择SSH Targets，点击设置按钮

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216174936770.png" alt="image-20211216174936770" style="zoom:50%;" />

这个地方鼠标悬停后会出现一个设置按钮，点击后选择config文件，就进入上图的样式，输入用户名和IP地址，保存后左边就会出现datawhale字样，点击“+”即可连接成功。

## 2.Task1

### 2.1 任务一：使用命令行登录指定的Linux环境

按照上面步骤已完成<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216175328558.png" alt="image-20211216175328558" style="zoom: 50%;" />

### 2.2 任务二：在目录下创建文件夹、删除文件夹

常见的处理文件命令

- ls（英文全拼：list files）: 列出目录及文件名
- cd（英文全拼：change directory）：切换目录
- pwd（英文全拼：print work directory）：显示目前的目录
- mkdir（英文全拼：make directory）：创建一个新的目录
- rmdir（英文全拼：remove directory）：删除一个空的目录
- cp（英文全拼：copy file）: 复制文件或目录
- rm（英文全拼：remove）: 删除文件或目录
- mv（英文全拼：move file）: 移动文件与目录，或修改文件与目录的名称

> 在/home/datawhale目录下，新建一个以你英文昵称（中间不要有空格哦）的文件夹A

在root文件夹下使用命令```mkdir huixiang```，即可。

> 在文件夹A内部创建一个以datawhale命名的文件夹B

使用命令```cd huixiang```进入huixiang文件夹下```mkdir datawhale```

> 在B文件夹内创建一个空txt文件

使用命令```touch fangxin.txt```即可创建一个名为fangxin的txt文件

> 删除步骤4创建的文件

使用rm命令， rm [-fir] 文件或目录，其中

- -f ：就是 force 的意思，忽略不存在的文件，不会出现警告信息；
- -i ：互动模式，在删除前会询问使用者是否动作
- -r ：递归删除啊！最常用在目录的删除了！这是非常危险的选项！！！

使用```rm -i fangxin.txt```命令删除即可<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216200807386.png" alt="image-20211216200807386" style="zoom: 67%;" />

> 删除文件夹B，然后删除文件夹A

使用```rm -rf huixiang```删除文件夹A，其中r代表递归删除文件夹A下的各个文件夹，f代表强制删除。

### 任务3：在目录下下载文件、阅读文件

> 在home/datawhale目录下，新建一个以你英文昵称（中间不要有空格哦）的文件夹A
>
> 在文件夹A内部创建一个以datawhale命令的文件夹B

操作和任务2相同

> 使用wget命令下载[https://mirror.coggle.club/dataset/affairs.txt](https://mirror.coggle.club/dataset/affairs.txt，到文件夹B?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk2NDgwMTksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NjQ3NzE5LCJ1c2VySWQiOi0xNDE5NjUwODU0fQ.ER1H82_h-4AomSpnvVzkxk_1PhQiLlOYkGsKYeLPHdU)，到文件夹B

wget命令用来从指定的URL下载文件。wget非常稳定，它在带宽很窄的情况下和不稳定的网络中有很强的适应性，如果由于网络的原因下载失败，wget会不断的尝试，直到整个文件下载完毕。如果是服务器打断下载过程，它会再次连到服务器上从停止的地方继续下载。这对从那些限定了链接时间的服务器上下载大文件非常有用。

```wget(选项)（参数）``` 

选项：

```
-a<日志文件>：在指定的日志文件中记录资料的执行过程；
-A<后缀名>：指定要下载文件的后缀名，多个后缀名之间使用逗号进行分隔；
-b：进行后台的方式运行wget；
-B<连接地址>：设置参考的连接地址的基地地址；
-c：继续执行上次终端的任务；
-C<标志>：设置服务器数据块功能标志on为激活，off为关闭，默认值为on；
-d：调试模式运行指令；
-D<域名列表>：设置顺着的域名列表，域名之间用“，”分隔；
-e<指令>：作为文件“.wgetrc”中的一部分执行指定的指令；
-h：显示指令帮助信息；
-i<文件>：从指定文件获取要下载的URL地址；
-l<目录列表>：设置顺着的目录列表，多个目录用“，”分隔；
-L：仅顺着关联的连接；
-r：递归下载方式；
-nc：文件存在时，下载文件不覆盖原有文件；
-nv：下载时只显示更新和出错信息，不显示指令的详细执行过程；
-q：不显示指令执行过程；
-nh：不查询主机名称；
-v：显示详细执行过程；
-V：显示版本信息；
--passive-ftp：使用被动模式PASV连接FTP服务器；
--follow-ftp：从HTML文件中下载FTP连接文件。
```

参数：下载时需要的URL地址

参考博客：https://www.cnblogs.com/pretty-ru/p/10936023.html?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk2NDgwMTksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NjQ3NzE5LCJ1c2VySWQiOi0xNDE5NjUwODU0fQ.ER1H82_h-4AomSpnvVzkxk_1PhQiLlOYkGsKYeLPHdU

直接使用命令 ```wget https://mirror.coggle.club/dataset/affairs.txt``` 

> 使用head、cat、tail命令阅读下载的文件。

分别使用命令```head  affairs.txt```,```tail affairs.txt```, ```cat affairs.txt```。

> 在命令行使用ipython进入python3环境，并使用pandas读取下载的文件。

先进入datawhale文件夹下，输入```ipython```，剩余操作与windows类似

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216204604731.png" alt="image-20211216204604731" style="zoom: 67%;" />



### 任务4：在目录下使用vi或vim编辑文件

> 步骤1：学习Nano的使用，[https://blog.csdn.net/junxieshiguan/article/details/84104912](https://blog.csdn.net/junxieshiguan/article/details/84104912?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk2NDgwMTksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NjQ3NzE5LCJ1c2VySWQiOi0xNDE5NjUwODU0fQ.ER1H82_h-4AomSpnvVzkxk_1PhQiLlOYkGsKYeLPHdU)
>
> 步骤2：学习Vim的使用，[https://www.runoob.com/linux/linux-vim.html](https://www.runoob.com/linux/linux-vim.html?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk2NDgwMTksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NjQ3NzE5LCJ1c2VySWQiOi0xNDE5NjUwODU0fQ.ER1H82_h-4AomSpnvVzkxk_1PhQiLlOYkGsKYeLPHdU)

<img src="https://www.runoob.com/wp-content/uploads/2015/10/vi-vim-cheat-sheet-sch.gif" alt="img" style="zoom:70%;" />

常用的

### 命令模式：

用户刚刚启动 vi/vim，便进入了命令模式。

此状态下敲击键盘动作会被Vim识别为命令，而非输入字符。比如我们此时按下i，并不会输入一个字符，i被当作了一个命令。

以下是常用的几个命令：

- **i** 切换到输入模式，以输入字符。
- **x** 删除当前光标所在处的字符。
- **:** 切换到底线命令模式，以在最底一行输入命令。

若想要编辑文本：启动Vim，进入了命令模式，按下i，切换到输入模式。

命令模式只有一些最基本的命令，因此仍要依靠底线命令模式输入更多命令。

**输入模式**：

在命令模式下按下i就进入了输入模式。

在输入模式中，可以使用以下按键：

- **字符按键以及Shift组合**，输入字符
- **ENTER**，回车键，换行
- **BACK SPACE**，退格键，删除光标前一个字符
- **DEL**，删除键，删除光标后一个字符
- **方向键**，在文本中移动光标
- **HOME**/**END**，移动光标到行首/行尾
- **Page Up**/**Page Down**，上/下翻页
- **Insert**，切换光标为输入/替换模式，光标将变成竖线/下划线
- **ESC**，退出输入模式，切换到命令模式

### 底线命令模式

在命令模式下按下:（英文冒号）就进入了底线命令模式。

底线命令模式可以输入单个或多个字符的命令，可用的命令非常多。

在底线命令模式中，基本的命令有（已经省略了冒号）：

- q 退出程序
- w 保存文件

按ESC键可随时退出底线命令模式。

参考网址：https://www.runoob.com/linux/linux-vim.html?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk2NDgwMTksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NjQ3NzE5LCJ1c2VySWQiOi0xNDE5NjUwODU0fQ.ER1H82_h-4AomSpnvVzkxk_1PhQiLlOYkGsKYeLPHdU

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216211236560.png" alt="image-20211216211236560" style="zoom:80%;" />

### 任务5：在目录下创建py文件，并进行运行

> 步骤1：学习python下os模块处理文件和目录的函数，[https://www.runoob.com/python/os-file-methods.html](https://www.runoob.com/python/os-file-methods.html?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk2NDgwMTksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NjQ3NzE5LCJ1c2VySWQiOi0xNDE5NjUwODU0fQ.ER1H82_h-4AomSpnvVzkxk_1PhQiLlOYkGsKYeLPHdU)
>
> 步骤2：学习python下sys模块和传参函数，[https://www.runoob.com/python3/python3-module.html](https://www.runoob.com/python3/python3-module.html?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk2NDgwMTksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NjQ3NzE5LCJ1c2VySWQiOi0xNDE5NjUwODU0fQ.ER1H82_h-4AomSpnvVzkxk_1PhQiLlOYkGsKYeLPHdU)
>
> 步骤3：在home/datawhale目录下，在你英文昵称（中间不要有空格哦）的文件夹中，新建一个test5.py文件，改程序可以使用os、sys模块完成以下功能：
>
> - 功能1：打印命令行参数
> - 功能2：使用os模块打印**/usr/bin/**路径下所有以m开头的文件。

编辑test5.py文件

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216215532426.png" alt="image-20211216215532426" style="zoom:50%;" />

这样就可以实现上述功能

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216215625985.png" alt="image-20211216215625985" style="zoom:67%;" />

利用os.listdir遍历/usr/bin/文件夹下的文件名

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211216221400314.png" alt="image-20211216221400314" style="zoom:50%;" />

### **任务6：在目录下创建py目录，并进行import导入**

> 步骤1：学习python模块化，[https://www.runoob.com/python3/python3-module.html](https://www.runoob.com/python3/python3-module.html?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk3MDcwOTIsImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NzA2NzkyLCJ1c2VySWQiOi0xNDIzNzgxNjE1fQ.nBW3UL4lsUVMYNK9nAAEc8eoNtQhglqWQrdKC7NDxH0)
>
> 步骤2：在/home/datawhale目录下在你英文昵称（中间不要有空格哦）的文件夹中创建affairs文件夹。

在datawhale文件夹下使用```mkdir -p huixiang/affairs```迭代的创建affairs文件夹。

> 步骤3：编写test6.py和affairs.py完成以下功能：
>
> - 功能1：affairs.py代码完成文件的读取，这里可以直接pd.read_csv('[https://mirror.coggle.club/](https://mirror.coggle.club/dataset/affairs.txt，到文件夹B?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk3MDcwOTIsImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NzA2NzkyLCJ1c2VySWQiOi0xNDIzNzgxNjE1fQ.nBW3UL4lsUVMYNK9nAAEc8eoNtQhglqWQrdKC7NDxH0)[dataset/affairs.txt](https://mirror.coggle.club/dataset/affairs.txt?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk3MDcwOTIsImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NzA2NzkyLCJ1c2VySWQiOi0xNDIzNzgxNjE1fQ.nBW3UL4lsUVMYNK9nAAEc8eoNtQhglqWQrdKC7NDxH0)')来完成。这一部分建议写为函数。
>
> - 功能2：test6.py可以导入affairs.py代码
>
> - 功能3：test6.py可以进行命令行解析，输出[affairs.txt](https://mirror.coggle.club/dataset/affairs.txt?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2Mzk3MDcwOTIsImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjM5NzA2NzkyLCJ1c2VySWQiOi0xNDIzNzgxNjE1fQ.nBW3UL4lsUVMYNK9nAAEc8eoNtQhglqWQrdKC7NDxH0)具体的第几行内容。

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211217104458668.png" alt="image-20211217104458668" style="zoom:50%;" />

发现可以直接在左侧打开相应文件，直接新建affairs.py和test6.py文件。

<img src="C:\Users\fangxin\Desktop\杂七杂八\figures\微信图片_20211217103610.png" alt="微信图片_20211217103610" style="zoom: 33%;" />

<img src="C:\Users\fangxin\Desktop\杂七杂八\figures\微信图片_20211217103642.png" alt="微信图片_20211217103642" style="zoom: 33%;" />

运行结果在下方终端内

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211217105830453.png" alt="image-20211217105830453" style="zoom:50%;" />

为了实现功能2，重新编写了一下程序，输出内容在下面终端内



### 任务7：在Linux系统中后台运行应用程序，并打印日志

> 步骤1：在/home/datawhale目录下在你英文昵称（中间不要有空格哦）的文件夹中创建一个sleep.py文件，该文件需要完成以下功能：
>
> - 程序一直运行
>
> - 每10秒输出当前时间

直接在我的英文昵称文件夹下新建一个sleep.py的文件，程序内容如图所示，

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211222193709568.png" alt="image-20211222193709568" style="zoom: 67%;" />

在终端输入命令```python3 sleep.py```，即可每十秒打印当前时间了。

<img src="C:\Users\fangxin\AppData\Roaming\Typora\typora-user-images\image-20211222193848312.png" alt="image-20211222193848312" style="zoom:50%;" />

> 步骤2：学习 & 和 nohup后台执行的方法
>
> 学习链接
>
> [https://blog.csdn.net/a736933735/article/details/89577557](https://blog.csdn.net/a736933735/article/details/89577557?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2NDAxNzMxNjksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjQwMTcyODY5LCJ1c2VySWQiOi0xNDU2MDQyMzk0fQ.GVbC9mJKDmj1M0iczMguGA_hI7cl9PiAl7Ivvi1zcV4)
>
> [http://ipcmen.com/jobs](http://ipcmen.com/jobs?accessToken=eyJhbGciOiJIUzI1NiIsImtpZCI6ImRlZmF1bHQiLCJ0eXAiOiJKV1QifQ.eyJhdWQiOiJhY2Nlc3NfcmVzb3VyY2UiLCJleHAiOjE2NDAxNzMxNjksImciOiJ2NVlCR25qSkRBTXJLeWhrIiwiaWF0IjoxNjQwMTcyODY5LCJ1c2VySWQiOi0xNDU2MDQyMzk0fQ.GVbC9mJKDmj1M0iczMguGA_hI7cl9PiAl7Ivvi1zcV4)

以一个打包命令为例

```tar czf /data/backup.tgz /data/backup```

其中tar（tape archive）命令用于备份文件，

* -c或--create 建立新的备份文件
* -z或--gzip或--ungzip 通过gzip指令处理备份文件。
* -f<备份文件>或--file=<备份文件> 指定备份文件。

上述命令指将```/data/backup```中的所有文件打包压缩到```/data/backup.tgz```

#### 1.&命令

```tar czf /data/backup.tgz /data/backup &```

要使用ctrl+D退出才能后台执行，直接关闭窗口也会关闭进程。

#### 2.nohup命令

```nohup tar czf /data/backup.tgz /data/backup```

用ctrl+z挂起到后台

用bg命令先查看有多少个jobs

ctrl+d后台或者 直接关闭窗口，进程仍会在后台执行

#### 3.nohup+&命令

```nohup tar czf /data/backup.tgz /data/backup &```

ctrl+d 或者 直接关闭窗口 进程任然会在后台执行

#### 4.采用（command &）

```(tar czf /data/backup.tgz /data/backup &)```  

这样会将ppid设置为1，而非当前会话的id，并且jobs查看不到当前的作业。注意这里的括号即是这个方法的重点。

ctrl+d 或者 直接关闭窗口 进程任然会在后台执行

本文先简要记录几种容易易懂的方法。

其中nohup和nohup+&有什么区别呢**？**

nohup执行后默认会将输出保存在nohup.out文件，但执行后无法接受标准输入，关闭窗口后仍然会运行。

&无法将标准输出保存到文件中，关闭窗口后程序就会停止。

nohup &一起使用综合了两者的优点，既能标准输入也能将标准输出的日志输入到文件，关闭窗口后仍然会运行。

> 步骤3：学习tmux的使用，将步骤1的程序进行后台运行，并将输出结果写入到txt文件。

tmux学习地址;https://www.ruanyifeng.com/blog/2019/10/tmux.html

**Tmux 就是会话与窗口的"解绑"工具，将它们彻底分离。**

（1）它允许在单个窗口中，同时访问多个会话。这对于同时运行多个命令行程序很有用。

（2） 它可以让新窗口"接入"已经存在的会话。

（3）它允许每个会话有多个连接窗口，因此可以多人实时共享会话。

（4）它还支持窗口任意的垂直和水平拆分。

类似的终端复用器还有 GNU Screen。Tmux 与它功能相似，但是更易用，也更强大。

在vscode中可以直接通过下面终端操作界面打开tmux，十分便利

#### 会话管理

##### 1.新建会话

```bash
$ tmux new -s <session-name>
```

即可打开tmux并为其命名，注意，是在bash中输入，如

```tmux new -s task7.py```

##### 2.分离会话

在 Tmux 窗口中，按下`Ctrl+b d`或者输入`tmux detach`命令，就会将当前会话与窗口分离。

> ```bash
> $ tmux detach
> ```

上面命令执行后，就会退出当前 Tmux 窗口，但是会话和里面的进程仍然在后台运行。

`tmux ls`命令可以查看当前所有的 Tmux 会话。

##### 3.接入会话

`tmux attach`命令用于重新接入某个已存在的会话。（注意有个-t）

```bash
# 使用会话编号
$ tmux attach -t 0

# 使用会话名称
$ tmux attach -t <session-name>
```

##### 5.杀死会话

`tmux kill-session`命令用于杀死某个会话。

```bash
# 使用会话编号
$ tmux kill-session -t 0

# 使用会话名称
$ tmux kill-session -t <session-name>
```

##### 6.切换会话

`tmux switch`命令用于切换会话。

> ```bash
> # 使用会话编号
> $ tmux switch -t 0
> 
> # 使用会话名称
> $ tmux switch -t <session-name>
> ```

##### 7.重命名会话

`tmux rename-session`命令用于重命名会话。

```bash
$ tmux rename-session -t 0 <new-name>
```

上面将0会话重命名

##### 8.会话快捷键

下面是一些会话相关的快捷键。

- `Ctrl+b d`：分离当前会话。
- `Ctrl+b s`：列出所有会话。
- `Ctrl+b $`：重命名当前会话。

#### 简单的tmux操作流程

综上所述，以下是 Tmux 的最简操作流程。

> 1. 新建会话`tmux new -s my_session`。
> 2. 在 Tmux 窗口运行所需的程序。
> 3. 按下快捷键`Ctrl+b d`将会话分离。
> 4. 下次使用时，重新连接到会话`tmux attach-session -t my_session`。

使用一些vscode的快捷键可以方便调整tmux窗口位置。

在tmux中使用命令`python3 -u sleep.py > sleep.txt`命令将.py文件重定向输出到txt文件。

<img src="C:\Users\fangxin\Desktop\杂七杂八\figures\iii.png" alt="WLGU$85GU7HX0@)S{F{2JD4" style="zoom:50%;" />

如图 用命令将会话分离开来，程序仍然运行。关闭窗口即可。
