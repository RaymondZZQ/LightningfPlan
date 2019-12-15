#### 一、使用jupyter

1. 安装pip install jupyter

2. 启动  终端下输入 jupyter notebook 

   jupyter默认的服务器地址是 http://localhost:8888即127.0.0.1:8888

3. jupyter会自动创建一个config文件，用来配置各种设置，默认存储在C:\users\用户名\ .jupyter中，名称为 jupyter_notebook_config.py， 其中以“##”开头的是真正的注释，以"#"开头的是我们可以修改的语句，对应的是相关的配置，如，修改默认目录步骤如下：

   ```python
   ## The directory to use for notebooks and kernels.
   #c.NotebookApp.notebook_dir = ''
   #修改为自己的目录，我的目录为D:\LightingPlan2020\learningQita，修改之后如下：
   ## The directory to use for notebooks and kernels.
   c.NotebookApp.notebook_dir = 'D:\LightingPlan2020\learningQita'
   
   ```

4. jupyter左边有一个In[ ]，几种状态的含义如下：

   > In [ ]  程序未运行
   >
   > In [ * ] 程序正在运行或者正在等待被执行，如果一直是*，表明程序出现了无法终止的情况
   >
   > In [编号] 程序已经执行完毕，编号表示此代码执行的顺序

#### 二、jupyter的一些常用命令

1. jupyter notebook --help 查看命令的解释 --help-all会显示更加详细的命令
2. jupyter notebook list  查看当前server
3. jupyter notebook stop port 关闭指定端口号的server
4. jupyter password 输入后会提示输入密码和确认密码，然后会将密码写在配置文件中，在web端访问时就需要输入密码才可以进入
5. jupyter notebook --generate-config 产生配置文件
6. jupyter notebook --no-browser 启动jupyter但是不打开web浏览器
7. jupyter notebook --pylab  这样可以在jupyter notebook中使用pylab或者matplotlib了
8. jupyter notebook --port==8889 指定端口号，默认8888
9. jupyter notebook --ip=< Unicode >  指定ip，默认是localhost即127.0.0.1
10. jupyter notebook --notebook-dir=< Unicode >



#### 三、jupyter的一些知识，技巧

1. 单元格的颜色有绿色和蓝色，分别代表Edit模式和Command模式，按Enter进入编辑模式，按ESC进入command模式

   绿色表示内容编辑模式，此时可以修改单元格中的内容，

   蓝色表示处于单元格操作模式，此时可以对单元格进行操作，比如删除单元格(双D)，

2. 快捷键

   > 1. 执行当前cell并跳到下一个cell:  shift + Enter
   >2. 执行当前cell，执行后不跳到下一个cell， Ctrl + Enter
   > 3. 选中cell后，双D即可删除单元格Cell
   >4. ESC 退出当前Cell的编辑模式，即到操作模式
   > 5. 为当前cell中的代码添加line number， 单L
   >6. 撤销对某个单元格的删除， z
   > 7. 快速回到首个cell，  Ctrl + Home（home按键就是左箭头）
   >8. 快速回到最后一个cell， ctrl + end（end按键就是右箭头）
   > 9. 从光标处分割cell   快捷键    ctrl + shift + 减号
   >10. 在操作模式下，按 a 在当前cell下创建一个cell
   > 
   >​							按b在当前cell上创建一个cell
   > 
   >10. cell中code和markdown格式的切换：
   > 
   >    >  在操作模式下，按 y进入code编辑模式
   >  >
   >    > ​							按m进入markdown编辑模式
   >    
   >11. 在cell的command模式下，按s，保存整个notebook
   > 12. tab键 代码补全
   >13. 
   
3. jupyter中的magic关键字，其实是ipython中的一些高级用法，可以运行特殊的命令，然后控制notebook，magic命令的前面一般有一个或者两个百分号%或者%%，分别代表行magic命令和单元格magic命令，

   行magic命令只运用于编写magic命令时所在的行，

   单元格magic命令时则是应用于整个单元格，

   

   **下面介绍相关magic命令---行命令**

   > 1. % load test.py     将本地python文件test.py中的代码加载到当前cell中
   >
   > 2. % run test.py      运行本地的python文件test.py，结果会显示在当前cell中
   >
   > 3. % matplotlib inline 这样式样matplotlib画图时，图片嵌入在jupter notebook中
   >
   > 4. % lsmagic   列举多有magic命令
   >
   > 5. %timeit  为代码执行计时,直接在这条指令后面添加指令，如```%timeit print("time is ")```
   >
   >    %%timeit 测算整个单元格的时间
   >
   > 6. bash命令 :
   >
   >    > % pwd  显示当前路径
   >    >
   >    > % mkdir folderName 创建文件夹
   >    >
   >    > % rmdir folderName  删除文件夹
   >    >
   >    > % cd folderName  更改当前目录
   >    >
   >    > % cp src dst  复制
   >    >
   >    > 
   >
   > 7. % whos  查看当前变量，当前程序中出现的变量的类型和值，以及其信息等，
   >
   > 8. %pdb 开启交互式的调试器，出错时候能检查当前命名空间中的变量

4. 在jupyter运行终端命令，只需在终端命令前加 **！**，如下：

   > ！python --version
   >
   >  ! python test.py
   >
   >  ! dir

5. jupyter下的工具栏包含了很多功能，工具栏如下：

   ![alt 工具栏](data\jupyter面板.png)

   在工具栏中可以实现很多功能，如下：

   > 1. 可以将整个notebook转化为pdf，或者markdown，或者html等格式文件保存下来，具体操作是：
   >
   >   File   ---->   Download as --->选择相应的文件即可
   >
   >    上述方法可能不会得到很好的效果，或者转化为pdf直接报错，可以先将notebook转化为网
   >
   > html，然后再将html转化为PDF，  方法2：将其转化为mrakdown格式的文件，然后再打印成PDF
   >
   > 2. 还可以对cell进行操作，将cell上移或者下移，
   >
   > 3. insert是用来插入cell的
   >
   > 4. 可以为每个cell添加注释，注释本身其实就是一个cell，只是默认cell中的内容是“code"，只需要将类型设置为标题或者标记，此时即可使用markdown格式的语言来描述cell了，
   >
   >    值得注意的是，在注释cell中，基本上所有markdown的特性都可以在线使用