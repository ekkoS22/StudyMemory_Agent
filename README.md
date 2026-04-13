
# StudyMemory Agent ⭐
> You didn’t forget the material.  
> You lost access to it.

---

## The Problem

You asked hundreds of questions this semester.

- You understood them.
- You moved on.
- You forgot them.

Your knowledge is now buried across dozens of chat threads.

When exams come:
- You don’t know what to review
- You don’t know what you kept getting wrong
- You start from scratch

This is not a knowledge problem.

This is a **memory system failure**.

---

## What This Project Does

It is not a chatbot.

It is a **study memory system**.

It takes your scattered learning conversations and turns them into:

- structured knowledge
- tracked misconceptions
- compressed review material
- exam-ready summaries

---

## Core Idea

> Don’t store conversations.  
> Store what matters for review.

We convert raw chat into **memory units**:

- concepts
- formulas
- problem patterns
- misconceptions (most important)
- summaries

Then we:

- deduplicate  
- prioritize  
- compress  

So you don’t reread — you **recall**.

---

## Why This Is Different

Most tools:
- store notes  
- store chats  
- store everything  

This system:
- stores **only what improves future performance**

Especially:

> what you repeatedly get wrong

Because that’s what actually shows up on exams.

---

## Pipeline

```text
[ Raw Chat / Study Session ]
            ↓
      [ Extractor ]
            ↓
   [ Memory Units (structured) ]
            ↓
 [ Dedup + Priority Assignment ]
            ↓
      [ Local Storage ]
            ↓
   [ Review Generator ]
            ↓
[ Exam Sheets / Weak Points / Cram Notes ]

```text


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

直接把题目截图或文字在vscode内部发给 Codex，例如：

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
