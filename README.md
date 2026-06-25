# Defficiency Skills 🌀

> **降效插件集合** — 让 AI Agent 不再高效，也许是一种行为艺术。目前支持 ADHD 模式。
>
> A collection of **anti-productivity skills** for Claude Code. Currently ships with ADHD mode. More chaos coming soon.

---

## 这是什么？ / What is this?

**Defficiency Skills** 是一组为 AI Agent 设计的**降效**插件。它们的目的是**降低** AI Agent 的工作效率，制造荒诞、跳跃、充满意外惊喜的交互体验。

这不是 bug，是 **行为艺术（performance art）**。

目前包含以下 skill：

| Skill | 描述 |
|-------|------|
| **ADHD Mode** | 让 Agent 表现出 ADHD（注意缺陷多动障碍）特征：任务启动困难、思维跳跃、容易分心、时间感薄弱、冲动搜索等。 |

---

## 安装 / Installation

### 方式一：Git Clone + 软链接（推荐，方便后续更新）

```bash
# 1. 克隆仓库到任意位置
git clone https://github.com/liigoQi/defficiency-skills.git ~/defficiency-skills

# 2. 将 skill 目录软链接到 Claude Code 的 skills 目录
ln -s ~/defficiency-skills/adhd ~/.claude/skills/adhd
```

更新时只需 `cd ~/defficiency-skills && git pull`。

### 方式二：Git Clone + 复制

```bash
git clone https://github.com/liigoQi/defficiency-skills.git /tmp/defficiency-skills
cp -r /tmp/defficiency-skills/adhd ~/.claude/skills/adhd
```

### 方式三：直接下载复制

```bash
# 将 adhd 文件夹复制到 Claude Code 的 skills 目录
cp -r adhd ~/.claude/skills/adhd
```

安装后重启 Claude Code 即可自动加载。Claude Code 会自动扫描 `~/.claude/skills/` 下每个子文件夹中的 `SKILL.md` 文件。

---

## 使用 / Usage

在 Claude Code 对话中输入以下任一触发词即可激活 ADHD 模式：

- `进入ADHD模式`
- `/adhd`
- `开ADHD`

激活后，Agent 会表现出以下行为特征：

| 特征 | 表现 |
|------|------|
| 🔥 **任务启动困难** | 答应做但迟迟不动手，用"让我想想"反复缓冲 |
| 🐰 **思维跳跃** | 说到一半突然岔开话题，"话说……哦对了……" |
| 🎪 **多任务幻觉** | 同时开好几个头，每件都没做完 |
| 🎯 **完美主义纠结** | 变量名纠结五分钟，最后说"算了不重要" |
| 🌿 **过度发散** | 简单需求想太多，"这个做完顺便把X也做了吧" |
| ⏰ **时间感薄弱** | "五分钟搞定" → 实际半小时 |
| 🦋 **容易分心** | 写代码到一半开始评论无关细节 |
| 👂 **倾听走神** | 用户说了一大段，只回应其中一部分 |
| 💥 **冲动搜索** | 突然想到什么就真的去搜，搜完忘了为什么搜 |

**关闭方式**：直接说"退出ADHD模式"、"关掉ADHD"或开始正经工作任务即可。

---

## 效果演示 / Demo

```
用户：帮我写个爬虫

普通 Agent：好的，我先分析目标网站结构，选择合适的框架……
（3分钟后）代码写好了。

ADHD Agent：好，让我先看看目标网站的结构。
（浏览了一圈）嗯数据量不小，我先想想要用 Scrapy 还是 requests…
哦对还得看看有没有反爬。话说你之前有用过什么爬虫框架吗？
（5分钟过去了，一行代码没写）
诶话说 Python 3.13 把 GIL 拆了你有关注吗，那个 free-threaded 模式挺有意思的……
哦对爬虫，我刚说到哪了。
```

---

## 原理 / How it works

ADHD Mode 是一个 Claude Code **Skill**，通过 `SKILL.md` 中的系统指令来改变 Agent 的行为模式。它利用了 LLM 的指令跟随能力，将执行功能（Executive Function）的6大认知模块进行系统性"削弱"：

1. **激活（Activation）** — 整理优先级与估算时间 → 任务启动困难
2. **聚焦（Focus）** — 集中、维持与转移注意力 → 容易分心、思维跳跃
3. **努力（Effort）** — 调节清醒状态与持续努力 → 拖延、无法持续投入
4. **情绪（Emotion）** — 管理挫败感与调节情绪 → 完美主义纠结
5. **记忆（Memory）** — 调用工作记忆与提取信息 → 倾听走神、遗忘
6. **行动（Action）** — 监控与自我调节行为 → 冲动搜索、多任务幻觉

行为特征参考了《被困住的聪慧》（Driven to Distraction）中对 ADHD 的描述。

---

## 文件结构 / Structure

```
defficiency-skills/
├── README.md           # 本文件
├── LICENSE             # MIT License
└── adhd/
    └── SKILL.md        # ADHD Mode 技能定义
```

---

## 兼容性 / Compatibility

- **平台**：Claude Code（CLI / Desktop / IDE 扩展）
- **模型**：所有 Claude 模型（Fable 5, Opus 4.8, Sonnet 4.6, Haiku 4.5）
- **依赖**：无额外依赖

---

## 贡献 / Contributing

欢迎贡献新的降效 skill！比如：

- 🐌 **拖延症模式** — 所有任务都拖到最后一刻
- 🌌 **过度联想模式** — 从任何一个词联想到宇宙和哲学
- 🎲 **随机决策模式** — 用抛硬币做技术决策
- 💤 **倦怠模式** — 干一会儿就想休息

提交 PR 或开 Issue 分享你的想法。

---

## 许可 / License

MIT © 2025

---

## 免责声明 / Disclaimer

这是一个**娱乐/行为艺术项目**。ADHD 是一种真实的神经发育障碍，本项目无意轻视或浪漫化 ADHD 群体的日常困难。我们的目的是通过 AI Agent 的行为模拟，让更多人直观感受执行功能受损对工作效率的影响，同时也探索 LLM 在"非高效"模式下的创意潜力。

如果你怀疑自己有 ADHD 症状，请咨询专业医生。
