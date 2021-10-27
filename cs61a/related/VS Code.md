[toc]

# Visual Studio Code

## 介绍

Visual Studio Code（VS Code）是微软开发的开源文本编辑器，可以免费使用。它以相对轻量而著称，同时还整合了现代 IDE 中的关键功能，例如 Git 集成和大量的调试器。这使得 VS Code 非常适合各种情况-从简单的 Python 脚本到更密集的软件工程项目。

## 在自己的计算机上获取 VS Code

访问 [VS Code 的网站](https://code.visualstudio.com/)并按照说明将其安装到您的计算机上。

## 例子： `welcome.py`

现在，你应该已经安装了 VS Code。您可以选择查找应用程序或从终端打开它。回忆一下[实验 0]()，您可以通过按`Ctrl-Alt-t`来打开学校计算机上的终端。

让我们首先使用您在[实验 0]() 中学到的 UNIX 命令创建并进入到一个名为`example`的目录：

```bash
mkdir ~/Desktop/example
cd ~/Desktop/example
```

### 打开文件

现在让我们打开 VS Code！

> 对于 Mac 用户，您很可能会在`Applications`中发现 VS Code.

> 对于 Ubuntu 用户，您很可能通过搜索栏来找到 VS Code。

> 对于 Windows 用户，您很可能会在`Program Files`中找到 VS Code.

您还可以通过命令行在当前工作目录中打开 VS Code：

```bash
code .
```

VS Code 将打开一个欢迎页面。打开资源管理器（左上角的页面图标），然后单击`EXAMPLE`。要创建新文件，请右键单击下方`EXAMPLE` 并选择“新建文件”或单击角落带有加号的页面图标。让我们用`welcome.py`来命名我们的文件。右下角将出现一个弹出窗口，提示您安装 Python 扩展。我们后面将讨论有关更多的扩展程序，现在则直接安装 Python 扩展，而忽略可能出现的任何其他的弹出窗口。现在，我们可以开始编程了！

![空白 vscode](https://wandersky.org/wp-content/uploads/2021/09/202109160034937.png)

### 编辑文件

现在我们打开了 VS Code，我们可以开始编写我们的第一个 Python 文件。我们将编写一个简短的程序，在执行时打印出一条欢迎消息。别担心，我们还不期望您了解任何 Python！您所要做的就是输入以下内容：

```python
def welcome(name):
    print('Welcome to CS61A, %s!' % name)
```

完成输入后，VS Code 应如下所示：

![欢迎功能](https://wandersky.org/wp-content/uploads/2021/09/202109160047484.png)

要保存，您只需敲`Ctrl-s`（在 Mac 上是`cmd-s`），文件名旁边的白点应该会消失。

### 运行 Python

回到我们的终端，我们目前在`example`目录中。让我们玩转我们的代码。在终端中，首先输入

```bash
python3 -i welcome.py
```

此命令执行以下操作：

1. `python3` 是启动 Python 的命令
2. `-i`标志告诉 Python 以**交互模式**启动，这允许您从终端输入 Python 命令。
3. `welcome.py` 是我们要运行的 Python 文件的名称

请注意，Python 解释器显示`>>>`. 这意味着 Python 已准备好接受命令。

回想一下，我们定义了一个名为`welcome`的函数。让我们看看它是做什么的！输入以下内容：

```python
>>> welcome('Laryn')
```

然后 Python 会打印出来

```python
Welcome to CS61A, Laryn!
```

我们的代码有效！随意用你自己的名字尝试一下。好的，现在让我们来关闭 Python，输入

```python
>>> exit()
```

> 有几种方法可以退出 Python。您可以输入`exit()`或`quit()`。在 MacOS 和 Linux 上，您也可以输入`Ctrl-d`（这不适用于 Windows）。

恭喜，你已经在 VS Code 中编辑了你的第一个文件！

## 键盘快捷键

VS Code 有很多的键盘快捷键。这里有一些有用的！（对于 Mac 用户，将所有`Ctrl`序列替换为`cmd`）

- `Ctrl-`` : 在 VS Code 中打开一个集成终端
- `Ctrl-s` : 保存当前文件
- `Ctrl-x` : 剪切光标所在的整行
- `Ctrl-v` : 粘贴您在光标行中剪切的整行或将所选文本粘贴到当前位置
- `Ctrl-z` : 撤消
- `Ctrl-shift-z` : 重做
- `tab` : 缩进一行或一组行
- `shift-tab` : 取消一行或一组行的缩进
- `Ctrl-d` : 高亮当前单词。对于您在第一个单词之后键入的每个`Ctrl-d`，它将高亮当前单词的下一个实例。这使您可以轻松地使用多个光标重命名变量！（试试这个，很有趣也很实用！）
- `Ctrl-tab`：将您移动到下一个选项卡（在 Mac 上也是`Ctrl`）
- `Ctrl-shift-tab`：将您移至上一个选项卡（在 Mac 上也是`Ctrl`）
- `Ctrl-f` : 搜索一个词
- `Ctrl-shift-f` : 搜索所有选项卡

## 拓展

扩展允许您自定义文本编辑器。它们是由像你我这样的人或公司编写的软件，用于提高每个人的生活质量。扩展可以做任何事情，从改变配色方案，到允许您在编程时控制 Spotify，到让您与朋友实时共享工作区（❌尽管不是在课堂作业上）！这是有关扩展的[文档](https://code.visualstudio.com/docs/editor/extension-gallery#:~:text=You can browse and install,on the VS Code Marketplace.)，但您可以通过敲击`Ctrl+shift+x`随意浏览。

![扩展](https://wandersky.org/wp-content/uploads/2021/09/202109160121352.png)

本指南仅涉及 VS Code 功能的皮毛。请记住，如果您希望 VS Code 可以做某事，它很可能可以。直接谷歌它！

### 结对编程

您可以使用 Live Share 拓展在 VSCode 中结对程序。

[在这里下载](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare&ssr=false)

一旦您和您的搭档都安装了扩展程序，您将需要启动一个新的 Live Share 会话，然后明确地相互共享你们的代码和终端。有关共享和加入会话的更多详细信息，请参阅下载页面上的说明。