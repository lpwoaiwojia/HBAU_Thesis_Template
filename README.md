# 河北农业大学博士学位论文 LaTeX 模板

## 📋 项目概述

本模板依据《河北农业大学研究生学位（毕业）论文格式要求及撰写规范》及学校提供的 Word 模板制作，可**直接在 Overleaf 编译运行**，适用于河北农业大学博士学位论文的撰写。

---

## ⚠️ 前期准备（必读）

### 1. 系统要求

| 项目 | 要求 |
|------|------|
| 编译器 | **XeLaTeX**（不可用 pdfLaTeX / LaTeX） |
| 参考文献引擎 | **Biber**（不可用 BibTeX） |
| Overleaf 版本 | 标准版或以上 |
| 浏览器 | Chrome / Firefox / Safari（最新版） |

### 2. 需要提前准备的材料

在开始填写模板之前，请准备好以下信息：

- **论文题目**（中文、英文各一个）
- **学位申请人姓名**
- **指导教师姓名及职称**
- **学科专业名称**
- **学位类别**（如工学博士、农学博士等）
- **答辩日期**（中文格式，如"二〇二六年六月"）
- **分类号**（按《中国图书资料分类法》填写）
- **学号**
- **论文图片文件**（建议放入 `figures/` 文件夹）

### 3. 文件使用说明

| 文件 | 需要用户修改？ | 说明 |
|------|:------------:|------|
| `main.tex` | **必须修改** | 填写封面信息（标题、姓名等） |
| `chapters/*.tex` | **必须修改** | 替换为您的正文内容 |
| `abstract.tex` | **必须修改** | 替换为您的摘要内容 |
| `abstract_en.tex` | **必须修改** | 替换为您的英文摘要 |
| `conclusion.tex` | **必须修改** | 替换为您的结论 |
| `acknowledgements.tex` | **必须修改** | 替换为您的致谢 |
| `references.bib` | **必须修改** | 替换为您的参考文献数据 |
| `hbauthesis.sty` | **无需修改** | 格式定义（已按学校要求配置好） |
| `cover.tex` | **无需修改** | 封面版式（数据自动从 main.tex 读取） |
| `statement.tex` | **无需修改** | 声明页版式 |
| `toc.tex` | **无需修改** | 目录配置 |
| `references.tex` | **无需修改** | 参考文献输出配置 |

### 4. 文件结构

```
HBAU_Thesis_Template/
│
├── main.tex               # 📄 主文件（入口 + 用户信息填写区）
├── hbauthesis.sty         # 📄 格式定义包（所有排版参数集中在此）
│
├── cover.tex              # 封面
├── titlepage.tex          # 扉页
├── statement.tex          # 独创性声明及版权使用授权书
├── abstract.tex           # 中文摘要
├── abstract_en.tex        # 英文摘要
├── toc.tex                # 目录
├── conclusion.tex         # 结论
├── references.tex         # 参考文献
├── references.bib         # 参考文献数据库（.bib 文件）
├── acknowledgements.tex   # 致谢
│
├── chapters/              # 📁 各章节文件
│   ├── chap01_intro.tex   # 第一章 绪论（示例）
│   └── chap02_example.tex # 第二章 材料与方法（示例）
│
├── figures/               # 📁 存放论文中的图片
│   └── (请放入您的图片文件)
│
└── README.md              # 本文件
```

---

## 🚀 Overleaf 完整使用流程

### 第一步：上传项目

