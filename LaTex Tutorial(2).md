# 8. *基本的文档结构*
>- **创建Abstract**
>>- 在**正文部分**中，使用 **abstract环境** 来对论文中的Abstract进行排版。具体的LaTex命令结构如下：
>>>- begin{abstract}
>>>- 摘要内容
>>>- end{abstract}


>- **创建New Paragraph、段落内换行**
>>- **创建新段落**：**连续按两次Enter键**，就会开始一个新的段落。
>>- **段落内换行**： 使用 **双反斜杠 \\\\** 命令 或者 使用 **\newline** 命令


>- **创建Chapter（章节）、Section（节）**
>>- 注意：对于不同的文档类，其Chapter和Section有不同的latex命令。其中，**article文档类** 中 **无chapter** 概念，**只有节（section）、子节（subsection）、子子节（subsubsection）等** 概念，因此我们主要介绍article文档类。
>>>- **\section{}**
>>>>- \section{Introduction}：会在 **PDF文档** 中创建一个名为 **Introduction** 的**节**，且 **节前会自动编号**。
>>>>- \section{Background}：会在 **PDF文档** 中创建一个名为 **Background** 的 **节**，且 **节前会自动编号**。
>>>- **\subsection{}**
>>>>- \subsection{CNN}：会在 **当前节** 下创建一个名为 **CNN** 的 **子节**，且 **子节前会自动编号**。
>>>- **\subsubsection{}**
>>>>- \subsubsection{Details}：会在 **当前子节** 下创建一个名为 **Details** 的 **子子节**，且 **子子节前会自动编号**。
>>- 若想 **节、子节、子子节前面不编号**，可以使用 \section*{}、\subsection*{}、\subsubsection*{} 等命令。

>- **创建Table（以及添加 边框lines/borders、线条rules、标题caption）**
>>- 在**正文部分**中，使用 **tabular环境** 来对论文中的Table进行排版。
>>- 具体的**LaTex命令结构**如下：
>>>- **\begin{center}**  ：center表示**居中对齐**、r表示**右对齐**、l表示**左对齐**
>>>- **\begin{tabular}{c c c}** ： **{c c c}表示创建的Table有三列**
>>>- cell1 & cell2 & cell3 \\\\ ： 表示每行中各数据之间用 **&** 进行分隔，然后用 **\\\\** 结束此行，但最后一行不需要 **\\\\**。
>>>- **\end{tabular}**
>>>- **\end{center}**
>- 总之，直接编写LaTex代码来生成Table比较耗时，因此会使用**Table在线生成器来自动生成LaTex代码** 

>- **给Table添加 边框lines/borders**：
>>- 使用 **\hline .... \hline** 来对 .... 添加**上下单边框**；使用 **| .... |** 来对 .... 添加**左右单边框**；使用 **|| .... ||** 来对 .... 添加**左右双边框** 

>- **给Table添加 标题caption、标签label（即编号）、引用reference**
>>- 在**正文部分**中，使用 **table环境** 来对论文中的Table添加 **标题caption**、**标签label**（即编号）、通过标签**引用reference**Table。
>>- 具体的**LaTex命令结构**如下：
>>>- **\begin{table}[h!]** ： 表示**此处插入表格**，h表示**此处插入表格后**，**尽可能向上移动**；!表示**此处插入表格后**，**尽可能向下移动**；t表示**此处插入表格后**，**尽可能向左移动**；b表示**此处插入表格后**，**尽可能向右移动**。
>>>- **\centering** ： 表示**表格居中**。
>>>- \begin{tabular}{||c c c c||} 
>>>- 表格内容
>>>- \end{tabular}
>>>- **\caption{Accuracy comparison}** ： 表示Table的标题是**Accuracy comparison**。
>>>- **\label{Table 1}** ：表示Table的标签是**Table 1**，即Table的**编号是 Table 1**。
>>>- Table **\ref{Table 1}** shows how to add a table caption and reference a table ：表示通过Table的**标签 / 编号 Table 1**在正文中来引用该Table。
>>>- **\end{table}**

>- **给PDF文档添加目录content**
>>- **\tableofcontents** ：用于自动生成文档目录，它会将文档中**带编号的节、子节等结构**自动列出，并生成**相应的页码**。
>>- 具体的**LaTex命令结构**如下：
>>>- \documentclass{article}
>>>- \title{LaTex Tutorial}
>>>- \author{张三}
>>>- \date{August 2024}
>>>- \begin{document}
>>>- \maketitle
>>>- **\tableofcontents**
>>>- 带编号的节、子节、子子节等正文内容
>>>- \end{document}
>>- 当想把**不带编号的节、子节等结构**手动加入目录中时，需要使用 **\addcontentsline{toc}{section}{节标题}** 命令；**\addcontentsline{toc}{subsection}{子节标题}** 命令。