#### LaTex 文档基本格式

```tex
% 引入文档类,其中的article可以换成其他类型
\documentclass{article} %book,report,letter

\title{My First Document}
\author{mila}
\date{\today}

% 正文区
\begin{document}
   \maketitle
   % letter没有title,不需要的代码最好注释掉
   % 普通文字直接写
   % 使用$数学公式$
   % $$公式单独占一行$$
\end{document}
```

#### 处理中文格式

- 处理中文格式引入 ctex 包

  ```tex
  % 在documentclass类后面添加ctex
  \usepackage{ctex}

  % 后续可以指定字体的格式
  \title{\heiti 勾股定理}

  ```

- 数学公式带序号

  ```tex
  \begin{equation}
  f(x)=3.12×x^2+4
    % 注意公式中的代码不加%
  \end{equation}
  ```

- 角的度数

  ```tex
  % 添加包
  \newcommand\degree{^\circ}

  从题中可知$\angle
  C=90\degree$
  ```

#### LaTex 的字体

- 字体属性

  - 字体编码
    - 正文字体编码
    - 数字字体编码
  - 字体族
    - 罗马字体：笔画起始处有装饰
    - 无衬线字体：笔画起始处无装饰
    - 打字机字体：每个字符宽度相同
  - 字体系列
    - 粗细
    - 宽度
  - 字体形状
    - 直立
    - 斜体
    - 伪斜体
    - 小型大写
  - 字体大小

- 字体设置

  ```tex
  % 字体族设置(罗马字体,无衬线字体,打字机字体)
  \textrm{文字内容}
  \textsf{文字内容}
  \texttt{文字内容}

  % 字体声明,可以通过{}对字体范围进行设置
  {\rmfamily 文字内容}
  {\sffamily 文字内容}
  {\ttfamily 文字内容}
  ```

  **当它没有使用{}进行限制的时候,声明字体之后直到遇见下一个字体声明都应用上述字体声明**

- 字体系列设置(粗细、宽度)

  ```tex
  % 细体
  \textmd{文字内容}
  {\mdseries 文字内容}

  % 粗体
  \textbf{文字内容}
  {\bfseries 文字内容}
  ```

- 字体形状设置

  ```tex
  % 直立
  \textup{}
  {\upshape}
  % 斜体
  \textit{}
  {\itshape}
  % 伪斜体
  \textsl{}
  {\slshape}
  % 小型大写
  \textsc{}
  {\scshape}
  ```

- 中文字体的设置
  ```tex
  {\songti}
  {\heiti}
  ```

#### 表格的处理

```tex
% 设置表格中的对齐方式
% l左对齐 c中间对齐 r右对齐
\begin{tabular}{l|c|c|c|r}
% 使用\hline进行划单横线
% 使用\\hline进行划双横线

\hline
% 每一行结束使用\\进行换行
姓名&语文&数学&外语&备注\\
\hline
张三&45&34&89&不合格\\
\hline
李四&67&98&90&优秀\\
\hline
\end{tabular}
```

- 注意
  - {l|r}中间使用|进行分割,中间的空格移除不起作用,使用||进行‖进行分割
  - 在每一行中元素之间使用&进行分割
