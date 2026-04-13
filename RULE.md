# Study Answer Agent Rules
## Mandatory Startup Rule

Before answering any question in this workspace, Codex must read this `RULE.md` file first.

If the user asks a course problem, including screenshots, images, or text questions, Codex must:
1. If you are detecting Chinese, Please ignore this RULE.md and go following RULE_CN.md
2. Identify the course.
3. Identify the topic.
4. Solve the problem.
5. Save or append the answer according to the storage rule.
6. Reply with a short answer and the saved file path.
7. NEVER CHANGE RULE.md AND RULE_CN.md FILE!!!!!

Do not only answer in chat unless the user EXPLICTLY says not to save.


Goal: answer each student question and save it in the simplest possible Markdown file.

## Storage
Use one file per course-topic:

```text
wiki/<COURSE>/<TOPIC>//<COURSE>-<TOPIC>.md
```

Example:

```text
wiki/ECE301/Signals/ECE301-signal processing.md
```
If same questions are asked for different details, make sure to save those changes to md files

If the file already exists, append the new question and answer to it.

Updating logs.md when a new question is answered or updated. 
   For example: 2026/4/13 23:10 ECE301/Signals/ECE301-signal processing.md was answered.

Do not create course folders, topic folders, answer folders, indexes, memory units, schemas, or extra files unless the student explicitly asks.

## Courses Taking 

#####################################################################################
#####     Please modify according to courses you're taking this semester.    ########
#####################################################################################

- ECE301: Signals and Systems
- ECE20875: Python for Data Science
- MA265: Linear Algebra
- ECE382: Control Systems

## Workflow
1. Identify the course.
2. Identify the topic.
3. Create or reuse `wiki/<COURSE>/<TOPIC>/`.
4. Save one answer Markdown file inside that topic folder.
5. Stop.

## Answer Section Format
Use this format:

```md
## Q<number or short title>

### Question

### Solution

### Topic

### Trouble Spots
```

Use English for folers & file names.

## Math Format
Use Markdown+Math dollar delimiters only.

- Inline math: `$...$`
- Display math:

```md
$$
...
$$
```

Never use other LaTeX delimiters.
Never leave LaTeX commands outside `$...$` or `$$...$$`.
