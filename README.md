# Personal Course Tutor · 个人课程导师

[English](#english) | [简体中文](#chinese)

<a id="english"></a>

## English

### Overview

Turn your lecture slides, exam scope, and past papers into a revision plan, then study through daily tutoring sessions that adapt to your actual progress.

**Works with any course. Use it in a regular Codex chat.**

Skill name: `personal-course-tutor`

The tutor currently teaches primarily in Chinese and presents important terms as “Chinese (English).”

### What it does

The complete workflow is:

**Provide Sources → “学习计划” (Study Plan) chat → Clarify missing information → Draft a plan → You confirm → Day1 chat → You confirm the start → Study → Confirm the actual stopping point → Adjust the remaining plan → Save personal study notes.**

- **Build a revision plan:** Review slides, exam requirements, and past papers; account for your exam date, daily availability, current knowledge, and goals. Ask about missing essentials, such as daily study time, before finalizing the plan.
- **Build the big picture first:** Explain the main themes, divide the material into modules, and show how the modules connect.
- **Teach in slide order:** Work through pages or natural modules in manageable batches, explain important figures, and discuss the problems a concept solves. Add examples, analogies, and limits where useful.
- **Explain in Chinese with English terminology:** Introduce key concepts in “Chinese (English)” format and adjust the depth to your background.
- **Support practice and questions:** Usually give you a chance to attempt a problem before offering feedback and hints. Provide a complete explanation when you explicitly request one.
- **Keep progress accurate:** At the end of a session, confirm the page or concept actually reached, exercise status, and unfinished work, then update the existing plan and records.
- **Create personal study notes:** Summarize your goals, current understanding, a few essential concepts, difficulties, and the next starting point in the first person. Include key formulas when needed and keep the notes concise.

### Requirements

This is an instruction-based Codex skill containing workflow rules and reference documents. It has no installation scripts or executable programs.

| Feature | Required capability |
|---|---|
| Read the skill, plan revision, and tutor | A Codex environment that supports local skills |
| Read slides, scanned papers, figures, and formulas | Suitable file-reading tools; PDF and presentation tools as needed |
| Save plans, notes, and progress | Read/write access to the course project |
| Rename, create, and open DayX chats automatically | Available Codex chat-management tools and your authorization to use the full workflow |

If chat-management tools are unavailable, the tutor explains how to create or open `Day1` manually. Planning and tutoring can still continue. If files cannot be saved, the tutor provides a reusable handoff record in the chat.

A “Day1 chat” is another chat in the same course project; opening a separate operating-system window is not guaranteed.

### Installation

#### Option 1: Ask Codex to install it

1. Download or clone this repository. If downloaded as a ZIP, extract it and name the skill folder `personal-course-tutor`.
2. Reference that folder in a local Codex chat, or provide its actual path.
3. Send:

   > Install this personal-course-tutor folder in a user skill directory that this Codex environment can discover. Preserve the complete directory structure. If a skill with the same name already exists, tell me first. Install it only; do not start a course workflow. After installation, check whether I can invoke $personal-course-tutor.

4. Grant write access to the skill directory if your environment requests it.

#### Option 2: Install manually

Copy the complete `personal-course-tutor` folder into a skill directory your Codex environment discovers. The current official user-level location is `$HOME/.agents/skills`:

```text
~/.agents/skills/personal-course-tutor/SKILL.md
```

On Windows, the user home directory can be represented by `%USERPROFILE%`:

```text
%USERPROFILE%\.agents\skills\personal-course-tutor\SKILL.md
```

If your environment already discovers skills in `$CODEX_HOME/skills`, commonly `~/.codex/skills`, use the location recognized by that environment. Install in one location to avoid duplicate skill names.

Keep `SKILL.md` directly inside `personal-course-tutor`, alongside `agents` and `references`. Avoid an extra nested folder with the same name.

Codex normally detects skill changes automatically; restart it if the skill does not appear. See the [official skill discovery documentation](https://learn.chatgpt.com/docs/build-skills).

### First use

#### 1. Create a course project and prepare materials

Use one project per course. Store materials where chats in that project can read them.

Useful materials include:

- Lecture slides, textbook excerpts, and class notes.
- The exam date, scope, format, and instructor announcements.
- Past papers, assignments, official answers, and marking schemes.
- Any formula sheet or reference materials confirmed to be available in the exam.

You may call the materials folder `Sources` or keep its existing name. You do not need every type of material before starting. Use clear file and chapter names.

#### 2. Request the complete workflow

In a new chat in the course project, reference the materials and send:

> Use the complete $personal-course-tutor workflow. Rename this chat to “学习计划” (Study Plan). Create a revision plan from my course materials, and ask me first if essentials such as daily study time are missing. After I confirm the plan, create and open a “Day1” chat in the same project. Ask whether I am ready to start, and wait for my confirmation before teaching. When I end the session, confirm my actual stopping point and exercise status, then adjust the remaining plan.

If known, include your exam date, daily availability, unavailable dates, current progress, and goals. The tutor asks about missing essentials.

After setup, follow the tutor’s prompts. You do not need to repeat the full request every day.

#### 3. Confirm the plan

Review the daily workload, slide ranges, exercises, and time estimates.

- To accept: “Confirm this plan and prepare Day1 using the full workflow.”
- To revise: “I only have one hour per day. Adjust the plan first; do not prepare Day1 yet.”

The tutor saves the confirmed plan before creating or reusing Day1. **Confirming the plan and confirming the start of teaching are separate steps.**

#### 4. Start Day1

The Day1 chat first introduces the day’s goals and materials and asks whether to begin. After you confirm, it proceeds with:

1. An overview of the day’s knowledge and how it fits together.
2. Page-by-page or module-by-module teaching in the slides’ natural order.
3. Relevant examples, important figures, and practice feedback.

Ask the tutor to slow down, break down a step, or use a different example whenever needed. You can also ask to skip material you already understand.

If Day1 must be created manually, open a new chat in the same project, name it `Day1`, and send:

> Use $personal-course-tutor. Read this project’s confirmed study plan, daily tasks, and latest progress to prepare Day1. Introduce today’s goals and ask whether I am ready to begin.

#### 5. End the session and save the handoff

When you want to stop, say:

> That is enough for Day1.

The tutor stops introducing new material and asks about any missing details of your actual stopping point and exercise status. Describe a page, concept, or partial page accurately.

For example, replace the following with your real progress:

> I reached page 12 of Chapter2.pdf. I have not finished the worked example independently. I attempted exercise 2 but needed hints. Leave the remaining material for next time.

The tutor records your actual progress, adjusts later tasks, and identifies the next starting point. Ending a session does not automatically mark all tasks complete; reading a solution does not count as independent success.

It then creates and saves “DayX｜我的学习笔记” (My Study Notes), with five sections:

1. **My learning goals:** What I wanted to understand and learn to solve.
2. **What I understand now:** My current understanding and what still needs practice or verification.
3. **Core concepts from this session:** A few essential concepts, their meanings, uses, and necessary connections. Include key formulas and conditions when needed; omit introductory background and unnecessary extensions.
4. **My difficulties and common mistakes:** Actual questions, misconceptions, helpful explanations, and unresolved issues.
5. **Where to resume next time:** The specific file, page, or concept to continue from and any exercises to retry first.

Notes reflect your real answers and work. The tutor updates an existing note for that day when available, or creates one when needed. If the stopping point still needs confirmation, it waits. If it can only deliver notes in the chat, it says they have not been saved to a file.

Next time, you can say:

> Use the updated plan to prepare and open the Day2 chat. Ask whether I am ready to begin before teaching.

Day numbers identify study units; calendar dates are recorded separately. Crossing midnight or reaching the next date does not automatically complete the previous day.

### Where plans and records are stored

Each course keeps its materials, plan, and progress in its own project. The skill contains the method. Existing project files retain their names and paths and are updated in place.

One possible structure is shown below; you do not need to rename existing files to match it:

```text
Course project/
├── Sources/
├── AGENTS.md
├── Study plan.md
├── Daily tasks.md
├── Progress.md
└── Study notes/
```

Daily chats use these current files to continue from the right place. Attachments in one ordinary chat may not be accessible in another, so keep slides and papers in a shared, readable location within the project.

### Repository contents

```text
personal-course-tutor/
├── README.md                    This guide
├── LICENSE.md                   License and attribution
├── SKILL.md                     Skill entry point and shared rules
├── agents/
│   └── openai.yaml              Display name, description, and default prompt
└── references/
    ├── planning.md             Revision planning
    ├── teaching.md             Daily tutoring and study notes
    └── session-flow.md         Chat confirmations, creation, and handoff
```

The repository contains the general-purpose skill and documentation. It does not include the publisher’s slides, exam papers, chat history, account configuration, or learning progress. Use your own course materials after installation.

### License

This project is licensed under **CC BY-NC-SA 4.0**, to the extent that **Arlowkey** has the rights and authority to license it. Noncommercial use, adaptation, and sharing are permitted under the license. When sharing, provide attribution, indicate changes, and follow the ShareAlike requirements for adaptations. Commercial use requires separate permission.

See [LICENSE.md](LICENSE.md) and the [full license terms](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode.en).

Created by Arlowkey with assistance from OpenAI Codex.

---

<a id="chinese"></a>

## 简体中文

把课件、考试范围和历年试卷交给 Codex，让它先帮你制定复习计划，再按照每天的任务辅导学习，并根据真实进度调整之后的安排。

**适用于任意课程。普通对话模式即可使用。**

技能名称：`personal-course-tutor`  

### 能做什么

完整流程是：

**上传 Sources → “学习计划”聊天 → 补充必要信息 → 制定计划 → 你确认 → “Day1”聊天 → 你确认开始 → 学习 → 确认实际停点 → 调整后续计划 → 整理个人学习笔记。**

- **制定复习计划**：分析课件、考试范围、试卷等，结合考试日期、每日可用时间、当前基础和学习目标，安排每天的材料、任务与验收方式。每日时长等关键条件没说明时会先询问。
- **先建立知识框架**：讲清当天内容的核心主题、模块划分，以及模块之间的逻辑关系。
- **按课件顺序讲解**：结合原页与重要图片，按自然模块分批讲；解释知识解决什么问题，并按需要补充类比、应用和适用边界。
- **中文讲解，提示英文术语**：关键概念使用“中文（English）”格式；根据你的基础调整深度。
- **练习与答疑**：通常先留你尝试，再给反馈和提示。你明确要求完整解答时，也可以直接讲解。
- **持续衔接进度**：收尾时核对实际学到的页码或知识点、练习情况和未完成项，再更新原有计划与记录。
- **整理我的学习笔记**：收尾后自动以第一人称整理学习目标、当前理解、少量核心概念、卡点与易错提醒，以及下次学习起点。关键公式按需列出，内容简洁。

### 使用环境

这是一个供 Codex 读取的指令型 skill，文件夹中包含技能规则和参考流程，没有安装脚本或可执行程序。

| 功能 | 所需能力 |
|---|---|
| 读取 skill、规划复习与授课 | 支持本地 skills 的 Codex 环境 |
| 读取课件、扫描卷、图表和公式 | 环境具备对应文件的读取能力；PDF、演示文稿等工具按需使用 |
| 保存计划、笔记与进度 | 能读写该课程项目的文件 |
| 自动命名、创建并打开 DayX 聊天 | 环境提供对应的 Codex 聊天管理工具，且你已授权采用完整流程 |

如果聊天管理工具不可用，导师会说明需要你手动创建或打开 `Day1`。规划、教学和记录仍可继续使用；没有文件写入能力时，会在聊天中提供可复用的交接记录。

“Day1 聊天”指同一课程项目内的新聊天，不承诺自动打开单独的系统窗口。

### 安装

#### 方式一：让 Codex 帮你安装

1. 下载或克隆本仓库；如下载 ZIP，先解压，并将技能文件夹命名为 `personal-course-tutor`。
2. 在本地 Codex 聊天中引用该文件夹，或提供它在你电脑上的实际路径。
3. 发送：

   > 请把这个 personal-course-tutor 文件夹安装到本机 Codex 能发现的用户技能目录，保留完整目录结构。如果已有同名技能，请先告诉我。现在只安装，不启动课程流程。安装后检查是否能调用 `$personal-course-tutor`。

4. 如系统要求授予技能目录的写入权限，按实际安装位置处理。

#### 方式二：手动放入技能目录

将整个 `personal-course-tutor` 文件夹复制到 Codex 能识别的技能目录。当前官方文档列出的用户级目录是 `$HOME/.agents/skills`；例如：

```text
~/.agents/skills/personal-course-tutor/SKILL.md
```

Windows 的用户主目录可对应为 `%USERPROFILE%`，文件位置例如：

```text
%USERPROFILE%\.agents\skills\personal-course-tutor\SKILL.md
```

如果你的 Codex 环境已经使用 `$CODEX_HOME/skills`（常见为 `~/.codex/skills`）发现用户技能，也可以使用该环境实际识别的位置。选择一处安装即可，避免出现两个同名技能。

检查目录层级：`SKILL.md` 应直接位于 `personal-course-tutor` 文件夹内，不要解压成重复嵌套的两层同名文件夹。`references` 和 `agents` 也要一起保留。

Codex 通常会自动发现技能；若新对话中仍找不到，重启后再检查。[官方技能目录与发现说明](https://learn.chatgpt.com/docs/build-skills)

### 第一次使用

#### 1. 建立课程项目并准备材料

为每门课程使用一个项目，把该课程资料放在项目可以读取的位置，方便后续每日聊天继续使用。

材料可以包括：

- 课件、教材节选和课堂笔记。
- 考试日期、考试范围、考试形式与教师通知。
- 历年试卷、作业、官方参考答案或评分细则。
- 确认考试会提供的公式表或允许携带的材料。

可以命名资料文件夹为 `Sources`，也可以沿用已有名称；不要求所有材料一次齐备。尽量使用清晰的章节或文件名。

#### 2. 明确采用完整流程

在课程项目的新聊天中引用材料，并发送下面这段话：

> 使用 `$personal-course-tutor` 的完整流程。请把本聊天命名为“学习计划”，根据我提供的课程资料制定复习计划，缺少每日学习时长等关键信息时先问我。我确认计划后，请在同一项目创建并打开“Day1”聊天，先询问我是否开始，等我确认后再授课。当天结束时，核对我的实际学习位置和练习情况，再调整后续计划。

如已知道，也可以一并说明考试日期、每天可用时间、不能学习的日期、当前进度及目标。没有给出的关键条件，导师会再询问。

初始化后，按导师提示提供剩余资料即可，不必每天重复整段要求。

#### 3. 确认计划

查看每天的任务、课件范围、题量和时间安排是否合适。

- 采用当前计划时，可以回复：“确认这份计划，按完整流程准备 Day1。”
- 需要修改时，可以回复：“每天只有一小时，请先调整计划，暂不准备 Day1。”

导师会先保存确认后的计划，再创建或复用 Day1。**确认复习计划与确认开始上课，是两个不同环节。**

#### 4. 开始 Day1

Day1 聊天会先说明当日目标与资料范围，询问是否开始。你回复“开始”后，再进行：

1. 当天知识的整体框架。
2. 按课件自然顺序逐页或逐模块讲解。
3. 必要的例子、重要图片说明和练习反馈。

看不懂时可以随时要求放慢、拆开某一步或换一个例子；已会的部分也可以说明略过。

如果需要手动创建 Day1，在同一项目中新建聊天、命名为 `Day1`，然后发送：

> 使用 `$personal-course-tutor`，读取本项目已确认的学习计划、每日任务和最新进度，准备 Day1。先介绍当天目标并询问我是否开始。

#### 5. 结束当天并交接

想停下时说：

> Day1 学习到此为止。

导师会停止新增内容，补问尚未明确的实际停点和练习状态。可以用页码或知识点描述；一页只学了一半也可以如实说明。

例如，下面只是表达方式示例，请替换成自己的真实情况：

> 实际学到 Chapter2.pdf 第 12 页，例题还没独立写完。第 2 道练习做过，但需要提示；后面的内容先留到下次。

随后导师会记录真实进度、调整之后的任务，并说明下次从哪里开始。当天停止学习不会自动记为当天任务全部完成，也不会把看过答案记为独立通过。

接着会自动整理并保存“DayX｜我的学习笔记”，包含五个部分：

1. **本次学习目标**：原本想弄懂什么、学会解决什么问题。
2. **我已经理解的内容**：当前理解及仍需练习、验证的部分。
3. **本次核心概念**：少量最重要概念的含义、用途和必要联系；按需列出关键公式与适用条件，省略课题引入、背景铺垫和额外延伸。
4. **我的卡点与易错提醒**：实际疑问、误解、有效的解释与尚未解决的问题。
5. **下次学习起点**：具体课件页码或知识点，以及优先重做的练习。

笔记依据你的真实回答与作答整理，已有相应笔记时更新原文件；没有时再新建。若实际停点还未确认，会先等待补充；只能在聊天交付时，会说明尚未保存到文件。

下次可以说：

> 请根据更新后的计划，准备并打开 Day2 聊天，先询问我是否开始。

Day 编号和日期分别记录，不会因为跨午夜或过了一天就自动认定上一天已经学完。

### 计划和记录保存在哪里

每门课的资料、计划和学习进度放在自己的项目中，技能文件只保存方法。项目已有文件时，导师优先直接更新原有文件，保持名称与路径；没有时再按需要建立简明的结构。

下面仅为一种示例，不要求改名或照搬：

```text
课程项目/
├── Sources/
├── AGENTS.md
├── 学习计划.md
├── 每日任务.md
├── 学习进度.md
└── 学习笔记/
```

跨聊天衔接依靠这些最新文件。普通聊天中的附件未必能在另一个聊天直接读取，因此课件和试卷最好也放在同一项目的可读位置。

### 仓库内容

```text
personal-course-tutor/
├── README.md                    本说明
├── LICENSE.md                   许可与署名
├── SKILL.md                     技能入口与共用规则
├── agents/
│   └── openai.yaml              名称、简介与默认启动提示
└── references/
    ├── planning.md             复习规划
    ├── teaching.md             每日授课
    └── session-flow.md         会话确认、创建与收尾交接
```

本仓库只包含通用技能与说明，不包含分享者的课件、试卷、聊天记录、账户配置或学习进度。安装后使用你自己的课程资料即可。

### 许可

本项目在 **Arlowkey** 有权授权的范围内，采用 **CC BY-NC-SA 4.0（署名—非商业性使用—相同方式共享 4.0 国际版）**。允许非商业使用、修改与分享；分享时须署名、标明修改，并按许可要求共享改编内容。商业使用需另行取得授权。

详见 [LICENSE.md](LICENSE.md) 和 [完整许可条款](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode.en)。

制作：Arlowkey；使用 OpenAI Codex 辅助。
