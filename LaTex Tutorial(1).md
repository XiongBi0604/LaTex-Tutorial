# *LaTex Tutorial* 
>- *Overleaf* 将 *LaTex文档* 存储为一个名为 *main.tex* 的文件。
>- % 开头的任何内容都是**注释（comment）**，但不会出现在生成的PDF文档中。
>- 所有的LaTeX命令都必须以**反斜杠\ 开头**。

# 1. *前言部分（preamble）*
>- 包括**文档类型**、**标题**、**作者**、**日期**、**字体及字号**、**LaTex包**等。

>- **文档类型：\documentclass{}**
>>- \documentclass{article} 表示**文档类型为论文类**，此外book表示书籍类，report表示报告类。
>>- \documentclass[12pt, a4paper]{article} 表示**文档类型为论文类，字号为12pt，纸张大小为a4**。

>- **LaTex包：\usepackage{}**
>>- \usepackage{ctex} 表示**使用中文包**。
>>- \usepackage{amsmath} 表示**使用数学公式包**。
>>- \usepackage{graphicx} 表示**使用插图包**。

>- **标题：\title{}**
>>- \title{my paper title} 表示论文的题目为**my paper title**。

>- **作者：\author{}**
>>- \author{xiong bi} 表示论文的作者为**xiong bi**。
>>- \author{xiong bi \and HE} 表示论文的作者为**xiong bi** 和 **HE**。
>>- \author{xiong bi\thanks{Email: xiong.bi@temple.edu}} 表示论文的作者为**xiong bi**，并在作者名的右上方添加一个图标，然后在页面最下方对图标进行解释，解释的内容就是**Email: xiong.bi@temple.edu**。
>>- \author{xiong bi\thanks{Email: xiong.bi@temple.edu} \and HE\thanks{Email: HE@temple.edu}} 表示论文的作者为**xiong bi** 和 **HE**， 并分别在作者名右上方添加一个图标，然后在页面最下方对两个图标进行解释，解释的内容分别为**Email: xiong.bi@temple.edu** 和 **Email: HE@temple.edu**。

>- **日期：\date{}**
>>- \date{August 2024} 表示论文的日期为**2024年8月**。


# 2. *正文部分*
>- **正文部分** 位于 **\begin{document}** 和 **\end{document}** 之间。且**正文部分**包括**摘要**、**论文内容**、**参考文献**、**附录**、**图像**等。

>- **\maketitle** 命令自动生成并排版**标题页**，显示**前言部分**中定义的标题、作者、日期等信息。

>- **正文部分的LaTex命令结构**
>>- **\begin{document}**
>>- **\maketitle**
>>- **正文部分**
>>- **\end{document}**

>- 若对**正文部分**进行了修改，则点击overleaf中的**Recompile**按钮以进行手动重新编译。

>- 每次对**正文内容**进行修改后overleaf也可自动重新编译，只需点击Recompile旁边的小箭头，然后将**Auto Compile设置为On**就行了。

# 3. *粗体（bold）、斜体（italics）、下划线（underlining）操作*
>- **\textbf{}**：将{}中的内容进行加粗
>- **\textit{}**: 将{}中的内容进行斜体
>- **\underline{}**: 将{}中的内容进行下划线
>- **\textbf{\textit{}}**：将{}中的内容进行加粗、斜体
>- **\textbf{\underline{}}**：将{}中的内容进行加粗、下划线

>>- **\emph{}**: 若某一句的字体为是斜体，则该命令将{}中的内容变为非斜体；若某一句的字体是非斜体，则该命令将{}中的内容变为斜体

# 4. *插入图像*
>- **方法一**：点击工具栏上的 **Insert Figure** 按钮插入图像
>- **方法二**：直接将图像复制粘贴到 **code editor** 或者 **visual editor** 中

>- **方法三**：手动插入
>>- 先在 **preamble部分** 中使用 **\usepackage{graphicx}** 命令，再使用 **\graphicspath{{images/}}**。其中 **images** 表示存储图像的文件夹名称，**{images/}** 表示图像的存储路径。
>>- 再在 **正文部分中** 中使用 **\includegraphics{universe}** 命令。其中 **universe** 表示图像的名称，不需要写 **.jpg** 等后缀名，overleaf会自动识别。

>>- 当使用方法三来插入图像时，尽量保证图像的名称中无后缀名。即使有后缀名也无妨，但尽量让后缀名小写。

# 5. *为插入的图像添加标题（caption）、添加标签（label，即编号）、通过标签引用插入图像*
>- 1.在**正文部分**中设置**figure环境**：设置插入图像的标题（caption），标签（label），插入位置[h]，对齐方式，宽度width。
>>- **具体的LaTex命令结构**：
>>>- **\begin{figure}[h]**
>>>>- 定义了一个figure环境。[h]表示尽量在**当前位置（here）** 插入图片
>>>- **\centering**
>>>>- 将图片**居中对齐**
>>>- **\includegraphics[width=0.75\textwidth]{mesh}**
>>>>- 将**图片的宽度width**设置为文本宽度textwidth的0.75倍；mesh为**图片的名称**
>>>- **\caption{A nice plot.}**
>>>>- 将**图片的标题caption**设置为**A nice plot.**
>>>- **\label{fig:mesh1}**
>>>>- 将**图片的标签label**设置为**fig:mesh1**，通过该标签可以在该文档的其他地方引用插入图片。
>>>- **end{figure}**
>>>>- 也是定义了一个figure环境

>- 2.在**正文部分**中通过标签label来引用插入的图像。
>>- **\ref{fig:mesh1}**: 使用 **\ref{}** 命令来引用插入的图像，其中**fig:mesh1**为插入图像的标签label。
>>- **\pageref{fig:mesh1}**: 使用 **\pageref{}** 命令来引用插入图像所在的页码。

# 6. *创建无序列表、有序列表*
>- **无序列表(unordered lists)**：在**正文部分**中使用 **itemize** 环境来创建无序列表。无序列表就是每一条之前加一个 **黑点（bullet）** 来做标记。
>>- **\begin{itemize}**
>>- **\item 列表内容（如一句话）**
>>- **\end{itemize}**

>>>- 注意，在创建无序列表时，每一个列表内容之前要用 **\item** 命令来开头。

>- **有序列表(ordered lists)**：在**正文部分**中使用 **enumerate** 环境来创建有序列表。有序列表就是每一条之前加一个 **数字（number）** 来做标记。
>>- **begin{enumerate}**
>>- **\item 列表内容（如一句话）**
>>- **end{enumerate}**

>>>- 注意，在创建有序列表时，每一个列表内容之前要用 **\item** 命令来开头。

# 7. *添加数学表达式*
>- **行内公式(inline math)**：在某一个段落内部
>>- **$  数学表达式  $** 
>>- **\begin{math}  数学表达式  \end{math}** 

>- **行间公式(display math)**：单独成行
>>- **\[  数学表达式  \]** 
>>- **\begin{equation}  数学表达式  \end{equation}**

>- **上标**
>>- **$a^b$**：b为次方数

>- **下标**
>>- **$a_b$**：b为下标

>- **分数**
>>- **$\frac{a}{b}$**：a为分子，b为分母

>- 注意，可以在 **preamble部分** 中加入 **\usepackage{amsmath}** 命令来使用 **amsmath数学公式包**。