1. 将整个 `HBAU_Thesis_Template` 文件夹压缩为 `.zip` 文件
2. 登录 [Overleaf](https://www.overleaf.com/)
3. 点击左上角 **New Project** → **Upload Project**
4. 选择压缩包上传
5. 确认左侧文件列表中有 `main.tex`

### 第二步：设置编译器（最关键的一步！）

> ⚠️ **这一步如果遗漏，编译必定失败！**

1. 点击 Overleaf 左上角 **Menu** 按钮
2. 在 **Settings** 区域找到 **Compiler**
3. **必须选择 XeLaTeX**（默认是 pdfLaTeX，不可用）
4. 关闭菜单

> 本模板在 `main.tex` 开头设置了编译器检测代码。如果忘记选择 XeLaTeX，编译时会显示红色错误提示，按照提示操作即可。

### 第三步：修改封面信息

打开 `main.tex`，在"用户信息填写区"修改以下内容：

```latex
% --- 封面信息 ---
\thesistitlecn{论文中文题目}                     % ← 修改这里
\thesistitleen{English Title of the Thesis}       % ← 修改这里

\applicant{姓\quad 名}                            % ← 修改这里
\supervisor{导师姓名\quad 教授}                   % ← 修改这里
\majorcn{专业名称}                                % ← 修改这里
\categorycn{工学博士}                             % ← 修改这里
\unitname{河北农业大学}                           % ← 不用改
\defensedate{二〇二六年六月}                      % ← 修改这里
```

> **注意：** 姓名的 `\quad` 表示一个汉字的空格。例如"张三"改为"张\quad 三"。
> 如果姓名只有两个字，`\quad` 放在中间。三个字的名字也可以加空格。

### 第四步：填写扉页信息

```latex
% --- 扉页信息 ---
\classification{}        % ← 填写分类号（如 S126）
\security{}              % ← 密级（公开不用填写）
\studentid{}             % ← 填写学号
```

### 第五步：编译

1. 点击 **Recompile** 按钮
2. **首次编译需要 2-3 轮**才能生成完整的目录和参考文献：
   - 第 1 次：生成辅助文件
   - 第 2 次：生成参考文献
   - 第 3 次：生成完整目录
3. 多点击几次 Recompile 即可

> Overleaf 的自动编译机制通常会自动完成多轮编译，直接等待即可。

---

## 📝 各项内容填写指南

### 如何写摘要

打开 `abstract.tex`：

- **"摘要"** 两字无需改动（自动设置为黑体小四号居中）
- **摘要正文**替换为您的实际摘要内容（宋体小四号，行距18磅）
- **关键词**修改以下行的词条：
  ```latex
  \noindent{\zihao{-4}\heiti 关键词：}%
  {\zihao{-4}\songti 关键词1；关键词2；关键词3；关键词4；关键词5}
  ```
- 关键词之间用**分号**隔开，4~6 个为宜

英文摘要同理，修改 `abstract_en.tex`。

### 如何添加新章节

1. 在 `chapters/` 文件夹中创建新文件，如 `chap03_results.tex`
2. 文件开头用章节命令：
   ```latex
   \chapter{结果与分析}
   \label{chap:results}
   
   \section{数据统计结果}
   \label{sec:stats}
   
   \subsection{描述性统计}
   \label{subsec:descriptive}
   ```
3. 在 `main.tex` 正文区添加：
   ```latex
   \include{chapters/chap03_results}
   ```

### 如何插入图片

1. 将图片文件放入 `figures/` 文件夹
2. 在正文中使用：
   ```latex
   \begin{figure}[htbp]
     \centering
     \includegraphics[width=0.7\textwidth]{figures/your_image.png}
     \caption{图标题（中文）}
     \label{fig:your_label}
     \bigskip
     \centering
     {\zihao{5}\normalfont Figure~\ref{fig:your_label} Figure title (English)}
   \end{figure}
   ```
3. 支持的图片格式：PDF（推荐）、PNG、JPG、EPS

### 如何制作三线表

```latex
\begin{table}[htbp]
  \centering
  \caption{表标题}
  \label{tab:your_label}
  \bigskip
  {\zihao{5}\normalfont Table~\ref{tab:your_label} Table title}\\[4pt]
  \begin{tabular}{lcc}
    \toprule
    列1 & 列2 & 列3 \\
    \midrule
    数据1 & 数据2 & 数据3 \\
    数据4 & 数据5 & 数据6 \\
    \bottomrule
  \end{tabular}
\end{table}
```

### 如何写公式

```latex
\begin{equation}
  \label{eq:your_label}
  y = ax^2 + bx + c
\end{equation}
```
公式自动居中，编号自动生成，编号格式为 `(章号.序号)`。

### 如何引用参考文献

在正文中引用：`\cite{ref1}` 或 `\cite{ref1,ref2}`

在 `references.bib` 中添加文献条目。示例格式：

```bibtex
@article{ref1,
  author  = {作者1 and 作者2},
  title   = {文章标题},
  journal = {期刊名称},
  year    = {2024},
  volume  = {10},
  number  = {2},
  pages   = {100--110},
}

@book{ref3,
  author    = {作者},
  title     = {书名},
  address   = {出版地},
  publisher = {出版社},
  year      = {2023},
}
```

---

## 🔧 排版参数对照表

| 格式项 | Word 规范要求 | LaTeX 对应 |
|--------|-------------|-----------|
| 纸张 | A4（210mm×297mm） | `a4paper` |
| 左边距 | 30mm | `left=30mm` |
| 右边距 | 25mm | `right=25mm` |
| 上边距 | 30mm | `top=30mm` |
| 下边距 | 25mm | `bottom=25mm` |
| 页眉边距 | 23mm | `headheight=15pt` + `headsep=10mm` |
| 页脚边距 | 18mm | `footskip=18mm` |
| 一级标题 | 黑体三号，居中，段前段后1行 | `\chapter`（ctexset） |
| 二级标题 | 宋体四号，左对齐，段前段后1行 | `\section`（ctexset） |
| 三级标题 | 黑体小四号，左对齐，段前段后1行 | `\subsection`（ctexset） |
| 正文 | 宋体小四号，行距18磅 | `\zihao{-4}` + `\setstretch{1.5}` |
| 中文摘要 | "摘要"黑体小四号居中 | 手动设置 |
| 英文摘要 | Times New Roman 12pt | 手动设置 |
| 图表标题 | 小五号黑体，中英文对照 | caption + 手动英文标题 |
| 表格 | 三线表 | `booktabs` 宏包 |
| 页眉 | 奇数页：论文题名 / 偶数页：河北农业大学博士学位论文 | `fancyhdr` |
| 页眉横线 | 单直线，粗度1.5磅 | `\headrulewidth{1.5pt}` |
| 参考文献 | GB/T 7714-2015 顺序编码制 | `biblatex` + `gb7714-2015` |
| 目录 | "目 录"黑体三号，显示三级标题 | `ctexset` + `tocdepth=3` |

---

## 🖥️ 本地编译指南

### 在本地 Windows/Mac 编译（需安装 TeX Live 或 MacTeX）

#### 方案一：使用 Overleaf 相同的字体（推荐）

已安装 TeX Live 2025 的用户，`fontset=ubuntu` 可直接使用 Noto CJK 字体。

编译命令（终端或命令行）：
```bash
xelatex main
biber main
xelatex main
xelatex main
```

#### 方案二：使用 Windows 系统字体（宋体/黑体）

打开 `main.tex`，将：
```latex
\documentclass[UTF8,...,fontset=ubuntu]{ctexbook}
```
改为：
```latex
\documentclass[UTF8,...,fontset=windows]{ctexbook}
```
然后**删除**以下行（因为 `fontset=windows` 会自动定义 `\songti` / `\heiti`，且 `\setmainfont` 与 `fontset=windows` 不兼容）：

```latex
\setmainfont{Times New Roman}
```

编译命令同上：`xelatex → biber → xelatex → xelatex`

---

## 💡 字体说明

### Overleaf 字体映射（fontset=ubuntu）

| 用途 | 映射字体 | 对应 Word 字体 |
|------|---------|---------------|
| 宋体（`\songti`） | Noto Serif CJK SC | 宋体 |
| 黑体（`\heiti`） | Noto Sans CJK SC | 黑体 |
| 英文/数字 | Times New Roman | Times New Roman |

> Overleaf 已预装以上字体，无需手动安装。

---

## ❓ 常见问题与解决方法

### Q1：编译后没有 PDF，报错 "fontspec requires XeTeX"

**原因：** 编译器未设置为 XeLaTeX，错误地使用了 pdfLaTeX。  
**解决：** Overleaf 左上角 **Menu → Compiler → 选择 XeLaTeX**，然后重新编译。

### Q2：编译后中文显示为方框（豆腐块）

**原因：** 字体加载失败或未使用 XeLaTeX。  
**解决：**
- 确认 Overleaf 的 Compiler 设置为 **XeLaTeX**
- 确认文档类选项为 `fontset=ubuntu`（不是 `fontset=windows` 或 `fontset=fandol`）

### Q3：编译报错 "CTeX fontset `fandol' is unavailable"

**原因：** TeX Live 2025 已移除 fandol 字体包。  
**解决：** 本模板已使用 `fontset=ubuntu`，无需 fandol。请确认 `main.tex` 中为：
```latex
\documentclass[...,fontset=ubuntu]{ctexbook}
```

### Q4：参考文献没有显示或显示为问号 "?"

**原因：** 未完成 biber 编译步骤。  
**解决：** 多点击几次 **Recompile**（2~3 次）。Overleaf 会自动完成 `xelatex → biber → xelatex` 流程。

### Q5：目录没有内容或没有页码

**原因：** 只编译了一次，目录信息尚未生成。  
**解决：** 再次点击 Recompile。多个章节需多次编译才能生成正确目录。

### Q6：封面没有页码／页码不是从正文开始

**注意：** 模板已自动处理页码格式：
- 封面、扉页、声明页：无页码
- 摘要、目录：大写罗马数字（I, II, III...）
- 正文开始：阿拉伯数字（1, 2, 3...）

如仍有问题，检查 `toc.tex` 中的 `\pagenumbering{arabic}` 是否被意外删除。

### Q7：图片插入后位置不对（跑到了其他页面）

**原因：** LaTeX 的浮动体机制会自动调整图片位置以优化排版。  
**解决：**
- 使用 `[htbp]` 选项：`\begin{figure}[htbp]`
- 如果想强制固定位置，加 `[H]` 选项：`\begin{figure}[H]`（需导入 `float` 宏包，已包含）

### Q8：表格中的文字过宽超出页面

**解决：**
- 使用 `tabularx` 环境自动调整列宽
- 或者将 `\begin{tabular}{lll}` 改为 `\begin{tabular}{p{3cm}p{4cm}p{5cm}}`

### Q9：编译超时或内存不够

**解决：**
- 减少同时编译的图片数量
- 图片文件不要过大（建议分辨率不超过 300dpi，宽度不超过 15cm）
- 在 Overleaf 中设置编译超时为 60 秒

### Q10：如何加粗正文中的文字

中文加粗：`\textbf{重要结论}`  
注意：如果使用 `fontset=ubuntu`，Noto CJK 字体的加粗效果有限。如需更明显的加粗效果，可以考虑使用黑体：`{\heiti 重要结论}`。

---

## 📐 格式规范速查

### 页面要求
- A4 纸（210mm×297mm）
- 左侧装订
- 版芯：左边距 30mm，右边距 25mm，上边距 30mm，下边距 25mm

### 正文要求
- 中文：宋体小四号（12pt）
- 英文/数字：Times New Roman
- 行距：18磅（1.5倍行距）
- 段首缩进：2个汉字字符
- 博士论文一般 5~10 万字

### 标题要求
- 一级标题：黑体三号（16pt），居中，段前段后各 1 行
- 二级标题：宋体四号（14pt），左对齐，段前段后各 1 行
- 三级标题：黑体小四号（12pt），左对齐，段前段后各 1 行

### 图表要求
- 图序及图名置于图的下方，居中
- 表序及表名置于表的上方，居中
- 标题：小五号黑体（10.5pt），中英文对照
- 表格一律使用三线表

### 参考文献要求
- GB/T 7714-2015 顺序编码制
- 按引用顺序排列
- 作者不超过 3 位全部列出，超过 3 位加"等"或"et al"
- 参考文献类型标识：专著[M]、期刊[J]、学位论文[D]等

---

## 📌 小贴士

- **定期编译**：建议每写一部分内容就编译一次，避免最后一次性编译时出现大量错误难以排查
- **先看 PDF**：每次修改后查看 PDF 输出效果，确保排版符合要求
- **备份**：重要版本建议导出 `.zip` 备份
- **Overleaf 自动保存**：Overleaf 会自动保存您的修改，无需手动保存
- **协同编辑**：Overleaf 支持多人协同，可以邀请导师在线查看批注
