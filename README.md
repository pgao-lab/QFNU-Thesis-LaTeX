# 曲阜师范大学硕博学位论文LaTeX模板

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/username/QFNU-Thesis-LaTeX?style=social)](https://github.com/username/QFNU-Thesis-LaTeX/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/username/QFNU-Thesis-LaTeX?style=social)](https://github.com/username/QFNU-Thesis-LaTeX/network/members)

本项目提供了一个用于排版曲阜师范大学硕士、博士学位论文的LaTeX模板。该模板严格按照学校研究生院的学位论文格式要求设计，支持中英文摘要、图表、公式、算法、参考文献等学术论文的必要元素。

## 模板特点

- 符合学校规范：严格遵循曲阜师范大学研究生院的学位论文格式要求
- 模块化设计：样式与内容分离，便于维护和扩展
- 简单易用：提供清晰的文档结构和详细使用说明
- 自动生成：封面、页眉页脚、目录等元素自动生成
- 统一样式：字体、间距、标题格式等统一设置
- 功能完备：支持图表、公式、算法、参考文献等学术论文常用元素

## 目录结构（优化版）

```
QFNU-Thesis-LaTeX/
├── main.tex               # 主文件 - 控制论文整体结构
├── README.md              # 说明文档
├── .gitignore             # Git忽略文件
│
├── styles/                # 样式文件 - 集中管理所有格式设置
│   ├── packages.tex       # 包导入文件 - 集中管理所有需要的包
│   ├── format.tex         # 格式设置文件 - 字体、间距、标题等格式
│   └── info.tex           # 文档信息文件 - 用户需要自定义的信息
│
├── front/                 # 前置部分
│   ├── cover.tex          # 封面及声明页
│   ├── abstract.tex       # 摘要（中英文）
│   └── tableofcontents.tex # 目录设置
│
├── chapters/              # 章节文件
│   ├── Abstract1.tex      # 中文摘要内容
│   ├── Abstract2.tex      # 英文摘要内容
│   ├── chapter1.tex       # 第一章：绪论
│   ├── chapter2.tex       # 第二章：基础知识与相关研究
│   ├── chapter3.tex       # 第三章：模版设计与实现
│   ├── chapter4.tex       # 第四章：模版使用说明
│   ├── chapter5.tex       # 第五章：总结与展望
│   ├── chapter6.tex       # 发表的学术论文及研究成果
│   └── chapter7.tex       # 致谢
│
├── bib/                   # 参考文献
│   ├── references.bib     # 参考文献数据库
│   └── gbt7714-numerical.bst # 参考文献样式文件
│
├── figure/                # 图片资源
│   └── logo/              # 学校标志（logo-1.png, logo-2.png）
│
└── fonts/                 # 特殊字体（如需）
```

## 快速上手指南

### 环境配置

本模板需要使用XeLaTeX编译器，推荐安装最新版的TeX Live或MiKTeX。

#### 安装LaTeX环境

- Windows：[TeX Live](https://tug.org/texlive/)
- macOS：[MacTeX](https://tug.org/mactex/)
- Linux：TeX Live（通过包管理器安装）

#### 编辑器推荐

- [TeXstudio](https://www.texstudio.org/)：跨平台LaTeX编辑器，提供良好的编辑体验
- [VS Code](https://code.visualstudio.com/) + [LaTeX Workshop插件](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)：灵活且功能强大
- [Overleaf](https://www.overleaf.com/)：在线LaTeX编辑器，无需本地安装

### 使用方法

#### 1. 修改个人信息

打开`styles/info.tex`文件，修改以下个人信息：

```latex
% 基本信息
\title{你的论文标题}                       % 论文标题
\author{你的姓名}                         % 作者姓名
\newcommand{\thesuper}{导师姓名\hspace{0.5em}职称}   % 指导教师
\newcommand{\thedept}{你的学院}                     % 培养单位
\newcommand{\themajor}{你的专业}                    % 一级学科
\newcommand{\thesubmajor}{二级学科（如有）}          % 二级学科

% 日期和时间
\newcommand{\thecompletiondate}{YYYY年MM月DD日}     % 论文完成日期
\newcommand{\thedefenddate}{YYYY年MM月DD日}         % 答辩日期

% 论文类型
\newcommand{\thesistype}{Master}                    % 可选：Master（硕士）, Doctor（博士）

% 摘要关键词
\newcommand{\zhkeywords}{关键词1，关键词2，关键词3}     % 中文关键词
\newcommand{\enkeywords}{keyword1, keyword2, keyword3} % 英文关键词
```

#### 2. 编写摘要

- 编辑`chapters/Abstract1.tex`文件撰写中文摘要
- 编辑`chapters/Abstract2.tex`文件撰写英文摘要

#### 3. 编写正文内容

编辑`chapters/`目录下的各章节文件：

- `chapter1.tex`：绪论
- `chapter2.tex`：基础知识与相关研究
- 以此类推...

每个章节使用`\section{}`命令开始，子节使用`\subsection{}`和`\subsubsection{}`。

示例：
```latex
\section{绪论}

\subsection{研究背景}
这里是研究背景内容...

\subsection{研究意义}
这里是研究意义内容...
```

#### 4. 添加参考文献

在`bib/references.bib`文件中添加参考文献条目，例如：

```bibtex
@article{wang2022example,
  title={论文标题},
  author={Wang, Peng and Zhang, San},
  journal={期刊名称},
  volume={10},
  number={2},
  pages={100--110},
  year={2022},
  publisher={出版商}
}
```

在正文中使用`\cite{wang2022example}`引用文献。

#### 5. 编译论文

推荐使用以下编译流程：

```bash
xelatex main
bibtex main
xelatex main
xelatex main
```

大多数LaTeX编辑器都提供"一键编译"功能，推荐配置为上述流程。

## 自定义样式

### 字体设置

模板默认使用以下字体：
- 宋体（SimSun）：正文主要字体
- 黑体（simhei）：标题字体
- 仿宋（FangSong）：特定内容
- 楷体（KaiTi）：特定内容
- Times New Roman：所有西文文本（包括无衬线和等宽字体）

#### 本地字体文件

为了确保在不同系统环境中具有一致的排版效果，模板已配置为优先使用`fonts`文件夹中的本地字体文件：

- 中文字体：SimSun.ttf, simhei.ttf, FangSong.ttf, KaiTi.ttf
- 英文字体：times new roman.ttf, times new roman bold.ttf, times new roman italic.ttf, times new roman bold italic.ttf
- 数学字体：XITSMath-Regular.otf, XITSMath-Bold.otf

本模板统一使用Times New Roman作为所有西文字体，包括正文、无衬线和等宽字体，以保持西文字体样式的一致性。

如需修改字体，请编辑`styles/format.tex`文件中的字体设置部分。

### 章节标题格式

章节标题格式在`styles/format.tex`文件中定义，可根据需要进行调整：

```latex
% 一级标题格式
\titleformat{\section}{\centering\heiti\zihao{-3}\bfseries}{第\arabic{section}章}{1em}{}
\titlespacing{\section}{0pt}{24pt}{18pt}

% 二级标题格式
\titleformat{\subsection}{\heiti\zihao{4}}{\arabic{section}.\arabic{subsection}}{1em}{}
\titlespacing{\subsection}{0pt}{10pt}{10pt}
```

## 常见问题解答

### 编译错误

如果遇到编译错误，常见原因包括：

1. **字体问题**：确保系统安装了模板使用的字体，或修改`styles/format.tex`中的字体设置
2. **LaTeX包缺失**：使用包管理器安装缺失的包
3. **XeLaTeX配置**：确保使用XeLaTeX编译，而非pdfLaTeX

### 图片插入

使用以下代码插入图片：

```latex
\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.7\textwidth]{figure/your_image.png}
    \caption{图片说明}
    \label{fig:label}
\end{figure}
```

### 表格插入

使用以下代码插入表格：

```latex
\begin{table}[htbp]
    \centering
    \caption{表格标题}
    \label{tab:label}
    \begin{tabular}{|c|c|c|}
        \hline
        表头1 & 表头2 & 表头3 \\
        \hline
        内容1 & 内容2 & 内容3 \\
        \hline
    \end{tabular}
\end{table}
```

## 版本历史

- v2.0.0 (2025.02.24)：优化模板结构，实现样式与内容分离
- v1.0.0 (2025.02.23)：首次发布

## 贡献指南

欢迎对本模板提出改进建议和贡献代码：

1. Fork 本项目
2. 创建您的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开一个 Pull Request

## 授权许可

本项目采用 [MIT 许可证](LICENSE)。

## 致谢

感谢所有为本项目提供帮助和建议的老师和同学，以及国内外 LaTeX 社区的贡献者们。

---

**免责声明**：本模板为非官方模板，使用前请确认符合学校最新的论文格式要求。如有冲突，请以学校研究生院的官方要求为准。
