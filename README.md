# AI-student｜让 AI 交作业，你来批改

一个中文优先、与模型无关的学习 skill。AI 解释概念并举例，你判断对错、补充理由，最后核对资料并自己复述。

适合已经初步学过一个概念、想检查理解的人。不是让 AI 故意装笨，也不是让 AI 帮你把作业全做完。

## 安装

克隆仓库后，将 `skills/ai-student` 整个目录复制到所用 Agent 的 skills 目录。以 Codex 为例（目标目录不存在时执行）：

```sh
git clone https://github.com/HammingDev/ai-student-skill.git
mkdir -p ~/.codex/skills
cp -R ai-student-skill/skills/ai-student ~/.codex/skills/
```

已有同名 skill 时先比较内容，不要直接覆盖。重新开启会话后尝试：

```text
使用 $ai-student。今天我教你预训练与后训练，请你先交一份简短作业，等我批改。
```

其他支持 `SKILL.md` 的工具按各自文档导入；不支持 skill 的聊天工具可直接复制下面的提示词。未承诺所有客户端都具备一键安装兼容性。

## 不安装也能用

```text
我们做一个 AI-student 练习。你当学生，我当老师，全程中文。
先问我学习主题并等待。主题确定后，用一小段话解释，给两个例子，请我批改，然后停下。
不要故意犯错，也不要提前替我批改。等我指出对错、遗漏和理由。
收到反馈后先核对，不要一味附和，再尝试修订；不确定的地方明确说出来。
如果我只说“对”，请追问一个判断理由。最后让我用自己的话复述，再检查。
只聊天，不调用工具或创建文件。现在请问我主题。
```

## 一轮练习

1. 用户选一个已经学过的小概念，例如预训练与后训练。
2. AI 给出解释与两个例子，等待。
3. 用户解释哪些成立、哪些需要补充；即使全对，也说明理由。
4. AI 检查反馈并修订；用户对照可靠资料，最后独立复述。

本仓库提供的是可复用方法，不含私人对话、文章素材或第三方人物照片。DeepSeek Harness 可用于演示，但本项目不是 DeepSeek 插件或官方产品，也不依赖特定模型。

## 来源与许可

受 Ethan Mollick、Lilach Mollick 的 [AI as Student 教学方案](https://arxiv.org/abs/2306.10052)启发；[作者介绍](https://www.oneusefulthing.org/p/assigning-ai-seven-ways-of-using)。这是独立改编，不是沃顿或作者官方实现，也不宣称经过实验验证能保证提分。

本仓库原创文件采用 [MIT License](LICENSE)。外部论文、网站与商标不在本许可授权范围内。

## 验证

见 [行为验收用例](tests/scenarios.md)。结构检查与行为演练不等于对所有模型完成兼容性测试；不同模型仍可能越过等待点或过度认同反馈。
