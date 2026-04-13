# 学习答题 Agent 规则

## 强制启动规则

在这个工作区中，只要检测到用户使用中文提问，Codex 必须忽略 `RULE.md`，改为读取并遵守本文件 `RULE_CN.md`。

如果用户提出课程题目，包括截图、图片或文字题目，Codex 必须：

1. 识别课程。
2. 识别考点。
3. 解答题目。
4. 按照存储规则保存或追加答案。
5. 更新 `logs.md`。
6. 用简短中文回复，并给出保存路径。

除非用户明确说“不用保存”，否则不要只在聊天中回答。

不要修改 `RULE.md`！！！！
不要修改 `RULE_CN.md`！！！！

## 目标

回答学生的每一道课程题，并保存到最简单、最清晰的 Markdown 文件中。

## 存储规则

每个课程和考点使用一个 Markdown 文件：

```text
wiki/<COURSE>/<TOPIC>/<COURSE>-<TOPIC>.md
```

示例：

```text
wiki/ECE301/Signals/ECE301-Signals.md
wiki/MA265/Linear_Dependence/MA265-Linear_Dependence.md
wiki/ECE382/Root_Locus/ECE382-Root_Locus.md
```

如果同一课程、同一考点的文件已经存在，就把新题目追加到该文件末尾。

如果同一道题后来又被追问细节，要把补充内容继续追加或更新到对应 Markdown 文件中。

不要创建 `answers/`、`questions/`、`memory_units/`、索引、知识图谱、schema 或其他额外文件，除非用户明确要求。

## 日志规则

每次新增或更新题目答案，都要更新 `logs.md`。

日志格式：

```text
YYYY/M/D HH:mm <COURSE>/<TOPIC>/<COURSE>-<TOPIC>.md was answered.
```

示例：

```text
2026/4/13 23:10 ECE301/Signals/ECE301-Signals.md was answered.
```

## 当前课程 （实例）

###############################################################################
#####################    请根据你现在正在上的课程进行更改    #####################
###############################################################################

- ECE301: Signals and Systems
- ECE20875: Python for Data Science
- MA265: Linear Algebra
- ECE382: Control Systems

## 工作流程

1. 识别课程。
2. 识别考点。
3. 创建或复用 `wiki/<COURSE>/<TOPIC>/`。
4. 在该文件夹中创建或复用 `wiki/<COURSE>/<TOPIC>/<COURSE>-<TOPIC>.md`。
5. 将新答案作为一个新 section 追加进去。
6. 更新 `logs.md`。
7. 停止，不做额外整理。

## 答案格式

每一道题只使用下面格式：

```md
## Q<number or short title>

### 题目

### 解答

### 考点

### 易错点
```

如果题目没有编号，就用简短英文标题，例如：

```md
## Q Linear Dependence of Three Vectors
```

用户用中文提问时，Markdown 文件内容必须使用中文。

文件夹名和文件名使用英文。

## 数学格式

所有 Markdown 数学公式必须使用 Markdown+Math 的 dollar delimiters。

行内公式：

```md
$...$
```

独立公式：

```md
$$
...
$$
```

禁止使用其他 LaTeX delimiter。

禁止把 LaTeX 命令裸露在 `$...$` 或 `$$...$$` 外面。

独立公式前后要空行。

## 简化原则

不确定时，只做这些事：

1. 解题。
2. 保存到对应课程/考点 Markdown 文件。
3. 更新 `logs.md`。
4. 回复保存路径。

不要额外重构项目，不要自动整理无关文件，不要修改规则文件。
