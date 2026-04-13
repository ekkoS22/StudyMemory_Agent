
# StudyMemory Agent ⭐

Important:

This project uses the VS Code extension `Markdown+Math`. When viewing answer files, press `Ctrl+Shift+V` to open Markdown Preview and render math formulas.

This is a minimal course-question archive project.

Its goal is not to build a complex knowledge base. Instead, every time you send a problem to Codex, Codex should:

1. Identify the course
2. Identify the topic
3. Solve the problem
4. Save the answer to the correct Markdown file
5. Update `logs.md`

## Project Structure

The core structure is:

```text
wiki/
  <COURSE>/
    <TOPIC>/
      <COURSE>-<TOPIC>.md
logs.md
RULE.md
RULE_CN.md
README.md
```

Examples:

```text
wiki/ECE301/DTFT/ECE301-DTFT.md
wiki/MA265/Markov_Matrices/MA265-Markov_Matrices.md
wiki/MA265/Spherical_Coordinates/MA265-Spherical_Coordinates.md
```

Problems from the same course and the same topic should be appended to the same Markdown file.

## Rule Files

`RULE.md` is the English rule file.

`RULE_CN.md` is the Chinese rule file.

If you ask in Chinese, Codex should read and follow `RULE_CN.md`.

If you ask in English, Codex should read and follow `RULE.md`.

## How To Use

Send Codex a screenshot or text version of a problem, for example:

```text
How do I solve this?
```

Codex should identify the course and topic automatically, then save the answer to a path like:

```text
wiki/MA265/Spherical_Coordinates/MA265-Spherical_Coordinates.md
```

At the end, Codex should give you a short answer summary and the saved file path.

## Current Courses

The project currently includes a few example files. Update the course list in `RULE.md` and `RULE_CN.md` according to the courses you are taking this semester.

```text
ECE301   Signals and Systems
ECE20875 Python for Data Science
MA265    Linear Algebra
ECE382   Control Systems
```

## Markdown Math Format

This project uses Markdown+Math dollar delimiters.

Inline math:

```md
$x^2+y^2=z^2$
```

Display math:

```md
$$
F(\omega)=\frac{1}{1-\frac{3}{4}e^{-j\omega}}
$$
```

Do not use other LaTeX delimiters.

Do not leave LaTeX commands outside `$...$` or `$$...$$`.

## Answer Format

English answers usually use:

```md
## Q<number or short title>

### Question

### Solution

### Topic

### Trouble Spots
```

Chinese answers usually use:

```md
## Q<number or short title>

### 题目

### 解答

### 考点

### 易错点
```

## Logs

Every time an answer is added or updated, `logs.md` should be updated.

Recommended format:

```text
YYYY/M/D HH:mm <COURSE>/<TOPIC>/<COURSE>-<TOPIC>.md was answered.
```

Example:

```text
2026/4/13 00:37 MA265/Spherical_Coordinates/MA265-Spherical_Coordinates.md was updated.
```

## Encoding Note

Markdown files should be saved as UTF-8.

If Chinese text appears garbled in VS Code or the terminal, check the file encoding before changing the content.

## Simplicity Principle

This project has one job: save course-problem solutions.

The ideal state is one Markdown file per topic, with questions accumulating clearly over time.


--------------------------------------------- 中文分割线：以下是中文说明 ----------------------------------------------

重要！！：
本项目使用 VSCode 内部插件 'Markdown+Math'，查看答案时请使用   'ctrl+Shift+V'    以查看数学公式形式

这是一个极简课程题目归档项目。
它的目标不是做复杂知识库，而是让你每次把题目丢给 Codex 后，Codex 自动完成：

1. 判断课程
2. 判断考点
3. 解题
4. 把答案保存到对应 Markdown 文件
5. 更新 `logs.md`

## 项目结构

当前约定的核心结构是：

```text
wiki/
  <COURSE>/
    <TOPIC>/
      <COURSE>-<TOPIC>.md
logs.md
RULE.md
RULE_CN.md
README.md
```

例子：

```text
wiki/ECE301/DTFT/ECE301-DTFT.md
wiki/MA265/Markov_Matrices/MA265-Markov_Matrices.md
wiki/MA265/Spherical_Coordinates/MA265-Spherical_Coordinates.md
```

同一门课、同一个考点的题目，会继续追加到同一个 Markdown 文件里。

## 规则文件

`RULE.md` 是英文规则。
`RULE_CN.md` 是中文规则。

如果你用中文提问，Codex 应该读取并遵守 `RULE_CN.md`。
如果你用英文提问，Codex 应该读取并遵守 `RULE.md`。


## 使用方式

直接把题目截图或文字发给 Codex，例如：

```text
这题怎么做
```

Codex 应该自动识别课程和考点，然后保存到类似路径：

```text
wiki/MA265/Spherical_Coordinates/MA265-Spherical_Coordinates.md
```

回答结束时，Codex 应该告诉你答案摘要和保存路径。

## 当前课程

目前已有少许案例文件供参考，请根据本学期上的课程自行更换以供智能体识别
如果学期课程变了，更新 `RULE.md` 和 `RULE_CN.md` 里的课程列表即可。

```text
ECE301   Signals and Systems
ECE20875 Python for Data Science
MA265    Linear Algebra
ECE382   Control Systems
```

## Markdown 数学格式

本项目使用 Markdown+Math 的 dollar delimiters。

行内公式：

```md
$x^2+y^2=z^2$
```

独立公式：

```md
$$
F(\omega)=\frac{1}{1-\frac{3}{4}e^{-j\omega}}
$$
```

不要使用其他 LaTeX delimiter。

不要把 LaTeX 命令裸露在 `$...$` 或 `$$...$$` 外面。

## 答案格式

英文回答通常使用：

```md
## Q<number or short title>

### Question

### Solution

### Topic

### Trouble Spots
```

中文回答通常使用：

```md
## Q<number or short title>

### 题目

### 解答

### 考点

### 易错点
```

## 日志

每次新增或更新题目答案，都应该更新 `logs.md`。

推荐格式：

```text
YYYY/M/D HH:mm <COURSE>/<TOPIC>/<COURSE>-<TOPIC>.md was answered.
```

例子：

```text
2026/4/13 00:37 MA265/Spherical_Coordinates/MA265-Spherical_Coordinates.md was updated.
```

## 编码提醒

Markdown 文件建议统一保存为 UTF-8。

如果中文在 VS Code 或终端里显示乱码，优先检查文件编码，而不是先改内容。

## 简化原则

这个项目只做一件事：保存课程题目的解答。

理想状态是：每个考点一个 Markdown 文件，题目越积越清楚。
