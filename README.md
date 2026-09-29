# 🐯 海虎强者语（Haihu Strongman Speech）改写组件

> **“成功将磁场力量驳上，霸气立刻暴增！狂增！劲增！杀杀杀杀！”**  
> 一款将任意日常文本无缝转换为港漫《海虎》（温日良主编）“强者语”风格的 AI Agent 提示词与技能插件。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Author](https://img.shields.io/badge/Author-hannibal114514-blue.svg)](https://github.com/hannibal114514)

---

## 📖 简介 (Introduction)

《海虎》作为香港硬派科幻漫画的里程碑，其独树一帜的台词风格被华语网络社群奉为**“强者语”**——充满极致的自我确信、压倒性的辈分压制、磁场转动的力量量化，以及浓厚的粤语口风。

<p align="center">
  <img src="assets/haihu-quotes.jpg" alt="海虎强者语速成指南" width="420" />
</p>

本项目将海虎强者语的核心语法与语录规则抽象为标准的 **AI Agent Skill** 与 **System Prompt**。无论你使用的是命令行智能体、代码编辑器插件，还是普通的网页端聊天模型，都能一秒化身“海虎”，将输入的每一句话都改写成霸气无匹的强者发言！

---

## 🚀 全平台接入指南 (Integration Guide)

### 1. Antigravity (AGY)

#### 方式 A：作为全局或工作区专属 Skill
将本项目作为 Skill 目录挂载到你的 Antigravity 配置中：
1. 复制本项目目录至 Antigravity 的技能存放路径，例如：
   ```bash
   mkdir -p ~/.gemini/antigravity/skills/haihu-rewriter
   cp SKILL.md ~/.gemini/antigravity/skills/haihu-rewriter/SKILL.md
   ```
2. 在对话中直接指示 Agent 激活或切换为海虎改写模式。

#### 方式 B：在 `AGENTS.md` / `GEMINI.md` 中挂载
若希望当前工作区长期生效，可直接在项目根目录的规则文件追加以下规则：
```markdown
## 海虎改写器指令
当用户要求“改写为海虎风格”或输入文本时，将文本输入映射为港漫《海虎》强者语，仅输出改写后的台词。
```

---

### 2. Claude Code

Claude Code 支持读取项目根目录下的全局指导文件：
1. 在你的项目根目录下创建或编辑 `CLAUDE.md`：
   ```markdown
   # 海虎文本改写协议
   当被要求改写文本为海虎风格时，严格套用以下规则：
   - 语气：绝对断言，严禁犹豫（消灭“可能”、“大概”）。
   - 粤风：用“便”替“就”，用“甚”替“什么”，用“搅”替“搞”，句尾常挂“呀”。
   - 修辞：以“磁场转动XX匹力量”量化程度，以“爆增！狂增！劲增！”表达激增。
   - 仅输出改写内容本身，不附带多余解释。
   ```
2. 或在执行终端中使用系统提示参数加载 `system-prompt.txt`。

---

### 3. Codex / GitHub Copilot / Cursor

#### Cursor 用户
1. 在项目根目录创建 `.cursor/rules/haihu.mdc`（或旧版 `.cursorrules`）。
2. 将本项目中 [system-prompt.txt](system-prompt.txt) 的完整内容粘贴进去。
3. 在 Composer 窗口中 `@haihu` 或直接输入文字，指令其完成重写。

#### GitHub Copilot 用户
在仓库根目录添加 `.github/copilot-instructions.md`，追加本项目提供的改写规则即可。

---

### 4. DSH (DeepSeek Hub / 本地 Agent 工具)

1. 打开 DSH 界面中的 Agent / Persona（角色设定）配置页。
2. 新建一个助手角色，命名为 **“海虎改写器”**。
3. 在 **System Prompt（系统提示词）** 字段中，完整粘贴本项目的 [system-prompt.txt](system-prompt.txt)。
4. 保存后新建对话，向其发送任意句子，即可自动获得纯强者语输出。

---

### 5. 网页端能不能用？（ChatGPT / Claude.ai / Gemini / DeepSeek 网页版）

**答案是：完全可以，而且极其方便！**

网页端无需任何代码或终端环境，主要有以下三种用法：

#### 方法 A：长期专属助手（最推荐）
- **ChatGPT**：点击头像 → **自定义 ChatGPT (Custom Instructions)** 或创建专属 **GPTs**，将 `system-prompt.txt` 粘贴进 Instructions 框中。
- **Claude.ai**：创建专属 **Project**，在 Project Knowledge / Custom Instructions 贴入改写规则。
- **Gemini 网页端**：创建专属 **Gems**，将改写提示词填入 System Instructions。

#### 方法 B：单次临时对话
在任何大模型的网页对话框中，第一句话直接发送：
> “请扮演海虎改写器。接下来我发送的所有话，你都不要当作问题回答，而是按照《海虎》港漫强者语风格进行改写，直接输出改写结果，不加任何解释。”

随后直接输入你想说的话即可。

---

## ⚡ 核心转换秘笈 (Core Cheat Sheet)

| 日常输入 | 海虎强者语替换 | 原作神韵 |
|:---|:---|:---|
| 天哪 | 这又是什么高手了 | 遭遇深不可测之敌 |
| 好的 / 收到 | 绝对可以，轻易可以 | 战力碾压下的绝对笃定 |
| 抱歉 / 对不起 | 嗯，可以和解吗 | 强者的霸权式退让 |
| 喜欢 | 我们敬爱你呀 | 歇斯底里的狂热崇拜 |
| 想看 | 就算死也值回票价呀 | 押上性命见证神仙打架 |
| 都要 | 两个我都同样的要呀 | 霸者不做选择题 |
| 聪明 | 惊世智慧 | 极度深沉的算计（亦带讽刺反差） |
| 悲伤 | 今日，我手震... | 极致悲愤导致的肌肉失控 |
| 期待 | 更是给你意外惊喜呀 | 后手大招蓄势待发 |
| 闭嘴 | 每当我想给你一些尊重你便开口说话 | 降维式言语霸凌 |
| 可笑 | 搅什么啦 | 粤式鄙夷 |
| 逆天 / 离谱 | 屎！？ | 强烈的荒诞与冲击 |
| 想多 | 想象力这么好做甚了 | 讥讽对方凭空妄想 |
| 表白 | 是了，我也爱你 | 毫无掩饰的癫狂爱意 |
| 小便 / 厕所 | 终极膀胱剑 | 强行武学招式化 |
| 不懂 | 不知所谓 | 睥睨庸俗之辈 |
| 找死 | 儿，爹来杀你了 | 纯粹的杀意与宗族压迫 |
| 不行 | 没可能，没可能的呀 | 无可争辩的否定断言 |

---

## 📂 项目结构 (Repository Structure)

```text
haihu-style/
├── README.md           # 本说明文件（多平台集成与指南）
├── SKILL.md            # 符合 Agent 规范的 Skill 定义文档
├── system-prompt.txt   # 开箱即用的纯文本 System Prompt
├── rules.json          # 机器可读的映射字典（供脚本或前端拓展使用）
├── examples.md         # 涵盖生活、职场、吃喝拉撒的改写范例
└── LICENSE             # MIT 开源协议
```

---

## 👨‍💻 作者与维护 (Author)

- **Author**: hannibal114514
- **Email**: zhongxin960@gmail.com
- **GitHub**: [https://github.com/hannibal114514](https://github.com/hannibal114514)

欢迎提交 Issue 和 PR 补充更多港漫神仙语录！
